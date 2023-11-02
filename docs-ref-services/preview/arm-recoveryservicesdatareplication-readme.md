---
title: Azure Site Recovery Management client library for JavaScript
keywords: Azure, javascript, SDK, API, @azure/arm-recoveryservicesdatareplication, recoveryservicesdatareplication
ms.date: 10/23/2023
ms.topic: reference
ms.devlang: javascript
ms.service: recoveryservicesdatareplication
---
# Azure Site Recovery Management client library for JavaScript - version 1.0.0-beta.1 


This package contains an isomorphic SDK (runs both in Node.js and in browsers) for Azure Site Recovery Management client.

A first party Azure service enabling the data replication.

[Source code](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/sdk/recoveryservicesdatareplication/arm-recoveryservicesdatareplication) |
[Package (NPM)](https://www.npmjs.com/package/@azure/arm-recoveryservicesdatareplication) |
[API reference documentation](/javascript/api/@azure/arm-recoveryservicesdatareplication?view=azure-node-preview) |
[Samples](https://github.com/Azure-Samples/azure-samples-js-management)

## Getting started

### Currently supported environments

- [LTS versions of Node.js](https://github.com/nodejs/release#release-schedule)
- Latest versions of Safari, Chrome, Edge and Firefox.

See our [support policy](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/SUPPORT.md) for more details.

### Prerequisites

- An [Azure subscription][azure_sub].

### Install the `@azure/arm-recoveryservicesdatareplication` package

Install the Azure Site Recovery Management client library for JavaScript with `npm`:

```bash
npm install @azure/arm-recoveryservicesdatareplication
```

### Create and authenticate a `AzureSiteRecoveryManagementServiceAPI`

To create a client object to access the Azure Site Recovery Management API, you will need the `endpoint` of your Azure Site Recovery Management resource and a `credential`. The Azure Site Recovery Management client can use Azure Active Directory credentials to authenticate.
You can find the endpoint for your Azure Site Recovery Management resource in the [Azure Portal][azure_portal].

You can authenticate with Azure Active Directory using a credential from the [@azure/identity][azure_identity] library or [an existing AAD Token](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/sdk/identity/identity/samples/AzureIdentityExamples.md#authenticating-with-a-pre-fetched-access-token).

To use the [DefaultAzureCredential][defaultazurecredential] provider shown below, or other credential providers provided with the Azure SDK, please install the `@azure/identity` package:

```bash
npm install @azure/identity
```

You will also need to **register a new AAD application and grant access to Azure Site Recovery Management** by assigning the suitable role to your service principal (note: roles such as `"Owner"` will not grant the necessary permissions).
Set the values of the client ID, tenant ID, and client secret of the AAD application as environment variables: `AZURE_CLIENT_ID`, `AZURE_TENANT_ID`, `AZURE_CLIENT_SECRET`.

For more information about how to create an Azure AD Application check out [this guide](/azure/active-directory/develop/howto-create-service-principal-portal).

```javascript
const { AzureSiteRecoveryManagementServiceAPI } = require("@azure/arm-recoveryservicesdatareplication");
const { DefaultAzureCredential } = require("@azure/identity");
// For client-side applications running in the browser, use InteractiveBrowserCredential instead of DefaultAzureCredential. See https://aka.ms/azsdk/js/identity/examples for more details.

const subscriptionId = "00000000-0000-0000-0000-000000000000";
const client = new AzureSiteRecoveryManagementServiceAPI(new DefaultAzureCredential(), subscriptionId);

// For client-side applications running in the browser, use this code instead:
// const credential = new InteractiveBrowserCredential({
//   tenantId: "<YOUR_TENANT_ID>",
//   clientId: "<YOUR_CLIENT_ID>"
// });
// const client = new AzureSiteRecoveryManagementServiceAPI(credential, subscriptionId);
```


### JavaScript Bundle
To use this client library in the browser, first you need to use a bundler. For details on how to do this, please refer to our [bundling documentation](https://aka.ms/AzureSDKBundling).

## Key concepts

### AzureSiteRecoveryManagementServiceAPI

`AzureSiteRecoveryManagementServiceAPI` is the primary interface for developers using the Azure Site Recovery Management client library. Explore the methods on this client object to understand the different features of the Azure Site Recovery Management service that you can access.

## Troubleshooting

### Logging

Enabling logging may help uncover useful information about failures. In order to see a log of HTTP requests and responses, set the `AZURE_LOG_LEVEL` environment variable to `info`. Alternatively, logging can be enabled at runtime by calling `setLogLevel` in the `@azure/logger`:

```javascript
const { setLogLevel } = require("@azure/logger");
setLogLevel("info");
```

For more detailed instructions on how to enable logs, you can look at the [@azure/logger package docs](https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/sdk/core/logger).

## Next steps

Please take a look at the [samples](https://github.com/Azure-Samples/azure-samples-js-management) directory for detailed examples on how to use this library.

## Contributing

If you'd like to contribute to this library, please read the [contributing guide](https://github.com/Azure/azure-sdk-for-js/blob/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/CONTRIBUTING.md) to learn more about how to build and test the code.

## Related projects

- [Microsoft Azure SDK for JavaScript](https://github.com/Azure/azure-sdk-for-js)

![Impressions](https://azure-sdk-impressions.azurewebsites.net/api/impressions/azure-sdk-for-js%2Fsdk%2Frecoveryservicesdatareplication%2Farm-recoveryservicesdatareplication%2FREADME.png)

[azure_cli]: /cli/azure
[azure_sub]: https://azure.microsoft.com/free/
[azure_sub]: https://azure.microsoft.com/free/
[azure_portal]: https://portal.azure.com
[azure_identity]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/sdk/identity/identity
[defaultazurecredential]: https://github.com/Azure/azure-sdk-for-js/tree/@azure/arm-recoveryservicesdatareplication_1.0.0-beta.1/sdk/identity/identity#defaultazurecredential
