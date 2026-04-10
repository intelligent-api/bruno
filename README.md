# Bruno Collection for using the Intelligent API

## Pre-requisites

1. [Bruno](https://www.usebruno.com/downloads) installed

## How to use

### Importing the Collections

1. Open Bruno and select `Open Collection`.
2. To use the OAuth collection, browse to and select the `Intelligent API` folder.
3. To use the Basic Auth collection, browse to and select the `Intelligent API - Basic Auth` folder.

### Environment Variables Setup

1. To begin, ensure you have signed up at https://dash.intelligent-api.com and have generated at least one set of credentials (either a Basic or OAuth set of credentials).
2. Within Bruno, open the relevant collection and select the `intelligent-api` environment from the environment dropdown in the top right.
3. Select `Configure` (or click the environment name) to edit the environment variables.
4. If you have setup OAuth Credentials, update the `clientId` and `clientSecret` values.
5. If you have setup Basic Credentials, update the `basicAuthClientId` and `basicAuthClientSecret` values.
6. Ensure you save your changes before continuing.

> NB: Secret variables (`clientId`, `clientSecret`, `basicAuthClientId`, `basicAuthClientSecret`) are marked as secrets in Bruno and will not be synced or committed to version control.

### Using the OAuth Collection

1. Open the `Intelligent API` collection in Bruno.
2. Ensure the `intelligent-api` environment is selected in the top right dropdown.
3. Begin by generating a token — invoke the `02 Request Token` endpoint in the root of the collection. This will automatically store the returned token in your environment variables for use with subsequent requests.
4. You can now invoke any of the other API endpoints within the collection.

> NB: When generating a token, you will only be able to specify `scopes` that the credentials you generated were granted access to when you created them in the https://dash.intelligent-api.com dashboard. So for example if you created credentials and unticked some of the scopes, you cannot include those scopes when requesting a token and subsequently can also not invoke any endpoints that require those scopes.

> For more information on the Scopes and which endpoints require which Scopes, please see https://dash.intelligent-api.com/platform/apiaccess/scopes.

5. Tokens are valid for 4 hours. After expiry, re-run `02 Request Token` to generate a new one.
6. The `Document` endpoints all require files as input. To send a file, select the relevant endpoint, go to the `Body` tab, and use the file picker to browse for and select an appropriate file.

### Using the Basic Auth Collection

1. Open the `Intelligent API - Basic Auth` collection in Bruno.
2. Ensure the `intelligent-api` environment is selected in the top right dropdown.
3. You can now invoke any of the API endpoints directly — no token generation step is required.

> NB: When using Basic Credentials, you will only be able to invoke endpoints that the credentials were granted access to when you created them in the https://dash.intelligent-api.com dashboard. So for example if you created credentials and unticked some of the scopes, you cannot invoke endpoints that require those scopes.

> For more information on the Scopes and which endpoints require which Scopes, please see https://dash.intelligent-api.com/platform/apiaccess/scopes.

4. The `Document` endpoints all require files as input. To send a file, select the relevant endpoint, go to the `Body` tab, and use the file picker to browse for and select an appropriate file.
