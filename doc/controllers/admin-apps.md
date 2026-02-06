# Admin Apps

```python
admin_apps_api = client.admin_apps
```

## Class Name

`AdminAppsApi`

## Methods

* [Admin Apps Approve](../../doc/controllers/admin-apps.md#admin-apps-approve)
* [Admin Apps Restrict](../../doc/controllers/admin-apps.md#admin-apps-restrict)


# Admin Apps Approve

Approve an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.approve](https://api.slack.com/methods/admin.apps.approve)

```python
def admin_apps_approve(self,
                      token,
                      app_id=None,
                      request_id=None,
                      team_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `app_id` | `str` | Form, Optional | The id of the app to approve. |
| `request_id` | `str` | Form, Optional | The id of the request to approve. |
| `team_id` | `str` | Form, Optional | - |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = admin_apps_api.admin_apps_approve(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Apps Restrict

Restrict an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.restrict](https://api.slack.com/methods/admin.apps.restrict)

```python
def admin_apps_restrict(self,
                       token,
                       app_id=None,
                       request_id=None,
                       team_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `app_id` | `str` | Form, Optional | The id of the app to restrict. |
| `request_id` | `str` | Form, Optional | The id of the request to restrict. |
| `team_id` | `str` | Form, Optional | - |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = admin_apps_api.admin_apps_restrict(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

