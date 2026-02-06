# Reactions

```python
reactions_api = client.reactions
```

## Class Name

`ReactionsApi`

## Methods

* [Reactions Add](../../doc/controllers/reactions.md#reactions-add)
* [Reactions Get](../../doc/controllers/reactions.md#reactions-get)
* [Reactions List](../../doc/controllers/reactions.md#reactions-list)
* [Reactions Remove](../../doc/controllers/reactions.md#reactions-remove)


# Reactions Add

Adds a reaction to an item.

API method documentation: [https://api.slack.com/methods/reactions.add](https://api.slack.com/methods/reactions.add)

```python
def reactions_add(self,
                 channel,
                 name,
                 timestamp,
                 token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `str` | Form, Required | Channel where the message to add reaction to was posted. |
| `name` | `str` | Form, Required | Reaction (emoji) name. |
| `timestamp` | `str` | Form, Required | Timestamp of the message to add reaction to. |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `reactions:write` |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ReactionsAddSchema`](../../doc/models/reactions-add-schema.md).

## Example Usage

```python
channel = 'channel4'

name = 'name0'

timestamp = 'timestamp2'

token = 'token6'

result = reactions_api.reactions_add(
    channel,
    name,
    timestamp,
    token
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsAddErrorSchemaException`](../../doc/models/reactions-add-error-schema-exception.md) |


# Reactions Get

Gets reactions for an item.

API method documentation: [https://api.slack.com/methods/reactions.get](https://api.slack.com/methods/reactions.get)

```python
def reactions_get(self,
                 token,
                 channel=None,
                 file=None,
                 file_comment=None,
                 full=None,
                 timestamp=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `channel` | `str` | Query, Optional | Channel where the message to get reactions for was posted. |
| `file` | `str` | Query, Optional | File to get reactions for. |
| `file_comment` | `str` | Query, Optional | File comment to get reactions for. |
| `full` | `bool` | Query, Optional | If true always return the complete reaction list. |
| `timestamp` | `str` | Query, Optional | Timestamp of the message to get reactions for. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type `Any`.

## Example Usage

```python
token = 'token6'

result = reactions_api.reactions_get(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Example Response

```
{
  "file": {
    "channels": [
      "C2U7V2YA2"
    ],
    "comments_count": 1,
    "created": 1507850315,
    "groups": [],
    "id": "F7H0D7ZA4",
    "ims": [],
    "name": "computer.gif",
    "reactions": [
      {
        "count": 1,
        "name": "stuck_out_tongue_winking_eye",
        "users": [
          "U2U85N1RV"
        ]
      }
    ],
    "timestamp": 1507850315,
    "title": "computer.gif",
    "user": "U2U85N1RV"
  },
  "ok": true,
  "type": "file"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsGetErrorSchemaException`](../../doc/models/reactions-get-error-schema-exception.md) |


# Reactions List

Lists reactions made by a user.

API method documentation: [https://api.slack.com/methods/reactions.list](https://api.slack.com/methods/reactions.list)

```python
def reactions_list(self,
                  token,
                  user=None,
                  full=None,
                  count=None,
                  page=None,
                  cursor=None,
                  limit=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `user` | `str` | Query, Optional | Show reactions made by this user. Defaults to the authed user. |
| `full` | `bool` | Query, Optional | If true always return the complete reaction list. |
| `count` | `int` | Query, Optional | - |
| `page` | `int` | Query, Optional | - |
| `cursor` | `str` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ReactionsListSchema`](../../doc/models/reactions-list-schema.md).

## Example Usage

```python
token = 'token6'

result = reactions_api.reactions_list(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsListErrorSchemaException`](../../doc/models/reactions-list-error-schema-exception.md) |


# Reactions Remove

Removes a reaction from an item.

API method documentation: [https://api.slack.com/methods/reactions.remove](https://api.slack.com/methods/reactions.remove)

```python
def reactions_remove(self,
                    token,
                    name,
                    file=None,
                    file_comment=None,
                    channel=None,
                    timestamp=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `reactions:write` |
| `name` | `str` | Form, Required | Reaction (emoji) name. |
| `file` | `str` | Form, Optional | File to remove reaction from. |
| `file_comment` | `str` | Form, Optional | File comment to remove reaction from. |
| `channel` | `str` | Form, Optional | Channel where the message to remove reaction from was posted. |
| `timestamp` | `str` | Form, Optional | Timestamp of the message to remove reaction from. |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ReactionsRemoveSchema`](../../doc/models/reactions-remove-schema.md).

## Example Usage

```python
token = 'token6'

name = 'name0'

result = reactions_api.reactions_remove(
    token,
    name
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsRemoveErrorSchemaException`](../../doc/models/reactions-remove-error-schema-exception.md) |

