
# Chat Delete Success Schema

Schema for successful response of chat.delete method

*This model accepts additional fields of type Any.*

## Structure

`ChatDeleteSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `str` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `ts` | `str` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel4",
  "ok": "True",
  "ts": "ts2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

