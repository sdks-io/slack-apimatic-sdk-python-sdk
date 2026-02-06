
# Conversations Rename Success Schema

Schema for successful response from conversations.rename method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsRenameSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `Any` | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

