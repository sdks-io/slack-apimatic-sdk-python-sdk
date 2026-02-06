
# Paging Object

*This model accepts additional fields of type Any.*

## Structure

`PagingObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `count` | `int` | Optional | - |
| `page` | `int` | Required | - |
| `pages` | `int` | Optional | - |
| `per_page` | `int` | Optional | - |
| `spill` | `int` | Optional | - |
| `total` | `int` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "count": 190,
  "page": 160,
  "pages": 28,
  "per_page": 72,
  "spill": 132,
  "total": 140,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

