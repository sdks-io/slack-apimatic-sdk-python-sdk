
# Dnd End Snooze Schema

Schema for successful response from dnd.endSnooze method

*This model accepts additional fields of type Any.*

## Structure

`DndEndSnoozeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `dnd_enabled` | `bool` | Required | - |
| `next_dnd_end_ts` | `int` | Required | - |
| `next_dnd_start_ts` | `int` | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `snooze_enabled` | `bool` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 248,
  "next_dnd_start_ts": 88,
  "ok": "True",
  "snooze_enabled": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

