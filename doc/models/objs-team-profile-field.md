
# Objs Team Profile Field

*This model accepts additional fields of type Any.*

## Structure

`ObjsTeamProfileField`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `field_name` | `str` | Optional | - |
| `hint` | `str` | Required | - |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^X[a-zA-Z0-9]{9,}$` |
| `is_hidden` | `bool` | Optional | - |
| `label` | `str` | Required | - |
| `options` | `Any` | Optional | - |
| `ordering` | `float` | Required | - |
| `possible_values` | `List[str]` | Optional | - |
| `mtype` | [`Type`](../../doc/models/type.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "field_name": "field_name4",
  "hint": "hint0",
  "id": "id0",
  "is_hidden": false,
  "label": "label0",
  "options": {
    "key1": "val1",
    "key2": "val2"
  },
  "ordering": 211.1,
  "possible_values": [
    "possible_values1",
    "possible_values2"
  ],
  "type": "options_list",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

