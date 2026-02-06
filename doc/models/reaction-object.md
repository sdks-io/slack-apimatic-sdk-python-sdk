
# Reaction Object

*This model accepts additional fields of type Any.*

## Structure

`ReactionObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `count` | `int` | Required | - |
| `name` | `str` | Required | - |
| `users` | `List[str]` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "count": 186,
  "name": "name6",
  "users": [
    "users3",
    "users2"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

