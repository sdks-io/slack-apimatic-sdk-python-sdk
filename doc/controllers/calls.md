# Calls

```python
calls_api = client.calls
```

## Class Name

`CallsApi`

## Methods

* [Calls Add](../../doc/controllers/calls.md#calls-add)
* [Calls End](../../doc/controllers/calls.md#calls-end)
* [Calls Info](../../doc/controllers/calls.md#calls-info)
* [Calls Update](../../doc/controllers/calls.md#calls-update)


# Calls Add

Registers a new Call.

API method documentation: [https://api.slack.com/methods/calls.add](https://api.slack.com/methods/calls.add)

```python
def calls_add(self,
             token,
             external_unique_id,
             join_url,
             external_display_id=None,
             desktop_app_join_url=None,
             date_start=None,
             title=None,
             created_by=None,
             users=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `external_unique_id` | `str` | Form, Required | An ID supplied by the 3rd-party Call provider. It must be unique across all Calls from that service. |
| `join_url` | `str` | Form, Required | The URL required for a client to join the Call. |
| `external_display_id` | `str` | Form, Optional | An optional, human-readable ID supplied by the 3rd-party Call provider. If supplied, this ID will be displayed in the Call object. |
| `desktop_app_join_url` | `str` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |
| `date_start` | `int` | Form, Optional | Call start time in UTC UNIX timestamp format |
| `title` | `str` | Form, Optional | The name of the Call. |
| `created_by` | `str` | Form, Optional | The valid Slack user ID of the user who created this Call. When this method is called with a user token, the `created_by` field is optional and defaults to the authed user of the token. Otherwise, the field is required. |
| `users` | `str` | Form, Optional | The list of users to register as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

external_unique_id = 'external_unique_id0'

join_url = 'join_url6'

result = calls_api.calls_add(
    token,
    external_unique_id,
    join_url
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


# Calls End

Ends a Call.

API method documentation: [https://api.slack.com/methods/calls.end](https://api.slack.com/methods/calls.end)

```python
def calls_end(self,
             token,
             id,
             duration=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `str` | Form, Required | `id` returned when registering the call using the [`calls.add`](/methods/calls.add) method. |
| `duration` | `int` | Form, Optional | Call duration in seconds |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

id = 'id0'

result = calls_api.calls_end(
    token,
    id
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


# Calls Info

Returns information about a Call.

API method documentation: [https://api.slack.com/methods/calls.info](https://api.slack.com/methods/calls.info)

```python
def calls_info(self,
              token,
              id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `calls:read` |
| `id` | `str` | Query, Required | `id` of the Call returned by the [`calls.add`](/methods/calls.add) method. |

## Requires scope

### slackAuth

`calls:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

id = 'id0'

result = calls_api.calls_info(
    token,
    id
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


# Calls Update

Updates information about a Call.

API method documentation: [https://api.slack.com/methods/calls.update](https://api.slack.com/methods/calls.update)

```python
def calls_update(self,
                token,
                id,
                title=None,
                join_url=None,
                desktop_app_join_url=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `str` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `title` | `str` | Form, Optional | The name of the Call. |
| `join_url` | `str` | Form, Optional | The URL required for a client to join the Call. |
| `desktop_app_join_url` | `str` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

id = 'id0'

result = calls_api.calls_update(
    token,
    id
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

