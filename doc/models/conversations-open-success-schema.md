
# Conversations Open Success Schema

Schema for successful response from conversations.open method when opening channels, ims, mpims

*This model accepts additional fields of type Any.*

## Structure

`ConversationsOpenSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `already_open` | `bool` | Optional | - |
| `channel` | `Any` | Required | - |
| `no_op` | `bool` | Optional | - |
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
  "already_open": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

