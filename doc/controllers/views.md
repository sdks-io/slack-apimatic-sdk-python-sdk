# Views

```python
views_api = client.views
```

## Class Name

`ViewsApi`

## Methods

* [Views Open](../../doc/controllers/views.md#views-open)
* [Views Publish](../../doc/controllers/views.md#views-publish)
* [Views Push](../../doc/controllers/views.md#views-push)
* [Views Update](../../doc/controllers/views.md#views-update)


# Views Open

Open a view for a user.

API method documentation: [https://api.slack.com/methods/views.open](https://api.slack.com/methods/views.open)

```python
def views_open(self,
              token,
              trigger_id,
              view)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `none` |
| `trigger_id` | `str` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `str` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

trigger_id = 'trigger_id6'

view = 'view2'

result = views_api.views_open(
    token,
    trigger_id,
    view
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Publish

Publish a static view for a User.

API method documentation: [https://api.slack.com/methods/views.publish](https://api.slack.com/methods/views.publish)

```python
def views_publish(self,
                 token,
                 user_id,
                 view,
                 hash=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `none` |
| `user_id` | `str` | Query, Required | `id` of the user you want publish a view to. |
| `view` | `str` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `str` | Query, Optional | A string that represents view state to protect against possible race conditions. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

user_id = 'user_id8'

view = 'view2'

result = views_api.views_publish(
    token,
    user_id,
    view
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Push

Push a view onto the stack of a root view.

API method documentation: [https://api.slack.com/methods/views.push](https://api.slack.com/methods/views.push)

```python
def views_push(self,
              token,
              trigger_id,
              view)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `none` |
| `trigger_id` | `str` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `str` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

trigger_id = 'trigger_id6'

view = 'view2'

result = views_api.views_push(
    token,
    trigger_id,
    view
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Update

Update an existing view.

API method documentation: [https://api.slack.com/methods/views.update](https://api.slack.com/methods/views.update)

```python
def views_update(self,
                token,
                view_id=None,
                external_id=None,
                view=None,
                hash=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `none` |
| `view_id` | `str` | Query, Optional | A unique identifier of the view to be updated. Either `view_id` or `external_id` is required. |
| `external_id` | `str` | Query, Optional | A unique identifier of the view set by the developer. Must be unique for all views on a team. Max length of 255 characters. Either `view_id` or `external_id` is required. |
| `view` | `str` | Query, Optional | A [view object](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `str` | Query, Optional | A string that represents view state to protect against possible race conditions. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = views_api.views_update(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

