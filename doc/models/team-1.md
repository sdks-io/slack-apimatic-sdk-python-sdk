
# Team 1

*This model accepts additional fields of type Any.*

## Structure

`Team1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `domain` | `str` | Required | - |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `name` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "domain": "domain0",
  "id": "id4",
  "name": "name4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

