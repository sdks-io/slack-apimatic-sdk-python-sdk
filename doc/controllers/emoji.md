# Emoji

```python
emoji_api = client.emoji
```

## Class Name

`EmojiApi`


# Emoji List

Lists custom emoji for a team.

API method documentation: [https://api.slack.com/methods/emoji.list](https://api.slack.com/methods/emoji.list)

```python
def emoji_list(self,
              token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `emoji:read` |

## Requires scope

### slackAuth

`emoji:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = emoji_api.emoji_list(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

