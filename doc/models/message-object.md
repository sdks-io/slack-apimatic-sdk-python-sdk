
# Message Object

*This model accepts additional fields of type Any.*

## Structure

`MessageObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `attachments` | [`List[Attachment]`](../../doc/models/attachment.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `blocks` | [`List[BlockKitBlock]`](../../doc/models/block-kit-block.md) | Optional | This is a very loose definition, in the future, we'll populate this with deeper schema in this definition namespace. |
| `bot_id` | `Any` | Optional | - |
| `bot_profile` | [`BotProfileObject`](../../doc/models/bot-profile-object.md) | Optional | - |
| `client_msg_id` | `str` | Optional | - |
| `comment` | [`FileCommentObject`](../../doc/models/file-comment-object.md) | Optional | - |
| `display_as_bot` | `bool` | Optional | - |
| `file` | [`FileObject`](../../doc/models/file-object.md) | Optional | - |
| `files` | [`List[FileObject]`](../../doc/models/file-object.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `icons` | [`Icons1`](../../doc/models/icons-1.md) | Optional | - |
| `inviter` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `is_delayed_message` | `bool` | Optional | - |
| `is_intro` | `bool` | Optional | - |
| `is_starred` | `bool` | Optional | - |
| `last_read` | `str` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `latest_reply` | `str` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `name` | `str` | Optional | - |
| `old_name` | `str` | Optional | - |
| `parent_user_id` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `permalink` | `str` | Optional | - |
| `pinned_to` | `List[str]` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `purpose` | `str` | Optional | - |
| `reactions` | [`List[ReactionObject]`](../../doc/models/reaction-object.md) | Optional | - |
| `reply_count` | `int` | Optional | - |
| `reply_users` | `List[str]` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `reply_users_count` | `int` | Optional | - |
| `source_team` | `str` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `subscribed` | `bool` | Optional | - |
| `subtype` | `str` | Optional | - |
| `team` | `str` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `text` | `str` | Required | - |
| `thread_ts` | `str` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `topic` | `str` | Optional | - |
| `ts` | `str` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `mtype` | `str` | Required | - |
| `unread_count` | `int` | Optional | - |
| `upload` | `bool` | Optional | - |
| `user` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `user_profile` | [`ObjsUserProfileShort`](../../doc/models/objs-user-profile-short.md) | Optional | - |
| `user_team` | `str` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `username` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "fallback": "fallback4",
      "id": 36,
      "image_bytes": 34,
      "image_height": 154,
      "image_url": "image_url6",
      "image_width": 24,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "fallback": "fallback4",
      "id": 36,
      "image_bytes": 34,
      "image_height": 154,
      "image_url": "image_url6",
      "image_width": 24,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "blocks": [
    {
      "type": "type4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "type": "type4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "bot_id": {
    "key1": "val1",
    "key2": "val2"
  },
  "bot_profile": {
    "app_id": "app_id8",
    "deleted": false,
    "icons": {
      "image_36": "image_362",
      "image_48": "image_488",
      "image_72": "image_722",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "id": "id8",
    "name": "name8",
    "team_id": "team_id8",
    "updated": 44,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "client_msg_id": "client_msg_id4",
  "text": "text8",
  "ts": "ts0",
  "type": "type8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

