
# Chat Me Message Schema

Schema for successful response from chat.meMessage method

*This model accepts additional fields of type Any.*

## Structure

`ChatMeMessageSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `str` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `ts` | `str` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "channel": "channel0",
  "ts": "ts6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

