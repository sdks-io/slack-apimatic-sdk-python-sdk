# Admin Conversations Restrict Access

```python
admin_conversations_restrict_access_api = client.admin_conversations_restrict_access
```

## Class Name

`AdminConversationsRestrictAccessApi`

## Methods

* [Admin Conversations Restrict Access Add Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-add-group)
* [Admin Conversations Restrict Access List Groups](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-list-groups)
* [Admin Conversations Restrict Access Remove Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-remove-group)


# Admin Conversations Restrict Access Add Group

Add an allowlist of IDP groups for accessing a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup)

```python
def admin_conversations_restrict_access_add_group(self,
                                                 token,
                                                 group_id,
                                                 channel_id,
                                                 team_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `group_id` | `str` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to be an allowlist for the private channel. |
| `channel_id` | `str` | Form, Required | The channel to link this group to. |
| `team_id` | `str` | Form, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

group_id = 'group_id0'

channel_id = 'channel_id4'

result = admin_conversations_restrict_access_api.admin_conversations_restrict_access_add_group(
    token,
    group_id,
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


# Admin Conversations Restrict Access List Groups

List all IDP Groups linked to a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups](https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups)

```python
def admin_conversations_restrict_access_list_groups(self,
                                                   token,
                                                   channel_id,
                                                   team_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channel_id` | `str` | Query, Required | - |
| `team_id` | `str` | Query, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

channel_id = 'channel_id4'

result = admin_conversations_restrict_access_api.admin_conversations_restrict_access_list_groups(
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


# Admin Conversations Restrict Access Remove Group

Remove a linked IDP group linked from a private channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup)

```python
def admin_conversations_restrict_access_remove_group(self,
                                                    token,
                                                    team_id,
                                                    group_id,
                                                    channel_id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `team_id` | `str` | Form, Required | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |
| `group_id` | `str` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to remove from the private channel. |
| `channel_id` | `str` | Form, Required | The channel to remove the linked group from. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

team_id = 'team_id6'

group_id = 'group_id0'

channel_id = 'channel_id4'

result = admin_conversations_restrict_access_api.admin_conversations_restrict_access_remove_group(
    token,
    team_id,
    group_id,
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

