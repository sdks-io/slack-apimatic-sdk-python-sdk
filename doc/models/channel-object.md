
# Channel Object

*This model accepts additional fields of type Any.*

## Structure

`ChannelObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accepted_user` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `created` | `int` | Required | - |
| `creator` | `str` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `id` | `str` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `is_archived` | `bool` | Optional | - |
| `is_channel` | `bool` | Required | - |
| `is_frozen` | `bool` | Optional | - |
| `is_general` | `bool` | Optional | - |
| `is_member` | `bool` | Optional | - |
| `is_moved` | `int` | Optional | - |
| `is_mpim` | `bool` | Required | - |
| `is_non_threadable` | `bool` | Optional | - |
| `is_org_shared` | `bool` | Required | - |
| `is_pending_ext_shared` | `bool` | Optional | - |
| `is_private` | `bool` | Required | - |
| `is_read_only` | `bool` | Optional | - |
| `is_shared` | `bool` | Required | - |
| `is_thread_only` | `bool` | Optional | - |
| `last_read` | `str` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `latest` | `Any` | Optional | - |
| `members` | `List[str]` | Required | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `name` | `str` | Required | - |
| `name_normalized` | `str` | Required | - |
| `num_members` | `int` | Optional | - |
| `pending_shared` | `List[str]` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `previous_names` | `List[str]` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required* |
| `priority` | `float` | Optional | - |
| `purpose` | [`Purpose`](../../doc/models/purpose.md) | Required | - |
| `topic` | [`Topic`](../../doc/models/topic.md) | Required | - |
| `unlinked` | `int` | Optional | - |
| `unread_count` | `int` | Optional | - |
| `unread_count_display` | `int` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "accepted_user": "accepted_user4",
  "created": 68,
  "creator": "creator4",
  "id": "id6",
  "is_archived": false,
  "is_channel": false,
  "is_frozen": false,
  "is_general": false,
  "is_member": false,
  "is_mpim": false,
  "is_org_shared": false,
  "is_private": false,
  "is_shared": false,
  "members": [
    "members4",
    "members5",
    "members6"
  ],
  "name": "name6",
  "name_normalized": "name_normalized4",
  "purpose": {
    "creator": "creator4",
    "last_set": 30,
    "value": "value8",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "topic": {
    "creator": "creator6",
    "last_set": 242,
    "value": "value0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

