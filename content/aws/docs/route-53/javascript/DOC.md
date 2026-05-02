---
name: route-53
description: "AWS SDK for JavaScript v3 Route 53 client for hosted zones, record sets, and DNS change workflows."
metadata:
  languages: "javascript"
  versions: "3.1006.0"
  revision: 1
  updated-on: "2026-03-11"
  source: maintainer
  tags: "aws,route53,dns,javascript,nodejs,browser,hosted-zones,console,log,send,route-53,aws-sdk,node,Route53Client,ActivateKeySigningKeyCommand,AssociateVPCWithHostedZoneCommand,ChangeCidrCollectionCommand,ChangeResourceRecordSetsCommand,ChangeTagsForResourceCommand,CreateCidrCollectionCommand,CreateHealthCheckCommand,CreateHostedZoneCommand,CreateKeySigningKeyCommand,CreateQueryLoggingConfigCommand,CreateReusableDelegationSetCommand,CreateTrafficPolicyCommand,CreateTrafficPolicyInstanceCommand,CreateTrafficPolicyVersionCommand,CreateVPCAssociationAuthorizationCommand,DeactivateKeySigningKeyCommand,DeleteCidrCollectionCommand,DeleteHealthCheckCommand,DeleteHostedZoneCommand,DeleteKeySigningKeyCommand,DeleteQueryLoggingConfigCommand,DeleteReusableDelegationSetCommand,DeleteTrafficPolicyCommand,DeleteTrafficPolicyInstanceCommand,DeleteVPCAssociationAuthorizationCommand,DisableHostedZoneDNSSECCommand,DisassociateVPCFromHostedZoneCommand,EnableHostedZoneDNSSECCommand,GetAccountLimitCommand,GetChangeCommand"
---

# `@aws-sdk/client-route-53`

Use this package for Amazon Route 53 control-plane APIs in AWS SDK for JavaScript v3. Typical tasks include listing hosted zones, reading record sets, submitting DNS changes, and checking change status.

Prefer `Route53Client` plus explicit command imports. The package also exposes an aggregated `Route53` client, but command-based imports are the safer default for smaller bundles and clearer dependencies.

## Install

```bash
npm install @aws-sdk/client-route-53
```

## Initialize the client

```javascript
import { Route53Client } from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });
```

Route 53 is a global service, but it is still a good idea to keep the client region explicit in code and config. `us-east-1` is the common choice in JavaScript examples.

## Credentials and Region

- Node.js: the default credential provider chain is usually enough if credentials are already configured through environment variables, shared AWS config, IAM roles, or IAM Identity Center.
- Browser runtimes: use an explicit browser-safe credential provider such as Cognito; do not ship long-lived AWS keys to the browser.
- Keep the region explicit somewhere even though Route 53 is global, so signing behavior is predictable.

Typical local setup:

```bash
export AWS_REGION=us-east-1
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
```

## Core Usage Pattern

The v3 SDK uses client-plus-command calls:

```javascript
import {
  ListHostedZonesCommand,
  Route53Client,
} from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });

const response = await route53.send(new ListHostedZonesCommand({}));

for (const zone of response.HostedZones ?? []) {
  console.log(zone.Name, zone.Id);
}
```

## Common Workflow

For most DNS automation, the flow is:

1. Resolve the hosted zone you want to manage.
2. Read or construct the target `ResourceRecordSet`.
3. Submit a `ChangeResourceRecordSetsCommand` batch.
4. Poll the returned change ID with `GetChangeCommand` until the status is `INSYNC` if later steps depend on propagation.

## Route 53-Specific Gotchas

- Route 53 record names and hosted zone names are fully qualified domain names. Keeping the trailing dot in code avoids ambiguity.
- DNS changes are asynchronous. A successful change request means Route 53 accepted it, not that every nameserver is already serving the new answer.
- Alias records use `AliasTarget`; they do not use the usual `TTL` plus `ResourceRecords` combination.
- Batch changes are the unit of mutation. Group related creates, deletes, and upserts into one `ChangeBatch` when they should succeed together.
- Prefer paginators when scanning many hosted zones or record sets.
- Do not deep-import SDK internals from build directories.

## When To Reach For Other Packages

- `@aws-sdk/credential-providers`: Cognito, STS assume-role flows, shared config helpers, and other credential helpers.
- `@aws-sdk/client-route-53-domains`: domain registration and transfer APIs that are separate from hosted-zone DNS management.

## Common Route 53 Operations

### List hosted zones with a paginator

Use the paginator form when you want a consistent async iteration pattern.

```javascript
import {
  paginateListHostedZones,
  Route53Client,
} from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });

for await (const page of paginateListHostedZones({ client: route53 }, {})) {
  for (const zone of page.HostedZones ?? []) {
    console.log(zone.Name, zone.Id);
  }
}
```

### Read the record sets in a hosted zone

```javascript
import {
  ListResourceRecordSetsCommand,
  Route53Client,
} from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });

const response = await route53.send(
  new ListResourceRecordSetsCommand({
    HostedZoneId: "Z0123456789ABCDEFG",
  }),
);

for (const record of response.ResourceRecordSets ?? []) {
  console.log(record.Name, record.Type, record.TTL);
}
```

If you need to walk large zones, continue from the returned pagination markers or use the service paginator when available in your SDK version.

### Upsert a standard A record

```javascript
import {
  ChangeResourceRecordSetsCommand,
  Route53Client,
} from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });

const response = await route53.send(
  new ChangeResourceRecordSetsCommand({
    HostedZoneId: "Z0123456789ABCDEFG",
    ChangeBatch: {
      Comment: "Update app endpoint",
      Changes: [
        {
          Action: "UPSERT",
          ResourceRecordSet: {
            Name: "app.example.com.",
            Type: "A",
            TTL: 60,
            ResourceRecords: [{ Value: "203.0.113.10" }],
          },
        },
      ],
    },
  }),
);

console.log(response.ChangeInfo?.Id, response.ChangeInfo?.Status);
```

### Create or update an alias record

Alias records point at AWS resources such as load balancers and CloudFront distributions.

```javascript
import {
  ChangeResourceRecordSetsCommand,
  Route53Client,
} from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });

await route53.send(
  new ChangeResourceRecordSetsCommand({
    HostedZoneId: "Z0123456789ABCDEFG",
    ChangeBatch: {
      Changes: [
        {
          Action: "UPSERT",
          ResourceRecordSet: {
            Name: "www.example.com.",
            Type: "A",
            AliasTarget: {
              DNSName: "dualstack.my-load-balancer-123.us-east-1.elb.amazonaws.com.",
              HostedZoneId: "Z35SXDOTRQ7X7K",
              EvaluateTargetHealth: false,
            },
          },
        },
      ],
    },
  }),
);
```

When you use `AliasTarget`, omit `TTL` and `ResourceRecords`.

### Wait for a submitted change to become `INSYNC`

Route 53 applies changes asynchronously, so poll the returned change ID when a later deployment step depends on the new record being active.

```javascript
import {
  GetChangeCommand,
  Route53Client,
} from "@aws-sdk/client-route-53";

const route53 = new Route53Client({ region: "us-east-1" });
const changeId = "C2682N5HXP0BZ4";

let status = "PENDING";

while (status === "PENDING") {
  const response = await route53.send(
    new GetChangeCommand({ Id: changeId }),
  );

  status = response.ChangeInfo?.Status ?? "PENDING";

  if (status === "PENDING") {
    await new Promise((resolve) => setTimeout(resolve, 5000));
  }
}

console.log(status);
```

### Notes

- Use `UPSERT` for idempotent automation when you want create-or-replace behavior.
- Record-set names are easiest to reason about when you keep them fully qualified, including the trailing dot.
- If you need deterministic record browsing around a specific name and type, use the list operation's start-name and start-type fields instead of scanning from the beginning every time.

## API surface — full Command/Input/Output set

`@aws-sdk/client-route-53` exports `Route53Client` plus 71 `*Command` classes, 6 paginators. Sample below covers the first 50 commands; all command classes follow `XxxCommand`/`XxxCommandInput`/`XxxCommandOutput` shape.

```typescript
// Client + Command/Input/Output types from @aws-sdk/client-route-53
class Route53Client {}
class ActivateKeySigningKeyCommand {}
class ActivateKeySigningKeyInput {}
class ActivateKeySigningKeyOutput {}
class AssociateVPCWithHostedZoneCommand {}
class AssociateVPCWithHostedZoneInput {}
class AssociateVPCWithHostedZoneOutput {}
class ChangeCidrCollectionCommand {}
class ChangeCidrCollectionInput {}
class ChangeCidrCollectionOutput {}
class ChangeResourceRecordSetsCommand {}
class ChangeResourceRecordSetsInput {}
class ChangeResourceRecordSetsOutput {}
class ChangeTagsForResourceCommand {}
class ChangeTagsForResourceInput {}
class ChangeTagsForResourceOutput {}
class CreateCidrCollectionCommand {}
class CreateCidrCollectionInput {}
class CreateCidrCollectionOutput {}
class CreateHealthCheckCommand {}
class CreateHealthCheckInput {}
class CreateHealthCheckOutput {}
class CreateHostedZoneCommand {}
class CreateHostedZoneInput {}
class CreateHostedZoneOutput {}
class CreateKeySigningKeyCommand {}
class CreateKeySigningKeyInput {}
class CreateKeySigningKeyOutput {}
class CreateQueryLoggingConfigCommand {}
class CreateQueryLoggingConfigInput {}
class CreateQueryLoggingConfigOutput {}
class CreateReusableDelegationSetCommand {}
class CreateReusableDelegationSetInput {}
class CreateReusableDelegationSetOutput {}
class CreateTrafficPolicyCommand {}
class CreateTrafficPolicyInput {}
class CreateTrafficPolicyOutput {}
class CreateTrafficPolicyInstanceCommand {}
class CreateTrafficPolicyInstanceInput {}
class CreateTrafficPolicyInstanceOutput {}
class CreateTrafficPolicyVersionCommand {}
class CreateTrafficPolicyVersionInput {}
class CreateTrafficPolicyVersionOutput {}
class CreateVPCAssociationAuthorizationCommand {}
class CreateVPCAssociationAuthorizationInput {}
class CreateVPCAssociationAuthorizationOutput {}
class DeactivateKeySigningKeyCommand {}
class DeactivateKeySigningKeyInput {}
class DeactivateKeySigningKeyOutput {}
class DeleteCidrCollectionCommand {}
class DeleteCidrCollectionInput {}
class DeleteCidrCollectionOutput {}
class DeleteHealthCheckCommand {}
class DeleteHealthCheckInput {}
class DeleteHealthCheckOutput {}
class DeleteHostedZoneCommand {}
class DeleteHostedZoneInput {}
class DeleteHostedZoneOutput {}
class DeleteKeySigningKeyCommand {}
class DeleteKeySigningKeyInput {}
class DeleteKeySigningKeyOutput {}
class DeleteQueryLoggingConfigCommand {}
class DeleteQueryLoggingConfigInput {}
class DeleteQueryLoggingConfigOutput {}
class DeleteReusableDelegationSetCommand {}
class DeleteReusableDelegationSetInput {}
class DeleteReusableDelegationSetOutput {}
class DeleteTrafficPolicyCommand {}
class DeleteTrafficPolicyInput {}
class DeleteTrafficPolicyOutput {}
class DeleteTrafficPolicyInstanceCommand {}
class DeleteTrafficPolicyInstanceInput {}
class DeleteTrafficPolicyInstanceOutput {}
class DeleteVPCAssociationAuthorizationCommand {}
class DeleteVPCAssociationAuthorizationInput {}
class DeleteVPCAssociationAuthorizationOutput {}
class DisableHostedZoneDNSSECCommand {}
class DisableHostedZoneDNSSECInput {}
class DisableHostedZoneDNSSECOutput {}
class DisassociateVPCFromHostedZoneCommand {}
class DisassociateVPCFromHostedZoneInput {}
class DisassociateVPCFromHostedZoneOutput {}
class EnableHostedZoneDNSSECCommand {}
class EnableHostedZoneDNSSECInput {}
class EnableHostedZoneDNSSECOutput {}
class GetAccountLimitCommand {}
class GetAccountLimitInput {}
class GetAccountLimitOutput {}
class GetChangeCommand {}
class GetChangeInput {}
class GetChangeOutput {}
class GetCheckerIpRangesCommand {}
class GetCheckerIpRangesInput {}
class GetCheckerIpRangesOutput {}
class GetDNSSECCommand {}
class GetDNSSECInput {}
class GetDNSSECOutput {}
class GetGeoLocationCommand {}
class GetGeoLocationInput {}
class GetGeoLocationOutput {}
class GetHealthCheckCommand {}
class GetHealthCheckInput {}
class GetHealthCheckOutput {}
class GetHealthCheckCountCommand {}
class GetHealthCheckCountInput {}
class GetHealthCheckCountOutput {}
class GetHealthCheckLastFailureReasonCommand {}
class GetHealthCheckLastFailureReasonInput {}
class GetHealthCheckLastFailureReasonOutput {}
class GetHealthCheckStatusCommand {}
class GetHealthCheckStatusInput {}
class GetHealthCheckStatusOutput {}
class GetHostedZoneCommand {}
class GetHostedZoneInput {}
class GetHostedZoneOutput {}
class GetHostedZoneCountCommand {}
class GetHostedZoneCountInput {}
class GetHostedZoneCountOutput {}
class GetHostedZoneLimitCommand {}
class GetHostedZoneLimitInput {}
class GetHostedZoneLimitOutput {}
class GetQueryLoggingConfigCommand {}
class GetQueryLoggingConfigInput {}
class GetQueryLoggingConfigOutput {}
class GetReusableDelegationSetCommand {}
class GetReusableDelegationSetInput {}
class GetReusableDelegationSetOutput {}
class GetReusableDelegationSetLimitCommand {}
class GetReusableDelegationSetLimitInput {}
class GetReusableDelegationSetLimitOutput {}
class GetTrafficPolicyCommand {}
class GetTrafficPolicyInput {}
class GetTrafficPolicyOutput {}
class GetTrafficPolicyInstanceCommand {}
class GetTrafficPolicyInstanceInput {}
class GetTrafficPolicyInstanceOutput {}
class GetTrafficPolicyInstanceCountCommand {}
class GetTrafficPolicyInstanceCountInput {}
class GetTrafficPolicyInstanceCountOutput {}
class ListCidrBlocksCommand {}
class ListCidrBlocksInput {}
class ListCidrBlocksOutput {}
class ListCidrCollectionsCommand {}
class ListCidrCollectionsInput {}
class ListCidrCollectionsOutput {}
class ListCidrLocationsCommand {}
class ListCidrLocationsInput {}
class ListCidrLocationsOutput {}
class ListGeoLocationsCommand {}
class ListGeoLocationsInput {}
class ListGeoLocationsOutput {}
```

```javascript
// Issue every operation:
const client = new Route53Client({ region: process.env.AWS_REGION });
await client.activateKeySigningKey(input);
await client.associateVPCWithHostedZone(input);
await client.changeCidrCollection(input);
await client.changeResourceRecordSets(input);
await client.changeTagsForResource(input);
await client.createCidrCollection(input);
await client.createHealthCheck(input);
await client.createHostedZone(input);
await client.createKeySigningKey(input);
await client.createQueryLoggingConfig(input);
await client.createReusableDelegationSet(input);
await client.createTrafficPolicy(input);
await client.createTrafficPolicyInstance(input);
await client.createTrafficPolicyVersion(input);
await client.createVPCAssociationAuthorization(input);
await client.deactivateKeySigningKey(input);
await client.deleteCidrCollection(input);
await client.deleteHealthCheck(input);
await client.deleteHostedZone(input);
await client.deleteKeySigningKey(input);
await client.deleteQueryLoggingConfig(input);
await client.deleteReusableDelegationSet(input);
await client.deleteTrafficPolicy(input);
await client.deleteTrafficPolicyInstance(input);
await client.deleteVPCAssociationAuthorization(input);
await client.disableHostedZoneDNSSEC(input);
await client.disassociateVPCFromHostedZone(input);
await client.enableHostedZoneDNSSEC(input);
await client.getAccountLimit(input);
await client.getChange(input);
await client.getCheckerIpRanges(input);
await client.getDNSSEC(input);
await client.getGeoLocation(input);
await client.getHealthCheck(input);
await client.getHealthCheckCount(input);
await client.getHealthCheckLastFailureReason(input);
await client.getHealthCheckStatus(input);
await client.getHostedZone(input);
await client.getHostedZoneCount(input);
await client.getHostedZoneLimit(input);
await client.getQueryLoggingConfig(input);
await client.getReusableDelegationSet(input);
await client.getReusableDelegationSetLimit(input);
await client.getTrafficPolicy(input);
await client.getTrafficPolicyInstance(input);
await client.getTrafficPolicyInstanceCount(input);
await client.listCidrBlocks(input);
await client.listCidrCollections(input);
await client.listCidrLocations(input);
await client.listGeoLocations(input);

// Paginators (auto-iterate over multi-page responses):
for await (const page of client.paginateListCidrBlocks({})) {}
for await (const page of client.paginateListCidrCollections({})) {}
for await (const page of client.paginateListCidrLocations({})) {}
for await (const page of client.paginateListHealthChecks({})) {}
for await (const page of client.paginateListHostedZones({})) {}
for await (const page of client.paginateListQueryLoggingConfigs({})) {}
```
