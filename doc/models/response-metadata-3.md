
# Response Metadata 3

*This model accepts additional fields of type Any.*

## Structure

`ResponseMetadata3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `warnings` | `List[str]` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "warnings": [
    "warnings4",
    "warnings5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

