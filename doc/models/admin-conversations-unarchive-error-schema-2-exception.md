
# Admin Conversations Unarchive Error Schema 2 Exception

Schema for error response from admin.conversations.rename

*This model accepts additional fields of type Any.*

## Structure

`AdminConversationsUnarchiveErrorSchema2Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsRenameErrorEnum`](../../doc/models/admin-conversations-rename-error-enum.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "name_taken",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

