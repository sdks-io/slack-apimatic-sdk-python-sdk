
# Conversations Invite Error Schema

Schema for successful response from conversations.invite method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsInviteErrorSchema`

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

