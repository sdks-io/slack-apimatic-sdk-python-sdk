
# User Profile Object

*This model accepts additional fields of type Any.*

## Structure

`UserProfileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `always_active` | `bool` | Optional | - |
| `api_app_id` | `str` | Optional | **Constraints**: *Pattern*: `^(A[A-Z0-9]{1,})?$` |
| `avatar_hash` | `str` | Required | - |
| `bot_id` | `str` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `display_name` | `str` | Required | - |
| `display_name_normalized` | `str` | Required | - |
| `email` | `str` | Optional | - |
| `fields` | `List[Any]` | Required | - |
| `first_name` | `str` | Optional | - |
| `guest_expiration_ts` | `int` | Optional | - |
| `guest_invited_by` | `str` | Optional | - |
| `image_1024` | `str` | Optional | - |
| `image_192` | `str` | Optional | - |
| `image_24` | `str` | Optional | - |
| `image_32` | `str` | Optional | - |
| `image_48` | `str` | Optional | - |
| `image_512` | `str` | Optional | - |
| `image_72` | `str` | Optional | - |
| `image_original` | `str` | Optional | - |
| `is_app_user` | `bool` | Optional | - |
| `is_custom_image` | `bool` | Optional | - |
| `is_restricted` | `bool` | Optional | - |
| `is_ultra_restricted` | `bool` | Optional | - |
| `last_avatar_image_hash` | `str` | Optional | - |
| `last_name` | `str` | Optional | - |
| `memberships_count` | `int` | Optional | - |
| `name` | `str` | Optional | - |
| `phone` | `str` | Required | - |
| `pronouns` | `str` | Optional | - |
| `real_name` | `str` | Required | - |
| `real_name_normalized` | `str` | Required | - |
| `skype` | `str` | Required | - |
| `status_default_emoji` | `str` | Optional | - |
| `status_default_text` | `str` | Optional | - |
| `status_default_text_canonical` | `str` | Optional | - |
| `status_emoji` | `str` | Required | - |
| `status_expiration` | `int` | Optional | - |
| `status_text` | `str` | Required | - |
| `status_text_canonical` | `str` | Optional | - |
| `team` | `str` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `title` | `str` | Required | - |
| `updated` | `int` | Optional | - |
| `user_id` | `str` | Optional | - |
| `username` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "always_active": false,
  "api_app_id": "api_app_id8",
  "avatar_hash": "avatar_hash8",
  "bot_id": "bot_id8",
  "display_name": "display_name8",
  "display_name_normalized": "display_name_normalized8",
  "email": "email8",
  "fields": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "first_name": "first_name8",
  "phone": "phone2",
  "real_name": "real_name6",
  "real_name_normalized": "real_name_normalized8",
  "skype": "skype8",
  "status_emoji": "status_emoji2",
  "status_text": "status_text0",
  "title": "title4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

