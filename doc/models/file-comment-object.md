
# File Comment Object

*This model accepts additional fields of type Any.*

## Structure

`FileCommentObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `comment` | `str` | Required | - |
| `created` | `int` | Required | - |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^Fc[A-Z0-9]{8,}$` |
| `is_intro` | `bool` | Required | - |
| `is_starred` | `bool` | Optional | - |
| `num_stars` | `int` | Optional | - |
| `pinned_info` | `Any` | Optional | - |
| `pinned_to` | `List[str]` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `reactions` | [`List[ReactionObject]`](../../doc/models/reaction-object.md) | Optional | - |
| `timestamp` | `int` | Required | - |
| `user` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "comment": "comment2",
  "created": 212,
  "id": "id4",
  "is_intro": false,
  "is_starred": false,
  "num_stars": 180,
  "pinned_info": {
    "key1": "val1",
    "key2": "val2"
  },
  "pinned_to": [
    "pinned_to8",
    "pinned_to9"
  ],
  "reactions": [
    {
      "count": 208,
      "name": "name8",
      "users": [
        "users5",
        "users6",
        "users7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "count": 208,
      "name": "name8",
      "users": [
        "users5",
        "users6",
        "users7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "timestamp": 66,
  "user": "user4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

