
# Scopes

*This model accepts additional fields of type Any.*

## Structure

`Scopes`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `app_home` | `List[str]` | Optional | - |
| `channel` | `List[str]` | Optional | - |
| `group` | `List[str]` | Optional | - |
| `im` | `List[str]` | Optional | - |
| `mpim` | `List[str]` | Optional | - |
| `team` | `List[str]` | Optional | - |
| `user` | `List[str]` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "app_home": [
    "app_home2",
    "app_home1",
    "app_home0"
  ],
  "channel": [
    "channel0",
    "channel9"
  ],
  "group": [
    "group9"
  ],
  "im": [
    "im1",
    "im0",
    "im9"
  ],
  "mpim": [
    "mpim0"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

