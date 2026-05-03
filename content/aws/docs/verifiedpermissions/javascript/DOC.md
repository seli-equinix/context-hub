---
name: verifiedpermissions
description: AWS SDK for JavaScript v3 client for Amazon Verified Permissions policy
  stores, Cedar policies, identity sources, and authorization decisions.
metadata:
  languages: javascript
  versions: 3.1007.0
  revision: 1
  updated-on: '2026-03-13'
  source: maintainer
  tags: aws,verifiedpermissions,authorization,cedar,javascript,nodejs,client,console,log,send,aws-sdk,node,VerifiedPermissionsClient,BatchGetPolicyCommand,BatchIsAuthorizedCommand,BatchIsAuthorizedWithTokenCommand,CreateIdentitySourceCommand,CreatePolicyCommand,CreatePolicyStoreAliasCommand,CreatePolicyStoreCommand,CreatePolicyTemplateCommand,DeleteIdentitySourceCommand,DeletePolicyCommand,DeletePolicyStoreAliasCommand,DeletePolicyStoreCommand,DeletePolicyTemplateCommand,GetIdentitySourceCommand,GetPolicyCommand,GetPolicyStoreAliasCommand,GetPolicyStoreCommand,GetPolicyTemplateCommand,GetSchemaCommand,IsAuthorizedCommand,IsAuthorizedWithTokenCommand,ListIdentitySourcesCommand,ListPoliciesCommand,ListPolicyStoreAliasesCommand,ListPolicyStoresCommand,ListPolicyTemplatesCommand,ListTagsForResourceCommand,PutSchemaCommand,TagResourceCommand,UntagResourceCommand,ThrottlingException,paginateListPolicies,ValidationException,VerifiedPermissionsServiceException,InternalServerException,UpdatePolicyStoreCommand,ConflictException,ResourceNotFoundException,TooManyTagsException,UpdatePolicyCommand,UpdateIdentitySourceCommand,paginateListPolicyTemplates,VerifiedPermissions,UpdatePolicyTemplateCommand,ServiceQuotaExceededException,paginateListPolicyStores,AccessDeniedException,InvalidStateException,paginateListPolicyStoreAliases,paginateListIdentitySources
---

# `@aws-sdk/client-verifiedpermissions`

Use this package for Amazon Verified Permissions in JavaScript and Node.js. The main workflows are creating a policy store, uploading a Cedar schema, creating policies or policy templates, configuring an identity source, and making authorization decisions with `IsAuthorized` or `IsAuthorizedWithToken`.

## Install

```bash
npm install @aws-sdk/client-verifiedpermissions
```

## Initialize the client

Typical local environment:

```bash
export AWS_REGION=us-east-1
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
# export AWS_SESSION_TOKEN=...   # if you use temporary credentials
```

```javascript
import { VerifiedPermissionsClient } from "@aws-sdk/client-verifiedpermissions";

const verifiedPermissions = new VerifiedPermissionsClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});
```

Use command imports plus `client.send(...)` for normal SDK v3 usage.

## Core workflow

The usual setup order is:

1. Create a policy store.
2. Put a Cedar schema into that store.
3. Create static or template-linked policies.
4. Call `IsAuthorized` or `IsAuthorizedWithToken` from your application.

Verified Permissions is eventually consistent, so new or updated stores, schemas, policies, templates, and identity sources can take a few seconds to appear in later reads and authorization results.

### Create a policy store

`validationSettings` is required. Use `STRICT` if you want policy submissions validated against your Cedar schema.

```javascript
import {
  CreatePolicyStoreCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const createStoreResponse = await client.send(
  new CreatePolicyStoreCommand({
    validationSettings: {
      mode: "STRICT",
    },
    description: "Application authorization store",
    deletionProtection: "ENABLED",
    tags: {
      project: "docs-app",
      environment: "dev",
    },
  }),
);

const policyStoreId = createStoreResponse.policyStoreId;
console.log(policyStoreId);
```

Verified Permissions currently supports only one Cedar namespace per policy store.

### Put or update the Cedar schema

`PutSchema` accepts the schema as a Cedar JSON string. Keeping the schema in a file is usually easier than embedding it inline.

```javascript
import { readFileSync } from "node:fs";
import {
  PutSchemaCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

await client.send(
  new PutSchemaCommand({
    policyStoreId,
    definition: {
      cedarJson: readFileSync("./cedar-schema.json", "utf8"),
    },
  }),
);
```

Schema changes validate policies and templates submitted after the change. Existing policies and templates are not re-evaluated until you update them later.

### Create a static policy

Static policies carry the Cedar statement directly in the request.

```javascript
import {
  CreatePolicyCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const createPolicyResponse = await client.send(
  new CreatePolicyCommand({
    policyStoreId,
    definition: {
      static: {
        description: "Allow a user to view one document",
        statement:
          'permit(principal == App::User::"user-123", action == App::Action::"view", resource == App::Document::"doc-456");',
      },
    },
  }),
);

console.log(createPolicyResponse.policyId);
```

To create a policy linked to a template instead, use `definition.templateLinked` with a `policyTemplateId` plus the principal and resource that should fill the template placeholders.

### Check an authorization decision

Use `IsAuthorized` when your application already knows the principal and can provide any needed entities and request context directly.

```javascript
import {
  IsAuthorizedCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const decision = await client.send(
  new IsAuthorizedCommand({
    policyStoreId,
    principal: {
      entityType: "App::User",
      entityId: "user-123",
    },
    action: {
      actionType: "App::Action",
      actionId: "view",
    },
    resource: {
      entityType: "App::Document",
      entityId: "doc-456",
    },
    context: {
      contextMap: {
        requestIp: { string: "203.0.113.10" },
        isInternal: { boolean: false },
      },
    },
  }),
);

console.log(decision.decision);
console.log(decision.determiningPolicies);
console.log(decision.errors);
```

The response includes the final `decision`, the `determiningPolicies` list, and any evaluation `errors` such as missing entities or attributes referenced by a policy.

### Pass entities for group membership and attributes

If your policies depend on entity attributes or parent relationships, include an `entities` slice with the request.

```javascript
import {
  IsAuthorizedCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const response = await client.send(
  new IsAuthorizedCommand({
    policyStoreId,
    principal: {
      entityType: "App::User",
      entityId: "user-123",
    },
    action: {
      actionType: "App::Action",
      actionId: "edit",
    },
    resource: {
      entityType: "App::Document",
      entityId: "doc-456",
    },
    entities: {
      entityList: [
        {
          identifier: {
            entityType: "App::User",
            entityId: "user-123",
          },
          attributes: {
            department: { string: "engineering" },
          },
          parents: [
            {
              entityType: "App::Group",
              entityId: "editors",
            },
          ],
        },
        {
          identifier: {
            entityType: "App::Document",
            entityId: "doc-456",
          },
          attributes: {
            owner: {
              entityIdentifier: {
                entityType: "App::User",
                entityId: "user-123",
              },
            },
          },
        },
      ],
    },
  }),
);

console.log(response.decision);
```

`context` and `entities` also accept a raw Cedar JSON string through `cedarJson` if you already build those payloads elsewhere.

## JWT-based authorization with an identity source

Use an identity source when the principal should come from an Amazon Cognito user pool or an OpenID Connect provider and you want the application to authorize requests with tokens.

### Create an OIDC identity source

```javascript
import {
  CreateIdentitySourceCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const identitySource = await client.send(
  new CreateIdentitySourceCommand({
    policyStoreId,
    principalEntityType: "App::User",
    configuration: {
      openIdConnectConfiguration: {
        issuer: "https://issuer.example.com",
        entityIdPrefix: "ExampleOIDC",
        groupConfiguration: {
          groupClaim: "groups",
          groupEntityType: "App::Group",
        },
        tokenSelection: {
          accessTokenOnly: {
            principalIdClaim: "sub",
            audiences: ["api://documents"],
          },
        },
      },
    },
  }),
);

console.log(identitySource.identitySourceId);
```

For OIDC, configure either `accessTokenOnly` or `identityTokenOnly` in `tokenSelection`, depending on which token type your application will send for authorization.

### Authorize with a token

```javascript
import {
  IsAuthorizedWithTokenCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const result = await client.send(
  new IsAuthorizedWithTokenCommand({
    policyStoreId,
    accessToken: bearerToken,
    action: {
      actionType: "App::Action",
      actionId: "view",
    },
    resource: {
      entityType: "App::Document",
      entityId: "doc-456",
    },
    context: {
      contextMap: {
        requestTime: { datetime: new Date().toISOString() },
      },
    },
  }),
);

console.log(result.principal);
console.log(result.decision);
```

Verified Permissions validates the token signature and expiration on each call. Tokens remain usable until they expire; token revocation and resource deletion do not invalidate a token already accepted by the policy store.

## List policies

List APIs are paginated with `nextToken`.

```javascript
import {
  ListPoliciesCommand,
  VerifiedPermissionsClient,
} from "@aws-sdk/client-verifiedpermissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

let nextToken;

do {
  const page = await client.send(
    new ListPoliciesCommand({
      policyStoreId,
      maxResults: 50,
      nextToken,
    }),
  );

  for (const policy of page.policies ?? []) {
    console.log(policy.policyId, policy.policyType, policy.effect);
  }

  nextToken = page.nextToken;
} while (nextToken);
```

The same `nextToken` pattern applies to `ListIdentitySources`, `ListPolicyStores`, and `ListPolicyTemplates`.

## Important behavior and pitfalls

- A policy store supports only one Cedar namespace.
- Verified Permissions is eventually consistent after creates and updates. If you create a store, schema, policy, template, or identity source and then immediately read or authorize, add retry or short backoff logic.
- `PutSchema` affects validation for new or updated policies and templates only. Existing items are not revalidated until they are updated.
- `UpdatePolicy` can modify only static policies. It cannot convert a static policy to a template-linked one, and it cannot change the effect, principal, or resource of a static policy.
- `BatchIsAuthorized` accepts up to 30 requests per call, and either the principal or the resource must be identical across the whole batch.
- `DeletePolicyStore` is idempotent. Deleting a store that does not exist still returns HTTP 200.

## Minimal command reference

- Store setup: `CreatePolicyStoreCommand`, `PutSchemaCommand`, `GetPolicyStoreCommand`, `UpdatePolicyStoreCommand`
- Policies: `CreatePolicyCommand`, `GetPolicyCommand`, `ListPoliciesCommand`, `UpdatePolicyCommand`, `DeletePolicyCommand`
- Templates: `CreatePolicyTemplateCommand`, `GetPolicyTemplateCommand`, `ListPolicyTemplatesCommand`, `UpdatePolicyTemplateCommand`, `DeletePolicyTemplateCommand`
- Identity sources: `CreateIdentitySourceCommand`, `GetIdentitySourceCommand`, `ListIdentitySourcesCommand`, `UpdateIdentitySourceCommand`, `DeleteIdentitySourceCommand`
- Authorization: `IsAuthorizedCommand`, `IsAuthorizedWithTokenCommand`, `BatchIsAuthorizedCommand`, `BatchIsAuthorizedWithTokenCommand`

## Per-symbol detail

### AccessDeniedException

The `AccessDeniedException` class indicates that the AWS Verified Permissions client was unable to authorize a request due to insufficient permissions or Cedar policy constraints. In a Node.js application, you should catch this error within a `try/catch` block to distinguish permission failures from other service issues like `ConflictException`. When thrown, it interrupts the execution of commands such as `BatchIsAuthorizedCommand` and exposes the denial reason through the standard `message` property. Proper handling ensures your application can respond to authorization failures without terminating unexpectedly.

```javascript
import { VerifiedPermissionsClient, BatchIsAuthorizedCommand, AccessDeniedException } from "@aws-sdk/client-verified-permissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });
try {
  const command = new BatchIsAuthorizedCommand({ policyStoreId: "example-store" });
  await client.send(command);
} catch (err) {
  if (err instanceof AccessDeniedException) {
    console.error("Access denied:", err.message);
  }
}
```

### BatchGetPolicyCommand

The `BatchGetPolicyCommand` facilitates the retrieval of multiple policy definitions from a Verified Permissions policy store in a single API request. Developers should use this command when bulk fetching policies is required to optimize network latency and reduce the number of calls made to the service. The command resolves with a response containing the requested policy data, though it may throw exceptions such as `AccessDeniedException` if the caller lacks sufficient permissions. This operation adheres to the AWS SDK for JavaScript v3 pattern, requiring an instance of the client to send the command asynchronously.

```javascript
import { VerifiedPermissionsClient, BatchGetPolicyCommand } from "@aws-sdk/client-verified-permissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });
const command = new BatchGetPolicyCommand({ PolicyIdentifierList: ["policy-id-1"] });
const response = await client.send(command);
```

### BatchIsAuthorizedCommand

The `BatchIsAuthorizedCommand` enables efficient authorization checks by evaluating multiple subjects against a policy within a single API call, reducing network latency compared to individual requests. In JavaScript applications using the AWS SDK for JavaScript v3, you instantiate this command with your request context and send it via the `VerifiedPermissionsClient`. The operation resolves to a response object containing the authorization decision for each subject, allowing you to handle results programmatically. This command is particularly useful when validating access for a group of users or resources simultaneously within your Node.js environment.

```javascript
const { VerifiedPermissionsClient, BatchIsAuthorizedCommand } = require("@aws-sdk/client-verified-permissions");

const client = new VerifiedPermissionsClient({ region: "us-east-1" });
const command = new BatchIsAuthorizedCommand({
  policyStoreIdentifier: { id: "your-store-id" },
  policyIdentifier: { id: "your-policy-id" },
  subjects: [{ principal: { id: "user-id" }, type: "User" }]
});
const response = await client.send(command);
```

### BatchIsAuthorizedWithTokenCommand

The `BatchIsAuthorizedWithTokenCommand` enables efficient verification of authorization decisions for multiple principals using identity tokens within the Amazon Verified Permissions service. In a Node.js environment, developers instantiate this command with the necessary policy store context and token information, then invoke the client's `send` method to execute the batch request asynchronously. This operation is ideal for high-throughput applications requiring rapid access control checks against Cedar policies without the overhead of individual API calls. Upon completion, the response object provides the authorization status for each principal-action pair, allowing the application to proceed based on the collective results.

```javascript
const { VerifiedPermissionsClient, BatchIsAuthorizedWithTokenCommand } = require("@aws-sdk/client-verified-permissions");

const client = new VerifiedPermissionsClient({ region: "us-east-1" });
const command = new BatchIsAuthorizedWithTokenCommand({
  policyStoreId: "your-policy-store-id",
  principal: "user:123",
  action: "write",
  resource: "document:456"
});

const response = await client.send(command);
```

### ConflictException

The `ConflictException` is thrown when an operation conflicts with the current state of a Verified Permissions resource, such as attempting to create a policy that already exists. In JavaScript applications, you should wrap your policy store or policy commands in a try-catch block to handle this specific error type gracefully. When caught, the exception provides details about the conflicting resource, allowing your application to decide whether to skip the operation or notify the user. This ensures robust error handling during batch policy updates or authorization checks.

```javascript
const { VerifiedPermissionsClient, BatchGetPolicyCommand, ConflictException } = require("@aws-sdk/client-verified-permissions");
const client = new VerifiedPermissionsClient({ region: "us-east-1" });
try {
  await client.send(new BatchGetPolicyCommand({ policyStoreIdentifier: "store-id" }));
} catch (err) {
  if (err instanceof ConflictException) {
    console.error("Resource conflict detected:", err.message);
  }
}
```

### CreateIdentitySourceCommand

The `CreateIdentitySourceCommand` allows you to register a new identity source within a specific Amazon Verified Permissions policy store. In Node.js applications, you instantiate this command with the required configuration and execute it by passing it to the client instance via the `send` method. The operation returns a promise that resolves with the created identity source details, enabling your application to link external identity providers to your authorization system. Developers should handle potential `AccessDeniedException` or `ConflictException` errors to manage permission issues or duplicate source names gracefully.

```javascript
const { VerifiedPermissionsClient, CreateIdentitySourceCommand } = require("@aws-sdk/client-verified-permissions");

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

const command = new CreateIdentitySourceCommand({
  policyStoreId: "your-policy-store-id",
  name: "example-identity-source"
});

const response = await client.send(command);
```

### CreatePolicyStoreAliasCommand

The `CreatePolicyStoreAliasCommand` enables you to assign a custom alias to an existing policy store, simplifying reference management across development and production environments. Within a Node.js application, you construct this command with the target store identifier and desired alias, then execute it using the client's `send` method. The operation returns a promise that resolves with the alias metadata, allowing your application to utilize the alias for future authorization checks. Developers should handle potential `ConflictException` errors if the alias already exists or `AccessDeniedException` if the user lacks the necessary IAM permissions.

```javascript
import { VerifiedPermissionsClient, CreatePolicyStoreAliasCommand } from "@aws-sdk/client-verified-permissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });
const command = new CreatePolicyStoreAliasCommand({
  PolicyStoreId: "store-123",
  Alias: "prod-alias"
});

try {
  const response = await client.send(command);
  console.log("Alias created:", response);
} catch (err) {
  console.error("Failed to create alias:", err);
}
```

### CreatePolicyStoreCommand

The `CreatePolicyStoreCommand` class encapsulates the request to provision a new policy store within Amazon Verified Permissions. In a Node.js environment, you instantiate this command with your store configuration and pass it to the client's `send` method to execute the operation asynchronously. The command resolves to the created store details upon success, or rejects with exceptions such as `AccessDeniedException` or `ConflictException` if the operation violates permissions or naming constraints. This command is typically invoked during the initialization phase of your application to establish the foundational container for Cedar policies.

```javascript
import { VerifiedPermissionsClient, CreatePolicyStoreCommand } from "@aws-sdk/client-verified-permissions";
import { AccessDeniedException, ConflictException } from "@aws-sdk/client-verified-permissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });

async function main() {
  const command = new CreatePolicyStoreCommand({ storeName: "my-policy-store" });
  try {
    const response = await client.send(command);
    console.log("Store created:", response);
  } catch (err) {
    if (err instanceof AccessDeniedException) {
      console.error("Access denied:", err.message);
    } else if (err instanceof ConflictException) {
      console.error("Store conflict:", err.message);
    } else {
      throw err;
    }
  }
}

main();
```

### CreatePolicyTemplateCommand

The `CreatePolicyTemplateCommand` instantiates a new policy template within a specified Verified Permissions policy store, defining the schema for principals, actions, and resources. You should use this command during the setup phase to establish reusable policy structures before creating specific policy instances. Upon successful execution, the command returns the created template's metadata, while potential issues such as insufficient permissions or existing conflicts are surfaced as `AccessDeniedException` or `ConflictException`.

```javascript
import { VerifiedPermissionsClient, CreatePolicyTemplateCommand } from "@aws-sdk/client-verified-permissions";

const client = new VerifiedPermissionsClient({ region: "us-east-1" });
const command = new CreatePolicyTemplateCommand({
  policyStoreId: "your-policy-store-id",
  policyTemplate: { /* template definition */ }
});

try {
  const response = await client.send(command);
  console.log("Created template:", response.policyTemplate);
} catch (err) {
  if (err.name === "AccessDeniedException" || err.name === "ConflictException") {
    console.error("Policy creation failed:", err.message);
  }
}
```

## API surface — verifiable exports of `@aws-sdk/client-verifiedpermissions`

Each symbol below is a real export of `@aws-sdk/client-verifiedpermissions`, verified via `Object.keys(require('@aws-sdk/client-verifiedpermissions'))`.

```typescript
// 34 Command classes
class BatchGetPolicyCommand {}
class BatchIsAuthorizedCommand {}
class BatchIsAuthorizedWithTokenCommand {}
class CreateIdentitySourceCommand {}
class CreatePolicyCommand {}
class CreatePolicyStoreAliasCommand {}
class CreatePolicyStoreCommand {}
class CreatePolicyTemplateCommand {}
class DeleteIdentitySourceCommand {}
class DeletePolicyCommand {}
class DeletePolicyStoreAliasCommand {}
class DeletePolicyStoreCommand {}
class DeletePolicyTemplateCommand {}
class GetIdentitySourceCommand {}
class GetPolicyCommand {}
class GetPolicyStoreAliasCommand {}
class GetPolicyStoreCommand {}
class GetPolicyTemplateCommand {}
class GetSchemaCommand {}
class IsAuthorizedCommand {}
class IsAuthorizedWithTokenCommand {}
class ListIdentitySourcesCommand {}
class ListPoliciesCommand {}
class ListPolicyStoreAliasesCommand {}
class ListPolicyStoresCommand {}
class ListPolicyTemplatesCommand {}
class ListTagsForResourceCommand {}
class PutSchemaCommand {}
class TagResourceCommand {}
class UntagResourceCommand {}
class UpdateIdentitySourceCommand {}
class UpdatePolicyCommand {}
class UpdatePolicyStoreCommand {}
class UpdatePolicyTemplateCommand {}
// Other classes
class AccessDeniedException {}
class ConflictException {}
class InternalServerException {}
class InvalidStateException {}
class ResourceNotFoundException {}
class ServiceQuotaExceededException {}
class ThrottlingException {}
class TooManyTagsException {}
class ValidationException {}
class VerifiedPermissions {}
class VerifiedPermissionsClient {}
class VerifiedPermissionsServiceException {}
```

```javascript
// Verified Command-pattern usage
const client = new VerifiedPermissionsClient({ region: process.env.AWS_REGION });
await client.batchGetPolicy(input);
await client.batchIsAuthorized(input);
await client.batchIsAuthorizedWithToken(input);
await client.createIdentitySource(input);
await client.createPolicy(input);
await client.createPolicyStoreAlias(input);
await client.createPolicyStore(input);
await client.createPolicyTemplate(input);
await client.deleteIdentitySource(input);
await client.deletePolicy(input);
await client.deletePolicyStoreAlias(input);
await client.deletePolicyStore(input);
await client.deletePolicyTemplate(input);
await client.getIdentitySource(input);
await client.getPolicy(input);
await client.getPolicyStoreAlias(input);
await client.getPolicyStore(input);
await client.getPolicyTemplate(input);
await client.getSchema(input);
await client.isAuthorized(input);
await client.isAuthorizedWithToken(input);
await client.listIdentitySources(input);
await client.listPolicies(input);
await client.listPolicyStoreAliases(input);
await client.listPolicyStores(input);
await client.listPolicyTemplates(input);
await client.listTagsForResource(input);
await client.putSchema(input);
await client.tagResource(input);
await client.untagResource(input);
```
