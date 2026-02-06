
# Chat Post Ephemeral Success Schema

Schema for successful response from chat.postEphemeral method

*This model accepts additional fields of type Any.*

## Structure

`ChatPostEphemeralSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `message_ts` | `str` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "message_ts": "message_ts0",
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

