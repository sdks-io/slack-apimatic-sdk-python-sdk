
# Profile 1

*This model accepts additional fields of type Any.*

## Structure

`Profile1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `avatar_hash` | `str` | Required | **Constraints**: *Pattern*: `^[0-9a-f]{12}$` |
| `image_1024` | `str` | Required | - |
| `image_192` | `str` | Required | - |
| `image_24` | `str` | Required | - |
| `image_32` | `str` | Required | - |
| `image_48` | `str` | Required | - |
| `image_512` | `str` | Required | - |
| `image_72` | `str` | Required | - |
| `image_original` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash6",
  "image_1024": "image_10242",
  "image_192": "image_1922",
  "image_24": "image_242",
  "image_32": "image_322",
  "image_48": "image_484",
  "image_512": "image_5128",
  "image_72": "image_720",
  "image_original": "image_original2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

