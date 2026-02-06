
# Usergroups Users List Schema

Schema for successful response from usergroups.users.list method

*This model accepts additional fields of type Any.*

## Structure

`UsergroupsUsersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `users` | `List[str]` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "users": [
    "users3"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

