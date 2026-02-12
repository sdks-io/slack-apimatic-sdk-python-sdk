# Files

```python
files_api = client.files
```

## Class Name

`FilesApi`

## Methods

* [Files Delete](../../doc/controllers/files.md#files-delete)
* [Files Info](../../doc/controllers/files.md#files-info)
* [Files List](../../doc/controllers/files.md#files-list)
* [Files Revoke Public URL](../../doc/controllers/files.md#files-revoke-public-url)
* [Files Shared Public URL](../../doc/controllers/files.md#files-shared-public-url)
* [Files Upload](../../doc/controllers/files.md#files-upload)


# Files Delete

Deletes a file.

API method documentation: [https://api.slack.com/methods/files.delete](https://api.slack.com/methods/files.delete)

```python
def files_delete(self,
                token=None,
                file=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `str` | Form, Optional | ID of file to delete. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesDeleteSchema`](../../doc/models/files-delete-schema.md).

## Example Usage

```python
result = files_api.files_delete()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesDeleteErrorSchemaException`](../../doc/models/files-delete-error-schema-exception.md) |


# Files Info

Gets information about a file.

API method documentation: [https://api.slack.com/methods/files.info](https://api.slack.com/methods/files.info)

```python
def files_info(self,
              token=None,
              file=None,
              count=None,
              page=None,
              limit=None,
              cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `file` | `str` | Query, Optional | Specify a file by providing its ID. |
| `count` | `str` | Query, Optional | - |
| `page` | `str` | Query, Optional | - |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |
| `cursor` | `str` | Query, Optional | Parameter for pagination. File comments are paginated for a single file. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection of comments. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesInfoSchema`](../../doc/models/files-info-schema.md).

## Example Usage

```python
result = files_api.files_info()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesInfoErrorSchemaException`](../../doc/models/files-info-error-schema-exception.md) |


# Files List

List for a team, in a channel, or from a user with applied filters.

API method documentation: [https://api.slack.com/methods/files.list](https://api.slack.com/methods/files.list)

```python
def files_list(self,
              token=None,
              user=None,
              channel=None,
              ts_from=None,
              ts_to=None,
              types=None,
              count=None,
              page=None,
              show_files_hidden_by_limit=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `user` | `str` | Query, Optional | Filter files created by a single user. |
| `channel` | `str` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `ts_from` | `float` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `ts_to` | `float` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `types` | `str` | Query, Optional | Filter files by type ([see below](#file_types)). You can pass multiple values in the types argument, like `types=spaces,snippets`.The default value is `all`, which does not filter the list. |
| `count` | `str` | Query, Optional | - |
| `page` | `str` | Query, Optional | - |
| `show_files_hidden_by_limit` | `bool` | Query, Optional | Show truncated file info for files hidden due to being too old, and the team who owns the file being over the file limit. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesListSchema`](../../doc/models/files-list-schema.md).

## Example Usage

```python
result = files_api.files_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesListErrorSchemaException`](../../doc/models/files-list-error-schema-exception.md) |


# Files Revoke Public URL

Revokes public/external sharing access for a file

API method documentation: [https://api.slack.com/methods/files.revokePublicURL](https://api.slack.com/methods/files.revokePublicURL)

```python
def files_revoke_public_url(self,
                           token=None,
                           file=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `str` | Form, Optional | File to revoke |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesRevokePublicUrlSchema`](../../doc/models/files-revoke-public-url-schema.md).

## Example Usage

```python
result = files_api.files_revoke_public_url()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesRevokePublicUrlErrorSchemaException`](../../doc/models/files-revoke-public-url-error-schema-exception.md) |


# Files Shared Public URL

Enables a file for public/external sharing.

API method documentation: [https://api.slack.com/methods/files.sharedPublicURL](https://api.slack.com/methods/files.sharedPublicURL)

```python
def files_shared_public_url(self,
                           token=None,
                           file=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `str` | Form, Optional | File to share |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesSharedPublicUrlSchema`](../../doc/models/files-shared-public-url-schema.md).

## Example Usage

```python
result = files_api.files_shared_public_url()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesSharedPublicUrlErrorSchemaException`](../../doc/models/files-shared-public-url-error-schema-exception.md) |


# Files Upload

Uploads or creates a file.

API method documentation: [https://api.slack.com/methods/files.upload](https://api.slack.com/methods/files.upload)

```python
def files_upload(self,
                token=None,
                file=None,
                content=None,
                filetype=None,
                filename=None,
                title=None,
                initial_comment=None,
                channels=None,
                thread_ts=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `str` | Form, Optional | File contents via `multipart/form-data`. If omitting this parameter, you must submit `content`. |
| `content` | `str` | Form, Optional | File contents via a POST variable. If omitting this parameter, you must provide a `file`. |
| `filetype` | `str` | Form, Optional | A [file type](/types/file#file_types) identifier. |
| `filename` | `str` | Form, Optional | Filename of file. |
| `title` | `str` | Form, Optional | Title of file. |
| `initial_comment` | `str` | Form, Optional | The message text introducing the file in specified `channels`. |
| `channels` | `str` | Form, Optional | Comma-separated list of channel names or IDs where the file will be shared. |
| `thread_ts` | `float` | Form, Optional | Provide another message's `ts` value to upload this file as a reply. Never use a reply's `ts` value; use its parent instead. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`FilesUploadSchema`](../../doc/models/files-upload-schema.md).

## Example Usage

```python
result = files_api.files_upload()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesUploadErrorSchemaException`](../../doc/models/files-upload-error-schema-exception.md) |

