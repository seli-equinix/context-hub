---
name: proton
description: "AWS Proton SDK for JavaScript guide for template discovery, environment and service lifecycle operations, and deployment inspection"
metadata:
  languages: "javascript"
  versions: "3.1007.0"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "aws,proton,javascript,nodejs,infrastructure,platform-engineering,send,console,log,aws-sdk,node,ProtonClient,AcceptEnvironmentAccountConnectionCommand,CancelComponentDeploymentCommand,CancelEnvironmentDeploymentCommand,CancelServiceInstanceDeploymentCommand,CancelServicePipelineDeploymentCommand,CreateComponentCommand,CreateEnvironmentAccountConnectionCommand,CreateEnvironmentCommand,CreateEnvironmentTemplateCommand,CreateEnvironmentTemplateVersionCommand,CreateRepositoryCommand,CreateServiceCommand,CreateServiceInstanceCommand,CreateServiceSyncConfigCommand,CreateServiceTemplateCommand,CreateServiceTemplateVersionCommand,CreateTemplateSyncConfigCommand,DeleteComponentCommand,DeleteDeploymentCommand,DeleteEnvironmentAccountConnectionCommand,DeleteEnvironmentCommand,DeleteEnvironmentTemplateCommand,DeleteEnvironmentTemplateVersionCommand,DeleteRepositoryCommand,DeleteServiceCommand,DeleteServiceSyncConfigCommand,DeleteServiceTemplateCommand,DeleteServiceTemplateVersionCommand,DeleteTemplateSyncConfigCommand,GetAccountSettingsCommand"
---

# AWS Proton SDK for JavaScript

## Golden Rule

Use `@aws-sdk/client-proton` for Proton control-plane work from JavaScript or Node.js: discover templates, create or update environments and services, manage service instances, and inspect deployment outputs.

Most Proton write APIs take a `spec` field as a YAML string, not a nested JavaScript object. Keep the spec in a file that matches your Proton template bundle and load it as text.

```bash
npm install @aws-sdk/client-proton
```

Before you call create or update APIs, make sure the target Region already has the Proton environment template, service template, and published template versions you plan to use.

## Credentials And Region

Proton is regional. Use the same AWS Region as your Proton templates, environments, services, linked repositories, and CodeStar connection resources.

Typical local setup:

```bash
export AWS_REGION=us-west-2
export AWS_PROFILE=dev

export PROTON_ENV_TEMPLATE_NAME=network-env
export PROTON_SERVICE_TEMPLATE_NAME=orders-service
export PROTON_ENVIRONMENT_NAME=orders-dev
export PROTON_SERVICE_NAME=orders-api
export PROTON_SERVICE_INSTANCE_NAME=orders-api-dev

export PROTON_SERVICE_ROLE_ARN=arn:aws:iam::123456789012:role/AWSProtonServiceRole
export PROTON_COMPONENT_ROLE_ARN=arn:aws:iam::123456789012:role/ProtonEnvironmentComponentRole
export PROTON_ENV_ACCOUNT_CONNECTION_ID=12345678-1234-1234-1234-123456789012

export PROTON_REPOSITORY_CONNECTION_ARN=arn:aws:codestar-connections:us-west-2:123456789012:connection/11111111-2222-3333-4444-555555555555
export PROTON_REPOSITORY_ID=myorg/orders-api
export PROTON_REPOSITORY_BRANCH=main

export PROTON_PROVISIONING_REPO_NAME=infra-live
export PROTON_PROVISIONING_REPO_BRANCH=main
```

The SDK uses the standard AWS credential provider chain in Node.js, including environment variables, shared AWS config files, IAM roles, and other standard AWS credential sources.

For environment provisioning, choose one mode and keep the request shape consistent:

- AWS-managed provisioning: send `protonServiceRoleArn` or `environmentAccountConnectionId`, and omit `provisioningRepository`.
- Self-managed provisioning: send `provisioningRepository`, and omit `protonServiceRoleArn` and `environmentAccountConnectionId`.

## Client Initialization

```javascript
import { ProtonClient } from "@aws-sdk/client-proton";

export const proton = new ProtonClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});
```

## Common Workflows

### Discover templates and published versions

List templates first, then inspect template versions before you hardcode a template name or version.

```javascript
import {
  ListServiceTemplateVersionsCommand,
  ProtonClient,
  paginateListEnvironmentTemplates,
  paginateListServiceTemplates,
} from "@aws-sdk/client-proton";

const proton = new ProtonClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});

for await (const page of paginateListEnvironmentTemplates(
  { client: proton },
  {},
)) {
  for (const template of page.templates ?? []) {
    console.log("environment template", template.name, template.recommendedVersion);
  }
}

for await (const page of paginateListServiceTemplates(
  { client: proton },
  {},
)) {
  for (const template of page.templates ?? []) {
    console.log("service template", template.name, template.recommendedVersion);
  }
}

const { templateVersions } = await proton.send(
  new ListServiceTemplateVersionsCommand({
    templateName: process.env.PROTON_SERVICE_TEMPLATE_NAME,
  }),
);

for (const version of templateVersions ?? []) {
  if (version.status === "PUBLISHED") {
    console.log(
      `${version.templateName} ${version.majorVersion}.${version.minorVersion}`,
      "recommended minor:",
      version.recommendedMinorVersion,
    );
  }
}
```

Use the published versions from these APIs when you set `templateMajorVersion` and `templateMinorVersion` on create or update calls.

### Create an environment and wait for deployment

`CreateEnvironmentCommand` requires `name`, `spec`, `templateMajorVersion`, and `templateName`. The `spec` must match the schema in your environment template bundle.

```javascript
import { readFileSync } from "node:fs";
import {
  CreateEnvironmentCommand,
  GetEnvironmentCommand,
  ProtonClient,
  waitUntilEnvironmentDeployed,
} from "@aws-sdk/client-proton";

const proton = new ProtonClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});

const environmentSpec = readFileSync("./proton/environment-spec.yaml", "utf8");

await proton.send(
  new CreateEnvironmentCommand({
    name: process.env.PROTON_ENVIRONMENT_NAME,
    templateName: process.env.PROTON_ENV_TEMPLATE_NAME,
    templateMajorVersion: "1",
    spec: environmentSpec,
    protonServiceRoleArn: process.env.PROTON_SERVICE_ROLE_ARN,
    componentRoleArn: process.env.PROTON_COMPONENT_ROLE_ARN,
  }),
);

await waitUntilEnvironmentDeployed(
  { client: proton, maxWaitTime: 30 * 60 },
  { name: process.env.PROTON_ENVIRONMENT_NAME },
);

const { environment } = await proton.send(
  new GetEnvironmentCommand({
    name: process.env.PROTON_ENVIRONMENT_NAME,
  }),
);

console.log(environment?.deploymentStatus, environment?.templateName);
```

If your environment uses self-managed provisioning, replace `protonServiceRoleArn` with `provisioningRepository: { name, branch, provider }` and omit both `protonServiceRoleArn` and `environmentAccountConnectionId`.

### Create a service and inspect pipeline status

Repository-backed service creation commonly includes `branchName`, `repositoryConnectionArn`, and `repositoryId`, but the API model does not require those fields for every service template. Send them only when your service template or provisioning model needs them.

```javascript
import { readFileSync } from "node:fs";
import {
  CreateServiceCommand,
  GetServiceCommand,
  ProtonClient,
  waitUntilServiceCreated,
} from "@aws-sdk/client-proton";

const proton = new ProtonClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});

const serviceSpec = readFileSync("./proton/service-spec.yaml", "utf8");

await proton.send(
  new CreateServiceCommand({
    name: process.env.PROTON_SERVICE_NAME,
    templateName: process.env.PROTON_SERVICE_TEMPLATE_NAME,
    templateMajorVersion: "1",
    spec: serviceSpec,
    branchName: process.env.PROTON_REPOSITORY_BRANCH,
    repositoryConnectionArn: process.env.PROTON_REPOSITORY_CONNECTION_ARN,
    repositoryId: process.env.PROTON_REPOSITORY_ID,
  }),
);

await waitUntilServiceCreated(
  { client: proton, maxWaitTime: 30 * 60 },
  { name: process.env.PROTON_SERVICE_NAME },
);

const { service } = await proton.send(
  new GetServiceCommand({
    name: process.env.PROTON_SERVICE_NAME,
  }),
);

console.log(service?.status, service?.pipeline?.deploymentStatus);
```

For service templates with pipelines, the service `spec` is still a YAML string. AWS CLI examples show a `proton: ServiceSpec` document with `pipeline` and `instances` sections, so keep the YAML in source control instead of embedding a large multiline string in your application code.

### Update a service instance

`UpdateServiceInstanceCommand` always requires `deploymentType`, `name`, and `serviceName`. Use `CURRENT_VERSION` when you are changing only the instance spec on the current template version.

```javascript
import { readFileSync } from "node:fs";
import {
  ProtonClient,
  UpdateServiceInstanceCommand,
  waitUntilServiceInstanceDeployed,
} from "@aws-sdk/client-proton";

const proton = new ProtonClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});

const serviceInstanceSpec = readFileSync(
  "./proton/service-instance-spec.yaml",
  "utf8",
);

await proton.send(
  new UpdateServiceInstanceCommand({
    name: process.env.PROTON_SERVICE_INSTANCE_NAME,
    serviceName: process.env.PROTON_SERVICE_NAME,
    deploymentType: "CURRENT_VERSION",
    spec: serviceInstanceSpec,
  }),
);

await waitUntilServiceInstanceDeployed(
  { client: proton, maxWaitTime: 30 * 60 },
  {
    name: process.env.PROTON_SERVICE_INSTANCE_NAME,
    serviceName: process.env.PROTON_SERVICE_NAME,
  },
);
```

Use `MINOR_VERSION` or `MAJOR_VERSION` only when you are intentionally moving the service instance to a newer published template version. Use `NONE` for metadata-only updates that should not trigger a deployment.

If you are adding a brand-new instance to an existing service, use `CreateServiceInstanceCommand` with `name`, `serviceName`, and an instance `spec`, then wait with `waitUntilServiceInstanceDeployed`.

### Read environment outputs and provisioned resources

After deployment, the outputs and provisioned-resource list APIs are the practical way to discover IDs, ARNs, stack outputs, and downstream resource names.

```javascript
import {
  ListEnvironmentOutputsCommand,
  ListServiceInstanceProvisionedResourcesCommand,
  ProtonClient,
} from "@aws-sdk/client-proton";

const proton = new ProtonClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});

const { outputs } = await proton.send(
  new ListEnvironmentOutputsCommand({
    environmentName: process.env.PROTON_ENVIRONMENT_NAME,
  }),
);

for (const output of outputs ?? []) {
  console.log("environment output", output.key, output.valueString);
}

const { provisionedResources } = await proton.send(
  new ListServiceInstanceProvisionedResourcesCommand({
    serviceInstanceName: process.env.PROTON_SERVICE_INSTANCE_NAME,
    serviceName: process.env.PROTON_SERVICE_NAME,
  }),
);

for (const resource of provisionedResources ?? []) {
  console.log(
    "provisioned resource",
    resource.name,
    resource.identifier,
    resource.provisioningEngine,
  );
}
```

If you need outputs or resources for a specific deployment attempt, the output-list APIs also accept `deploymentId`.

## Common Pitfalls

- Sending the Proton `spec` as a JavaScript object. The current API expects a YAML string.
- Treating `templateMajorVersion` and `templateMinorVersion` as numbers. The API model defines them as strings.
- Creating or updating resources before checking that the target template version is `PUBLISHED`.
- Mixing environment provisioning modes. Self-managed provisioning uses `provisioningRepository`; AWS-managed provisioning uses `protonServiceRoleArn` or `environmentAccountConnectionId`.
- Forgetting `deploymentType` on `UpdateEnvironmentCommand` or `UpdateServiceInstanceCommand`.
- Assuming the initial create or update call means the deployment already finished. Use Proton waiters or poll `GetEnvironment`, `GetService`, or `GetServiceInstance`.
- Expecting list APIs to return every result in one call. Proton exposes paginators for templates, environments, services, service instances, outputs, provisioned resources, repositories, and deployments.
- Sending repository fields for a service template that does not use repository-backed pipeline provisioning.

## Version Notes

- This guide targets `@aws-sdk/client-proton` version `3.1007.0`.
- The underlying Proton service model reports API version `2020-07-20`.
- The current Proton API model exposes paginators for 21 list-style operations, including `paginateListEnvironmentTemplates`, `paginateListServices`, `paginateListServiceInstances`, and the output and provisioned-resource list APIs.
- The current waiter set includes service and environment helpers that map to `waitUntilEnvironmentDeployed`, `waitUntilServiceCreated`, `waitUntilServiceUpdated`, `waitUntilServiceInstanceDeployed`, and `waitUntilServicePipelineDeployed` in AWS SDK for JavaScript v3.

## Official Sources

- AWS SDK for JavaScript v3 Proton client docs: `https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/client/proton/`
- AWS Proton API Reference: `https://docs.aws.amazon.com/proton/latest/APIReference/Welcome.html`
- AWS Proton Administrator Guide: `https://docs.aws.amazon.com/proton/latest/adminguide/`
- AWS Proton User Guide: `https://docs.aws.amazon.com/proton/latest/userguide/`
- AWS SDK for JavaScript v3 credential configuration for Node.js: `https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/setting-credentials-node.html`
- AWS CLI Proton reference: `https://docs.aws.amazon.com/cli/latest/reference/proton/`
- npm package: `https://www.npmjs.com/package/@aws-sdk/client-proton`

## API surface — full Command/Input/Output set

`@aws-sdk/client-proton` exports `ProtonClient` plus 87 `*Command` classes, 21 paginators. Sample below covers the first 50 commands; all command classes follow `XxxCommand`/`XxxCommandInput`/`XxxCommandOutput` shape.

```typescript
// Client + Command/Input/Output types from @aws-sdk/client-proton
class ProtonClient {}
class AcceptEnvironmentAccountConnectionCommand {}
class AcceptEnvironmentAccountConnectionInput {}
class AcceptEnvironmentAccountConnectionOutput {}
class CancelComponentDeploymentCommand {}
class CancelComponentDeploymentInput {}
class CancelComponentDeploymentOutput {}
class CancelEnvironmentDeploymentCommand {}
class CancelEnvironmentDeploymentInput {}
class CancelEnvironmentDeploymentOutput {}
class CancelServiceInstanceDeploymentCommand {}
class CancelServiceInstanceDeploymentInput {}
class CancelServiceInstanceDeploymentOutput {}
class CancelServicePipelineDeploymentCommand {}
class CancelServicePipelineDeploymentInput {}
class CancelServicePipelineDeploymentOutput {}
class CreateComponentCommand {}
class CreateComponentInput {}
class CreateComponentOutput {}
class CreateEnvironmentAccountConnectionCommand {}
class CreateEnvironmentAccountConnectionInput {}
class CreateEnvironmentAccountConnectionOutput {}
class CreateEnvironmentCommand {}
class CreateEnvironmentInput {}
class CreateEnvironmentOutput {}
class CreateEnvironmentTemplateCommand {}
class CreateEnvironmentTemplateInput {}
class CreateEnvironmentTemplateOutput {}
class CreateEnvironmentTemplateVersionCommand {}
class CreateEnvironmentTemplateVersionInput {}
class CreateEnvironmentTemplateVersionOutput {}
class CreateRepositoryCommand {}
class CreateRepositoryInput {}
class CreateRepositoryOutput {}
class CreateServiceCommand {}
class CreateServiceInput {}
class CreateServiceOutput {}
class CreateServiceInstanceCommand {}
class CreateServiceInstanceInput {}
class CreateServiceInstanceOutput {}
class CreateServiceSyncConfigCommand {}
class CreateServiceSyncConfigInput {}
class CreateServiceSyncConfigOutput {}
class CreateServiceTemplateCommand {}
class CreateServiceTemplateInput {}
class CreateServiceTemplateOutput {}
class CreateServiceTemplateVersionCommand {}
class CreateServiceTemplateVersionInput {}
class CreateServiceTemplateVersionOutput {}
class CreateTemplateSyncConfigCommand {}
class CreateTemplateSyncConfigInput {}
class CreateTemplateSyncConfigOutput {}
class DeleteComponentCommand {}
class DeleteComponentInput {}
class DeleteComponentOutput {}
class DeleteDeploymentCommand {}
class DeleteDeploymentInput {}
class DeleteDeploymentOutput {}
class DeleteEnvironmentAccountConnectionCommand {}
class DeleteEnvironmentAccountConnectionInput {}
class DeleteEnvironmentAccountConnectionOutput {}
class DeleteEnvironmentCommand {}
class DeleteEnvironmentInput {}
class DeleteEnvironmentOutput {}
class DeleteEnvironmentTemplateCommand {}
class DeleteEnvironmentTemplateInput {}
class DeleteEnvironmentTemplateOutput {}
class DeleteEnvironmentTemplateVersionCommand {}
class DeleteEnvironmentTemplateVersionInput {}
class DeleteEnvironmentTemplateVersionOutput {}
class DeleteRepositoryCommand {}
class DeleteRepositoryInput {}
class DeleteRepositoryOutput {}
class DeleteServiceCommand {}
class DeleteServiceInput {}
class DeleteServiceOutput {}
class DeleteServiceSyncConfigCommand {}
class DeleteServiceSyncConfigInput {}
class DeleteServiceSyncConfigOutput {}
class DeleteServiceTemplateCommand {}
class DeleteServiceTemplateInput {}
class DeleteServiceTemplateOutput {}
class DeleteServiceTemplateVersionCommand {}
class DeleteServiceTemplateVersionInput {}
class DeleteServiceTemplateVersionOutput {}
class DeleteTemplateSyncConfigCommand {}
class DeleteTemplateSyncConfigInput {}
class DeleteTemplateSyncConfigOutput {}
class GetAccountSettingsCommand {}
class GetAccountSettingsInput {}
class GetAccountSettingsOutput {}
class GetComponentCommand {}
class GetComponentInput {}
class GetComponentOutput {}
class GetDeploymentCommand {}
class GetDeploymentInput {}
class GetDeploymentOutput {}
class GetEnvironmentAccountConnectionCommand {}
class GetEnvironmentAccountConnectionInput {}
class GetEnvironmentAccountConnectionOutput {}
class GetEnvironmentCommand {}
class GetEnvironmentInput {}
class GetEnvironmentOutput {}
class GetEnvironmentTemplateCommand {}
class GetEnvironmentTemplateInput {}
class GetEnvironmentTemplateOutput {}
class GetEnvironmentTemplateVersionCommand {}
class GetEnvironmentTemplateVersionInput {}
class GetEnvironmentTemplateVersionOutput {}
class GetRepositoryCommand {}
class GetRepositoryInput {}
class GetRepositoryOutput {}
class GetRepositorySyncStatusCommand {}
class GetRepositorySyncStatusInput {}
class GetRepositorySyncStatusOutput {}
class GetResourcesSummaryCommand {}
class GetResourcesSummaryInput {}
class GetResourcesSummaryOutput {}
class GetServiceCommand {}
class GetServiceInput {}
class GetServiceOutput {}
class GetServiceInstanceCommand {}
class GetServiceInstanceInput {}
class GetServiceInstanceOutput {}
class GetServiceInstanceSyncStatusCommand {}
class GetServiceInstanceSyncStatusInput {}
class GetServiceInstanceSyncStatusOutput {}
class GetServiceSyncBlockerSummaryCommand {}
class GetServiceSyncBlockerSummaryInput {}
class GetServiceSyncBlockerSummaryOutput {}
class GetServiceSyncConfigCommand {}
class GetServiceSyncConfigInput {}
class GetServiceSyncConfigOutput {}
class GetServiceTemplateCommand {}
class GetServiceTemplateInput {}
class GetServiceTemplateOutput {}
class GetServiceTemplateVersionCommand {}
class GetServiceTemplateVersionInput {}
class GetServiceTemplateVersionOutput {}
class GetTemplateSyncConfigCommand {}
class GetTemplateSyncConfigInput {}
class GetTemplateSyncConfigOutput {}
class GetTemplateSyncStatusCommand {}
class GetTemplateSyncStatusInput {}
class GetTemplateSyncStatusOutput {}
class ListComponentOutputsCommand {}
class ListComponentOutputsInput {}
class ListComponentOutputsOutput {}
class ListComponentProvisionedResourcesCommand {}
class ListComponentProvisionedResourcesInput {}
class ListComponentProvisionedResourcesOutput {}
```

```javascript
// Issue every operation:
const client = new ProtonClient({ region: process.env.AWS_REGION });
await client.acceptEnvironmentAccountConnection(input);
await client.cancelComponentDeployment(input);
await client.cancelEnvironmentDeployment(input);
await client.cancelServiceInstanceDeployment(input);
await client.cancelServicePipelineDeployment(input);
await client.createComponent(input);
await client.createEnvironmentAccountConnection(input);
await client.createEnvironment(input);
await client.createEnvironmentTemplate(input);
await client.createEnvironmentTemplateVersion(input);
await client.createRepository(input);
await client.createService(input);
await client.createServiceInstance(input);
await client.createServiceSyncConfig(input);
await client.createServiceTemplate(input);
await client.createServiceTemplateVersion(input);
await client.createTemplateSyncConfig(input);
await client.deleteComponent(input);
await client.deleteDeployment(input);
await client.deleteEnvironmentAccountConnection(input);
await client.deleteEnvironment(input);
await client.deleteEnvironmentTemplate(input);
await client.deleteEnvironmentTemplateVersion(input);
await client.deleteRepository(input);
await client.deleteService(input);
await client.deleteServiceSyncConfig(input);
await client.deleteServiceTemplate(input);
await client.deleteServiceTemplateVersion(input);
await client.deleteTemplateSyncConfig(input);
await client.getAccountSettings(input);
await client.getComponent(input);
await client.getDeployment(input);
await client.getEnvironmentAccountConnection(input);
await client.getEnvironment(input);
await client.getEnvironmentTemplate(input);
await client.getEnvironmentTemplateVersion(input);
await client.getRepository(input);
await client.getRepositorySyncStatus(input);
await client.getResourcesSummary(input);
await client.getService(input);
await client.getServiceInstance(input);
await client.getServiceInstanceSyncStatus(input);
await client.getServiceSyncBlockerSummary(input);
await client.getServiceSyncConfig(input);
await client.getServiceTemplate(input);
await client.getServiceTemplateVersion(input);
await client.getTemplateSyncConfig(input);
await client.getTemplateSyncStatus(input);
await client.listComponentOutputs(input);
await client.listComponentProvisionedResources(input);

// Paginators (auto-iterate over multi-page responses):
for await (const page of client.paginateListComponentOutputs({})) {}
for await (const page of client.paginateListComponentProvisionedResources({})) {}
for await (const page of client.paginateListComponents({})) {}
for await (const page of client.paginateListDeployments({})) {}
for await (const page of client.paginateListEnvironmentAccountConnections({})) {}
for await (const page of client.paginateListEnvironmentOutputs({})) {}
for await (const page of client.paginateListEnvironmentProvisionedResources({})) {}
for await (const page of client.paginateListEnvironmentTemplateVersions({})) {}
for await (const page of client.paginateListEnvironmentTemplates({})) {}
for await (const page of client.paginateListEnvironments({})) {}
for await (const page of client.paginateListRepositories({})) {}
for await (const page of client.paginateListRepositorySyncDefinitions({})) {}
for await (const page of client.paginateListServiceInstanceOutputs({})) {}
for await (const page of client.paginateListServiceInstanceProvisionedResources({})) {}
for await (const page of client.paginateListServiceInstances({})) {}
for await (const page of client.paginateListServicePipelineOutputs({})) {}
for await (const page of client.paginateListServicePipelineProvisionedResources({})) {}
for await (const page of client.paginateListServiceTemplateVersions({})) {}
for await (const page of client.paginateListServiceTemplates({})) {}
for await (const page of client.paginateListServices({})) {}
```
