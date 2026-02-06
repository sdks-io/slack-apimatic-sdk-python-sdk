
# Default Error Template Exception

This method either only returns a brief _not OK_ response or a verbose schema is not available for this method.

*This model accepts additional fields of type Any.*

## Structure

`DefaultErrorTemplateException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

