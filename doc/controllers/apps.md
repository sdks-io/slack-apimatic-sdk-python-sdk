# Apps

```python
apps_api = client.apps
```

## Class Name

`AppsApi`


# Apps Uninstall

Uninstalls your app from a workspace.

API method documentation: [https://api.slack.com/methods/apps.uninstall](https://api.slack.com/methods/apps.uninstall)

```python
def apps_uninstall(self,
                  token=None,
                  client_id=None,
                  client_secret=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `none` |
| `client_id` | `str` | Query, Optional | Issued when you created your application. |
| `client_secret` | `str` | Query, Optional | Issued when you created your application. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AppsUninstallSchema`](../../doc/models/apps-uninstall-schema.md).

## Example Usage

```python
result = apps_api.apps_uninstall()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsUninstallErrorSchemaException`](../../doc/models/apps-uninstall-error-schema-exception.md) |

