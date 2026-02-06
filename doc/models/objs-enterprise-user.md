
# Objs Enterprise User

*This model accepts additional fields of type Any.*

## Structure

`ObjsEnterpriseUser`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `enterprise_id` | `str` | Required | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` |
| `enterprise_name` | `str` | Required | - |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^[WU][A-Z0-9]{8,}$` |
| `is_admin` | `bool` | Required | - |
| `is_owner` | `bool` | Required | - |
| `teams` | `List[str]` | Required | **Constraints**: *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id0",
  "enterprise_name": "enterprise_name0",
  "id": "id0",
  "is_admin": false,
  "is_owner": false,
  "teams": [
    "teams3",
    "teams4",
    "teams5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

