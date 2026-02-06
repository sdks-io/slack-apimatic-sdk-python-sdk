# Admin Conversations

```python
admin_conversations_api = client.admin_conversations
```

## Class Name

`AdminConversationsApi`

## Methods

* [Admin Conversations Archive](../../doc/controllers/admin-conversations.md#admin-conversations-archive)
* [Admin Conversations Convert to Private](../../doc/controllers/admin-conversations.md#admin-conversations-convert-to-private)
* [Admin Conversations Create](../../doc/controllers/admin-conversations.md#admin-conversations-create)
* [Admin Conversations Delete](../../doc/controllers/admin-conversations.md#admin-conversations-delete)
* [Admin Conversations Disconnect Shared](../../doc/controllers/admin-conversations.md#admin-conversations-disconnect-shared)
* [Admin Conversations Get Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-get-conversation-prefs)
* [Admin Conversations Get Teams](../../doc/controllers/admin-conversations.md#admin-conversations-get-teams)
* [Admin Conversations Invite](../../doc/controllers/admin-conversations.md#admin-conversations-invite)
* [Admin Conversations Rename](../../doc/controllers/admin-conversations.md#admin-conversations-rename)
* [Admin Conversations Search](../../doc/controllers/admin-conversations.md#admin-conversations-search)
* [Admin Conversations Set Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-set-conversation-prefs)
* [Admin Conversations Set Teams](../../doc/controllers/admin-conversations.md#admin-conversations-set-teams)
* [Admin Conversations Unarchive](../../doc/controllers/admin-conversations.md#admin-conversations-unarchive)


# Admin Conversations Archive

Archive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.archive](https://api.slack.com/methods/admin.conversations.archive)

```python
def admin_conversations_archive(self,
                               token,
                               channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to archive. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsArchiveSchema`](../../doc/models/admin-conversations-archive-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_archive(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsArchiveErrorSchemaException`](../../doc/models/admin-conversations-archive-error-schema-exception.md) |


# Admin Conversations Convert to Private

Convert a public channel to a private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.convertToPrivate](https://api.slack.com/methods/admin.conversations.convertToPrivate)

```python
def admin_conversations_convert_to_private(self,
                                          token,
                                          channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to convert to private. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsConvertToPrivateSchema`](../../doc/models/admin-conversations-convert-to-private-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_convert_to_private(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsConvertToPrivateErrorSchemaException`](../../doc/models/admin-conversations-convert-to-private-error-schema-exception.md) |


# Admin Conversations Create

Create a public or private channel-based conversation.

API method documentation: [https://api.slack.com/methods/admin.conversations.create](https://api.slack.com/methods/admin.conversations.create)

```python
def admin_conversations_create(self,
                              token,
                              name,
                              is_private,
                              description=None,
                              org_wide=None,
                              team_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `name` | `str` | Form, Required | Name of the public or private channel to create. |
| `is_private` | `bool` | Form, Required | When `true`, creates a private channel instead of a public channel |
| `description` | `str` | Form, Optional | Description of the public or private channel to create. |
| `org_wide` | `bool` | Form, Optional | When `true`, the channel will be available org-wide. Note: if the channel is not `org_wide=true`, you must specify a `team_id` for this channel |
| `team_id` | `str` | Form, Optional | The workspace to create the channel in. Note: this argument is required unless you set `org_wide=true`. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsCreateSchema`](../../doc/models/admin-conversations-create-schema.md).

## Example Usage

```python
token = 'token6'

name = 'name0'

is_private = False

result = admin_conversations_api.admin_conversations_create(
    token,
    name,
    is_private
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsCreateErrorSchemaException`](../../doc/models/admin-conversations-create-error-schema-exception.md) |


# Admin Conversations Delete

Delete a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.delete](https://api.slack.com/methods/admin.conversations.delete)

```python
def admin_conversations_delete(self,
                              token,
                              channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to delete. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsDeleteSchema`](../../doc/models/admin-conversations-delete-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_delete(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsDeleteErrorSchemaException`](../../doc/models/admin-conversations-delete-error-schema-exception.md) |


# Admin Conversations Disconnect Shared

Disconnect a connected channel from one or more workspaces.

API method documentation: [https://api.slack.com/methods/admin.conversations.disconnectShared](https://api.slack.com/methods/admin.conversations.disconnectShared)

```python
def admin_conversations_disconnect_shared(self,
                                         token,
                                         channel_id,
                                         leaving_team_ids=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to be disconnected from some workspaces. |
| `leaving_team_ids` | `str` | Form, Optional | The team to be removed from the channel. Currently only a single team id can be specified. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsRenameSchema`](../../doc/models/admin-conversations-rename-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_disconnect_shared(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsDisconnectSharedErrorSchemaException`](../../doc/models/admin-conversations-disconnect-shared-error-schema-exception.md) |


# Admin Conversations Get Conversation Prefs

Get conversation preferences for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.getConversationPrefs](https://api.slack.com/methods/admin.conversations.getConversationPrefs)

```python
def admin_conversations_get_conversation_prefs(self,
                                              token,
                                              channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channel_id` | `str` | Query, Required | The channel to get preferences for. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsGetConversationPrefsSchema`](../../doc/models/admin-conversations-get-conversation-prefs-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_get_conversation_prefs(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchemaException`](../../doc/models/admin-conversations-unarchive-error-schema-exception.md) |


# Admin Conversations Get Teams

Get all the workspaces a given public or private channel is connected to within this Enterprise org.

API method documentation: [https://api.slack.com/methods/admin.conversations.getTeams](https://api.slack.com/methods/admin.conversations.getTeams)

```python
def admin_conversations_get_teams(self,
                                 token,
                                 channel_id,
                                 cursor=None,
                                 limit=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channel_id` | `str` | Query, Required | The channel to determine connected workspaces within the organization for. |
| `cursor` | `str` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsGetTeamsSchema`](../../doc/models/admin-conversations-get-teams-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_get_teams(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsGetTeamsErrorSchemaException`](../../doc/models/admin-conversations-get-teams-error-schema-exception.md) |


# Admin Conversations Invite

Invite a user to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.invite](https://api.slack.com/methods/admin.conversations.invite)

```python
def admin_conversations_invite(self,
                              token,
                              user_ids,
                              channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `user_ids` | `str` | Form, Required | The users to invite. |
| `channel_id` | `str` | Form, Required | The channel that the users will be invited to. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsInviteSchema`](../../doc/models/admin-conversations-invite-schema.md).

## Example Usage

```python
token = 'token6'

user_ids = 'user_ids4'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_invite(
    token,
    user_ids,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsInviteErrorSchemaException`](../../doc/models/admin-conversations-invite-error-schema-exception.md) |


# Admin Conversations Rename

Rename a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.rename](https://api.slack.com/methods/admin.conversations.rename)

```python
def admin_conversations_rename(self,
                              token,
                              channel_id,
                              name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to rename. |
| `name` | `str` | Form, Required | - |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsRenameSchema1`](../../doc/models/admin-conversations-rename-schema-1.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

name = 'name0'

result = admin_conversations_api.admin_conversations_rename(
    token,
    channel_id,
    name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema2Exception`](../../doc/models/admin-conversations-unarchive-error-schema-2-exception.md) |


# Admin Conversations Search

Search for public or private channels in an Enterprise organization.

API method documentation: [https://api.slack.com/methods/admin.conversations.search](https://api.slack.com/methods/admin.conversations.search)

```python
def admin_conversations_search(self,
                              token,
                              team_ids=None,
                              query=None,
                              limit=None,
                              cursor=None,
                              search_channel_types=None,
                              sort=None,
                              sort_dir=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `team_ids` | `str` | Query, Optional | Comma separated string of team IDs, signifying the workspaces to search through. |
| `query` | `str` | Query, Optional | Name of the the channel to query by. |
| `limit` | `int` | Query, Optional | Maximum number of items to be returned. Must be between 1 - 20 both inclusive. Default is 10. |
| `cursor` | `str` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `search_channel_types` | `str` | Query, Optional | The type of channel to include or exclude in the search. For example `private` will search private channels, while `private_exclude` will exclude them. For a full list of types, check the [Types section](#types). |
| `sort` | `str` | Query, Optional | Possible values are `relevant` (search ranking based on what we think is closest), `name` (alphabetical), `member_count` (number of users in the channel), and `created` (date channel was created). You can optionally pair this with the `sort_dir` arg to change how it is sorted |
| `sort_dir` | `str` | Query, Optional | Sort direction. Possible values are `asc` for ascending order like (1, 2, 3) or (a, b, c), and `desc` for descending order like (3, 2, 1) or (c, b, a) |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsSearchSchema`](../../doc/models/admin-conversations-search-schema.md).

## Example Usage

```python
token = 'token6'

result = admin_conversations_api.admin_conversations_search(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsSearchErrorSchemaException`](../../doc/models/admin-conversations-search-error-schema-exception.md) |


# Admin Conversations Set Conversation Prefs

Set the posting permissions for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setConversationPrefs](https://api.slack.com/methods/admin.conversations.setConversationPrefs)

```python
def admin_conversations_set_conversation_prefs(self,
                                              token,
                                              channel_id,
                                              prefs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to set the prefs for |
| `prefs` | `str` | Form, Required | The prefs for this channel in a stringified JSON format. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsSetConversationPrefsSchema`](../../doc/models/admin-conversations-set-conversation-prefs-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

prefs = 'prefs0'

result = admin_conversations_api.admin_conversations_set_conversation_prefs(
    token,
    channel_id,
    prefs
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsSetConversationPrefsErrorSchemaException`](../../doc/models/admin-conversations-set-conversation-prefs-error-schema-exception.md) |


# Admin Conversations Set Teams

Set the workspaces in an Enterprise grid org that connect to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setTeams](https://api.slack.com/methods/admin.conversations.setTeams)

```python
def admin_conversations_set_teams(self,
                                 token,
                                 channel_id,
                                 team_id=None,
                                 target_team_ids=None,
                                 org_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The encoded `channel_id` to add or remove to workspaces. |
| `team_id` | `str` | Form, Optional | The workspace to which the channel belongs. Omit this argument if the channel is a cross-workspace shared channel. |
| `target_team_ids` | `str` | Form, Optional | A comma-separated list of workspaces to which the channel should be shared. Not required if the channel is being shared org-wide. |
| `org_channel` | `bool` | Form, Optional | True if channel has to be converted to an org channel |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_set_teams(
    token,
    channel_id
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


# Admin Conversations Unarchive

Unarchive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.unarchive](https://api.slack.com/methods/admin.conversations.unarchive)

```python
def admin_conversations_unarchive(self,
                                 token,
                                 channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channel_id` | `str` | Form, Required | The channel to unarchive. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AdminConversationsUnarchiveSchema`](../../doc/models/admin-conversations-unarchive-schema.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_api.admin_conversations_unarchive(
    token,
    channel_id
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema3Exception`](../../doc/models/admin-conversations-unarchive-error-schema-3-exception.md) |

