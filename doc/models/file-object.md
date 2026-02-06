
# File Object

*This model accepts additional fields of type Any.*

## Structure

`FileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channels` | `List[str]` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `comments_count` | `int` | Optional | - |
| `created` | `int` | Optional | - |
| `date_delete` | `int` | Optional | - |
| `display_as_bot` | `bool` | Optional | - |
| `editable` | `bool` | Optional | - |
| `editor` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `external_id` | `str` | Optional | - |
| `external_type` | `str` | Optional | - |
| `external_url` | `str` | Optional | - |
| `filetype` | `str` | Optional | - |
| `groups` | `List[str]` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[G][A-Z0-9]{8,}$` |
| `has_rich_preview` | `bool` | Optional | - |
| `id` | `str` | Optional | **Constraints**: *Pattern*: `^[F][A-Z0-9]{8,}$` |
| `image_exif_rotation` | `int` | Optional | - |
| `ims` | `List[str]` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[D][A-Z0-9]{8,}$` |
| `is_external` | `bool` | Optional | - |
| `is_public` | `bool` | Optional | - |
| `is_starred` | `bool` | Optional | - |
| `is_tombstoned` | `bool` | Optional | - |
| `last_editor` | `str` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `mimetype` | `str` | Optional | - |
| `mode` | `str` | Optional | - |
| `name` | `str` | Optional | - |
| `non_owner_editable` | `bool` | Optional | - |
| `num_stars` | `int` | Optional | - |
| `original_h` | `int` | Optional | - |
| `original_w` | `int` | Optional | - |
| `permalink` | `str` | Optional | - |
| `permalink_public` | `str` | Optional | - |
| `pinned_info` | `Any` | Optional | - |
| `pinned_to` | `List[str]` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `pretty_type` | `str` | Optional | - |
| `preview` | `str` | Optional | - |
| `public_url_shared` | `bool` | Optional | - |
| `reactions` | [`List[ReactionObject]`](../../doc/models/reaction-object.md) | Optional | - |
| `shares` | [`Shares`](../../doc/models/shares.md) | Optional | - |
| `size` | `int` | Optional | - |
| `source_team` | `str` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `state` | `str` | Optional | - |
| `thumb_1024` | `str` | Optional | - |
| `thumb_1024_h` | `int` | Optional | - |
| `thumb_1024_w` | `int` | Optional | - |
| `thumb_160` | `str` | Optional | - |
| `thumb_360` | `str` | Optional | - |
| `thumb_360_h` | `int` | Optional | - |
| `thumb_360_w` | `int` | Optional | - |
| `thumb_480` | `str` | Optional | - |
| `thumb_480_h` | `int` | Optional | - |
| `thumb_480_w` | `int` | Optional | - |
| `thumb_64` | `str` | Optional | - |
| `thumb_720` | `str` | Optional | - |
| `thumb_720_h` | `int` | Optional | - |
| `thumb_720_w` | `int` | Optional | - |
| `thumb_80` | `str` | Optional | - |
| `thumb_800` | `str` | Optional | - |
| `thumb_800_h` | `int` | Optional | - |
| `thumb_800_w` | `int` | Optional | - |
| `thumb_960` | `str` | Optional | - |
| `thumb_960_h` | `int` | Optional | - |
| `thumb_960_w` | `int` | Optional | - |
| `thumb_tiny` | `str` | Optional | - |
| `timestamp` | `int` | Optional | - |
| `title` | `str` | Optional | - |
| `updated` | `int` | Optional | - |
| `url_private` | `str` | Optional | - |
| `url_private_download` | `str` | Optional | - |
| `user` | `str` | Optional | - |
| `user_team` | `str` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `username` | `str` | Optional | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels2",
    "channels1"
  ],
  "comments_count": 94,
  "created": 2,
  "date_delete": 156,
  "display_as_bot": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

