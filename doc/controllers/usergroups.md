# Usergroups

```python
usergroups_api = client.usergroups
```

## Class Name

`UsergroupsApi`

## Methods

* [Usergroups Create](../../doc/controllers/usergroups.md#usergroups-create)
* [Usergroups Disable](../../doc/controllers/usergroups.md#usergroups-disable)
* [Usergroups Enable](../../doc/controllers/usergroups.md#usergroups-enable)
* [Usergroups List](../../doc/controllers/usergroups.md#usergroups-list)
* [Usergroups Update](../../doc/controllers/usergroups.md#usergroups-update)


# Usergroups Create

Create a User Group

API method documentation: [https://api.slack.com/methods/usergroups.create](https://api.slack.com/methods/usergroups.create)

```python
def usergroups_create(self,
                     token,
                     name,
                     channels=None,
                     description=None,
                     handle=None,
                     include_count=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `name` | `str` | Form, Required | A name for the User Group. Must be unique among User Groups. |
| `channels` | `str` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `description` | `str` | Form, Optional | A short description of the User Group. |
| `handle` | `str` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `include_count` | `bool` | Form, Optional | Include the number of users in each User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsergroupsCreateSchema`](../../doc/models/usergroups-create-schema.md).

## Example Usage

```python
token = 'token6'

name = 'name0'

result = usergroups_api.usergroups_create(
    token,
    name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsCreateErrorSchemaException`](../../doc/models/usergroups-create-error-schema-exception.md) |


# Usergroups Disable

Disable an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.disable](https://api.slack.com/methods/usergroups.disable)

```python
def usergroups_disable(self,
                      token,
                      usergroup,
                      include_count=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `str` | Form, Required | The encoded ID of the User Group to disable. |
| `include_count` | `bool` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsergroupsDisableSchema`](../../doc/models/usergroups-disable-schema.md).

## Example Usage

```python
token = 'token6'

usergroup = 'usergroup2'

result = usergroups_api.usergroups_disable(
    token,
    usergroup
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsDisableErrorSchemaException`](../../doc/models/usergroups-disable-error-schema-exception.md) |


# Usergroups Enable

Enable a User Group

API method documentation: [https://api.slack.com/methods/usergroups.enable](https://api.slack.com/methods/usergroups.enable)

```python
def usergroups_enable(self,
                     token,
                     usergroup,
                     include_count=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `str` | Form, Required | The encoded ID of the User Group to enable. |
| `include_count` | `bool` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsergroupsEnableSchema`](../../doc/models/usergroups-enable-schema.md).

## Example Usage

```python
token = 'token6'

usergroup = 'usergroup2'

result = usergroups_api.usergroups_enable(
    token,
    usergroup
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsEnableErrorSchemaException`](../../doc/models/usergroups-enable-error-schema-exception.md) |


# Usergroups List

List all User Groups for a team

API method documentation: [https://api.slack.com/methods/usergroups.list](https://api.slack.com/methods/usergroups.list)

```python
def usergroups_list(self,
                   token,
                   include_users=None,
                   include_count=None,
                   include_disabled=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `include_users` | `bool` | Query, Optional | Include the list of users for each User Group. |
| `include_count` | `bool` | Query, Optional | Include the number of users in each User Group. |
| `include_disabled` | `bool` | Query, Optional | Include disabled User Groups. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsergroupsListSchema`](../../doc/models/usergroups-list-schema.md).

## Example Usage

```python
token = 'token6'

result = usergroups_api.usergroups_list(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsListErrorSchemaException`](../../doc/models/usergroups-list-error-schema-exception.md) |


# Usergroups Update

Update an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.update](https://api.slack.com/methods/usergroups.update)

```python
def usergroups_update(self,
                     token,
                     usergroup,
                     handle=None,
                     description=None,
                     channels=None,
                     include_count=None,
                     name=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `str` | Form, Required | The encoded ID of the User Group to update. |
| `handle` | `str` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `description` | `str` | Form, Optional | A short description of the User Group. |
| `channels` | `str` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `include_count` | `bool` | Form, Optional | Include the number of users in the User Group. |
| `name` | `str` | Form, Optional | A name for the User Group. Must be unique among User Groups. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`UsergroupsUpdateSchema`](../../doc/models/usergroups-update-schema.md).

## Example Usage

```python
token = 'token6'

usergroup = 'usergroup2'

result = usergroups_api.usergroups_update(
    token,
    usergroup
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsUpdateErrorSchemaException`](../../doc/models/usergroups-update-error-schema-exception.md) |

