
# Errors Is Returned When an Error Associates an User

*This model accepts additional fields of type Any.*

## Structure

`ErrorsIsReturnedWhenAnErrorAssociatesAnUser`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`ConversationsInviteErrorEnum`](../../doc/models/conversations-invite-error-enum.md) | Required | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `user` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "error": "cant_invite",
  "ok": "False",
  "user": "user8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

