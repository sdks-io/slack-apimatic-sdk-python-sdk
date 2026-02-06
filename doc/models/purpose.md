
# Purpose

*This model accepts additional fields of type Any.*

## Structure

`Purpose`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `creator` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{8,}$\|^$` |
| `last_set` | `int` | Required | - |
| `value` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "creator": "creator6",
  "last_set": 108,
  "value": "value0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

