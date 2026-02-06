
# Conversations Close Success Schema

Schema for successful response conversations.close method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsCloseSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `already_closed` | `bool` | Optional | - |
| `no_op` | `bool` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "already_closed": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

