
# Chat Get Permalink Success Schema

Schema for successful response chat.getPermalink

*This model accepts additional fields of type Any.*

## Structure

`ChatGetPermalinkSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `str` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `permalink` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "ok": "True",
  "permalink": "permalink4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

