
# Conversations Create Error Schema Exception

Schema for error response from conversations.create method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsCreateErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `str` | Optional | Note: PHP callstack is only visible in dev/qa |
| `detail` | `str` | Optional | - |
| `error` | [`ConversationsCreateErrorEnum`](../../doc/models/conversations-create-error-enum.md) | Required | - |
| `needed` | `str` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `provided` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_array_arg",
  "ok": "False",
  "callstack": "callstack0",
  "detail": "detail4",
  "needed": "needed4",
  "provided": "provided0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

