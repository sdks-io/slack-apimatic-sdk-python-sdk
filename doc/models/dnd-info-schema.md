
# Dnd Info Schema

Schema for successful response from dnd.info method

*This model accepts additional fields of type Any.*

## Structure

`DndInfoSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `dnd_enabled` | `bool` | Required | - |
| `next_dnd_end_ts` | `int` | Required | - |
| `next_dnd_start_ts` | `int` | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `snooze_enabled` | `bool` | Optional | - |
| `snooze_endtime` | `int` | Optional | - |
| `snooze_remaining` | `int` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 138,
  "next_dnd_start_ts": 198,
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 96,
  "snooze_remaining": 96,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

