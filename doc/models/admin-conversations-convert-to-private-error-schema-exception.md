
# Admin Conversations Convert to Private Error Schema Exception

Schema for error response from admin.conversations.convertToPrivate

*This model accepts additional fields of type Any.*

## Structure

`AdminConversationsConvertToPrivateErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error1`](../../doc/models/error-1.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "default_org_wide_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

