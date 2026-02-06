# Files Comments

```python
files_comments_api = client.files_comments
```

## Class Name

`FilesCommentsApi`


# Files Comments Delete

Deletes an existing comment on a file.

API method documentation: [https://api.slack.com/methods/files.comments.delete](https://api.slack.com/methods/files.comments.delete)

```python
def files_comments_delete(self,
                         token=None,
                         file=None,
                         id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `str` | Form, Optional | File to delete a comment from. |
| `id` | `str` | Form, Optional | The comment to delete. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesCommentsDeleteSchema`](../../doc/models/files-comments-delete-schema.md).

## Example Usage

```python
result = files_comments_api.files_comments_delete()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`FilesCommentsDeleteErrorSchemaException`](../../doc/models/files-comments-delete-error-schema-exception.md) |

