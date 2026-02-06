
# Message Object 1

*This model accepts additional fields of type Any.*

## Structure

`MessageObject1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `attachments` | `List[Any]` | Optional | - |
| `blocks` | `Any` | Optional | - |
| `text` | `str` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "blocks": {
    "key1": "val1",
    "key2": "val2"
  },
  "text": "text4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

