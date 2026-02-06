
# Attachment

*This model accepts additional fields of type Any.*

## Structure

`Attachment`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fallback` | `str` | Optional | - |
| `id` | `int` | Required | - |
| `image_bytes` | `int` | Optional | - |
| `image_height` | `int` | Optional | - |
| `image_url` | `str` | Optional | - |
| `image_width` | `int` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "fallback": "fallback4",
  "id": 158,
  "image_bytes": 168,
  "image_height": 20,
  "image_url": "image_url6",
  "image_width": 146,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

