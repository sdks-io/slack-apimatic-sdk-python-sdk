
# Subteam Usergroup Object

*This model accepts additional fields of type Any.*

## Structure

`SubteamUsergroupObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `auto_provision` | `bool` | Required | - |
| `auto_type` | `Any` | Required | - |
| `channel_count` | `int` | Optional | - |
| `created_by` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `date_create` | `int` | Required | - |
| `date_delete` | `int` | Required | - |
| `date_update` | `int` | Required | - |
| `deleted_by` | `Any` | Required | - |
| `description` | `str` | Required | - |
| `enterprise_subteam_id` | `str` | Required | - |
| `handle` | `str` | Required | - |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^S[A-Z0-9]{2,}$` |
| `is_external` | `bool` | Required | - |
| `is_subteam` | `bool` | Required | - |
| `is_usergroup` | `bool` | Required | - |
| `name` | `str` | Required | - |
| `prefs` | [`Prefs`](../../doc/models/prefs.md) | Required | - |
| `team_id` | `str` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `updated_by` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `user_count` | `int` | Optional | - |
| `users` | `List[str]` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "auto_provision": false,
  "auto_type": {
    "key1": "val1",
    "key2": "val2"
  },
  "channel_count": 140,
  "created_by": "created_by4",
  "date_create": 240,
  "date_delete": 32,
  "date_update": 18,
  "deleted_by": {
    "key1": "val1",
    "key2": "val2"
  },
  "description": "description2",
  "enterprise_subteam_id": "enterprise_subteam_id6",
  "handle": "handle4",
  "id": "id8",
  "is_external": false,
  "is_subteam": false,
  "is_usergroup": false,
  "name": "name8",
  "prefs": {
    "channels": [
      "channels5",
      "channels4"
    ],
    "groups": [
      "groups4",
      "groups5",
      "groups6"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team_id": "team_id8",
  "updated_by": "updated_by2",
  "user_count": 110,
  "users": [
    "users5",
    "users4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

