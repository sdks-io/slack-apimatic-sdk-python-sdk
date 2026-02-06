# Chat Scheduled Messages

```python
chat_scheduled_messages_api = client.chat_scheduled_messages
```

## Class Name

`ChatScheduledMessagesApi`


# Chat Scheduled Messages List

Returns a list of scheduled messages.

API method documentation: [https://api.slack.com/methods/chat.scheduledMessages.list](https://api.slack.com/methods/chat.scheduledMessages.list)

```python
def chat_scheduled_messages_list(self,
                                token=None,
                                channel=None,
                                latest=None,
                                oldest=None,
                                limit=None,
                                cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `none` |
| `channel` | `str` | Query, Optional | The channel of the scheduled messages |
| `latest` | `float` | Query, Optional | A UNIX timestamp of the latest value in the time range |
| `oldest` | `float` | Query, Optional | A UNIX timestamp of the oldest value in the time range |
| `limit` | `int` | Query, Optional | Maximum number of original entries to return. |
| `cursor` | `str` | Query, Optional | For pagination purposes, this is the `cursor` value returned from a previous call to `chat.scheduledmessages.list` indicating where you want to start this call from. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatScheduledMessagesListSchema`](../../doc/models/chat-scheduled-messages-list-schema.md).

## Example Usage

```python
result = chat_scheduled_messages_api.chat_scheduled_messages_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the channel passed is invalid | [`ChatScheduledMessagesListErrorSchemaException`](../../doc/models/chat-scheduled-messages-list-error-schema-exception.md) |

