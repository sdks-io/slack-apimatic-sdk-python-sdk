# Admin Conversations Ekm

```python
admin_conversations_ekm_api = client.admin_conversations_ekm
```

## Class Name

`AdminConversationsEkmApi`


# Admin Conversations Ekm List Original Connected Channel Info

List all disconnected channels—i.e., channels that were once connected to other workspaces and then disconnected—and the corresponding original channel IDs for key revocation with EKM.

API method documentation: [https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo](https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo)

```python
def admin_conversations_ekm_list_original_connected_channel_info(self,
                                                                token,
                                                                channel_ids=None,
                                                                team_ids=None,
                                                                limit=None,
                                                                cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channel_ids` | `str` | Query, Optional | A comma-separated list of channels to filter to. |
| `team_ids` | `str` | Query, Optional | A comma-separated list of the workspaces to which the channels you would like returned belong. |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `str` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = admin_conversations_ekm_api.admin_conversations_ekm_list_original_connected_channel_info(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

