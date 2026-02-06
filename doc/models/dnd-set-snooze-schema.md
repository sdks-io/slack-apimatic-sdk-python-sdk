
# Dnd Set Snooze Schema

Schema for successful response from dnd.setSnooze method

*This model accepts additional fields of type Any.*

## Structure

`DndSetSnoozeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `snooze_enabled` | `bool` | Required | - |
| `snooze_endtime` | `int` | Required | - |
| `snooze_remaining` | `int` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 8,
  "snooze_remaining": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

