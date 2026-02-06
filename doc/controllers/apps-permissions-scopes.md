# Apps Permissions Scopes

```python
apps_permissions_scopes_api = client.apps_permissions_scopes
```

## Class Name

`AppsPermissionsScopesApi`


# Apps Permissions Scopes List

Returns list of scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.scopes.list](https://api.slack.com/methods/apps.permissions.scopes.list)

```python
def apps_permissions_scopes_list(self,
                                token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ApiPermissionsScopesListSuccessSchema`](../../doc/models/api-permissions-scopes-list-success-schema.md).

## Example Usage

```python
token = 'token6'

result = apps_permissions_scopes_api.apps_permissions_scopes_list(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsPermissionsScopesListErrorSchemaException`](../../doc/models/apps-permissions-scopes-list-error-schema-exception.md) |

