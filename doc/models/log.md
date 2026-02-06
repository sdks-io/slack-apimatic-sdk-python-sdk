
# Log

*This model accepts additional fields of type Any.*

## Structure

`Log`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `admin_app_id` | `str` | Optional | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `app_id` | `str` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `app_type` | `str` | Required | - |
| `change_type` | `str` | Required | - |
| `channel` | `str` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `date` | `str` | Required | - |
| `scope` | `str` | Required | - |
| `service_id` | `str` | Optional | - |
| `service_type` | `str` | Optional | - |
| `user_id` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `user_name` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "admin_app_id": "admin_app_id2",
  "app_id": "app_id2",
  "app_type": "app_type8",
  "change_type": "change_type2",
  "channel": "channel0",
  "date": "date0",
  "scope": "scope8",
  "service_id": "service_id6",
  "service_type": "service_type0",
  "user_id": "user_id2",
  "user_name": "user_name0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

