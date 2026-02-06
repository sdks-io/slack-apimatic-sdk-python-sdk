
# Chat Scheduled Messages List Schema

Schema for successful response from chat.scheduledMessages.list method

*This model accepts additional fields of type Any.*

## Structure

`ChatScheduledMessagesListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `str` | Required, Constant | **Value**: `"True"` |
| `response_metadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Required | - |
| `scheduled_messages` | [`List[ScheduledMessage]`](../../doc/models/scheduled-message.md) | Required | - |
| `additional_properties` | `Dict[str, Any]` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "response_metadata": {
    "next_cursor": "next_cursor2",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "scheduled_messages": [
    {
      "channel_id": "channel_id8",
      "date_created": 100,
      "id": "id2",
      "post_at": 0,
      "text": "text2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

