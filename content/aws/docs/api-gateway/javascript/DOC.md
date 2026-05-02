---
name: api-gateway
description: "AWS SDK for JavaScript v3 client for managing Amazon API Gateway REST APIs, resources, methods, deployments, stages, usage plans, and domains."
metadata:
  languages: "javascript"
  versions: "3.1006.0"
  revision: 1
  updated-on: "2026-03-11"
  source: maintainer
  tags: "aws,api-gateway,javascript,nodejs,rest-api,openapi,apiGateway,send,console,log,aws-sdk,node,APIGatewayClient,CreateApiKeyCommand,CreateAuthorizerCommand,CreateBasePathMappingCommand,CreateDeploymentCommand,CreateDocumentationPartCommand,CreateDocumentationVersionCommand,CreateDomainNameAccessAssociationCommand,CreateDomainNameCommand,CreateModelCommand,CreateRequestValidatorCommand,CreateResourceCommand,CreateRestApiCommand,CreateStageCommand,CreateUsagePlanCommand,CreateUsagePlanKeyCommand,CreateVpcLinkCommand,DeleteApiKeyCommand,DeleteAuthorizerCommand,DeleteBasePathMappingCommand,DeleteClientCertificateCommand,DeleteDeploymentCommand,DeleteDocumentationPartCommand,DeleteDocumentationVersionCommand,DeleteDomainNameAccessAssociationCommand,DeleteDomainNameCommand,DeleteGatewayResponseCommand,DeleteIntegrationCommand,DeleteIntegrationResponseCommand,DeleteMethodCommand,DeleteMethodResponseCommand"
---

# `@aws-sdk/client-api-gateway`

Use this package for the API Gateway **REST API control plane** in AWS SDK for JavaScript v3. It manages APIs, resources, methods, integrations, deployments, stages, usage plans, API keys, and custom domains.

This package does **not** invoke your deployed API for application traffic. It is for provisioning and admin workflows.

## Install

```bash
npm install @aws-sdk/client-api-gateway
```

Prefer `APIGatewayClient` plus explicit command imports. The aggregated `APIGateway` client exists, but command-based imports are the safer default for clearer code and smaller bundles.

## Initialize the client

```javascript
import { APIGatewayClient } from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({
  region: "us-east-1",
});
```

In Node.js, the SDK can usually resolve credentials from the default credential provider chain, so setting the region is often enough.

## Credentials and Region

- Node.js: credentials usually come from environment variables, shared AWS config files, ECS, EC2 instance metadata, or IAM Identity Center.
- Browser runtimes: use explicit browser-safe credentials only. In practice, this control-plane client is usually better kept on the server because it manages high-privilege infrastructure.
- Region is required somewhere: pass it in code, set `AWS_REGION`, or configure it in shared AWS config.

Typical local setup:

```bash
export AWS_REGION=us-east-1
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
```

## What This Client Covers

Use `@aws-sdk/client-api-gateway` for the original API Gateway REST API service:

- REST APIs and OpenAPI import/export
- resources, methods, and integrations
- deployments and stages
- usage plans and API keys
- custom domain names and base path mappings

If you need API Gateway HTTP APIs or WebSocket APIs, use the API Gateway v2 client instead of this package.

## Core Usage Pattern

The v3 SDK uses client-plus-command calls:

```javascript
import {
  APIGatewayClient,
  CreateRestApiCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const response = await apiGateway.send(
  new CreateRestApiCommand({
    name: "orders-api",
    description: "REST API for order operations",
    endpointConfiguration: {
      types: ["REGIONAL"],
    },
  }),
);

console.log(response.id);
console.log(response.rootResourceId);
```

Most workflows follow the same sequence:

1. create or import a `RestApi`
2. create resources under the API root
3. attach methods and integrations
4. create a deployment
5. bind or update a stage

## Common Operations

### List REST APIs with pagination

```javascript
import {
  APIGatewayClient,
  paginateGetRestApis,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const paginator = paginateGetRestApis(
  { client: apiGateway },
  { limit: 25 },
);

for await (const page of paginator) {
  for (const api of page.items ?? []) {
    console.log(api.id, api.name);
  }
}
```

### Get resources for an API

```javascript
import {
  APIGatewayClient,
  GetResourcesCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const { items = [] } = await apiGateway.send(
  new GetResourcesCommand({
    restApiId: "a1b2c3d4",
    limit: 500,
  }),
);

for (const resource of items) {
  console.log(resource.id, resource.path);
}
```

### Create a deployment

```javascript
import {
  APIGatewayClient,
  CreateDeploymentCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const deployment = await apiGateway.send(
  new CreateDeploymentCommand({
    restApiId: "a1b2c3d4",
    stageName: "prod",
    description: "Deploy current API configuration",
  }),
);

console.log(deployment.id);
```

Passing `stageName` creates or updates that stage as part of the deployment flow.

## API Gateway REST API Gotchas

- This package manages **REST APIs**. Do not confuse it with the separate API Gateway v2 service for HTTP APIs and WebSocket APIs.
- Control-plane changes are not live until you create a deployment or point a stage at a new deployment.
- `PutMethod` and `PutIntegration` are separate steps. A method without an integration still will not serve backend traffic.
- `CreateDeployment` can create or update a stage when you pass `stageName`; otherwise deploy first and create a stage separately.
- `PutRestApi` can merge or overwrite an existing API definition. Be explicit about update mode during OpenAPI-based workflows.
- `Update*` operations use patch operations. Treat them like targeted infrastructure mutations rather than partial JSON merges.
- Custom domain names, usage plans, and API keys are in this client too, so you do not need separate service packages for those control-plane APIs.
- Do not deep-import internals from package build directories.

## When To Reach For Other Packages

- `@aws-sdk/client-apigatewayv2`: API Gateway HTTP APIs and WebSocket APIs.
- `@aws-sdk/credential-providers`: Cognito, IAM Identity Center, shared config, assume-role flows, and other credential helpers.
- `@aws-sdk/signature-v4` or higher-level HTTP clients: signed runtime calls if you are invoking an API rather than administering it.

## Common API Gateway REST API Operations

### Import an API from an OpenAPI file

Use `ImportRestApiCommand` when the API definition already exists as OpenAPI or Swagger.

```javascript
import { readFile } from "node:fs/promises";
import {
  APIGatewayClient,
  ImportRestApiCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });
const body = await readFile("./openapi.json");

const response = await apiGateway.send(
  new ImportRestApiCommand({
    failOnWarnings: true,
    body,
    parameters: {
      endpointConfigurationTypes: "REGIONAL",
    },
  }),
);

console.log(response.id, response.name);
```

Use `PutRestApiCommand` later if you want to merge or overwrite an existing API with a revised definition.

### Create a child resource under the API root

`CreateRestApi` returns `rootResourceId`. Use that as the parent when adding new paths.

```javascript
import {
  APIGatewayClient,
  CreateResourceCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const resource = await apiGateway.send(
  new CreateResourceCommand({
    restApiId: "a1b2c3d4",
    parentId: "xyz987",
    pathPart: "orders",
  }),
);

console.log(resource.id, resource.path);
```

### Attach a method and HTTP proxy integration

`PutMethod` defines the method shape on the resource. `PutIntegration` connects that method to a backend.

```javascript
import {
  APIGatewayClient,
  PutIntegrationCommand,
  PutMethodCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });
const restApiId = "a1b2c3d4";
const resourceId = "r123456";

await apiGateway.send(
  new PutMethodCommand({
    restApiId,
    resourceId,
    httpMethod: "GET",
    authorizationType: "NONE",
  }),
);

await apiGateway.send(
  new PutIntegrationCommand({
    restApiId,
    resourceId,
    httpMethod: "GET",
    type: "HTTP_PROXY",
    integrationHttpMethod: "GET",
    uri: "https://example.com/orders",
  }),
);
```

If you use `AWS` or `AWS_PROXY` integrations, the `uri` must be the service-specific AWS integration URI, and the target service usually needs its own IAM permissions and resource policy setup.

### Deploy a specific API revision to a stage

If you do not pass `stageName` to `CreateDeployment`, create the stage separately.

```javascript
import {
  APIGatewayClient,
  CreateDeploymentCommand,
  CreateStageCommand,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const deployment = await apiGateway.send(
  new CreateDeploymentCommand({
    restApiId: "a1b2c3d4",
    description: "Deploy after method and integration updates",
  }),
);

await apiGateway.send(
  new CreateStageCommand({
    restApiId: "a1b2c3d4",
    deploymentId: deployment.id,
    stageName: "prod",
    tracingEnabled: true,
    variables: {
      LOG_LEVEL: "info",
    },
  }),
);
```

Use `UpdateStageCommand` when you only need to change stage settings or move the stage to a new deployment.

### Paginate all resources for a large API

Large REST APIs may require multiple `GetResources` calls.

```javascript
import {
  APIGatewayClient,
  paginateGetResources,
} from "@aws-sdk/client-api-gateway";

const apiGateway = new APIGatewayClient({ region: "us-east-1" });

const paginator = paginateGetResources(
  { client: apiGateway },
  {
    restApiId: "a1b2c3d4",
    limit: 500,
  },
);

for await (const page of paginator) {
  for (const resource of page.items ?? []) {
    console.log(resource.path);
  }
}
```

### Notes

- For OpenAPI-first workflows, `ImportRestApi` and `PutRestApi` are usually simpler than manually building every resource and method.
- For imperative workflows, store `restApiId`, `rootResourceId`, `resourceId`, `deployment.id`, and `stageName` as soon as they are created.
- Changes to resources, methods, and integrations do not affect live traffic until a deployment is created and a stage points at it.
- API Gateway resource trees can become large, so use the paginators rather than assuming one page is enough.

## API surface — full Command/Input/Output set

`@aws-sdk/client-api-gateway` exports `APIGatewayClient` plus 124 `*Command` classes, 12 paginators. Sample below covers the first 50 commands; all command classes follow `XxxCommand`/`XxxCommandInput`/`XxxCommandOutput` shape.

```typescript
// Client + Command/Input/Output types from @aws-sdk/client-api-gateway
class APIGatewayClient {}
class CreateApiKeyCommand {}
class CreateApiKeyInput {}
class CreateApiKeyOutput {}
class CreateAuthorizerCommand {}
class CreateAuthorizerInput {}
class CreateAuthorizerOutput {}
class CreateBasePathMappingCommand {}
class CreateBasePathMappingInput {}
class CreateBasePathMappingOutput {}
class CreateDeploymentCommand {}
class CreateDeploymentInput {}
class CreateDeploymentOutput {}
class CreateDocumentationPartCommand {}
class CreateDocumentationPartInput {}
class CreateDocumentationPartOutput {}
class CreateDocumentationVersionCommand {}
class CreateDocumentationVersionInput {}
class CreateDocumentationVersionOutput {}
class CreateDomainNameAccessAssociationCommand {}
class CreateDomainNameAccessAssociationInput {}
class CreateDomainNameAccessAssociationOutput {}
class CreateDomainNameCommand {}
class CreateDomainNameInput {}
class CreateDomainNameOutput {}
class CreateModelCommand {}
class CreateModelInput {}
class CreateModelOutput {}
class CreateRequestValidatorCommand {}
class CreateRequestValidatorInput {}
class CreateRequestValidatorOutput {}
class CreateResourceCommand {}
class CreateResourceInput {}
class CreateResourceOutput {}
class CreateRestApiCommand {}
class CreateRestApiInput {}
class CreateRestApiOutput {}
class CreateStageCommand {}
class CreateStageInput {}
class CreateStageOutput {}
class CreateUsagePlanCommand {}
class CreateUsagePlanInput {}
class CreateUsagePlanOutput {}
class CreateUsagePlanKeyCommand {}
class CreateUsagePlanKeyInput {}
class CreateUsagePlanKeyOutput {}
class CreateVpcLinkCommand {}
class CreateVpcLinkInput {}
class CreateVpcLinkOutput {}
class DeleteApiKeyCommand {}
class DeleteApiKeyInput {}
class DeleteApiKeyOutput {}
class DeleteAuthorizerCommand {}
class DeleteAuthorizerInput {}
class DeleteAuthorizerOutput {}
class DeleteBasePathMappingCommand {}
class DeleteBasePathMappingInput {}
class DeleteBasePathMappingOutput {}
class DeleteClientCertificateCommand {}
class DeleteClientCertificateInput {}
class DeleteClientCertificateOutput {}
class DeleteDeploymentCommand {}
class DeleteDeploymentInput {}
class DeleteDeploymentOutput {}
class DeleteDocumentationPartCommand {}
class DeleteDocumentationPartInput {}
class DeleteDocumentationPartOutput {}
class DeleteDocumentationVersionCommand {}
class DeleteDocumentationVersionInput {}
class DeleteDocumentationVersionOutput {}
class DeleteDomainNameAccessAssociationCommand {}
class DeleteDomainNameAccessAssociationInput {}
class DeleteDomainNameAccessAssociationOutput {}
class DeleteDomainNameCommand {}
class DeleteDomainNameInput {}
class DeleteDomainNameOutput {}
class DeleteGatewayResponseCommand {}
class DeleteGatewayResponseInput {}
class DeleteGatewayResponseOutput {}
class DeleteIntegrationCommand {}
class DeleteIntegrationInput {}
class DeleteIntegrationOutput {}
class DeleteIntegrationResponseCommand {}
class DeleteIntegrationResponseInput {}
class DeleteIntegrationResponseOutput {}
class DeleteMethodCommand {}
class DeleteMethodInput {}
class DeleteMethodOutput {}
class DeleteMethodResponseCommand {}
class DeleteMethodResponseInput {}
class DeleteMethodResponseOutput {}
class DeleteModelCommand {}
class DeleteModelInput {}
class DeleteModelOutput {}
class DeleteRequestValidatorCommand {}
class DeleteRequestValidatorInput {}
class DeleteRequestValidatorOutput {}
class DeleteResourceCommand {}
class DeleteResourceInput {}
class DeleteResourceOutput {}
class DeleteRestApiCommand {}
class DeleteRestApiInput {}
class DeleteRestApiOutput {}
class DeleteStageCommand {}
class DeleteStageInput {}
class DeleteStageOutput {}
class DeleteUsagePlanCommand {}
class DeleteUsagePlanInput {}
class DeleteUsagePlanOutput {}
class DeleteUsagePlanKeyCommand {}
class DeleteUsagePlanKeyInput {}
class DeleteUsagePlanKeyOutput {}
class DeleteVpcLinkCommand {}
class DeleteVpcLinkInput {}
class DeleteVpcLinkOutput {}
class FlushStageAuthorizersCacheCommand {}
class FlushStageAuthorizersCacheInput {}
class FlushStageAuthorizersCacheOutput {}
class FlushStageCacheCommand {}
class FlushStageCacheInput {}
class FlushStageCacheOutput {}
class GenerateClientCertificateCommand {}
class GenerateClientCertificateInput {}
class GenerateClientCertificateOutput {}
class GetAccountCommand {}
class GetAccountInput {}
class GetAccountOutput {}
class GetApiKeyCommand {}
class GetApiKeyInput {}
class GetApiKeyOutput {}
class GetApiKeysCommand {}
class GetApiKeysInput {}
class GetApiKeysOutput {}
class GetAuthorizerCommand {}
class GetAuthorizerInput {}
class GetAuthorizerOutput {}
class GetAuthorizersCommand {}
class GetAuthorizersInput {}
class GetAuthorizersOutput {}
class GetBasePathMappingCommand {}
class GetBasePathMappingInput {}
class GetBasePathMappingOutput {}
class GetBasePathMappingsCommand {}
class GetBasePathMappingsInput {}
class GetBasePathMappingsOutput {}
class GetClientCertificateCommand {}
class GetClientCertificateInput {}
class GetClientCertificateOutput {}
class GetClientCertificatesCommand {}
class GetClientCertificatesInput {}
class GetClientCertificatesOutput {}
```

```javascript
// Issue every operation:
const client = new APIGatewayClient({ region: process.env.AWS_REGION });
await client.createApiKey(input);
await client.createAuthorizer(input);
await client.createBasePathMapping(input);
await client.createDeployment(input);
await client.createDocumentationPart(input);
await client.createDocumentationVersion(input);
await client.createDomainNameAccessAssociation(input);
await client.createDomainName(input);
await client.createModel(input);
await client.createRequestValidator(input);
await client.createResource(input);
await client.createRestApi(input);
await client.createStage(input);
await client.createUsagePlan(input);
await client.createUsagePlanKey(input);
await client.createVpcLink(input);
await client.deleteApiKey(input);
await client.deleteAuthorizer(input);
await client.deleteBasePathMapping(input);
await client.deleteClientCertificate(input);
await client.deleteDeployment(input);
await client.deleteDocumentationPart(input);
await client.deleteDocumentationVersion(input);
await client.deleteDomainNameAccessAssociation(input);
await client.deleteDomainName(input);
await client.deleteGatewayResponse(input);
await client.deleteIntegration(input);
await client.deleteIntegrationResponse(input);
await client.deleteMethod(input);
await client.deleteMethodResponse(input);
await client.deleteModel(input);
await client.deleteRequestValidator(input);
await client.deleteResource(input);
await client.deleteRestApi(input);
await client.deleteStage(input);
await client.deleteUsagePlan(input);
await client.deleteUsagePlanKey(input);
await client.deleteVpcLink(input);
await client.flushStageAuthorizersCache(input);
await client.flushStageCache(input);
await client.generateClientCertificate(input);
await client.getAccount(input);
await client.getApiKey(input);
await client.getApiKeys(input);
await client.getAuthorizer(input);
await client.getAuthorizers(input);
await client.getBasePathMapping(input);
await client.getBasePathMappings(input);
await client.getClientCertificate(input);
await client.getClientCertificates(input);

// Paginators (auto-iterate over multi-page responses):
for await (const page of client.paginateGetApiKeys({})) {}
for await (const page of client.paginateGetBasePathMappings({})) {}
for await (const page of client.paginateGetClientCertificates({})) {}
for await (const page of client.paginateGetDeployments({})) {}
for await (const page of client.paginateGetDomainNames({})) {}
for await (const page of client.paginateGetModels({})) {}
for await (const page of client.paginateGetResources({})) {}
for await (const page of client.paginateGetRestApis({})) {}
for await (const page of client.paginateGetUsage({})) {}
for await (const page of client.paginateGetUsagePlanKeys({})) {}
for await (const page of client.paginateGetUsagePlans({})) {}
for await (const page of client.paginateGetVpcLinks({})) {}
```
