# Stars

```python
stars_api = client.stars
```

## Class Name

`StarsApi`

## Methods

* [Stars Add](../../doc/controllers/stars.md#stars-add)
* [Stars List](../../doc/controllers/stars.md#stars-list)
* [Stars Remove](../../doc/controllers/stars.md#stars-remove)


# Stars Add

Adds a star to an item.

API method documentation: [https://api.slack.com/methods/stars.add](https://api.slack.com/methods/stars.add)

```python
def stars_add(self,
             token,
             channel=None,
             file=None,
             file_comment=None,
             timestamp=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `str` | Form, Optional | Channel to add star to, or channel where the message to add star to was posted (used with `timestamp`). |
| `file` | `str` | Form, Optional | File to add star to. |
| `file_comment` | `str` | Form, Optional | File comment to add star to. |
| `timestamp` | `str` | Form, Optional | Timestamp of the message to add star to. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`StarsAddSchema`](../../doc/models/stars-add-schema.md).

## Example Usage

```python
token = 'token6'

result = stars_api.stars_add(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsAddErrorSchemaException`](../../doc/models/stars-add-error-schema-exception.md) |


# Stars List

Lists stars for a user.

API method documentation: [https://api.slack.com/methods/stars.list](https://api.slack.com/methods/stars.list)

```python
def stars_list(self,
              token=None,
              count=None,
              page=None,
              cursor=None,
              limit=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `stars:read` |
| `count` | `str` | Query, Optional | - |
| `page` | `str` | Query, Optional | - |
| `cursor` | `str` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |

## Requires scope

### slackAuth

`stars:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`StarsListSchema`](../../doc/models/stars-list-schema.md).

## Example Usage

```python
result = stars_api.stars_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsListErrorSchemaException`](../../doc/models/stars-list-error-schema-exception.md) |


# Stars Remove

Removes a star from an item.

API method documentation: [https://api.slack.com/methods/stars.remove](https://api.slack.com/methods/stars.remove)

```python
def stars_remove(self,
                token,
                channel=None,
                file=None,
                file_comment=None,
                timestamp=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `str` | Form, Optional | Channel to remove star from, or channel where the message to remove star from was posted (used with `timestamp`). |
| `file` | `str` | Form, Optional | File to remove star from. |
| `file_comment` | `str` | Form, Optional | File comment to remove star from. |
| `timestamp` | `str` | Form, Optional | Timestamp of the message to remove star from. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`StarsRemoveSchema`](../../doc/models/stars-remove-schema.md).

## Example Usage

```python
token = 'token6'

result = stars_api.stars_remove(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsRemoveErrorSchemaException`](../../doc/models/stars-remove-error-schema-exception.md) |

