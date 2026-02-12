
# Conversations Join Error Schema Exception

Schema for error response from conversations.join method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsJoinErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `str` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`ConversationsJoinErrorEnum`](../../doc/models/conversations-join-error-enum.md) | Required | - |
| `needed` | `str` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `provided` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_array_arg",
  "ok": "False",
  "callstack": "callstack2",
  "needed": "needed4",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

