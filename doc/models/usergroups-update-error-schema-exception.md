
# Usergroups Update Error Schema Exception

Schema for error response from usergroups.update method

*This model accepts additional fields of type Any.*

## Structure

`UsergroupsUpdateErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `str` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error86`](../../doc/models/error-86.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "token_revoked",
  "ok": "False",
  "callstack": "callstack2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

