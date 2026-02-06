
# Reminders List Schema

Schema for successful response from reminders.list method

*This model accepts additional fields of type Any.*

## Structure

`RemindersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `reminders` | [`List[ObjsReminder]`](../../doc/models/objs-reminder.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "reminders": [
    {
      "complete_ts": 28,
      "creator": "creator0",
      "id": "id2",
      "recurring": false,
      "text": "text2",
      "time": 186,
      "user": "user2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

