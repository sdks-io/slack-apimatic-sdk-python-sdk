
# Login

*This model accepts additional fields of type Any.*

## Structure

`Login`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `count` | `int` | Required | - |
| `country` | `str` | Required | - |
| `date_first` | `int` | Required | - |
| `date_last` | `int` | Required | - |
| `ip` | `str` | Required | - |
| `isp` | `str` | Required | - |
| `region` | `str` | Required | - |
| `user_agent` | `str` | Required | - |
| `user_id` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `username` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "count": 110,
  "country": "country6",
  "date_first": 14,
  "date_last": 2,
  "ip": "ip6",
  "isp": "isp2",
  "region": "region8",
  "user_agent": "user_agent4",
  "user_id": "user_id0",
  "username": "username8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

