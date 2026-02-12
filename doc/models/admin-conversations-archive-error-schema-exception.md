
# Admin Conversations Archive Error Schema Exception

Schema for error response from admin.conversations.archive

*This model accepts additional fields of type Any.*

## Structure

`AdminConversationsArchiveErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsArchiveErrorEnum`](../../doc/models/admin-conversations-archive-error-enum.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "already_archived",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

