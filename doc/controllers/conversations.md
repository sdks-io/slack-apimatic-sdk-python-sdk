# Conversations

```python
conversations_api = client.conversations
```

## Class Name

`ConversationsApi`

## Methods

* [Conversations Archive](../../doc/controllers/conversations.md#conversations-archive)
* [Conversations Close](../../doc/controllers/conversations.md#conversations-close)
* [Conversations Create](../../doc/controllers/conversations.md#conversations-create)
* [Conversations History](../../doc/controllers/conversations.md#conversations-history)
* [Conversations Info](../../doc/controllers/conversations.md#conversations-info)
* [Conversations Invite](../../doc/controllers/conversations.md#conversations-invite)
* [Conversations Join](../../doc/controllers/conversations.md#conversations-join)
* [Conversations Kick](../../doc/controllers/conversations.md#conversations-kick)
* [Conversations Leave](../../doc/controllers/conversations.md#conversations-leave)
* [Conversations List](../../doc/controllers/conversations.md#conversations-list)
* [Conversations Mark](../../doc/controllers/conversations.md#conversations-mark)
* [Conversations Members](../../doc/controllers/conversations.md#conversations-members)
* [Conversations Open](../../doc/controllers/conversations.md#conversations-open)
* [Conversations Rename](../../doc/controllers/conversations.md#conversations-rename)
* [Conversations Replies](../../doc/controllers/conversations.md#conversations-replies)
* [Conversations Set Purpose](../../doc/controllers/conversations.md#conversations-set-purpose)
* [Conversations Set Topic](../../doc/controllers/conversations.md#conversations-set-topic)
* [Conversations Unarchive](../../doc/controllers/conversations.md#conversations-unarchive)


# Conversations Archive

Archives a conversation.

API method documentation: [https://api.slack.com/methods/conversations.archive](https://api.slack.com/methods/conversations.archive)

```python
def conversations_archive(self,
                         token=None,
                         channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | ID of conversation to archive |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsArchiveSuccessSchema`](../../doc/models/conversations-archive-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_archive()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsArchiveErrorSchemaException`](../../doc/models/conversations-archive-error-schema-exception.md) |


# Conversations Close

Closes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.close](https://api.slack.com/methods/conversations.close)

```python
def conversations_close(self,
                       token=None,
                       channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | Conversation to close. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsCloseSuccessSchema`](../../doc/models/conversations-close-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_close()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsCloseErrorSchemaException`](../../doc/models/conversations-close-error-schema-exception.md) |


# Conversations Create

Initiates a public or private channel-based conversation

API method documentation: [https://api.slack.com/methods/conversations.create](https://api.slack.com/methods/conversations.create)

```python
def conversations_create(self,
                        token=None,
                        name=None,
                        is_private=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `name` | `str` | Form, Optional | Name of the public or private channel to create |
| `is_private` | `bool` | Form, Optional | Create a private channel instead of a public one |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsCreateSuccessSchema`](../../doc/models/conversations-create-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_create()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when name already in use | [`ConversationsCreateErrorSchemaException`](../../doc/models/conversations-create-error-schema-exception.md) |


# Conversations History

Fetches a conversation's history of messages and events.

API method documentation: [https://api.slack.com/methods/conversations.history](https://api.slack.com/methods/conversations.history)

```python
def conversations_history(self,
                         token=None,
                         channel=None,
                         latest=None,
                         oldest=None,
                         inclusive=None,
                         limit=None,
                         cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `str` | Query, Optional | Conversation ID to fetch history for. |
| `latest` | `float` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `float` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `bool` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsHistorySuccessSchema`](../../doc/models/conversations-history-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_history()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsHistoryErrorSchemaException`](../../doc/models/conversations-history-error-schema-exception.md) |


# Conversations Info

Retrieve information about a conversation.

API method documentation: [https://api.slack.com/methods/conversations.info](https://api.slack.com/methods/conversations.info)

```python
def conversations_info(self,
                      token=None,
                      channel=None,
                      include_locale=None,
                      include_num_members=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `str` | Query, Optional | Conversation ID to learn more about |
| `include_locale` | `bool` | Query, Optional | Set this to `true` to receive the locale for this conversation. Defaults to `false` |
| `include_num_members` | `bool` | Query, Optional | Set to `true` to include the member count for the specified conversation. Defaults to `false` |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsInfoSuccessSchema`](../../doc/models/conversations-info-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_info()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when a channel cannot be found | [`ConversationsInfoErrorSchemaException`](../../doc/models/conversations-info-error-schema-exception.md) |


# Conversations Invite

Invites users to a channel.

API method documentation: [https://api.slack.com/methods/conversations.invite](https://api.slack.com/methods/conversations.invite)

```python
def conversations_invite(self,
                        token=None,
                        channel=None,
                        users=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | The ID of the public or private channel to invite user(s) to. |
| `users` | `str` | Form, Optional | A comma separated list of user IDs. Up to 1000 users may be listed. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsInviteErrorSchema`](../../doc/models/conversations-invite-error-schema.md).

## Example Usage

```python
result = conversations_api.conversations_invite()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when an invite is attempted on a conversation type that does not support it | [`ConversationsInviteErrorSchema1Exception`](../../doc/models/conversations-invite-error-schema-1-exception.md) |


# Conversations Join

Joins an existing conversation.

API method documentation: [https://api.slack.com/methods/conversations.join](https://api.slack.com/methods/conversations.join)

```python
def conversations_join(self,
                      token=None,
                      channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `channels:write` |
| `channel` | `str` | Form, Optional | ID of conversation to join |

## Requires scope

### slackAuth

`channels:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsJoinSuccessSchema`](../../doc/models/conversations-join-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_join()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the conversation is archived and cannot be joined | [`ConversationsJoinErrorSchemaException`](../../doc/models/conversations-join-error-schema-exception.md) |


# Conversations Kick

Removes a user from a conversation.

API method documentation: [https://api.slack.com/methods/conversations.kick](https://api.slack.com/methods/conversations.kick)

```python
def conversations_kick(self,
                      token=None,
                      channel=None,
                      user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | ID of conversation to remove user from. |
| `user` | `str` | Form, Optional | User ID to be removed. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsKickSuccessSchema`](../../doc/models/conversations-kick-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_kick()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when you attempt to kick yourself from a channel | [`ConversationsKickErrorSchemaException`](../../doc/models/conversations-kick-error-schema-exception.md) |


# Conversations Leave

Leaves a conversation.

API method documentation: [https://api.slack.com/methods/conversations.leave](https://api.slack.com/methods/conversations.leave)

```python
def conversations_leave(self,
                       token=None,
                       channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | Conversation to leave |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsLeaveSuccessSchema`](../../doc/models/conversations-leave-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_leave()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when attempting to leave a workspace's "general" channel | [`ConversationsLeaveErrorSchemaException`](../../doc/models/conversations-leave-error-schema-exception.md) |


# Conversations List

Lists all channels in a Slack team.

API method documentation: [https://api.slack.com/methods/conversations.list](https://api.slack.com/methods/conversations.list)

```python
def conversations_list(self,
                      token=None,
                      exclude_archived=None,
                      types=None,
                      limit=None,
                      cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `exclude_archived` | `bool` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `types` | `str` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsListSuccessSchema`](../../doc/models/conversations-list-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsListErrorSchemaException`](../../doc/models/conversations-list-error-schema-exception.md) |


# Conversations Mark

Sets the read cursor in a channel.

API method documentation: [https://api.slack.com/methods/conversations.mark](https://api.slack.com/methods/conversations.mark)

```python
def conversations_mark(self,
                      token=None,
                      channel=None,
                      ts=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | Channel or conversation to set the read cursor for. |
| `ts` | `float` | Form, Optional | Unique identifier of message you want marked as most recently seen in this conversation. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsMarkSuccessSchema`](../../doc/models/conversations-mark-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_mark()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsMarkErrorSchemaException`](../../doc/models/conversations-mark-error-schema-exception.md) |


# Conversations Members

Retrieve members of a conversation.

API method documentation: [https://api.slack.com/methods/conversations.members](https://api.slack.com/methods/conversations.members)

```python
def conversations_members(self,
                         token=None,
                         channel=None,
                         limit=None,
                         cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `str` | Query, Optional | ID of the conversation to retrieve members for |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsMembersSuccessSchema`](../../doc/models/conversations-members-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_members()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when an invalid cursor is provided | [`ConversationsMembersErrorSchemaException`](../../doc/models/conversations-members-error-schema-exception.md) |


# Conversations Open

Opens or resumes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.open](https://api.slack.com/methods/conversations.open)

```python
def conversations_open(self,
                      token=None,
                      channel=None,
                      users=None,
                      return_im=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | Resume a conversation by supplying an `im` or `mpim`'s ID. Or provide the `users` field instead. |
| `users` | `str` | Form, Optional | Comma separated lists of users. If only one user is included, this creates a 1:1 DM.  The ordering of the users is preserved whenever a multi-person direct message is returned. Supply a `channel` when not supplying `users`. |
| `return_im` | `bool` | Form, Optional | Boolean, indicates you want the full IM channel definition in the response. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsOpenSuccessSchema`](../../doc/models/conversations-open-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_open()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsOpenErrorSchemaException`](../../doc/models/conversations-open-error-schema-exception.md) |


# Conversations Rename

Renames a conversation.

API method documentation: [https://api.slack.com/methods/conversations.rename](https://api.slack.com/methods/conversations.rename)

```python
def conversations_rename(self,
                        token=None,
                        channel=None,
                        name=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | ID of conversation to rename |
| `name` | `str` | Form, Optional | New name for conversation. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsRenameSuccessSchema`](../../doc/models/conversations-rename-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_rename()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when the calling user is not a member of the conversation | [`ConversationsRenameErrorSchemaException`](../../doc/models/conversations-rename-error-schema-exception.md) |


# Conversations Replies

Retrieve a thread of messages posted to a conversation

API method documentation: [https://api.slack.com/methods/conversations.replies](https://api.slack.com/methods/conversations.replies)

```python
def conversations_replies(self,
                         token=None,
                         channel=None,
                         ts=None,
                         latest=None,
                         oldest=None,
                         inclusive=None,
                         limit=None,
                         cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `str` | Query, Optional | Conversation ID to fetch thread from. |
| `ts` | `float` | Query, Optional | Unique identifier of a thread's parent message. `ts` must be the timestamp of an existing message with 0 or more replies. If there are no replies then just the single message referenced by `ts` will return - it is just an ordinary, unthreaded message. |
| `latest` | `float` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `float` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `bool` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsRepliesSuccessSchema`](../../doc/models/conversations-replies-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_replies()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsRepliesErrorSchemaException`](../../doc/models/conversations-replies-error-schema-exception.md) |


# Conversations Set Purpose

Sets the purpose for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setPurpose](https://api.slack.com/methods/conversations.setPurpose)

```python
def conversations_set_purpose(self,
                             token=None,
                             channel=None,
                             purpose=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | Conversation to set the purpose of |
| `purpose` | `str` | Form, Optional | A new, specialer purpose |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsSetPurposeSuccessSchema`](../../doc/models/conversations-set-purpose-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_set_purpose()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsSetPurposeErrorSchemaException`](../../doc/models/conversations-set-purpose-error-schema-exception.md) |


# Conversations Set Topic

Sets the topic for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setTopic](https://api.slack.com/methods/conversations.setTopic)

```python
def conversations_set_topic(self,
                           token=None,
                           channel=None,
                           topic=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | Conversation to set the topic of |
| `topic` | `str` | Form, Optional | The new topic string. Does not support formatting or linkification. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsSetTopicSuccessSchema`](../../doc/models/conversations-set-topic-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_set_topic()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsSetTopicErrorSchemaException`](../../doc/models/conversations-set-topic-error-schema-exception.md) |


# Conversations Unarchive

Reverses conversation archival.

API method documentation: [https://api.slack.com/methods/conversations.unarchive](https://api.slack.com/methods/conversations.unarchive)

```python
def conversations_unarchive(self,
                           token=None,
                           channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `str` | Form, Optional | ID of conversation to unarchive |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ConversationsUnarchiveSuccessSchema`](../../doc/models/conversations-unarchive-success-schema.md).

## Example Usage

```python
result = conversations_api.conversations_unarchive()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsUnarchiveErrorSchemaException`](../../doc/models/conversations-unarchive-error-schema-exception.md) |

