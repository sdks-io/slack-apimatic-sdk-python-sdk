
# Auth Test Success Schema

Schema for successful response auth.test method

*This model accepts additional fields of type Any.*

## Structure

`AuthTestSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `bot_id` | `str` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `is_enterprise_install` | `bool` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `team` | `str` | Required | - |
| `team_id` | `str` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `url` | `str` | Required | - |
| `user` | `str` | Required | - |
| `user_id` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "team": "team0",
  "team_id": "team_id4",
  "url": "url4",
  "user": "user0",
  "user_id": "user_id8",
  "bot_id": "bot_id6",
  "is_enterprise_install": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

