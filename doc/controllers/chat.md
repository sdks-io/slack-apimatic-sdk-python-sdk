# Chat

```python
chat_api = client.chat
```

## Class Name

`ChatApi`

## Methods

* [Chat Delete](../../doc/controllers/chat.md#chat-delete)
* [Chat Delete Scheduled Message](../../doc/controllers/chat.md#chat-delete-scheduled-message)
* [Chat Get Permalink](../../doc/controllers/chat.md#chat-get-permalink)
* [Chat Me Message](../../doc/controllers/chat.md#chat-me-message)
* [Chat Post Ephemeral](../../doc/controllers/chat.md#chat-post-ephemeral)
* [Chat Post Message](../../doc/controllers/chat.md#chat-post-message)
* [Chat Schedule Message](../../doc/controllers/chat.md#chat-schedule-message)
* [Chat Unfurl](../../doc/controllers/chat.md#chat-unfurl)
* [Chat Update](../../doc/controllers/chat.md#chat-update)


# Chat Delete

Deletes a message.

API method documentation: [https://api.slack.com/methods/chat.delete](https://api.slack.com/methods/chat.delete)

```python
def chat_delete(self,
               token=None,
               ts=None,
               channel=None,
               as_user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `ts` | `float` | Form, Optional | Timestamp of the message to be deleted. |
| `channel` | `str` | Form, Optional | Channel containing the message to be deleted. |
| `as_user` | `bool` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatDeleteSuccessSchema`](../../doc/models/chat-delete-success-schema.md).

## Example Usage

```python
result = chat_api.chat_delete()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatDeleteErrorSchemaException`](../../doc/models/chat-delete-error-schema-exception.md) |


# Chat Delete Scheduled Message

Deletes a pending scheduled message from the queue.

API method documentation: [https://api.slack.com/methods/chat.deleteScheduledMessage](https://api.slack.com/methods/chat.deleteScheduledMessage)

```python
def chat_delete_scheduled_message(self,
                                 token,
                                 channel,
                                 scheduled_message_id,
                                 as_user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `str` | Form, Required | The channel the scheduled_message is posting to |
| `scheduled_message_id` | `str` | Form, Required | `scheduled_message_id` returned from call to chat.scheduleMessage |
| `as_user` | `bool` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatDeleteScheduledMessageSchema`](../../doc/models/chat-delete-scheduled-message-schema.md).

## Example Usage

```python
token = 'token6'

channel = 'channel4'

scheduled_message_id = 'scheduled_message_id8'

result = chat_api.chat_delete_scheduled_message(
    token,
    channel,
    scheduled_message_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if no message is found | [`ChatDeleteScheduledMessageErrorSchemaException`](../../doc/models/chat-delete-scheduled-message-error-schema-exception.md) |


# Chat Get Permalink

Retrieve a permalink URL for a specific extant message

API method documentation: [https://api.slack.com/methods/chat.getPermalink](https://api.slack.com/methods/chat.getPermalink)

```python
def chat_get_permalink(self,
                      token,
                      channel,
                      message_ts)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `none` |
| `channel` | `str` | Query, Required | The ID of the conversation or channel containing the message |
| `message_ts` | `str` | Query, Required | A message's `ts` value, uniquely identifying it within a channel |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatGetPermalinkSuccessSchema`](../../doc/models/chat-get-permalink-success-schema.md).

## Example Usage

```python
token = 'token6'

channel = 'channel4'

message_ts = 'message_ts4'

result = chat_api.chat_get_permalink(
    token,
    channel,
    message_ts
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error response when channel cannot be found | [`ChatGetPermalinkErrorSchemaException`](../../doc/models/chat-get-permalink-error-schema-exception.md) |


# Chat Me Message

Share a me message into a channel.

API method documentation: [https://api.slack.com/methods/chat.meMessage](https://api.slack.com/methods/chat.meMessage)

```python
def chat_me_message(self,
                   token=None,
                   channel=None,
                   text=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `str` | Form, Optional | Channel to send message to. Can be a public channel, private group or IM channel. Can be an encoded ID, or a name. |
| `text` | `str` | Form, Optional | Text of the message to send. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatMeMessageSchema`](../../doc/models/chat-me-message-schema.md).

## Example Usage

```python
result = chat_api.chat_me_message()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatMeMessageErrorSchemaException`](../../doc/models/chat-me-message-error-schema-exception.md) |


# Chat Post Ephemeral

Sends an ephemeral message to a user in a channel.

API method documentation: [https://api.slack.com/methods/chat.postEphemeral](https://api.slack.com/methods/chat.postEphemeral)

```python
def chat_post_ephemeral(self,
                       token,
                       channel,
                       user,
                       as_user=None,
                       attachments=None,
                       blocks=None,
                       icon_emoji=None,
                       icon_url=None,
                       link_names=None,
                       parse=None,
                       text=None,
                       thread_ts=None,
                       username=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `str` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. |
| `user` | `str` | Form, Required | `id` of the user who will receive the ephemeral message. The user should be in the channel specified by the `channel` argument. |
| `as_user` | `bool` | Form, Optional | Pass true to post the message as the authed user. Defaults to true if the chat:write:bot scope is not included. Otherwise, defaults to false. |
| `attachments` | `str` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `str` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `icon_emoji` | `str` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `icon_url` | `str` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `link_names` | `bool` | Form, Optional | Find and link channel names and usernames. |
| `parse` | `str` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `text` | `str` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `thread_ts` | `str` | Form, Optional | Provide another message's `ts` value to post this message in a thread. Avoid using a reply's `ts` value; use its parent's value instead. Ephemeral messages in threads are only shown if there is already an active thread. |
| `username` | `str` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatPostEphemeralSuccessSchema`](../../doc/models/chat-post-ephemeral-success-schema.md).

## Example Usage

```python
token = 'token6'

channel = 'channel4'

user = 'user0'

result = chat_api.chat_post_ephemeral(
    token,
    channel,
    user
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatPostEphemeralErrorSchemaException`](../../doc/models/chat-post-ephemeral-error-schema-exception.md) |


# Chat Post Message

Sends a message to a channel.

API method documentation: [https://api.slack.com/methods/chat.postMessage](https://api.slack.com/methods/chat.postMessage)

```python
def chat_post_message(self,
                     token,
                     channel,
                     as_user=None,
                     attachments=None,
                     blocks=None,
                     icon_emoji=None,
                     icon_url=None,
                     link_names=None,
                     mrkdwn=None,
                     parse=None,
                     reply_broadcast=None,
                     text=None,
                     thread_ts=None,
                     unfurl_links=None,
                     unfurl_media=None,
                     username=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `str` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `as_user` | `str` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [authorship](#authorship) below. |
| `attachments` | `str` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `str` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `icon_emoji` | `str` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `icon_url` | `str` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `link_names` | `bool` | Form, Optional | Find and link channel names and usernames. |
| `mrkdwn` | `bool` | Form, Optional | Disable Slack markup parsing by setting to `false`. Enabled by default. |
| `parse` | `str` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `reply_broadcast` | `bool` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |
| `text` | `str` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `thread_ts` | `str` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `unfurl_links` | `bool` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurl_media` | `bool` | Form, Optional | Pass false to disable unfurling of media content. |
| `username` | `str` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatPostMessageSuccessSchema`](../../doc/models/chat-post-message-success-schema.md).

## Example Usage

```python
token = 'token6'

channel = 'channel4'

result = chat_api.chat_post_message(
    token,
    channel
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if too many attachments are included | [`ChatPostMessageErrorSchemaException`](../../doc/models/chat-post-message-error-schema-exception.md) |


# Chat Schedule Message

Schedules a message to be sent to a channel.

API method documentation: [https://api.slack.com/methods/chat.scheduleMessage](https://api.slack.com/methods/chat.scheduleMessage)

```python
def chat_schedule_message(self,
                         token=None,
                         channel=None,
                         text=None,
                         post_at=None,
                         parse=None,
                         as_user=None,
                         link_names=None,
                         attachments=None,
                         blocks=None,
                         unfurl_links=None,
                         unfurl_media=None,
                         thread_ts=None,
                         reply_broadcast=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `str` | Form, Optional | Channel, private group, or DM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `text` | `str` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `post_at` | `str` | Form, Optional | Unix EPOCH timestamp of time in future to send the message. |
| `parse` | `str` | Form, Optional | Change how messages are treated. Defaults to `none`. See [chat.postMessage](chat.postMessage#formatting). |
| `as_user` | `bool` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [chat.postMessage](chat.postMessage#authorship). |
| `link_names` | `bool` | Form, Optional | Find and link channel names and usernames. |
| `attachments` | `str` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `str` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `unfurl_links` | `bool` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurl_media` | `bool` | Form, Optional | Pass false to disable unfurling of media content. |
| `thread_ts` | `float` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `reply_broadcast` | `bool` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatScheduleMessageSuccessSchema`](../../doc/models/chat-schedule-message-success-schema.md).

## Example Usage

```python
result = chat_api.chat_schedule_message()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the `post_at` is invalid (ex. in the past or too far into the future) | [`ChatScheduleMessageErrorSchemaException`](../../doc/models/chat-schedule-message-error-schema-exception.md) |


# Chat Unfurl

Provide custom unfurl behavior for user-posted URLs

API method documentation: [https://api.slack.com/methods/chat.unfurl](https://api.slack.com/methods/chat.unfurl)

```python
def chat_unfurl(self,
               token,
               channel,
               ts,
               unfurls=None,
               user_auth_message=None,
               user_auth_required=None,
               user_auth_url=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `links:write` |
| `channel` | `str` | Form, Required | Channel ID of the message |
| `ts` | `str` | Form, Required | Timestamp of the message to add unfurl behavior to. |
| `unfurls` | `str` | Form, Optional | URL-encoded JSON map with keys set to URLs featured in the the message, pointing to their unfurl blocks or message attachments. |
| `user_auth_message` | `str` | Form, Optional | Provide a simply-formatted string to send as an ephemeral message to the user as invitation to authenticate further and enable full unfurling behavior |
| `user_auth_required` | `bool` | Form, Optional | Set to `true` or `1` to indicate the user must install your Slack app to trigger unfurls for this domain |
| `user_auth_url` | `str` | Form, Optional | Send users to this custom URL where they will complete authentication in your app to fully trigger unfurling. Value should be properly URL-encoded. |

## Requires scope

### slackAuth

`links:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatUnfurlSuccessSchema`](../../doc/models/chat-unfurl-success-schema.md).

## Example Usage

```python
token = 'token6'

channel = 'channel4'

ts = 'ts2'

result = chat_api.chat_unfurl(
    token,
    channel,
    ts
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatUnfurlErrorSchemaException`](../../doc/models/chat-unfurl-error-schema-exception.md) |


# Chat Update

Updates a message.

API method documentation: [https://api.slack.com/methods/chat.update](https://api.slack.com/methods/chat.update)

```python
def chat_update(self,
               token,
               channel,
               ts,
               as_user=None,
               attachments=None,
               blocks=None,
               link_names=None,
               parse=None,
               text=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `str` | Form, Required | Channel containing the message to be updated. |
| `ts` | `str` | Form, Required | Timestamp of the message to be updated. |
| `as_user` | `str` | Form, Optional | Pass true to update the message as the authed user. [Bot users](/bot-users) in this context are considered authed users. |
| `attachments` | `str` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. This field is required when not presenting `text`. If you don't include this field, the message's previous `attachments` will be retained. To remove previous `attachments`, include an empty array for this field. |
| `blocks` | `str` | Form, Optional | A JSON-based array of [structured blocks](/block-kit/building), presented as a URL-encoded string. If you don't include this field, the message's previous `blocks` will be retained. To remove previous `blocks`, include an empty array for this field. |
| `link_names` | `str` | Form, Optional | Find and link channel names and usernames. Defaults to `none`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `none`. |
| `parse` | `str` | Form, Optional | Change how messages are treated. Defaults to `client`, unlike `chat.postMessage`. Accepts either `none` or `full`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `client`. |
| `text` | `str` | Form, Optional | New text for the message, using the [default formatting rules](/reference/surfaces/formatting). It's not required when presenting `blocks` or `attachments`. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ChatUpdateSuccessSchema`](../../doc/models/chat-update-success-schema.md).

## Example Usage

```python
token = 'token6'

channel = 'channel4'

ts = 'ts2'

result = chat_api.chat_update(
    token,
    channel,
    ts
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatUpdateErrorSchemaException`](../../doc/models/chat-update-error-schema-exception.md) |

