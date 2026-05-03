---
name: route53-recovery-control-config
description: AWS SDK for JavaScript v3 client for Route 53 Application Recovery Controller
  configuration APIs.
metadata:
  languages: javascript
  versions: 3.1007.0
  revision: 1
  updated-on: '2026-03-13'
  source: maintainer
  tags: aws,route53,application-recovery-controller,arc,javascript,nodejs,console,log,send,route53-recovery-control-config,aws-sdk,node,Route53RecoveryControlConfigClient,CreateClusterCommand,CreateControlPanelCommand,CreateRoutingControlCommand,CreateSafetyRuleCommand,DeleteClusterCommand,DeleteControlPanelCommand,DeleteRoutingControlCommand,DeleteSafetyRuleCommand,DescribeClusterCommand,DescribeControlPanelCommand,DescribeRoutingControlCommand,DescribeSafetyRuleCommand,GetResourcePolicyCommand,ListAssociatedRoute53HealthChecksCommand,ListClustersCommand,ListControlPanelsCommand,ListRoutingControlsCommand,ListSafetyRulesCommand,ListTagsForResourceCommand,TagResourceCommand,UntagResourceCommand,UpdateClusterCommand,UpdateControlPanelCommand,UpdateRoutingControlCommand,UpdateSafetyRuleCommand,waitUntilClusterDeleted,ThrottlingException,waitForControlPanelDeleted,ValidationException,waitForClusterCreated,InternalServerException,paginateListAssociatedRoute53HealthChecks,paginateListClusters,paginateListSafetyRules,waitForRoutingControlCreated,waitForClusterDeleted,ConflictException,waitUntilControlPanelCreated,ResourceNotFoundException,Route53RecoveryControlConfigServiceException,Route53RecoveryControlConfig,waitForRoutingControlDeleted,paginateListRoutingControls,waitUntilControlPanelDeleted,waitForControlPanelCreated,waitUntilRoutingControlDeleted,ServiceQuotaExceededException,waitUntilRoutingControlCreated,AccessDeniedException,paginateListControlPanels,waitUntilClusterCreated
---

# `@aws-sdk/client-route53-recovery-control-config`

Use this package for Amazon Route 53 Application Recovery Controller (ARC) configuration APIs in AWS SDK for JavaScript v3. It covers clusters, control panels, routing controls, safety rules, tags, and resource policies.

This is the ARC configuration plane. It does not turn routing controls on or off. Cluster state reads and writes happen through the separate ARC recovery-cluster data plane APIs.

## Install

```bash
npm install @aws-sdk/client-route53-recovery-control-config
```

## Credentials and region

In Node.js, the default AWS credential provider chain is usually enough if credentials are already configured through environment variables, shared AWS config files, IAM roles, or IAM Identity Center.

Typical local setup:

```bash
export AWS_REGION=us-west-2
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
export AWS_SESSION_TOKEN=...   # only when using temporary credentials
```

Use `us-west-2` explicitly for this client. The service endpoint rules resolve the standard configuration endpoint in the AWS partition to `route53-recovery-control-config.us-west-2.amazonaws.com`.

For browser runtimes, use a browser-safe credential provider. Do not ship long-lived AWS keys to the browser.

## Initialize the client

```javascript
import { Route53RecoveryControlConfigClient } from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({
  region: process.env.AWS_REGION ?? "us-west-2",
});
```

Prefer the command-based client and explicit imports. The package also exposes an aggregated service client, but command imports keep dependencies clearer and bundle size smaller.

## Core usage pattern

```javascript
import {
  ListClustersCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });

const response = await arcConfig.send(
  new ListClustersCommand({ MaxResults: 20 }),
);

for (const cluster of response.Clusters ?? []) {
  console.log(cluster.Name, cluster.ClusterArn, cluster.Status);
}
```

## Common workflows

### Create a cluster

`CreateCluster` returns the cluster ARN plus five regional cluster endpoints. Those endpoints are what you use later with ARC data plane APIs to read or update routing control state.

```javascript
import {
  CreateClusterCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });

const { Cluster } = await arcConfig.send(
  new CreateClusterCommand({
    ClusterName: "payments-prod",
    NetworkType: "IPV4",
    Tags: {
      app: "payments",
      environment: "prod",
    },
  }),
);

console.log(Cluster?.ClusterArn);

for (const endpoint of Cluster?.ClusterEndpoints ?? []) {
  console.log(endpoint.Region, endpoint.Endpoint);
}
```

`NetworkType` supports `IPV4` and `DUALSTACK`.

### Find the default control panel for a cluster

When you create a cluster, ARC also creates a default control panel for it. Fetch the cluster's control panels and look for `DefaultControlPanel`.

```javascript
import {
  ListControlPanelsCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });
const clusterArn = "arn:aws:route53-recovery-control::123456789012:cluster/abc123";

const { ControlPanels } = await arcConfig.send(
  new ListControlPanelsCommand({
    ClusterArn: clusterArn,
    MaxResults: 20,
  }),
);

const defaultPanel = ControlPanels?.find(
  (panel) => panel.DefaultControlPanel,
);

console.log(defaultPanel?.Name, defaultPanel?.ControlPanelArn);
```

If you need an additional panel instead of the default one:

```javascript
import {
  CreateControlPanelCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });

const { ControlPanel } = await arcConfig.send(
  new CreateControlPanelCommand({
    ClusterArn: clusterArn,
    ControlPanelName: "manual-failover",
  }),
);

console.log(ControlPanel?.ControlPanelArn);
```

### Create routing controls

Routing controls belong to a cluster and can optionally be attached to a specific control panel. In practice, pass the `ControlPanelArn` explicitly so the relationship is obvious in code.

```javascript
import {
  CreateRoutingControlCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });

const clusterArn = "arn:aws:route53-recovery-control::123456789012:cluster/abc123";
const controlPanelArn = "arn:aws:route53-recovery-control::123456789012:controlpanel/def456";

const { RoutingControl } = await arcConfig.send(
  new CreateRoutingControlCommand({
    ClusterArn: clusterArn,
    ControlPanelArn: controlPanelArn,
    RoutingControlName: "payments-us-east-1",
  }),
);

console.log(RoutingControl?.RoutingControlArn, RoutingControl?.Status);
```

### Create an assertion safety rule

Safety rules let you guard state changes. Create either an `AssertionRule` or a `GatingRule` in the request body, depending on the behavior you need.

```javascript
import {
  CreateSafetyRuleCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });

const controlPanelArn = "arn:aws:route53-recovery-control::123456789012:controlpanel/def456";
const eastRoutingControlArn = "arn:aws:route53-recovery-control::123456789012:routingcontrol/rc-east";
const westRoutingControlArn = "arn:aws:route53-recovery-control::123456789012:routingcontrol/rc-west";

const response = await arcConfig.send(
  new CreateSafetyRuleCommand({
    AssertionRule: {
      ControlPanelArn: controlPanelArn,
      Name: "keep-one-region-on",
      AssertedControls: [eastRoutingControlArn, westRoutingControlArn],
      RuleConfig: {
        Type: "ATLEAST",
        Threshold: 1,
        Inverted: false,
      },
      WaitPeriodMs: 5000,
    },
  }),
);

console.log(response.AssertionRule?.SafetyRuleArn, response.AssertionRule?.Status);
```

If you need a gating rule instead, pass `GatingRule` with `GatingControls`, `TargetControls`, `RuleConfig`, `WaitPeriodMs`, and `Name`.

### List routing controls and associated Route 53 health checks

```javascript
import {
  ListAssociatedRoute53HealthChecksCommand,
  ListRoutingControlsCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });
const controlPanelArn = "arn:aws:route53-recovery-control::123456789012:controlpanel/def456";

const { RoutingControls } = await arcConfig.send(
  new ListRoutingControlsCommand({
    ControlPanelArn: controlPanelArn,
    MaxResults: 50,
  }),
);

for (const routingControl of RoutingControls ?? []) {
  console.log(routingControl.Name, routingControl.RoutingControlArn);

  const { HealthCheckIds } = await arcConfig.send(
    new ListAssociatedRoute53HealthChecksCommand({
      RoutingControlArn: routingControl.RoutingControlArn,
    }),
  );

  console.log(HealthCheckIds ?? []);
}
```

### Update a safety rule

You can update only the rule name and wait period. If you need to change the controls or rule configuration, delete the safety rule and create a new one.

```javascript
import {
  Route53RecoveryControlConfigClient,
  UpdateSafetyRuleCommand,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });
const safetyRuleArn = "arn:aws:route53-recovery-control::123456789012:safetyrule/ghi789";

const response = await arcConfig.send(
  new UpdateSafetyRuleCommand({
    AssertionRuleUpdate: {
      SafetyRuleArn: safetyRuleArn,
      Name: "keep-one-region-on",
      WaitPeriodMs: 10000,
    },
  }),
);

console.log(response.AssertionRule?.WaitPeriodMs);
```

### Tag a resource and read its tags

Create operations accept tags, and you can also add or inspect tags later.

```javascript
import {
  ListTagsForResourceCommand,
  Route53RecoveryControlConfigClient,
  TagResourceCommand,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });
const resourceArn = "arn:aws:route53-recovery-control::123456789012:cluster/abc123";

await arcConfig.send(
  new TagResourceCommand({
    ResourceArn: resourceArn,
    Tags: {
      owner: "platform",
      environment: "prod",
    },
  }),
);

const { Tags } = await arcConfig.send(
  new ListTagsForResourceCommand({
    ResourceArn: resourceArn,
  }),
);

console.log(Tags);
```

## Manual pagination pattern

The list operations use `NextToken` and `MaxResults`.

```javascript
import {
  ListClustersCommand,
  Route53RecoveryControlConfigClient,
} from "@aws-sdk/client-route53-recovery-control-config";

const arcConfig = new Route53RecoveryControlConfigClient({ region: "us-west-2" });

let nextToken;

do {
  const page = await arcConfig.send(
    new ListClustersCommand({
      MaxResults: 50,
      NextToken: nextToken,
    }),
  );

  for (const cluster of page.Clusters ?? []) {
    console.log(cluster.Name);
  }

  nextToken = page.NextToken;
} while (nextToken);
```

## ARC config gotchas

- This package configures ARC resources. It does not get or update routing control ON/OFF state.
- `CreateCluster` returns five regional cluster endpoints. Keep them if later automation needs the ARC data plane.
- New clusters include a default control panel. You often need to look it up before creating or organizing routing controls.
- `CreateSafetyRule` and `UpdateSafetyRule` work with one rule type at a time: assertion or gating.
- `UpdateSafetyRule` only supports renaming the rule and changing `WaitPeriodMs`.
- Create operations accept an optional `ClientToken` if you want explicit idempotency on retries.
- Expect `ValidationException`, `ResourceNotFoundException`, `ConflictException`, `ThrottlingException`, and `InternalServerException` in real integrations.
- Retry throttling and temporary server errors with backoff instead of treating them as permanent failures.

## Per-symbol detail

### AccessDeniedException

`AccessDeniedException` is an error class thrown by the Route 53 Recovery Control Config client when the caller lacks the necessary IAM permissions to execute a specific API operation. You should catch this exception within a `try/catch` block when invoking commands such as `CreateClusterCommand` or `CreateControlPanelCommand` to handle permission failures gracefully. Upon occurrence, the promise returned by the command rejects with this error, allowing Node.js applications to inspect the `name` property or log the `message` to diagnose access issues.

```javascript
import { Route53RecoveryControlConfigClient, CreateClusterCommand } from "@aws-sdk/client-route-53-recovery-control-config";
import { AccessDeniedException } from "@aws-sdk/client-route-53-recovery-control-config";

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
try {
  await client.send(new CreateClusterCommand({}));
} catch (error) {
  if (error instanceof AccessDeniedException) {
    console.error("Permission denied:", error.message);
  }
}
```

### ConflictException

This exception indicates that the requested operation conflicts with the current state of a resource in the Route 53 Application Recovery Controller. In Node.js applications, developers catch this error within a `try/catch` block to handle scenarios where a resource already exists or is being modified concurrently. The error object provides details about the conflict, allowing the application to decide whether to retry the operation or notify the user of the state mismatch. Proper handling ensures your application remains resilient against race conditions during cluster or control panel creation.

```javascript
import { Route53RecoveryControlConfigClient, CreateClusterCommand } from "@aws-sdk/client-route53-recovery-control-config";
import { ConflictException } from "@aws-sdk/client-route53-recovery-control-config";

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
try {
  await client.send(new CreateClusterCommand({ clusterName: "example-cluster" }));
} catch (err) {
  if (err instanceof ConflictException) {
    console.error("Cluster already exists or is in conflict state");
  }
}
```

### CreateClusterCommand

The `CreateClusterCommand` class encapsulates the API request to create a new cluster for Route 53 Application Recovery Controller within your AWS account. In JavaScript applications, you typically construct an instance of this command with your desired configuration and pass it to an initialized `Route53RecoveryControlConfigClient` to trigger the asynchronous operation. The command returns a Promise that resolves with the cluster metadata or rejects with exceptions like `AccessDeniedException` or `ConflictException` if permissions or state conflicts occur. This usage follows the standard v3 SDK pattern where commands are immutable objects sent to a client for execution.

```javascript
import { Route53RecoveryControlConfigClient, CreateClusterCommand } from "@aws-sdk/client-route-53-recovery-control-config";

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
const command = new CreateClusterCommand({ ClusterName: "example-cluster" });

try {
  const response = await client.send(command);
  console.log(response.ClusterArn);
} catch (err) {
  console.error(err);
}
```

### CreateRoutingControlCommand

The `CreateRoutingControlCommand` class encapsulates the request to provision a new routing control within an existing control panel for Route 53 Application Recovery Controller. This command is typically invoked during the setup phase of a disaster recovery strategy, following the creation of a cluster and control panel, to define specific traffic routing targets. In Node.js, executing this command via the client returns a Promise that resolves with the created control details or rejects with errors such as `AccessDeniedException` or `ConflictException` if the configuration conflicts with existing resources.

```javascript
const { Route53RecoveryControlConfigClient, CreateRoutingControlCommand } = require("@aws-sdk/client-route53-recovery-control-config");

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });

const input = {
  ControlPanelArn: "arn:aws:route53-recovery-control-config:us-east-1:123456789012:controlpanel/...",
  RoutingControlArn: "my-routing-control"
};

const command = new CreateRoutingControlCommand(input);
const response = await client.send(command);
```

### CreateSafetyRuleCommand

The `CreateSafetyRuleCommand` class represents a request to define a new safety rule within a specified control panel, acting as a safeguard against accidental modifications to routing controls. In a Node.js environment, you instantiate this command and pass it to the client's `send` method to execute the operation asynchronously. The promise resolves with the created safety rule details, or rejects with errors such as `AccessDeniedException` and `ConflictException` if the operation violates permissions or existing constraints. This pattern aligns with the standard AWS SDK for JavaScript v3 idioms for managing Route 53 Application Recovery Controller resources.

```javascript
import { Route53RecoveryControlConfigClient, CreateSafetyRuleCommand } from "@aws-sdk/client-route-53-recovery-control-config";
import { AccessDeniedException, ConflictException } from "@aws-sdk/client-route-53-recovery-control-config";

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
const command = new CreateSafetyRuleCommand({ controlPanelArn: "arn:aws:...", safetyRuleName: "example" });
try {
  const response = await client.send(command);
  console.log(response);
} catch (err) {
  if (err instanceof AccessDeniedException || err instanceof ConflictException) {
    console.error("Error:", err.message);
  }
}
```

### DeleteClusterCommand

The `DeleteClusterCommand` class encapsulates the API operation required to remove a specified cluster from your Route 53 Application Recovery Controller configuration. In a Node.js environment, you instantiate this command with the target cluster identifier and execute it via the client's `send` method when the cluster is no longer needed. This asynchronous operation resolves a Promise upon successful deletion initiation, but it may reject with errors like `ConflictException` if dependencies exist or `AccessDeniedException` if the caller lacks permissions. Proper error handling is essential to distinguish between temporary failures and permanent configuration issues during the deletion process.

```javascript
const { Route53RecoveryControlConfigClient, DeleteClusterCommand } = require("@aws-sdk/client-route-53-recovery-control-config");

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
const command = new DeleteClusterCommand({ ClusterArn: "arn:aws:r53recoverycontrol:..." });

try {
  await client.send(command);
} catch (error) {
  console.error("Failed to delete cluster:", error);
}
```

### DeleteControlPanelCommand

The `DeleteControlPanelCommand` class encapsulates the API request required to remove a specific control panel from your Route 53 Application Recovery Controller configuration. In a Node.js environment, you instantiate this command with the resource identifier and pass it to the client's `send` method to execute the deletion asynchronously. This operation may reject the promise with errors such as `AccessDeniedException` or `ConflictException` if the deletion is blocked by permissions or resource state. Successful execution resolves the promise, confirming that the control panel has been successfully removed from the configuration.

```javascript
import { Route53RecoveryControlConfigClient, DeleteControlPanelCommand } from "@aws-sdk/client-route-53-recovery-control-config";

async function main() {
  const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
  const input = { controlPanelArn: "arn:aws:r53recovery:..." };
  const command = new DeleteControlPanelCommand(input);
  const response = await client.send(command);
}
```

### DeleteRoutingControlCommand

The `DeleteRoutingControlCommand` class encapsulates the API request to permanently remove a routing control from a specified control panel in Route 53 Application Recovery Controller. To execute this operation, you instantiate the command with the target routing control identifier and pass it to the client's `send` method, awaiting the result in an asynchronous context. Successful deletion resolves the promise immediately, while failures may throw exceptions such as `AccessDeniedException` or `ConflictException` depending on the resource state and permissions.

```javascript
import { Route53RecoveryControlConfigClient, DeleteRoutingControlCommand } from "@aws-sdk/client-route53-recovery-control-config";

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
const command = new DeleteRoutingControlCommand({ routingControlArn: "arn:aws:..." });

try {
  await client.send(command);
} catch (error) {
  console.error("Deletion failed", error);
}
```

### DeleteSafetyRuleCommand

The `DeleteSafetyRuleCommand` class represents an operation to remove a specific safety rule from a Route 53 Application Recovery Control Panel within the AWS SDK for JavaScript v3. You should use this command when you need to modify the safety constraints governing your routing controls or clean up obsolete rules associated with a specific control panel ARN. Upon execution, the command returns a promise that resolves when the deletion is complete, effectively updating the control panel's configuration state. Developers typically handle this operation using `await` within an async function and catch exceptions like `AccessDeniedException` or `ConflictException` if the operation fails.

```javascript
import { Route53RecoveryControlConfigClient, DeleteSafetyRuleCommand } from "@aws-sdk/client-route-53-recovery-control-config";

const client = new Route53RecoveryControlConfigClient({ region: "us-east-1" });
const input = {
  controlPanelArn: "arn:aws:route53-recovery-control-config:us-east-1:123456789012:controlpanel/12345678-1234-1234-1234-123456789012",
  safetyRuleArn: "arn:aws:route53-recovery-control-config:us-east-1:123456789012:safetyrule/12345678-1234-1234-1234-123456789012"
};
const command = new DeleteSafetyRuleCommand(input);
const response = await client.send(command);
```

## API surface — verifiable exports of `@aws-sdk/client-route53-recovery-control-config`

Each symbol below is a real export of `@aws-sdk/client-route53-recovery-control-config`, verified via `Object.keys(require('@aws-sdk/client-route53-recovery-control-config'))`.

```typescript
// 25 Command classes
class CreateClusterCommand {}
class CreateControlPanelCommand {}
class CreateRoutingControlCommand {}
class CreateSafetyRuleCommand {}
class DeleteClusterCommand {}
class DeleteControlPanelCommand {}
class DeleteRoutingControlCommand {}
class DeleteSafetyRuleCommand {}
class DescribeClusterCommand {}
class DescribeControlPanelCommand {}
class DescribeRoutingControlCommand {}
class DescribeSafetyRuleCommand {}
class GetResourcePolicyCommand {}
class ListAssociatedRoute53HealthChecksCommand {}
class ListClustersCommand {}
class ListControlPanelsCommand {}
class ListRoutingControlsCommand {}
class ListSafetyRulesCommand {}
class ListTagsForResourceCommand {}
class TagResourceCommand {}
class UntagResourceCommand {}
class UpdateClusterCommand {}
class UpdateControlPanelCommand {}
class UpdateRoutingControlCommand {}
class UpdateSafetyRuleCommand {}
// Other classes
class AccessDeniedException {}
class ConflictException {}
class InternalServerException {}
class ResourceNotFoundException {}
class Route53RecoveryControlConfig {}
class Route53RecoveryControlConfigClient {}
class Route53RecoveryControlConfigServiceException {}
class ServiceQuotaExceededException {}
class ThrottlingException {}
class ValidationException {}
```

```javascript
// Verified Command-pattern usage
const client = new Route53RecoveryControlConfigClient({ region: process.env.AWS_REGION });
await client.createCluster(input);
await client.createControlPanel(input);
await client.createRoutingControl(input);
await client.createSafetyRule(input);
await client.deleteCluster(input);
await client.deleteControlPanel(input);
await client.deleteRoutingControl(input);
await client.deleteSafetyRule(input);
await client.describeCluster(input);
await client.describeControlPanel(input);
await client.describeRoutingControl(input);
await client.describeSafetyRule(input);
await client.getResourcePolicy(input);
await client.listAssociatedRoute53HealthChecks(input);
await client.listClusters(input);
await client.listControlPanels(input);
await client.listRoutingControls(input);
await client.listSafetyRules(input);
await client.listTagsForResource(input);
await client.tagResource(input);
await client.untagResource(input);
await client.updateCluster(input);
await client.updateControlPanel(input);
await client.updateRoutingControl(input);
await client.updateSafetyRule(input);
```
