# Admin Apps Requests

```python
admin_apps_requests_api = client.admin_apps_requests
```

## Class Name

`AdminAppsRequestsApi`


# Admin Apps Requests List

List app requests for a team/workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.requests.list](https://api.slack.com/methods/admin.apps.requests.list)

```python
def admin_apps_requests_list(self,
                            token,
                            limit=None,
                            cursor=None,
                            team_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin.apps:read` |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `str` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `team_id` | `str` | Query, Optional | - |

## Requires scope

### slackAuth

`admin.apps:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = admin_apps_requests_api.admin_apps_requests_list(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

