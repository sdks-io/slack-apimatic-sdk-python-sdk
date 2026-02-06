
# Prefs

*This model accepts additional fields of type Any.*

## Structure

`Prefs`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channels` | `List[str]` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `groups` | `List[str]` | Required | **Constraints**: *Pattern*: `^[G][A-Z0-9]{8,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels4",
    "channels5"
  ],
  "groups": [
    "groups6",
    "groups7"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

