---
name: ec2
description: "AWS SDK for JavaScript v3 EC2 client for managing instances and related compute resources."
metadata:
  languages: "javascript"
  versions: "3.1006.0"
  revision: 1
  updated-on: "2026-03-11"
  source: maintainer
  tags: "aws,ec2,javascript,nodejs,browser,compute,instances,send,console,log,aws-sdk,node,EC2Client,AcceptAddressTransferCommand,AcceptCapacityReservationBillingOwnershipCommand,AcceptReservedInstancesExchangeQuoteCommand,AcceptTransitGatewayClientVpnAttachmentCommand,AcceptTransitGatewayMulticastDomainAssociationsCommand,AcceptTransitGatewayPeeringAttachmentCommand,AcceptTransitGatewayVpcAttachmentCommand,AcceptVpcEndpointConnectionsCommand,AcceptVpcPeeringConnectionCommand,AdvertiseByoipCidrCommand,AllocateAddressCommand,AllocateHostsCommand,AllocateIpamPoolCidrCommand,ApplySecurityGroupsToClientVpnTargetNetworkCommand,AssignIpv6AddressesCommand,AssignPrivateIpAddressesCommand,AssignPrivateNatGatewayAddressCommand,AssociateAddressCommand,AssociateCapacityReservationBillingOwnerCommand,AssociateClientVpnTargetNetworkCommand,AssociateDhcpOptionsCommand,AssociateEnclaveCertificateIamRoleCommand,AssociateIamInstanceProfileCommand,AssociateInstanceEventWindowCommand,AssociateIpamByoasnCommand,AssociateIpamResourceDiscoveryCommand,AssociateNatGatewayAddressCommand,AssociateRouteServerCommand,AssociateRouteTableCommand,AssociateSecurityGroupVpcCommand"
---

# `@aws-sdk/client-ec2`

Use this package for the low-level Amazon EC2 API in AWS SDK for JavaScript v3. Prefer `EC2Client` plus explicit command imports for instance lifecycle, inventory, tagging, networking, and other EC2 control-plane operations.

## Install

```bash
npm install @aws-sdk/client-ec2
```

Common companion package:

```bash
npm install @aws-sdk/credential-providers
```

## Initialize the client

```javascript
import { EC2Client } from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });
```

In Node.js, the default credential provider chain is usually enough if your AWS access is already configured.

## Credentials and Region

- Node.js: credentials often come from environment variables, shared AWS config files, ECS, EC2 instance metadata, or IAM Identity Center.
- Browser runtimes: use explicit browser-safe credentials such as Cognito. Direct EC2 access from the browser is uncommon and needs intentional IAM and CORS design.
- Region is required somewhere: set it in code, via `AWS_REGION`, or through shared AWS config.

Typical local setup:

```bash
export AWS_REGION=us-east-1
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
```

## Core Usage Pattern

`DescribeInstances` is a common read path, but remember that instances are nested under reservations.

```javascript
import {
  DescribeInstancesCommand,
  EC2Client,
} from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

const response = await ec2.send(
  new DescribeInstancesCommand({
    Filters: [
      {
        Name: "instance-state-name",
        Values: ["running"],
      },
    ],
  }),
);

const instances = (response.Reservations ?? []).flatMap(
  (reservation) => reservation.Instances ?? [],
);

for (const instance of instances) {
  console.log(instance.InstanceId, instance.State?.Name);
}
```

Prefer `EC2Client` plus explicit commands for most code. The package also exports an aggregated `EC2` client, but command-based imports keep dependencies and bundle size more predictable.

## Common Operations

### Launch an instance

```javascript
import { EC2Client, RunInstancesCommand } from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

const response = await ec2.send(
  new RunInstancesCommand({
    ImageId: "ami-0123456789abcdef0",
    InstanceType: "t3.micro",
    MinCount: 1,
    MaxCount: 1,
    SubnetId: "subnet-0123456789abcdef0",
    SecurityGroupIds: ["sg-0123456789abcdef0"],
    ClientToken: "launch-web-1",
    TagSpecifications: [
      {
        ResourceType: "instance",
        Tags: [
          {
            Key: "Name",
            Value: "web-1",
          },
        ],
      },
    ],
  }),
);

console.log(response.Instances?.[0]?.InstanceId);
```

### Stop an instance

```javascript
import { EC2Client, StopInstancesCommand } from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

await ec2.send(
  new StopInstancesCommand({
    InstanceIds: ["i-0123456789abcdef0"],
  }),
);
```

### List instances with pagination

```javascript
import {
  EC2Client,
  paginateDescribeInstances,
} from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

const paginator = paginateDescribeInstances(
  { client: ec2 },
  {
    Filters: [
      {
        Name: "tag:Environment",
        Values: ["prod"],
      },
    ],
  },
);

for await (const page of paginator) {
  for (const reservation of page.Reservations ?? []) {
    for (const instance of reservation.Instances ?? []) {
      console.log(instance.InstanceId);
    }
  }
}
```

## EC2-Specific Gotchas

- `DescribeInstances` and similar APIs return `Reservations`, then `Instances`; do not expect a flat top-level array.
- Many mutating calls are asynchronous. After `RunInstances`, `StartInstances`, `StopInstances`, or `TerminateInstances`, wait for the state you need before assuming follow-up calls will succeed.
- `RunInstances` requires both `MinCount` and `MaxCount`, even when launching exactly one instance.
- Use `ClientToken` on launch flows so retries do not create duplicate instances.
- `DryRun: true` does not return a normal success response; EC2 commonly signals permission checks through `DryRunOperation` or `UnauthorizedOperation` errors.
- For repeated launch configuration, prefer launch templates instead of duplicating large `RunInstances` payloads.

## When To Reach For Other Packages

- `@aws-sdk/credential-providers`: Cognito, STS assume-role flows, shared config helpers, and browser-safe credential setup.
- `@aws-sdk/client-auto-scaling`: manage Auto Scaling groups instead of hand-rolling group behavior around individual instance launches.
- `@aws-sdk/client-ssm`: fetch AMI IDs or configuration values from Parameter Store, or work with EC2 instances through Systems Manager workflows.

## Common EC2 Operations And Waiters

### Wait for a launched instance to be running

EC2 launches are asynchronous. If later steps need the instance to exist in a running state, wait explicitly.

```javascript
import {
  EC2Client,
  RunInstancesCommand,
  waitUntilInstanceRunning,
} from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

const launch = await ec2.send(
  new RunInstancesCommand({
    ImageId: "ami-0123456789abcdef0",
    InstanceType: "t3.micro",
    MinCount: 1,
    MaxCount: 1,
  }),
);

const instanceId = launch.Instances?.[0]?.InstanceId;

if (!instanceId) {
  throw new Error("RunInstances did not return an instance ID");
}

await waitUntilInstanceRunning(
  { client: ec2, maxWaitTime: 300 },
  { InstanceIds: [instanceId] },
);
```

### Terminate an instance

```javascript
import {
  EC2Client,
  TerminateInstancesCommand,
} from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

await ec2.send(
  new TerminateInstancesCommand({
    InstanceIds: ["i-0123456789abcdef0"],
  }),
);
```

### Add or update tags

Use `CreateTagsCommand` for instances, volumes, snapshots, ENIs, and other EC2 resources that support tags.

```javascript
import {
  CreateTagsCommand,
  EC2Client,
} from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

await ec2.send(
  new CreateTagsCommand({
    Resources: ["i-0123456789abcdef0"],
    Tags: [
      {
        Key: "Environment",
        Value: "prod",
      },
      {
        Key: "Owner",
        Value: "platform",
      },
    ],
  }),
);
```

### Use `DryRun` to check permissions

Many EC2 APIs support `DryRun`. Treat `DryRunOperation` as proof that the caller is authorized for the action.

```javascript
import { EC2Client, StopInstancesCommand } from "@aws-sdk/client-ec2";

const ec2 = new EC2Client({ region: "us-east-1" });

try {
  await ec2.send(
    new StopInstancesCommand({
      InstanceIds: ["i-0123456789abcdef0"],
      DryRun: true,
    }),
  );
} catch (error) {
  if (error.name === "DryRunOperation") {
    console.log("The caller is allowed to stop this instance.");
  } else if (error.name === "UnauthorizedOperation") {
    console.log("The caller is not allowed to stop this instance.");
  } else {
    throw error;
  }
}
```

### Notes

- Waiters poll describe-style APIs and are a better default than hand-written sleep loops.
- EC2 has eventual consistency across instance, volume, ENI, and tagging state; read-after-write flows should expect short propagation windows.
- Launch templates are usually the right abstraction once `RunInstances` inputs become repetitive or environment-specific.

## API surface — full Command/Input/Output set

`@aws-sdk/client-ec2` exports `EC2Client` plus 763 `*Command` classes, 168 paginators. Sample below covers the first 50 commands; all command classes follow `XxxCommand`/`XxxCommandInput`/`XxxCommandOutput` shape.

```typescript
// Client + Command/Input/Output types from @aws-sdk/client-ec2
class EC2Client {}
class AcceptAddressTransferCommand {}
class AcceptAddressTransferInput {}
class AcceptAddressTransferOutput {}
class AcceptCapacityReservationBillingOwnershipCommand {}
class AcceptCapacityReservationBillingOwnershipInput {}
class AcceptCapacityReservationBillingOwnershipOutput {}
class AcceptReservedInstancesExchangeQuoteCommand {}
class AcceptReservedInstancesExchangeQuoteInput {}
class AcceptReservedInstancesExchangeQuoteOutput {}
class AcceptTransitGatewayClientVpnAttachmentCommand {}
class AcceptTransitGatewayClientVpnAttachmentInput {}
class AcceptTransitGatewayClientVpnAttachmentOutput {}
class AcceptTransitGatewayMulticastDomainAssociationsCommand {}
class AcceptTransitGatewayMulticastDomainAssociationsInput {}
class AcceptTransitGatewayMulticastDomainAssociationsOutput {}
class AcceptTransitGatewayPeeringAttachmentCommand {}
class AcceptTransitGatewayPeeringAttachmentInput {}
class AcceptTransitGatewayPeeringAttachmentOutput {}
class AcceptTransitGatewayVpcAttachmentCommand {}
class AcceptTransitGatewayVpcAttachmentInput {}
class AcceptTransitGatewayVpcAttachmentOutput {}
class AcceptVpcEndpointConnectionsCommand {}
class AcceptVpcEndpointConnectionsInput {}
class AcceptVpcEndpointConnectionsOutput {}
class AcceptVpcPeeringConnectionCommand {}
class AcceptVpcPeeringConnectionInput {}
class AcceptVpcPeeringConnectionOutput {}
class AdvertiseByoipCidrCommand {}
class AdvertiseByoipCidrInput {}
class AdvertiseByoipCidrOutput {}
class AllocateAddressCommand {}
class AllocateAddressInput {}
class AllocateAddressOutput {}
class AllocateHostsCommand {}
class AllocateHostsInput {}
class AllocateHostsOutput {}
class AllocateIpamPoolCidrCommand {}
class AllocateIpamPoolCidrInput {}
class AllocateIpamPoolCidrOutput {}
class ApplySecurityGroupsToClientVpnTargetNetworkCommand {}
class ApplySecurityGroupsToClientVpnTargetNetworkInput {}
class ApplySecurityGroupsToClientVpnTargetNetworkOutput {}
class AssignIpv6AddressesCommand {}
class AssignIpv6AddressesInput {}
class AssignIpv6AddressesOutput {}
class AssignPrivateIpAddressesCommand {}
class AssignPrivateIpAddressesInput {}
class AssignPrivateIpAddressesOutput {}
class AssignPrivateNatGatewayAddressCommand {}
class AssignPrivateNatGatewayAddressInput {}
class AssignPrivateNatGatewayAddressOutput {}
class AssociateAddressCommand {}
class AssociateAddressInput {}
class AssociateAddressOutput {}
class AssociateCapacityReservationBillingOwnerCommand {}
class AssociateCapacityReservationBillingOwnerInput {}
class AssociateCapacityReservationBillingOwnerOutput {}
class AssociateClientVpnTargetNetworkCommand {}
class AssociateClientVpnTargetNetworkInput {}
class AssociateClientVpnTargetNetworkOutput {}
class AssociateDhcpOptionsCommand {}
class AssociateDhcpOptionsInput {}
class AssociateDhcpOptionsOutput {}
class AssociateEnclaveCertificateIamRoleCommand {}
class AssociateEnclaveCertificateIamRoleInput {}
class AssociateEnclaveCertificateIamRoleOutput {}
class AssociateIamInstanceProfileCommand {}
class AssociateIamInstanceProfileInput {}
class AssociateIamInstanceProfileOutput {}
class AssociateInstanceEventWindowCommand {}
class AssociateInstanceEventWindowInput {}
class AssociateInstanceEventWindowOutput {}
class AssociateIpamByoasnCommand {}
class AssociateIpamByoasnInput {}
class AssociateIpamByoasnOutput {}
class AssociateIpamResourceDiscoveryCommand {}
class AssociateIpamResourceDiscoveryInput {}
class AssociateIpamResourceDiscoveryOutput {}
class AssociateNatGatewayAddressCommand {}
class AssociateNatGatewayAddressInput {}
class AssociateNatGatewayAddressOutput {}
class AssociateRouteServerCommand {}
class AssociateRouteServerInput {}
class AssociateRouteServerOutput {}
class AssociateRouteTableCommand {}
class AssociateRouteTableInput {}
class AssociateRouteTableOutput {}
class AssociateSecurityGroupVpcCommand {}
class AssociateSecurityGroupVpcInput {}
class AssociateSecurityGroupVpcOutput {}
class AssociateSubnetCidrBlockCommand {}
class AssociateSubnetCidrBlockInput {}
class AssociateSubnetCidrBlockOutput {}
class AssociateTransitGatewayMulticastDomainCommand {}
class AssociateTransitGatewayMulticastDomainInput {}
class AssociateTransitGatewayMulticastDomainOutput {}
class AssociateTransitGatewayPolicyTableCommand {}
class AssociateTransitGatewayPolicyTableInput {}
class AssociateTransitGatewayPolicyTableOutput {}
class AssociateTransitGatewayRouteTableCommand {}
class AssociateTransitGatewayRouteTableInput {}
class AssociateTransitGatewayRouteTableOutput {}
class AssociateTrunkInterfaceCommand {}
class AssociateTrunkInterfaceInput {}
class AssociateTrunkInterfaceOutput {}
class AssociateVpcCidrBlockCommand {}
class AssociateVpcCidrBlockInput {}
class AssociateVpcCidrBlockOutput {}
class AttachClassicLinkVpcCommand {}
class AttachClassicLinkVpcInput {}
class AttachClassicLinkVpcOutput {}
class AttachInternetGatewayCommand {}
class AttachInternetGatewayInput {}
class AttachInternetGatewayOutput {}
class AttachNetworkInterfaceCommand {}
class AttachNetworkInterfaceInput {}
class AttachNetworkInterfaceOutput {}
class AttachVerifiedAccessTrustProviderCommand {}
class AttachVerifiedAccessTrustProviderInput {}
class AttachVerifiedAccessTrustProviderOutput {}
class AttachVolumeCommand {}
class AttachVolumeInput {}
class AttachVolumeOutput {}
class AttachVpnGatewayCommand {}
class AttachVpnGatewayInput {}
class AttachVpnGatewayOutput {}
class AuthorizeClientVpnIngressCommand {}
class AuthorizeClientVpnIngressInput {}
class AuthorizeClientVpnIngressOutput {}
class AuthorizeSecurityGroupEgressCommand {}
class AuthorizeSecurityGroupEgressInput {}
class AuthorizeSecurityGroupEgressOutput {}
class AuthorizeSecurityGroupIngressCommand {}
class AuthorizeSecurityGroupIngressInput {}
class AuthorizeSecurityGroupIngressOutput {}
class BundleInstanceCommand {}
class BundleInstanceInput {}
class BundleInstanceOutput {}
class CancelBundleTaskCommand {}
class CancelBundleTaskInput {}
class CancelBundleTaskOutput {}
class CancelCapacityReservationCommand {}
class CancelCapacityReservationInput {}
class CancelCapacityReservationOutput {}
class CancelCapacityReservationFleetsCommand {}
class CancelCapacityReservationFleetsInput {}
class CancelCapacityReservationFleetsOutput {}
class CancelConversionTaskCommand {}
class CancelConversionTaskInput {}
class CancelConversionTaskOutput {}
```

```javascript
// Issue every operation:
const client = new EC2Client({ region: process.env.AWS_REGION });
await client.acceptAddressTransfer(input);
await client.acceptCapacityReservationBillingOwnership(input);
await client.acceptReservedInstancesExchangeQuote(input);
await client.acceptTransitGatewayClientVpnAttachment(input);
await client.acceptTransitGatewayMulticastDomainAssociations(input);
await client.acceptTransitGatewayPeeringAttachment(input);
await client.acceptTransitGatewayVpcAttachment(input);
await client.acceptVpcEndpointConnections(input);
await client.acceptVpcPeeringConnection(input);
await client.advertiseByoipCidr(input);
await client.allocateAddress(input);
await client.allocateHosts(input);
await client.allocateIpamPoolCidr(input);
await client.applySecurityGroupsToClientVpnTargetNetwork(input);
await client.assignIpv6Addresses(input);
await client.assignPrivateIpAddresses(input);
await client.assignPrivateNatGatewayAddress(input);
await client.associateAddress(input);
await client.associateCapacityReservationBillingOwner(input);
await client.associateClientVpnTargetNetwork(input);
await client.associateDhcpOptions(input);
await client.associateEnclaveCertificateIamRole(input);
await client.associateIamInstanceProfile(input);
await client.associateInstanceEventWindow(input);
await client.associateIpamByoasn(input);
await client.associateIpamResourceDiscovery(input);
await client.associateNatGatewayAddress(input);
await client.associateRouteServer(input);
await client.associateRouteTable(input);
await client.associateSecurityGroupVpc(input);
await client.associateSubnetCidrBlock(input);
await client.associateTransitGatewayMulticastDomain(input);
await client.associateTransitGatewayPolicyTable(input);
await client.associateTransitGatewayRouteTable(input);
await client.associateTrunkInterface(input);
await client.associateVpcCidrBlock(input);
await client.attachClassicLinkVpc(input);
await client.attachInternetGateway(input);
await client.attachNetworkInterface(input);
await client.attachVerifiedAccessTrustProvider(input);
await client.attachVolume(input);
await client.attachVpnGateway(input);
await client.authorizeClientVpnIngress(input);
await client.authorizeSecurityGroupEgress(input);
await client.authorizeSecurityGroupIngress(input);
await client.bundleInstance(input);
await client.cancelBundleTask(input);
await client.cancelCapacityReservation(input);
await client.cancelCapacityReservationFleets(input);
await client.cancelConversionTask(input);

// Paginators (auto-iterate over multi-page responses):
for await (const page of client.paginateDescribeAddressTransfers({})) {}
for await (const page of client.paginateDescribeAddressesAttribute({})) {}
for await (const page of client.paginateDescribeAwsNetworkPerformanceMetricSubscriptions({})) {}
for await (const page of client.paginateDescribeByoipCidrs({})) {}
for await (const page of client.paginateDescribeCapacityBlockExtensionHistory({})) {}
for await (const page of client.paginateDescribeCapacityBlockExtensionOfferings({})) {}
for await (const page of client.paginateDescribeCapacityBlockOfferings({})) {}
for await (const page of client.paginateDescribeCapacityBlockStatus({})) {}
for await (const page of client.paginateDescribeCapacityBlocks({})) {}
for await (const page of client.paginateDescribeCapacityManagerDataExports({})) {}
for await (const page of client.paginateDescribeCapacityReservationBillingRequests({})) {}
for await (const page of client.paginateDescribeCapacityReservationFleets({})) {}
for await (const page of client.paginateDescribeCapacityReservations({})) {}
for await (const page of client.paginateDescribeCarrierGateways({})) {}
for await (const page of client.paginateDescribeClassicLinkInstances({})) {}
for await (const page of client.paginateDescribeClientVpnAuthorizationRules({})) {}
for await (const page of client.paginateDescribeClientVpnConnections({})) {}
for await (const page of client.paginateDescribeClientVpnEndpoints({})) {}
for await (const page of client.paginateDescribeClientVpnRoutes({})) {}
for await (const page of client.paginateDescribeClientVpnTargetNetworks({})) {}
```
