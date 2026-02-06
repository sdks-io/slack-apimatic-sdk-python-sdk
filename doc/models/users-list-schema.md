
# Users List Schema

Schema for successful response from users.list method

*This model accepts additional fields of type Any.*

## Structure

`UsersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cache_ts` | `int` | Required | - |
| `members` | `List[Any]` | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `response_metadata` | `Any` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "cache_ts": 154,
  "members": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "response_metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

