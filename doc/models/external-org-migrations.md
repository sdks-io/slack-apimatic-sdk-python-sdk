
# External Org Migrations

*This model accepts additional fields of type Any.*

## Structure

`ExternalOrgMigrations`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `current` | [`List[Current]`](../../doc/models/current.md) | Required | - |
| `date_updated` | `int` | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "current": [
    {
      "date_started": 84,
      "team_id": "team_id0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "date_updated": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

