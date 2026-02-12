
# Conversations Invite Error Schema 1 Exception

Schema for error response from conversations.invite method

*This model accepts additional fields of type Any.*

## Structure

`ConversationsInviteErrorSchema1Exception`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `str` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`ConversationsInviteErrorEnum`](../../doc/models/conversations-invite-error-enum.md) | Optional | - |
| `errors` | [`List[ErrorsIsReturnedWhenAnErrorAssociatesAnUser]`](../../doc/models/errors-is-returned-when-an-error-associates-an-user.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `needed` | `str` | Optional | - |
| `ok` | `str` | Required, Constant | **Value**: `"False"` |
| `provided` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "False",
  "callstack": "callstack2",
  "error": "invalid_post_type",
  "errors": [
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "needed": "needed6",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

