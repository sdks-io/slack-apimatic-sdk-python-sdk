
# Admin Conversations Get Teams Error Schema Exception

Schema for error response from admin.conversations.getTeams

*This model accepts additional fields of type Any.*

## Structure

`AdminConversationsGetTeamsErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsGetTeamsErrorEnum`](../../doc/models/admin-conversations-get-teams-error-enum.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "channel_type_not_supported",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

