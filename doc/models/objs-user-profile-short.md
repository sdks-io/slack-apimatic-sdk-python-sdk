
# Objs User Profile Short

*This model accepts additional fields of type Any.*

## Structure

`ObjsUserProfileShort`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `avatar_hash` | `str` | Required | - |
| `display_name` | `str` | Required | - |
| `display_name_normalized` | `str` | Optional | - |
| `first_name` | `str` | Required | - |
| `image_72` | `str` | Required | - |
| `is_restricted` | `bool` | Required | - |
| `is_ultra_restricted` | `bool` | Required | - |
| `name` | `str` | Required | - |
| `real_name` | `str` | Required | - |
| `real_name_normalized` | `str` | Optional | - |
| `team` | `str` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash2",
  "display_name": "display_name2",
  "display_name_normalized": "display_name_normalized2",
  "first_name": "first_name2",
  "image_72": "image_726",
  "is_restricted": false,
  "is_ultra_restricted": false,
  "name": "name2",
  "real_name": "real_name8",
  "real_name_normalized": "real_name_normalized4",
  "team": "team8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

