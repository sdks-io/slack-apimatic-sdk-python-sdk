# Search

```python
search_api = client.search
```

## Class Name

`SearchApi`


# Search Messages

Searches for messages matching a query.

API method documentation: [https://api.slack.com/methods/search.messages](https://api.slack.com/methods/search.messages)

```python
def search_messages(self,
                   token,
                   query,
                   count=None,
                   highlight=None,
                   page=None,
                   sort=None,
                   sort_dir=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `search:read` |
| `query` | `str` | Query, Required | Search query. |
| `count` | `int` | Query, Optional | Pass the number of results you want per "page". Maximum of `100`. |
| `highlight` | `bool` | Query, Optional | Pass a value of `true` to enable query highlight markers (see below). |
| `page` | `int` | Query, Optional | - |
| `sort` | `str` | Query, Optional | Return matches sorted by either `score` or `timestamp`. |
| `sort_dir` | `str` | Query, Optional | Change sort direction to ascending (`asc`) or descending (`desc`). |

## Requires scope

### slackAuth

`search:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

query = 'query0'

result = search_api.search_messages(
    token,
    query
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

