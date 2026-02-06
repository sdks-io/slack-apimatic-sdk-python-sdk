
# Objs Reminder

*This model accepts additional fields of type Any.*

## Structure

`ObjsReminder`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `complete_ts` | `int` | Optional | - |
| `creator` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^Rm[A-Z0-9]{8,}$` |
| `recurring` | `bool` | Required | - |
| `text` | `str` | Required | - |
| `time` | `int` | Optional | - |
| `user` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "complete_ts": 102,
  "creator": "creator4",
  "id": "id6",
  "recurring": false,
  "text": "text4",
  "time": 252,
  "user": "user6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

