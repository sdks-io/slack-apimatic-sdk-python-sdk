
# Migration Exchange Success Schema

Schema for successful response from migration.exchange method

*This model accepts additional fields of type Any.*

## Structure

`MigrationExchangeSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `enterprise_id` | `str` | Required | - |
| `invalid_user_ids` | `List[str]` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `team_id` | `str` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `user_id_map` | `Any` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id8",
  "ok": "True",
  "team_id": "team_id8",
  "invalid_user_ids": [
    "invalid_user_ids6"
  ],
  "user_id_map": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

