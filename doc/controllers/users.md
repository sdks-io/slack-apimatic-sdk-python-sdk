# Users

```python
users_api = client.users
```

## Class Name

`UsersApi`

## Methods

* [Users Conversations](../../doc/controllers/users.md#users-conversations)
* [Users Delete Photo](../../doc/controllers/users.md#users-delete-photo)
* [Users Get Presence](../../doc/controllers/users.md#users-get-presence)
* [Users Identity](../../doc/controllers/users.md#users-identity)
* [Users Info](../../doc/controllers/users.md#users-info)
* [Users List](../../doc/controllers/users.md#users-list)
* [Users Lookup by Email](../../doc/controllers/users.md#users-lookup-by-email)
* [Users Set Active](../../doc/controllers/users.md#users-set-active)
* [Users Set Photo](../../doc/controllers/users.md#users-set-photo)
* [Users Set Presence](../../doc/controllers/users.md#users-set-presence)


# Users Conversations

List conversations the calling user may access.

API method documentation: [https://api.slack.com/methods/users.conversations](https://api.slack.com/methods/users.conversations)

```python
def users_conversations(self,
                       token=None,
                       user=None,
                       types=None,
                       exclude_archived=None,
                       limit=None,
                       cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `user` | `str` | Query, Optional | Browse conversations by a specific user ID's membership. Non-public channels are restricted to those where the calling user shares membership. |
| `types` | `str` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `exclude_archived` | `bool` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersConversationsSuccessSchema`](../../doc/models/users-conversations-success-schema.md).

## Example Usage

```python
result = users_api.users_conversations()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersConversationsErrorSchemaException`](../../doc/models/users-conversations-error-schema-exception.md) |


# Users Delete Photo

Delete the user profile photo

API method documentation: [https://api.slack.com/methods/users.deletePhoto](https://api.slack.com/methods/users.deletePhoto)

```python
def users_delete_photo(self,
                      token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Required | Authentication token. Requires scope: `users.profile:write` |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersDeletePhotoSchema`](../../doc/models/users-delete-photo-schema.md).

## Example Usage

```python
token = 'token6'

result = users_api.users_delete_photo(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersDeletePhotoErrorSchemaException`](../../doc/models/users-delete-photo-error-schema-exception.md) |


# Users Get Presence

Gets user presence information.

API method documentation: [https://api.slack.com/methods/users.getPresence](https://api.slack.com/methods/users.getPresence)

```python
def users_get_presence(self,
                      token,
                      user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `users:read` |
| `user` | `str` | Query, Optional | User to get presence info on. Defaults to the authed user. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ApiMethodUsersGetPresence`](../../doc/models/api-method-users-get-presence.md).

## Example Usage

```python
token = 'token6'

result = users_api.users_get_presence(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersCountsErrorSchemaException`](../../doc/models/users-counts-error-schema-exception.md) |


# Users Identity

Get a user's identity.

API method documentation: [https://api.slack.com/methods/users.identity](https://api.slack.com/methods/users.identity)

```python
def users_identity(self,
                  token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `identity.basic` |

## Requires scope

### slackAuth

`identity.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type `Any`.

## Example Usage

```python
result = users_api.users_identity()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response

```
{
  "ok": true,
  "team": {
    "id": "T0G9PQBBK"
  },
  "user": {
    "id": "U0G9QF9C6",
    "name": "Sonny Whether"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersIdentityErrorSchemaException`](../../doc/models/users-identity-error-schema-exception.md) |


# Users Info

Gets information about a user.

API method documentation: [https://api.slack.com/methods/users.info](https://api.slack.com/methods/users.info)

```python
def users_info(self,
              token,
              include_locale=None,
              user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `users:read` |
| `include_locale` | `bool` | Query, Optional | Set this to `true` to receive the locale for this user. Defaults to `false` |
| `user` | `str` | Query, Optional | User to get info on |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersInfoSuccessSchema`](../../doc/models/users-info-success-schema.md).

## Example Usage

```python
token = 'token6'

result = users_api.users_info(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersInfoErrorSchemaException`](../../doc/models/users-info-error-schema-exception.md) |


# Users List

Lists all users in a Slack team.

API method documentation: [https://api.slack.com/methods/users.list](https://api.slack.com/methods/users.list)

```python
def users_list(self,
              token=None,
              limit=None,
              cursor=None,
              include_locale=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `users:read` |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. Providing no `limit` value will result in Slack attempting to deliver you the entire result set. If the collection is too large you may experience `limit_required` or HTTP 500 errors. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `include_locale` | `bool` | Query, Optional | Set this to `true` to receive the locale for users. Defaults to `false` |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersListSchema`](../../doc/models/users-list-schema.md).

## Example Usage

```python
result = users_api.users_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersListErrorSchemaException`](../../doc/models/users-list-error-schema-exception.md) |


# Users Lookup by Email

Find a user with an email address.

API method documentation: [https://api.slack.com/methods/users.lookupByEmail](https://api.slack.com/methods/users.lookupByEmail)

```python
def users_lookup_by_email(self,
                         token,
                         email)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `users:read.email` |
| `email` | `str` | Query, Required | An email address belonging to a user in the workspace |

## Requires scope

### slackAuth

`users:read.email`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersLookupByEmailSuccessSchema`](../../doc/models/users-lookup-by-email-success-schema.md).

## Example Usage

```python
token = 'token6'

email = 'email6'

result = users_api.users_lookup_by_email(
    token,
    email
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersLookupByEmailErrorSchemaException`](../../doc/models/users-lookup-by-email-error-schema-exception.md) |


# Users Set Active

Marked a user as active. Deprecated and non-functional.

API method documentation: [https://api.slack.com/methods/users.setActive](https://api.slack.com/methods/users.setActive)

```python
def users_set_active(self,
                    token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `users:write` |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersSetActiveSchema`](../../doc/models/users-set-active-schema.md).

## Example Usage

```python
token = 'token6'

result = users_api.users_set_active(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetActiveErrorSchemaException`](../../doc/models/users-set-active-error-schema-exception.md) |


# Users Set Photo

Set the user profile photo

API method documentation: [https://api.slack.com/methods/users.setPhoto](https://api.slack.com/methods/users.setPhoto)

```python
def users_set_photo(self,
                   token,
                   crop_w=None,
                   crop_x=None,
                   crop_y=None,
                   image=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Required | Authentication token. Requires scope: `users.profile:write` |
| `crop_w` | `str` | Form, Optional | Width/height of crop box (always square) |
| `crop_x` | `str` | Form, Optional | X coordinate of top-left corner of crop box |
| `crop_y` | `str` | Form, Optional | Y coordinate of top-left corner of crop box |
| `image` | `str` | Form, Optional | File contents via `multipart/form-data`. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersSetPhotoSchema`](../../doc/models/users-set-photo-schema.md).

## Example Usage

```python
token = 'token6'

result = users_api.users_set_photo(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetPhotoErrorSchemaException`](../../doc/models/users-set-photo-error-schema-exception.md) |


# Users Set Presence

Manually sets user presence.

API method documentation: [https://api.slack.com/methods/users.setPresence](https://api.slack.com/methods/users.setPresence)

```python
def users_set_presence(self,
                      token,
                      presence)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `users:write` |
| `presence` | `str` | Form, Required | Either `auto` or `away` |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsersSetPresenceSchema`](../../doc/models/users-set-presence-schema.md).

## Example Usage

```python
token = 'token6'

presence = 'presence4'

result = users_api.users_set_presence(
    token,
    presence
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetPresenceErrorSchemaException`](../../doc/models/users-set-presence-error-schema-exception.md) |

