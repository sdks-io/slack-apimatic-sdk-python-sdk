# Admin Users Session

```python
admin_users_session_api = client.admin_users_session
```

## Class Name

`AdminUsersSessionApi`

## Methods

* [Admin Users Session Invalidate](../../doc/controllers/admin-users-session.md#admin-users-session-invalidate)
* [Admin Users Session Reset](../../doc/controllers/admin-users-session.md#admin-users-session-reset)


# Admin Users Session Invalidate

Invalidate a single session for a user by session_id

API method documentation: [https://api.slack.com/methods/admin.users.session.invalidate](https://api.slack.com/methods/admin.users.session.invalidate)

```python
def admin_users_session_invalidate(self,
                                  token,
                                  team_id,
                                  session_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `team_id` | `str` | Form, Required | ID of the team that the session belongs to |
| `session_id` | `int` | Form, Required | - |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

team_id = 'team_id6'

session_id = 2

result = admin_users_session_api.admin_users_session_invalidate(
    token,
    team_id,
    session_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Users Session Reset

Wipes all valid sessions on all devices for a given user

API method documentation: [https://api.slack.com/methods/admin.users.session.reset](https://api.slack.com/methods/admin.users.session.reset)

```python
def admin_users_session_reset(self,
                             token,
                             user_id,
                             mobile_only=None,
                             web_only=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `user_id` | `str` | Form, Required | The ID of the user to wipe sessions for |
| `mobile_only` | `bool` | Form, Optional | Only expire mobile sessions (default: false) |
| `web_only` | `bool` | Form, Optional | Only expire web sessions (default: false) |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

user_id = 'user_id8'

result = admin_users_session_api.admin_users_session_reset(
    token,
    user_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

