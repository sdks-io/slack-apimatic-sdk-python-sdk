
# Chat Update Success Schema

Schema for successful response of chat.update method

*This model accepts additional fields of type Any.*

## Structure

`ChatUpdateSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `str` | Required | - |
| `message` | [`MessageObject1`](../../doc/models/message-object-1.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `text` | `str` | Required | - |
| `ts` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "message": {
    "attachments": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      }
    ],
    "blocks": {
      "key1": "val1",
      "key2": "val2"
    },
    "text": "text0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "text": "text6",
  "ts": "ts8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

