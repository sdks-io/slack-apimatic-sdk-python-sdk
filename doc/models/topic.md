
# Topic

*This model accepts additional fields of type Any.*

## Structure

`Topic`

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
  "creator": "creator8",
  "last_set": 254,
  "value": "value2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

