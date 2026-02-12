
# Users Lookup by Email Error Schema Exception

Schema for error response from users.lookupByEmail method

*This model accepts additional fields of type Any.*

## Structure

`UsersLookupByEmailErrorSchemaException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `str` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`UsersLookupByEmailErrorEnum`](../../doc/models/users-lookup-by-email-error-enum.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_arg_name",
  "ok": "False",
  "callstack": "callstack4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

