
# Conversations Archive Error Schema Exception

Schema for error response from conversations.archive method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsArchiveErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `str` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`ConversationsArchiveErrorEnum`](../../doc/models/conversations-archive-error-enum.md) | Required | - |
| `needed` | `str` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `provided` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "already_archived",
  "ok": "False",
  "callstack": "callstack2",
  "needed": "needed6",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

