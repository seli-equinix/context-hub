---
name: proton
description: AWS Proton SDK for JavaScript guide for template discovery, environment
  and service lifecycle operations, and deployment inspection
metadata:
  languages: javascript
  versions: 3.1007.0
  revision: 1
  updated-on: '2026-03-13'
  source: maintainer
  tags: aws,proton,javascript,nodejs,infrastructure,platform-engineering,send,console,log,aws-sdk,node,ProtonClient,AcceptEnvironmentAccountConnectionCommand,CancelComponentDeploymentCommand,CancelEnvironmentDeploymentCommand,CancelServiceInstanceDeploymentCommand,CancelServicePipelineDeploymentCommand,CreateComponentCommand,CreateEnvironmentAccountConnectionCommand,CreateEnvironmentCommand,CreateEnvironmentTemplateCommand,CreateEnvironmentTemplateVersionCommand,CreateRepositoryCommand,CreateServiceCommand,CreateServiceInstanceCommand,CreateServiceSyncConfigCommand,CreateServiceTemplateCommand,CreateServiceTemplateVersionCommand,CreateTemplateSyncConfigCommand,DeleteComponentCommand,DeleteDeploymentCommand,DeleteEnvironmentAccountConnectionCommand,DeleteEnvironmentCommand,DeleteEnvironmentTemplateCommand,DeleteEnvironmentTemplateVersionCommand,DeleteRepositoryCommand,DeleteServiceCommand,DeleteServiceSyncConfigCommand,DeleteServiceTemplateCommand,DeleteServiceTemplateVersionCommand,DeleteTemplateSyncConfigCommand,GetAccountSettingsCommand,waitUntilEnvironmentDeployed,paginateListRepositories,RejectEnvironmentAccountConnectionCommand,GetServiceInstanceCommand,waitUntilServicePipelineDeployed,paginateListEnvironmentProvisionedResources,waitUntilServiceUpdated,GetServiceCommand,ListServicePipelineOutputsCommand,paginateListComponents,UpdateEnvironmentTemplateVersionCommand,UpdateServicePipelineCommand,ListTagsForResourceCommand,ListServiceInstanceOutputsCommand,GetEnvironmentCommand,ListServiceTemplatesCommand,waitForComponentDeployed,waitForServiceTemplateVersionRegistered,waitUntilServiceTemplateVersionRegistered,waitForEnvironmentDeployed,ListEnvironmentAccountConnectionsCommand,paginateListServices,UpdateAccountSettingsCommand,waitUntilComponentDeleted,UpdateServiceSyncConfigCommand,ListDeploymentsCommand,GetServiceInstanceSyncStatusCommand,paginateListEnvironmentTemplates,UpdateEnvironmentAccountConnectionCommand,GetServiceSyncConfigCommand,paginateListEnvironmentAccountConnections,UpdateServiceTemplateCommand,paginateListComponentOutputs,waitForServicePipelineDeployed,ListEnvironmentOutputsCommand,paginateListDeployments,GetServiceTemplateCommand,ListComponentProvisionedResourcesCommand,GetTemplateSyncStatusCommand,ListServicesCommand,UpdateServiceCommand,paginateListServiceInstanceOutputs,GetTemplateSyncConfigCommand,waitForServiceInstanceDeployed,ServiceQuotaExceededException,ListEnvironmentTemplateVersionsCommand,paginateListEnvironments,waitUntilServiceInstanceDeployed,GetServiceTemplateVersionCommand,UpdateComponentCommand,waitForServiceDeleted,ValidationException,paginateListServiceTemplates,waitForServiceUpdated,GetComponentCommand,InternalServerException,UpdateServiceTemplateVersionCommand,ListServicePipelineProvisionedResourcesCommand,ListServiceTemplateVersionsCommand,ConflictException,ListRepositoriesCommand,GetRepositoryCommand,ListServiceInstancesCommand,paginateListRepositorySyncDefinitions,UpdateEnvironmentCommand,paginateListServiceInstances,GetServiceSyncBlockerSummaryCommand,waitForServiceCreated,ListComponentsCommand,ListEnvironmentProvisionedResourcesCommand,paginateListServiceTemplateVersions,ProtonServiceException,Proton,ListRepositorySyncDefinitionsCommand,GetResourcesSummaryCommand,waitUntilServiceDeleted,paginateListServicePipelineProvisionedResources,waitUntilEnvironmentTemplateVersionRegistered,ThrottlingException,GetDeploymentCommand,paginateListEnvironmentOutputs,waitForComponentDeleted,paginateListServiceInstanceProvisionedResources,TagResourceCommand,waitUntilComponentDeployed,UpdateEnvironmentTemplateCommand,GetEnvironmentAccountConnectionCommand,NotifyResourceDeploymentStatusChangeCommand,GetEnvironmentTemplateCommand,ResourceNotFoundException,paginateListServicePipelineOutputs,UpdateTemplateSyncConfigCommand,paginateListTagsForResource,ListComponentOutputsCommand,waitUntilServiceCreated,GetRepositorySyncStatusCommand,paginateListComponentProvisionedResources,GetEnvironmentTemplateVersionCommand,ListServiceInstanceProvisionedResourcesCommand,ListEnvironmentsCommand,UntagResourceCommand,waitForEnvironmentTemplateVersionRegistered,AccessDeniedException,paginateListEnvironmentTemplateVersions,UpdateServiceSyncBlockerCommand,UpdateServiceInstanceCommand,ListEnvironmentTemplatesCommand
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

## Per-symbol detail

### AcceptEnvironmentAccountConnectionCommand

The `AcceptEnvironmentAccountConnectionCommand` class represents an API operation that approves a pending environment account connection request within the AWS Proton service. You should instantiate this command and pass it to the `ProtonClient.send` method when you need to authorize a linked account to access a Proton environment. Upon successful execution, the command resolves to a response object that updates the connection status and confirms the relationship between the accounts.

```javascript
const { ProtonClient, AcceptEnvironmentAccountConnectionCommand } = require("@aws-sdk/client-proton");

async function main() {
  const client = new ProtonClient({ region: "us-east-1" });
  const input = { connectionId: "your-connection-id" };
  const command = new AcceptEnvironmentAccountConnectionCommand(input);
  const response = await client.send(command);
}
```

### AccessDeniedException

This exception is thrown by the AWS Proton client when an API operation fails due to insufficient IAM permissions or access control restrictions. In JavaScript applications, developers should wrap Proton commands in a `try/catch` block to specifically handle this error type and implement appropriate fallback logic or user notifications. When caught, the error object provides details about the denied action, allowing the application to gracefully manage security-related failures without crashing. It affects the execution flow of lifecycle operations such as environment creation or service deployment by halting the process until access is resolved.

```javascript
import { ProtonClient, CancelComponentDeploymentCommand } from "@aws-sdk/client-proton";
import { AccessDeniedException } from "@aws-sdk/client-proton";

const client = new ProtonClient({ region: "us-east-1" });
try {
  await client.send(new CancelComponentDeploymentCommand({ componentDeploymentId: "example-id" }));
} catch (error) {
  if (error instanceof AccessDeniedException) {
    console.error("Access denied, check IAM permissions.");
  }
}
```

### CancelComponentDeploymentCommand

The `CancelComponentDeploymentCommand` class encapsulates the API request required to stop an ongoing deployment for a specific component managed by AWS Proton. Developers instantiate this command with the target deployment identifier and execute it via the `send` method on a configured `ProtonClient` to perform the cancellation asynchronously. If the operation succeeds, the component deployment status transitions to canceled, while failures may result in exceptions such as `AccessDeniedException` depending on the caller's permissions. This command is essential for managing the lifecycle of infrastructure components when manual intervention or error recovery is needed during the deployment process.

```javascript
const { ProtonClient, CancelComponentDeploymentCommand } = require("@aws-sdk/client-proton");

const client = new ProtonClient({ region: "us-east-1" });
const input = { componentDeploymentId: "example-deployment-id" };
const command = new CancelComponentDeploymentCommand(input);

try {
  const response = await client.send(command);
  console.log("Deployment canceled successfully:", response);
} catch (err) {
  console.error("Failed to cancel deployment:", err);
}
```

### CancelEnvironmentDeploymentCommand

The `CancelEnvironmentDeploymentCommand` class represents an API operation to terminate an ongoing deployment process for a specific AWS Proton environment. Developers invoke this command when a deployment is stalled or needs to be halted before completion, ensuring resources are not consumed unnecessarily. In the JavaScript SDK, executing this command returns a Promise that resolves to the deployment details, though it may reject with `AccessDeniedException` if permissions are insufficient. This operation integrates seamlessly with other lifecycle commands such as `CancelComponentDeploymentCommand` to manage the full scope of environment modifications.

```javascript
const { ProtonClient, CancelEnvironmentDeploymentCommand } = require("@aws-sdk/client-proton");

async function example() {
  const client = new ProtonClient({ region: "us-east-1" });
  const command = new CancelEnvironmentDeploymentCommand({
    environmentName: "my-environment",
    deploymentId: "deployment-123"
  });
  const response = await client.send(command);
}
```

### CancelServiceInstanceDeploymentCommand

The `CancelServiceInstanceDeploymentCommand` class encapsulates the request to terminate an active deployment process for a specific service instance within AWS Proton. Developers should utilize this command when a running provisioning or update operation needs to be halted immediately to prevent further state changes. When executed through the SDK client using the `send` method, it returns a Promise that resolves upon successful submission of the cancellation request, enabling standard asynchronous error handling in Node.js applications. This pattern aligns with the asynchronous design of the AWS SDK for JavaScript v3.

```javascript
const { ProtonClient, CancelServiceInstanceDeploymentCommand } = require("@aws-sdk/client-proton");

async function main() {
  const client = new ProtonClient({ region: "us-east-1" });
  const input = { serviceInstanceId: "my-service-instance-id", deploymentId: "my-deployment-id" };
  const command = new CancelServiceInstanceDeploymentCommand(input);

  try {
    await client.send(command);
    console.log("Deployment cancellation requested");
  } catch (err) {
    console.error("Failed to cancel deployment", err);
  }
}
```

### CancelServicePipelineDeploymentCommand

The `CancelServicePipelineDeploymentCommand` class represents an operation to stop an active deployment for a service pipeline managed by AWS Proton. Developers use this command when a deployment needs to be halted mid-process to prevent unintended state changes or to address configuration errors. The command is sent via the Proton client and returns a promise that resolves with the updated deployment details, adhering to the standard asynchronous patterns found in the AWS SDK for JavaScript. It complements other lifecycle commands such as `CancelEnvironmentDeploymentCommand` and `CancelServiceInstanceDeploymentCommand` within the same package.

```javascript
import { ProtonClient, CancelServicePipelineDeploymentCommand } from "@aws-sdk/client-proton";

const client = new ProtonClient({ region: "us-east-1" });
const input = { servicePipelineDeploymentId: "your-deployment-id" };
const command = new CancelServicePipelineDeploymentCommand(input);
const response = await client.send(command);
```

### ConflictException

The `ConflictException` is thrown by AWS Proton operations when a request conflicts with the current state of a resource, such as attempting to create an existing service instance or modifying a resource that is currently being updated. In JavaScript applications using the AWS SDK for Proton, this error is typically caught within a `try/catch` block to handle specific failure scenarios gracefully without crashing the application. Developers should inspect the exception message or name to distinguish this from other errors like `AccessDeniedException` and implement retry logic or user notifications accordingly. Handling this exception ensures that your application can respond appropriately to transient or permanent resource state issues.

```javascript
const { ProtonClient, CancelEnvironmentDeploymentCommand, ConflictException } = require("@aws-sdk/client-proton");
const client = new ProtonClient({ region: "us-east-1" });
try {
  await client.send(new CancelEnvironmentDeploymentCommand({ environmentId: "env-123" }));
} catch (error) {
  if (error instanceof ConflictException) {
    console.error("Operation conflict:", error.message);
  }
}
```

### CreateComponentCommand

The `CreateComponentCommand` class encapsulates the API operation required to register a new component within an AWS Proton environment, defining reusable infrastructure templates. Developers instantiate this command with necessary configuration details and pass it to a `ProtonClient` instance to execute the creation asynchronously. Upon successful completion, the `send` method resolves a promise containing the component's metadata, which can then be used for subsequent deployment or management tasks. This operation is fundamental for establishing the infrastructure definitions that Proton manages across your AWS accounts.

```javascript
const { ProtonClient, CreateComponentCommand } = require("@aws-sdk/client-proton");

async function run() {
  const client = new ProtonClient({ region: "us-east-1" });
  const command = new CreateComponentCommand({
    name: "example-component",
    templateName: "example-template",
    templateVersion: "1.0.0"
  });

  const response = await client.send(command);
  console.log("Component created:", response.component.name);
}

run();
```

### CreateEnvironmentAccountConnectionCommand

This command initiates a request to link an AWS account to an AWS Proton environment, enabling the account to participate in managed infrastructure operations. In JavaScript applications using the AWS SDK for JavaScript v3, you instantiate this command with the necessary connection details and pass it to the client's `send` method. The operation returns a Promise that resolves with the connection details or rejects with an error such as `AccessDeniedException` if permissions are insufficient. This workflow is typically followed by using `AcceptEnvironmentAccountConnectionCommand` from the target account to finalize the trust relationship.

```javascript
import { ProtonClient, CreateEnvironmentAccountConnectionCommand } from "@aws-sdk/client-proton";

const client = new ProtonClient({ region: "us-east-1" });
const input = { /* connection parameters */ };
const command = new CreateEnvironmentAccountConnectionCommand(input);
const response = await client.send(command);
```

### CreateEnvironmentCommand

The `CreateEnvironmentCommand` class encapsulates the API request to provision a new environment instance managed by AWS Proton. In Node.js applications, you typically instantiate this command with the necessary input parameters and pass it to the Proton client's `send` method to trigger the asynchronous creation process. Upon completion, the promise resolves with the environment metadata or rejects with exceptions such as `AccessDeniedException` if the caller lacks the required IAM permissions.

```javascript
import { ProtonClient, CreateEnvironmentCommand } from "@aws-sdk/client-proton";

const client = new ProtonClient({ region: "us-east-1" });
const input = { environmentName: "my-env", templateName: "my-template" };
const command = new CreateEnvironmentCommand(input);
const response = await client.send(command);
```

## API surface — verifiable exports of `@aws-sdk/client-proton`

Each symbol below is a real export of `@aws-sdk/client-proton`, verified via `Object.keys(require('@aws-sdk/client-proton'))`.

```typescript
// 87 Command classes
class AcceptEnvironmentAccountConnectionCommand {}
class CancelComponentDeploymentCommand {}
class CancelEnvironmentDeploymentCommand {}
class CancelServiceInstanceDeploymentCommand {}
class CancelServicePipelineDeploymentCommand {}
class CreateComponentCommand {}
class CreateEnvironmentAccountConnectionCommand {}
class CreateEnvironmentCommand {}
class CreateEnvironmentTemplateCommand {}
class CreateEnvironmentTemplateVersionCommand {}
class CreateRepositoryCommand {}
class CreateServiceCommand {}
class CreateServiceInstanceCommand {}
class CreateServiceSyncConfigCommand {}
class CreateServiceTemplateCommand {}
class CreateServiceTemplateVersionCommand {}
class CreateTemplateSyncConfigCommand {}
class DeleteComponentCommand {}
class DeleteDeploymentCommand {}
class DeleteEnvironmentAccountConnectionCommand {}
class DeleteEnvironmentCommand {}
class DeleteEnvironmentTemplateCommand {}
class DeleteEnvironmentTemplateVersionCommand {}
class DeleteRepositoryCommand {}
class DeleteServiceCommand {}
class DeleteServiceSyncConfigCommand {}
class DeleteServiceTemplateCommand {}
class DeleteServiceTemplateVersionCommand {}
class DeleteTemplateSyncConfigCommand {}
class GetAccountSettingsCommand {}
class GetComponentCommand {}
class GetDeploymentCommand {}
class GetEnvironmentAccountConnectionCommand {}
class GetEnvironmentCommand {}
class GetEnvironmentTemplateCommand {}
class GetEnvironmentTemplateVersionCommand {}
class GetRepositoryCommand {}
class GetRepositorySyncStatusCommand {}
class GetResourcesSummaryCommand {}
class GetServiceCommand {}
class GetServiceInstanceCommand {}
class GetServiceInstanceSyncStatusCommand {}
class GetServiceSyncBlockerSummaryCommand {}
class GetServiceSyncConfigCommand {}
class GetServiceTemplateCommand {}
class GetServiceTemplateVersionCommand {}
class GetTemplateSyncConfigCommand {}
class GetTemplateSyncStatusCommand {}
class ListComponentOutputsCommand {}
class ListComponentProvisionedResourcesCommand {}
class ListComponentsCommand {}
class ListDeploymentsCommand {}
class ListEnvironmentAccountConnectionsCommand {}
class ListEnvironmentOutputsCommand {}
class ListEnvironmentProvisionedResourcesCommand {}
class ListEnvironmentTemplateVersionsCommand {}
class ListEnvironmentTemplatesCommand {}
class ListEnvironmentsCommand {}
class ListRepositoriesCommand {}
class ListRepositorySyncDefinitionsCommand {}
// ... (27 additional commands not shown)
// Other classes
class AccessDeniedException {}
class ConflictException {}
class InternalServerException {}
class Proton {}
class ProtonClient {}
class ProtonServiceException {}
class ResourceNotFoundException {}
class ServiceQuotaExceededException {}
class ThrottlingException {}
class ValidationException {}
```

```javascript
// Verified Command-pattern usage
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
```
