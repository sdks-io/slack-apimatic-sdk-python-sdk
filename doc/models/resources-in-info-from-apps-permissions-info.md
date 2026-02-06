
# Resources in Info From Apps Permissions Info

*This model accepts additional fields of type Any.*

## Structure

`ResourcesInInfoFromAppsPermissionsInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `excluded_ids` | `List[Any]` | Optional | - |
| `ids` | `List[Any]` | Required | - |
| `wildcard` | `bool` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "excluded_ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "wildcard": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

