# Dialog

```python
dialog_api = client.dialog
```

## Class Name

`DialogApi`


# Dialog Open

Open a dialog with a user

API method documentation: [https://api.slack.com/methods/dialog.open](https://api.slack.com/methods/dialog.open)

```python
def dialog_open(self,
               token,
               dialog,
               trigger_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `none` |
| `dialog` | `str` | Query, Required | The dialog definition. This must be a JSON-encoded string. |
| `trigger_id` | `str` | Query, Required | Exchange a trigger to post to the user. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DialogOpenSchema`](../../doc/models/dialog-open-schema.md).

## Example Usage

```python
token = 'token6'

dialog = 'dialog4'

trigger_id = 'trigger_id6'

result = dialog_api.dialog_open(
    token,
    dialog,
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
| Default | Typical error response, before getting to any possible validation errors. | [`DialogOpenErrorSchemaException`](../../doc/models/dialog-open-error-schema-exception.md) |

