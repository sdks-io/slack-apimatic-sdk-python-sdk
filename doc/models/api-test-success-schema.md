
# Api Test Success Schema

Schema for successful response api.test method

*This model accepts additional fields of type Any.*

## Structure

`ApiTestSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

