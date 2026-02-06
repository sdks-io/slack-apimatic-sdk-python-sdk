
# Api Method Users Get Presence

Generated from users.getPresence with shasum e7251aec575d8863f9e0eb38663ae9dc26655f65

*This model accepts additional fields of type Any.*

## Structure

`ApiMethodUsersGetPresence`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `auto_away` | `bool` | Optional | - |
| `connection_count` | `int` | Optional | - |
| `last_activity` | `int` | Optional | - |
| `manual_away` | `bool` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `online` | `bool` | Optional | - |
| `presence` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "presence": "presence8",
  "auto_away": false,
  "connection_count": 42,
  "last_activity": 166,
  "manual_away": false,
  "online": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

