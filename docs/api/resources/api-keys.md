import APIKeysCreateRequest from './examples/_api_keys_create_request.md';
import APIKeysCreateResponse from './examples/_api_keys_create_response.md';
import APIKeysDeleteRequest from './examples/_api_keys_delete_request.md';
import APIKeysGetRequest from './examples/_api_keys_get_request.md';
import APIKeysGetResponse from './examples/_api_keys_get_response.md';
import APIKeysListRequest from './examples/_api_keys_list_request.md';
import APIKeysListResponse from './examples/_api_keys_list_response.md';
import APIKeysUpdateRequest from './examples/_api_keys_update_request.md';
import APIKeysUpdateResponse from './examples/_api_keys_update_response.md';

# API Keys
------------------

## Create API Key

Create a new API key. The generated API key can be used to authenticate to the ngrok API.

### Request

POST /api_keys

<APIKeysCreateRequest />

#### Parameters

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `description` | string | human-readable description of what uses the API key to authenticate. optional, max 255 bytes. |
| `metadata` | string | arbitrary user-defined data of this API key. optional, max 4096 bytes |

### Response

Returns a 201 response  on success

<APIKeysCreateResponse />

#### Fields

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `id` | string | unique API key resource identifier |
| `uri` | string | URI to the API resource of this API key |
| `description` | string | human-readable description of what uses the API key to authenticate. optional, max 255 bytes. |
| `metadata` | string | arbitrary user-defined data of this API key. optional, max 4096 bytes |
| `created_at` | string | timestamp when the api key was created, RFC 3339 format |
| `token` | string | the bearer token that can be placed into the Authorization header to authenticate request to the ngrok API. **This value is only available one time, on the API response from key creation. Otherwise it is null.** |


## Delete API Key

Delete an API key by ID

### Request

DELETE /api_keys/{id}

<APIKeysDeleteRequest />

### Response

Returns a 204 response with no body on success


## Get API Key

Get the details of an API key by ID.

### Request

GET /api_keys/{id}

<APIKeysGetRequest />

### Response

Returns a 200 response  on success

<APIKeysGetResponse />

#### Fields

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `id` | string | unique API key resource identifier |
| `uri` | string | URI to the API resource of this API key |
| `description` | string | human-readable description of what uses the API key to authenticate. optional, max 255 bytes. |
| `metadata` | string | arbitrary user-defined data of this API key. optional, max 4096 bytes |
| `created_at` | string | timestamp when the api key was created, RFC 3339 format |
| `token` | string | the bearer token that can be placed into the Authorization header to authenticate request to the ngrok API. **This value is only available one time, on the API response from key creation. Otherwise it is null.** |


## List API Keys

List all API keys owned by this account

### Request

GET /api_keys

<APIKeysListRequest />

### Response

Returns a 200 response  on success

<APIKeysListResponse />

#### Fields

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `keys` | [APIKey](#api-api-keys-list-fields-api-key) | the list of API keys for this account |
| `uri` | string | URI of the API keys list API resource |
| `next_page_uri` | string | URI of the next page, or null if there is no next page |

#### APIKey fields

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `id` | string | unique API key resource identifier |
| `uri` | string | URI to the API resource of this API key |
| `description` | string | human-readable description of what uses the API key to authenticate. optional, max 255 bytes. |
| `metadata` | string | arbitrary user-defined data of this API key. optional, max 4096 bytes |
| `created_at` | string | timestamp when the api key was created, RFC 3339 format |
| `token` | string | the bearer token that can be placed into the Authorization header to authenticate request to the ngrok API. **This value is only available one time, on the API response from key creation. Otherwise it is null.** |


## Update API Key

Update attributes of an API key by ID.

### Request

PATCH /api_keys/{id}

<APIKeysUpdateRequest />

#### Parameters

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `id` | string |  |
| `description` | string | human-readable description of what uses the API key to authenticate. optional, max 255 bytes. |
| `metadata` | string | arbitrary user-defined data of this API key. optional, max 4096 bytes |

### Response

Returns a 200 response  on success

<APIKeysUpdateResponse />

#### Fields

|&nbsp;| &nbsp;| &nbsp;|
|---|---|---|
| `id` | string | unique API key resource identifier |
| `uri` | string | URI to the API resource of this API key |
| `description` | string | human-readable description of what uses the API key to authenticate. optional, max 255 bytes. |
| `metadata` | string | arbitrary user-defined data of this API key. optional, max 4096 bytes |
| `created_at` | string | timestamp when the api key was created, RFC 3339 format |
| `token` | string | the bearer token that can be placed into the Authorization header to authenticate request to the ngrok API. **This value is only available one time, on the API response from key creation. Otherwise it is null.** |