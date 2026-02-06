# Apps Permissions

```python
apps_permissions_api = client.apps_permissions
```

## Class Name

`AppsPermissionsApi`

## Methods

* [Apps Permissions Info](../../doc/controllers/apps-permissions.md#apps-permissions-info)
* [Apps Permissions Request](../../doc/controllers/apps-permissions.md#apps-permissions-request)


# Apps Permissions Info

Returns list of permissions this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.info](https://api.slack.com/methods/apps.permissions.info)

```python
def apps_permissions_info(self,
                         token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AppsPermissionsInfoSchema`](../../doc/models/apps-permissions-info-schema.md).

## Example Usage

```python
result = apps_permissions_api.apps_permissions_info()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`AppsPermissionsInfoErrorSchemaException`](../../doc/models/apps-permissions-info-error-schema-exception.md) |


# Apps Permissions Request

Allows an app to request additional scopes

API method documentation: [https://api.slack.com/methods/apps.permissions.request](https://api.slack.com/methods/apps.permissions.request)

```python
def apps_permissions_request(self,
                            token,
                            scopes,
                            trigger_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `str` | Query, Required | A comma separated list of scopes to request for |
| `trigger_id` | `str` | Query, Required | Token used to trigger the permissions API |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AppsPermissionsRequestSchema`](../../doc/models/apps-permissions-request-schema.md).

## Example Usage

```python
token = 'token6'

scopes = 'scopes4'

trigger_id = 'trigger_id6'

result = apps_permissions_api.apps_permissions_request(
    token,
    scopes,
    trigger_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when trigger_id is invalid | [`AppsPermissionsRequestErrorSchemaException`](../../doc/models/apps-permissions-request-error-schema-exception.md) |

