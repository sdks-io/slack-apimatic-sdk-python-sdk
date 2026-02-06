
# Conversations Leave Success Schema

Schema for successful response from conversations.leave method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsLeaveSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `not_in_channel` | `bool` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "not_in_channel": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

