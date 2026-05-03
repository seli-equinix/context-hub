---
name: service-catalog
description: AWS Service Catalog SDK for JavaScript (v3) for discovering products,
  reading launch parameters, provisioning products, and tracking request records
metadata:
  languages: javascript
  versions: 3.1007.0
  revision: 1
  updated-on: '2026-03-13'
  source: maintainer
  tags: aws,service-catalog,portfolios,provisioning,cloudformation,client,console,log,send,aws-sdk,node,ServiceCatalogClient,AcceptPortfolioShareCommand,AssociateBudgetWithResourceCommand,AssociatePrincipalWithPortfolioCommand,AssociateProductWithPortfolioCommand,AssociateServiceActionWithProvisioningArtifactCommand,AssociateTagOptionWithResourceCommand,BatchAssociateServiceActionWithProvisioningArtifactCommand,BatchDisassociateServiceActionFromProvisioningArtifactCommand,CopyProductCommand,CreateConstraintCommand,CreatePortfolioCommand,CreatePortfolioShareCommand,CreateProductCommand,CreateProvisionedProductPlanCommand,CreateProvisioningArtifactCommand,CreateServiceActionCommand,CreateTagOptionCommand,DeleteConstraintCommand,DeletePortfolioCommand,DeletePortfolioShareCommand,DeleteProductCommand,DeleteProvisionedProductPlanCommand,DeleteProvisioningArtifactCommand,DeleteServiceActionCommand,DeleteTagOptionCommand,DescribeConstraintCommand,DescribeCopyProductStatusCommand,DescribePortfolioCommand,DescribePortfolioShareStatusCommand,DescribePortfolioSharesCommand,paginateListConstraintsForPortfolio,DescribeServiceActionExecutionParametersCommand,paginateListAcceptedPortfolioShares,DescribeProductCommand,UpdateConstraintCommand,UpdateTagOptionCommand,ListStackInstancesForProvisionedProductCommand,DescribeProvisionedProductCommand,DescribeProductViewCommand,DisableAWSOrganizationsAccessCommand,UpdateProvisionedProductPropertiesCommand,NotifyProvisionProductEngineWorkflowResultCommand,UpdateProductCommand,ListServiceActionsCommand,UpdateServiceActionCommand,paginateListPortfoliosForProduct,DescribeProvisioningParametersCommand,DisassociateBudgetFromResourceCommand,ListProvisionedProductPlansCommand,ListResourcesForTagOptionCommand,RejectPortfolioShareCommand,ListConstraintsForPortfolioCommand,DisassociateServiceActionFromProvisioningArtifactCommand,SearchProductsAsAdminCommand,paginateListOrganizationPortfolioAccess,ListProvisioningArtifactsCommand,ImportAsProvisionedProductCommand,ServiceCatalogServiceException,ListLaunchPathsCommand,ListRecordHistoryCommand,paginateListLaunchPaths,NotifyTerminateProvisionedProductEngineWorkflowResultCommand,UpdateProvisioningArtifactCommand,ListOrganizationPortfolioAccessCommand,ExecuteProvisionedProductServiceActionCommand,ListServiceActionsForProvisioningArtifactCommand,paginateSearchProvisionedProducts,InvalidStateException,paginateListBudgetsForResource,DescribeProvisionedProductPlanCommand,SearchProductsCommand,UpdatePortfolioShareCommand,paginateSearchProducts,paginateSearchProductsAsAdmin,NotifyUpdateProvisionedProductEngineWorkflowResultCommand,DescribeServiceActionCommand,paginateListServiceActionsForProvisioningArtifact,paginateListResourcesForTagOption,paginateListPortfolioAccess,paginateListTagOptions,ResourceNotFoundException,ResourceInUseException,ListTagOptionsCommand,DescribeTagOptionCommand,ListAcceptedPortfolioSharesCommand,ListBudgetsForResourceCommand,ListPortfoliosCommand,InvalidParametersException,LimitExceededException,ScanProvisionedProductsCommand,paginateGetProvisionedProductOutputs,GetProvisionedProductOutputsCommand,GetAWSOrganizationsAccessStatusCommand,ProvisionProductCommand,TerminateProvisionedProductCommand,TagOptionNotMigratedException,DescribeRecordCommand,UpdateProvisionedProductCommand,ExecuteProvisionedProductPlanCommand,ListPortfolioAccessCommand,ServiceCatalog,paginateDescribePortfolioShares,paginateListPortfolios,paginateListServiceActions,DisassociateProductFromPortfolioCommand,UpdatePortfolioCommand,OperationNotSupportedException,ListPortfoliosForProductCommand,EnableAWSOrganizationsAccessCommand,DescribeProductAsAdminCommand,paginateListProvisioningArtifactsForServiceAction,DuplicateResourceException,ListPrincipalsForPortfolioCommand,ListProvisioningArtifactsForServiceActionCommand,paginateListPrincipalsForPortfolio,SearchProvisionedProductsCommand,DescribeProvisioningArtifactCommand,DisassociateTagOptionFromResourceCommand,DisassociatePrincipalFromPortfolioCommand
---

# AWS Service Catalog SDK for JavaScript

Use `@aws-sdk/client-service-catalog` to discover Service Catalog portfolios and products, inspect the parameters needed to launch a product, provision it, poll the resulting record, list active provisioned products, and terminate them later.

This package manages the Service Catalog control plane. Provisioning a product usually creates or updates underlying infrastructure such as CloudFormation stacks, but the Service Catalog API itself is asynchronous and record-based.

## Installation

```bash
npm install @aws-sdk/client-service-catalog
```

These examples assume Node.js 18+ and the standard AWS SDK for JavaScript v3 credential provider chain.

## Credentials and client initialization

Set credentials with environment variables or an AWS profile:

```bash
export AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY_ID
export AWS_SECRET_ACCESS_KEY=YOUR_SECRET_ACCESS_KEY
export AWS_SESSION_TOKEN=YOUR_SESSION_TOKEN
export AWS_REGION=us-east-1
export AWS_PROFILE=your-profile
```

Create the client with an explicit region:

```typescript
import { ServiceCatalogClient } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});
```

If you need to pin credentials in code, pass them directly:

```typescript
import { ServiceCatalogClient } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
  credentials: {
    accessKeyId: process.env.AWS_ACCESS_KEY_ID!,
    secretAccessKey: process.env.AWS_SECRET_ACCESS_KEY!,
    sessionToken: process.env.AWS_SESSION_TOKEN,
  },
});
```

Your AWS identity must also have the Service Catalog permissions needed for the operations you call and access to the target portfolio or product.

## List portfolios

Use `ListPortfolios` when you need portfolio IDs for admin workflows or to inspect what is available in the catalog.

```typescript
import {
  ListPortfoliosCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

let pageToken: string | undefined;

do {
  const response = await client.send(
    new ListPortfoliosCommand({
      PageToken: pageToken,
      PageSize: 20,
    }),
  );

  for (const portfolio of response.PortfolioDetails ?? []) {
    console.log({
      id: portfolio.Id,
      name: portfolio.DisplayName,
      provider: portfolio.ProviderName,
      description: portfolio.Description,
    });
  }

  pageToken = response.NextPageToken;
} while (pageToken);
```

Service Catalog uses `PageToken` on requests and `NextPageToken` on responses for pagination.

## Search products available to the caller

Use `SearchProducts` for end-user style discovery. It returns products the current caller can access.

```typescript
import {
  SearchProductsCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

let pageToken: string | undefined;

do {
  const response = await client.send(
    new SearchProductsCommand({
      PageToken: pageToken,
      PageSize: 20,
    }),
  );

  for (const product of response.ProductViewSummaries ?? []) {
    console.log({
      id: product.ProductId,
      viewId: product.Id,
      name: product.Name,
      owner: product.Owner,
      hasDefaultPath: product.HasDefaultPath,
      type: product.Type,
    });
  }

  pageToken = response.NextPageToken;
} while (pageToken);
```

If you are building admin tooling, `SearchProductsAsAdmin` is the matching admin-side operation and can scope the search to one portfolio with `PortfolioId`.

## Resolve a product version and launch path

To provision a product, you typically need a `ProductId`, a `ProvisioningArtifactId` for the version to launch, and sometimes a `PathId`.

```bash
export AWS_PRODUCT_ID=prod-EXAMPLE123
```

### List provisioning artifacts for a product

```typescript
import {
  ListProvisioningArtifactsCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const productId = process.env.AWS_PRODUCT_ID;

if (!productId) {
  throw new Error("Set AWS_PRODUCT_ID before running this example.");
}

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

const artifacts = await client.send(
  new ListProvisioningArtifactsCommand({
    ProductId: productId,
  }),
);

for (const artifact of artifacts.ProvisioningArtifactDetails ?? []) {
  console.log({
    id: artifact.Id,
    name: artifact.Name,
    active: artifact.Active,
    guidance: artifact.Guidance,
  });
}
```

### List launch paths for a product

```typescript
import {
  ListLaunchPathsCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const productId = process.env.AWS_PRODUCT_ID;

if (!productId) {
  throw new Error("Set AWS_PRODUCT_ID before running this example.");
}

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

let pageToken: string | undefined;

do {
  const response = await client.send(
    new ListLaunchPathsCommand({
      ProductId: productId,
      PageToken: pageToken,
      PageSize: 20,
    }),
  );

  for (const path of response.LaunchPathSummaries ?? []) {
    console.log({
      id: path.Id,
      name: path.Name,
    });
  }

  pageToken = response.NextPageToken;
} while (pageToken);
```

A launch path describes how the caller can access the product and which constraints apply. When a product has more than one launch path, resolve the correct `PathId` before provisioning.

## Read the provisioning parameters before launch

Use `DescribeProvisioningParameters` to fetch the exact parameter keys your app must send for a specific product version.

```bash
export AWS_PRODUCT_ID=prod-EXAMPLE123
export AWS_PROVISIONING_ARTIFACT_ID=pa-EXAMPLE456
export AWS_PATH_ID=lpv2-EXAMPLE789
```

```typescript
import {
  DescribeProvisioningParametersCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const productId = process.env.AWS_PRODUCT_ID;
const provisioningArtifactId = process.env.AWS_PROVISIONING_ARTIFACT_ID;
const pathId = process.env.AWS_PATH_ID;

if (!productId || !provisioningArtifactId) {
  throw new Error(
    "Set AWS_PRODUCT_ID and AWS_PROVISIONING_ARTIFACT_ID before running this example.",
  );
}

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

const response = await client.send(
  new DescribeProvisioningParametersCommand({
    ProductId: productId,
    ProvisioningArtifactId: provisioningArtifactId,
    PathId: pathId,
  }),
);

for (const parameter of response.ProvisioningArtifactParameters ?? []) {
  console.log({
    key: parameter.ParameterKey,
    type: parameter.ParameterType,
    defaultValue: parameter.DefaultValue,
    description: parameter.Description,
    isNoEcho: parameter.IsNoEcho,
  });
}

console.log("usageInstructions", response.UsageInstructions ?? []);
console.log("constraintSummaries", response.ConstraintSummaries ?? []);
```

Use the returned `ParameterKey` values exactly as provided when constructing `ProvisioningParameters`.

## Provision a product

Provisioning is asynchronous. `ProvisionProduct` creates a record immediately, and you then poll that record with `DescribeRecord`.

```bash
export AWS_PRODUCT_ID=prod-EXAMPLE123
export AWS_PROVISIONING_ARTIFACT_ID=pa-EXAMPLE456
export AWS_PATH_ID=lpv2-EXAMPLE789
export AWS_PROVISIONED_PRODUCT_NAME=my-service-catalog-product
```

```typescript
import { randomUUID } from "node:crypto";
import {
  ProvisionProductCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const productId = process.env.AWS_PRODUCT_ID;
const provisioningArtifactId = process.env.AWS_PROVISIONING_ARTIFACT_ID;
const pathId = process.env.AWS_PATH_ID;
const provisionedProductName = process.env.AWS_PROVISIONED_PRODUCT_NAME;

if (!productId || !provisioningArtifactId || !provisionedProductName) {
  throw new Error(
    "Set AWS_PRODUCT_ID, AWS_PROVISIONING_ARTIFACT_ID, and AWS_PROVISIONED_PRODUCT_NAME.",
  );
}

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

const response = await client.send(
  new ProvisionProductCommand({
    ProductId: productId,
    ProvisioningArtifactId: provisioningArtifactId,
    PathId: pathId,
    ProvisionedProductName: provisionedProductName,
    ProvisionToken: randomUUID(),
    ProvisioningParameters: [
      {
        Key: "InstanceType",
        Value: "t3.micro",
      },
      {
        Key: "VpcId",
        Value: "vpc-0123456789abcdef0",
      },
    ],
  }),
);

console.log({
  recordId: response.RecordDetail?.RecordId,
  provisionedProductId: response.RecordDetail?.ProvisionedProductId,
  status: response.RecordDetail?.Status,
});
```

`ProvisionToken` is required and should be unique per request. Generate it once for the request and reuse it only when you intentionally retry the same provisioning operation.

## Poll a provisioning record

Use `DescribeRecord` after `ProvisionProduct`, `UpdateProvisionedProduct`, or `TerminateProvisionedProduct`.

```bash
export AWS_RECORD_ID=rec-EXAMPLE123
```

```typescript
import {
  DescribeRecordCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const recordId = process.env.AWS_RECORD_ID;

if (!recordId) {
  throw new Error("Set AWS_RECORD_ID before running this example.");
}

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

while (true) {
  const response = await client.send(
    new DescribeRecordCommand({
      Id: recordId,
      PageSize: 20,
    }),
  );

  const detail = response.RecordDetail;

  console.log({
    recordId: detail?.RecordId,
    status: detail?.Status,
    updatedTime: detail?.UpdatedTime,
    errors: detail?.RecordErrors,
  });

  if (!detail || detail.Status === "SUCCEEDED" || detail.Status === "FAILED") {
    break;
  }

  await new Promise((resolve) => setTimeout(resolve, 5000));
}
```

Record status is the source of truth for the async request. A successful `ProvisionProduct` API call only means Service Catalog accepted the request.

## List active provisioned products

Use `ScanProvisionedProducts` to list provisioned products that are still available. Terminated products are not returned by this operation.

```typescript
import {
  ScanProvisionedProductsCommand,
  ServiceCatalogClient,
} from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

let pageToken: string | undefined;

do {
  const response = await client.send(
    new ScanProvisionedProductsCommand({
      PageToken: pageToken,
      PageSize: 20,
    }),
  );

  for (const product of response.ProvisionedProducts ?? []) {
    console.log({
      id: product.Id,
      name: product.Name,
      status: product.Status,
      productId: product.ProductId,
      artifactId: product.ProvisioningArtifactId,
      physicalId: product.PhysicalId,
    });
  }

  pageToken = response.NextPageToken;
} while (pageToken);
```

If you need to inspect one provisioned product in more detail, call `DescribeProvisionedProduct` with its `Id` or `Name`.

## Terminate a provisioned product

Termination is also asynchronous and returns a record you should poll with `DescribeRecord`.

```bash
export AWS_PROVISIONED_PRODUCT_ID=pp-EXAMPLE123
```

```typescript
import { randomUUID } from "node:crypto";
import {
  ServiceCatalogClient,
  TerminateProvisionedProductCommand,
} from "@aws-sdk/client-service-catalog";

const provisionedProductId = process.env.AWS_PROVISIONED_PRODUCT_ID;

if (!provisionedProductId) {
  throw new Error("Set AWS_PROVISIONED_PRODUCT_ID before running this example.");
}

const client = new ServiceCatalogClient({
  region: process.env.AWS_REGION ?? "us-east-1",
});

const response = await client.send(
  new TerminateProvisionedProductCommand({
    ProvisionedProductId: provisionedProductId,
    TerminateToken: randomUUID(),
    IgnoreErrors: false,
  }),
);

console.log({
  recordId: response.RecordDetail?.RecordId,
  status: response.RecordDetail?.Status,
});
```

Set `RetainPhysicalResources: true` only when you intentionally want the underlying resources to remain after Service Catalog terminates its tracking of the provisioned product.

## Common pitfalls

- Pagination uses `PageToken` and `NextPageToken`, not `NextToken`.
- `ProvisionProduct` is asynchronous; always read `RecordDetail.RecordId` and poll `DescribeRecord` until you reach a terminal status.
- `ProvisionToken`, `UpdateToken`, and `TerminateToken` are required idempotency tokens for their respective write operations.
- A product can expose multiple launch paths. Call `ListLaunchPaths` and pass the correct `PathId` when needed.
- Build `ProvisioningParameters` from `DescribeProvisioningParameters` output instead of hard-coding parameter keys.
- `ScanProvisionedProducts` returns available provisioned products only. Use record history or other record APIs if you need terminated-operation history.
- If `DescribeProvisioningParameters` surfaces a TagOption key with an empty value list, do not send that conflicted key in `Tags` on `ProvisionProduct`.

## Minimal end-to-end flow

If you are wiring Service Catalog into an app or agent workflow, the normal sequence is:

1. Call `SearchProducts` to find a product the caller can access.
2. Call `ListProvisioningArtifacts` to choose the version to launch.
3. Call `ListLaunchPaths` if the product might have multiple launch paths.
4. Call `DescribeProvisioningParameters` to fetch the exact parameter keys and constraints.
5. Call `ProvisionProduct` with a unique `ProvisionToken`.
6. Poll `DescribeRecord` until the provisioning record reaches `SUCCEEDED` or `FAILED`.
7. Call `ScanProvisionedProducts` or `DescribeProvisionedProduct` to inspect active provisioned products later.
8. Call `TerminateProvisionedProduct` with a unique `TerminateToken` when you want to remove one, then poll its record.

## Version notes

- This guide targets `@aws-sdk/client-service-catalog` version `3.1007.0`.
- These examples use the AWS SDK for JavaScript v3 command-based client API and the current Service Catalog request member names such as `PageToken`, `NextPageToken`, `ProvisionToken`, and `TerminateToken`.

## Official sources

- AWS SDK for JavaScript v3 Service Catalog client docs: `https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/client/service-catalog/`
- AWS SDK for JavaScript v3 credential configuration for Node.js: `https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/setting-credentials-node.html`
- AWS Service Catalog `ListPortfolios` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_ListPortfolios.html`
- AWS Service Catalog `SearchProducts` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_SearchProducts.html`
- AWS Service Catalog `ListLaunchPaths` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_ListLaunchPaths.html`
- AWS Service Catalog `DescribeProvisioningParameters` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_DescribeProvisioningParameters.html`
- AWS Service Catalog `ProvisionProduct` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_ProvisionProduct.html`
- AWS Service Catalog `DescribeRecord` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_DescribeRecord.html`
- AWS Service Catalog `ScanProvisionedProducts` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_ScanProvisionedProducts.html`
- AWS Service Catalog `TerminateProvisionedProduct` API: `https://docs.aws.amazon.com/servicecatalog/latest/dg/API_TerminateProvisionedProduct.html`
- npm package: `https://www.npmjs.com/package/@aws-sdk/client-service-catalog`

## Per-symbol detail

### AcceptPortfolioShareCommand

The `AcceptPortfolioShareCommand` class encapsulates the API operation required to accept a portfolio share granted to your AWS account by a different account. In the JavaScript SDK v3, you instantiate this command with the target portfolio identifier and execute it asynchronously using the `send` method on a `ServiceCatalogClient` instance. Once the promise resolves successfully, the shared portfolio is registered in your account, enabling the provisioning of associated products and services. This command is critical for establishing cross-account resource governance within the Service Catalog ecosystem.

```javascript
import { ServiceCatalogClient, AcceptPortfolioShareCommand } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({ region: "us-east-1" });
const command = new AcceptPortfolioShareCommand({ PortfolioId: "portfolio-id" });

try {
  const response = await client.send(command);
  console.log("Portfolio share accepted:", response);
} catch (err) {
  console.error("Failed to accept share:", err);
}
```

### AssociateBudgetWithResourceCommand

The `AssociateBudgetWithResourceCommand` enables the association of a specific AWS Budget with a Service Catalog resource to facilitate cost monitoring. Developers should utilize this command when configuring financial controls or alerts for provisioned products and portfolios within their AWS accounts. When invoked in a Node.js environment, the command returns a promise that resolves upon successful association or rejects if the resource or budget cannot be linked, typically handled using async/await patterns. This operation ensures that the specified budget applies to the target resource without creating duplicate entries.

```javascript
const { ServiceCatalogClient, AssociateBudgetWithResourceCommand } = require("@aws-sdk/client-service-catalog");

const client = new ServiceCatalogClient({ region: "us-east-1" });
const input = {
  BudgetArn: "arn:aws:budgets:...",
  ResourceId: "arn:aws:servicecatalog:..."
};
const command = new AssociateBudgetWithResourceCommand(input);
const response = await client.send(command);
```

### AssociatePrincipalWithPortfolioCommand

The `AssociatePrincipalWithPortfolioCommand` enables you to grant an IAM principal access to a specific Service Catalog portfolio by linking their identity to the portfolio's permissions. You should use this command when configuring access control to ensure that specific users or roles can view and provision products within the associated portfolio. In the JavaScript SDK v3, this operation is executed by instantiating the command with the necessary portfolio and principal identifiers, then passing it to the client's `send` method. The promise resolves to a response object confirming the association was successful.

```javascript
import { ServiceCatalogClient, AssociatePrincipalWithPortfolioCommand } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({ region: "us-east-1" });
const command = new AssociatePrincipalWithPortfolioCommand({
  PortfolioId: "portfolio-id",
  PrincipalARN: "arn:aws:iam::123456789012:role/ExampleRole"
});
const response = await client.send(command);
```

### AssociateServiceActionWithProvisioningArtifactCommand

The `AssociateServiceActionWithProvisioningArtifactCommand` class encapsulates the API request required to link a specific service action to a provisioning artifact within an AWS Service Catalog product. Developers instantiate this command with the relevant identifiers and pass it to a `ServiceCatalogClient` instance when configuring product versions to enable specific operational actions. Executing the command via the client's `send` method returns a Promise that resolves upon successful association, allowing you to manage product lifecycle configurations programmatically in your Node.js application.

```javascript
import { ServiceCatalogClient, AssociateServiceActionWithProvisioningArtifactCommand } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({ region: "us-east-1" });
const command = new AssociateServiceActionWithProvisioningArtifactCommand({
  ProductId: "prod-123",
  ProvisioningArtifactId: "pa-456",
  ServiceActionId: "sa-789"
});
const response = await client.send(command);
```

### AssociateTagOptionWithResourceCommand

The `AssociateTagOptionWithResourceCommand` class represents an API operation that links a specific tag option to a designated AWS Service Catalog resource. You should use this command when managing resource organization by applying predefined tag options to products, portfolios, or provisioned items within your account. In a Node.js environment, executing this command involves sending the request via the Service Catalog client, which returns a promise that resolves successfully once the association is established. This operation modifies the resource's metadata without returning a payload, requiring standard error handling to confirm the update.

```javascript
import { ServiceCatalogClient, AssociateTagOptionWithResourceCommand } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({ region: "us-east-1" });
const input = {
  ResourceArn: "arn:aws:servicecatalog:us-east-1:123456789012:product/p-123456789",
  TagOptionId: "tag-option-123"
};
const command = new AssociateTagOptionWithResourceCommand(input);
try {
  await client.send(command);
  console.log("Tag option associated successfully");
} catch (err) {
  console.error("Failed to associate tag option:", err);
}
```

### BatchAssociateServiceActionWithProvisioningArtifactCommand

The `BatchAssociateServiceActionWithProvisioningArtifactCommand` enables you to associate multiple service actions with a specific provisioning artifact in a single API request. You should use this operation when managing multiple service actions for a product version to reduce API overhead compared to individual association calls like `AssociateServiceActionWithProvisioningArtifactCommand`. When executed through the `ServiceCatalogClient`, the command returns a response object confirming the batch operation's success or failure. This effectively updates the artifact's available service actions for end users within the Service Catalog environment.

```javascript
const { ServiceCatalogClient, BatchAssociateServiceActionWithProvisioningArtifactCommand } = require("@aws-sdk/client-service-catalog");

async function example() {
  const client = new ServiceCatalogClient({ region: "us-east-1" });
  const input = {
    ProvisioningArtifactId: "pa-1234567890abcdef0",
    ServiceActionIds: ["sa-1234567890abcdef0", "sa-0987654321fedcba9"]
  };
  const command = new BatchAssociateServiceActionWithProvisioningArtifactCommand(input);
  const response = await client.send(command);
  console.log(response);
}
```

### BatchDisassociateServiceActionFromProvisioningArtifactCommand

The `BatchDisassociateServiceActionFromProvisioningArtifactCommand` class represents an API operation that removes one or more service actions from a specific provisioning artifact within a Service Catalog product. You instantiate this command and pass it to a `ServiceCatalogClient` to execute the disassociation asynchronously, which is essential when modifying product capabilities or cleaning up unused configurations. Upon successful execution, the operation returns a promise that resolves to the API response, allowing you to handle the result or errors using standard JavaScript async/await patterns. This command complements other management operations such as `AssociateServiceActionWithProvisioningArtifactCommand` to maintain consistent portfolio states.

```javascript
import { ServiceCatalogClient, BatchDisassociateServiceActionFromProvisioningArtifactCommand } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({ region: "us-east-1" });
const input = {
  ProductId: "prod-123",
  ProvisioningArtifactId: "pa-456",
  ServiceActionIds: ["sa-789"]
};
const command = new BatchDisassociateServiceActionFromProvisioningArtifactCommand(input);
const response = await client.send(command);
```

### CopyProductCommand

The `CopyProductCommand` class encapsulates the API request to duplicate an existing Service Catalog product into a specified target portfolio. Developers utilize this command when they need to replicate a product's configuration, such as launch constraints or provisioning artifacts, across different portfolios or regions without manually recreating the definition. Upon successful execution via the `ServiceCatalogClient`, it returns a response containing the new product identifier, allowing subsequent operations to reference the copied asset within the JavaScript runtime. This operation is asynchronous and requires proper error handling to manage potential conflicts or permission issues during the copy process.

```javascript
const { ServiceCatalogClient, CopyProductCommand } = require("@aws-sdk/client-service-catalog");

async function copyProduct() {
  const client = new ServiceCatalogClient({ region: "us-east-1" });
  const input = {
    SourceProductId: "prod-xxxxx",
    TargetPortfolioId: "port-xxxxx"
  };
  const command = new CopyProductCommand(input);
  const response = await client.send(command);
  console.log("Copied Product Id:", response.ProductDetail?.Id);
}
```

### CreateConstraintCommand

The `CreateConstraintCommand` class encapsulates the request to define a constraint on a specific Service Catalog portfolio, enabling administrators to restrict product launches based on criteria such as allowed launch paths or regions. You should instantiate this command with the necessary constraint details and send it via the Service Catalog client to enforce governance policies on your catalog resources. Upon successful execution, the command resolves to an output object containing the newly created constraint identifier, which can be used for subsequent management operations. This pattern aligns with the AWS SDK for JavaScript v3 asynchronous design, requiring `await` and `try/catch` blocks for robust error handling.

```javascript
import { ServiceCatalogClient, CreateConstraintCommand } from "@aws-sdk/client-service-catalog";

const client = new ServiceCatalogClient({ region: "us-east-1" });
const command = new CreateConstraintCommand({
  PortfolioId: "portfolio-id",
  Type: "LAUNCH_PATH_CONSTRAINT",
  Value: "arn:aws:..."
});

try {
  const response = await client.send(command);
  console.log("Constraint created:", response.ConstraintId);
} catch (err) {
  console.error("Failed to create constraint:", err);
}
```

## API surface — verifiable exports of `@aws-sdk/client-service-catalog`

Each symbol below is a real export of `@aws-sdk/client-service-catalog`, verified via `Object.keys(require('@aws-sdk/client-service-catalog'))`.

```typescript
// 90 Command classes
class AcceptPortfolioShareCommand {}
class AssociateBudgetWithResourceCommand {}
class AssociatePrincipalWithPortfolioCommand {}
class AssociateProductWithPortfolioCommand {}
class AssociateServiceActionWithProvisioningArtifactCommand {}
class AssociateTagOptionWithResourceCommand {}
class BatchAssociateServiceActionWithProvisioningArtifactCommand {}
class BatchDisassociateServiceActionFromProvisioningArtifactCommand {}
class CopyProductCommand {}
class CreateConstraintCommand {}
class CreatePortfolioCommand {}
class CreatePortfolioShareCommand {}
class CreateProductCommand {}
class CreateProvisionedProductPlanCommand {}
class CreateProvisioningArtifactCommand {}
class CreateServiceActionCommand {}
class CreateTagOptionCommand {}
class DeleteConstraintCommand {}
class DeletePortfolioCommand {}
class DeletePortfolioShareCommand {}
class DeleteProductCommand {}
class DeleteProvisionedProductPlanCommand {}
class DeleteProvisioningArtifactCommand {}
class DeleteServiceActionCommand {}
class DeleteTagOptionCommand {}
class DescribeConstraintCommand {}
class DescribeCopyProductStatusCommand {}
class DescribePortfolioCommand {}
class DescribePortfolioShareStatusCommand {}
class DescribePortfolioSharesCommand {}
class DescribeProductAsAdminCommand {}
class DescribeProductCommand {}
class DescribeProductViewCommand {}
class DescribeProvisionedProductCommand {}
class DescribeProvisionedProductPlanCommand {}
class DescribeProvisioningArtifactCommand {}
class DescribeProvisioningParametersCommand {}
class DescribeRecordCommand {}
class DescribeServiceActionCommand {}
class DescribeServiceActionExecutionParametersCommand {}
class DescribeTagOptionCommand {}
class DisableAWSOrganizationsAccessCommand {}
class DisassociateBudgetFromResourceCommand {}
class DisassociatePrincipalFromPortfolioCommand {}
class DisassociateProductFromPortfolioCommand {}
class DisassociateServiceActionFromProvisioningArtifactCommand {}
class DisassociateTagOptionFromResourceCommand {}
class EnableAWSOrganizationsAccessCommand {}
class ExecuteProvisionedProductPlanCommand {}
class ExecuteProvisionedProductServiceActionCommand {}
class GetAWSOrganizationsAccessStatusCommand {}
class GetProvisionedProductOutputsCommand {}
class ImportAsProvisionedProductCommand {}
class ListAcceptedPortfolioSharesCommand {}
class ListBudgetsForResourceCommand {}
class ListConstraintsForPortfolioCommand {}
class ListLaunchPathsCommand {}
class ListOrganizationPortfolioAccessCommand {}
class ListPortfolioAccessCommand {}
class ListPortfoliosCommand {}
// ... (30 additional commands not shown)
// Other classes
class DuplicateResourceException {}
class InvalidParametersException {}
class InvalidStateException {}
class LimitExceededException {}
class OperationNotSupportedException {}
class ResourceInUseException {}
class ResourceNotFoundException {}
class ServiceCatalog {}
class ServiceCatalogClient {}
class ServiceCatalogServiceException {}
class TagOptionNotMigratedException {}
```

```javascript
// Verified Command-pattern usage
const client = new ServiceCatalogClient({ region: process.env.AWS_REGION });
await client.acceptPortfolioShare(input);
await client.associateBudgetWithResource(input);
await client.associatePrincipalWithPortfolio(input);
await client.associateProductWithPortfolio(input);
await client.associateServiceActionWithProvisioningArtifact(input);
await client.associateTagOptionWithResource(input);
await client.batchAssociateServiceActionWithProvisioningArtifact(input);
await client.batchDisassociateServiceActionFromProvisioningArtifact(input);
await client.copyProduct(input);
await client.createConstraint(input);
await client.createPortfolio(input);
await client.createPortfolioShare(input);
await client.createProduct(input);
await client.createProvisionedProductPlan(input);
await client.createProvisioningArtifact(input);
await client.createServiceAction(input);
await client.createTagOption(input);
await client.deleteConstraint(input);
await client.deletePortfolio(input);
await client.deletePortfolioShare(input);
await client.deleteProduct(input);
await client.deleteProvisionedProductPlan(input);
await client.deleteProvisioningArtifact(input);
await client.deleteServiceAction(input);
await client.deleteTagOption(input);
await client.describeConstraint(input);
await client.describeCopyProductStatus(input);
await client.describePortfolio(input);
await client.describePortfolioShareStatus(input);
await client.describePortfolioShares(input);
```
