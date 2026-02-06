
# Admin Conversations Unarchive Error Schema 3 Exception

Schema for error response from admin.conversations.unarchive

*This model accepts additional fields of type Any.*

## Structure

`AdminConversationsUnarchiveErrorSchema3Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error11`](../../doc/models/error-11.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "restricted_action",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

