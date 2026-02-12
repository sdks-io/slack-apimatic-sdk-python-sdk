# Files Remote

```python
files_remote_api = client.files_remote
```

## Class Name

`FilesRemoteApi`

## Methods

* [Files Remote Add](../../doc/controllers/files-remote.md#files-remote-add)
* [Files Remote Info](../../doc/controllers/files-remote.md#files-remote-info)
* [Files Remote List](../../doc/controllers/files-remote.md#files-remote-list)
* [Files Remote Remove](../../doc/controllers/files-remote.md#files-remote-remove)
* [Files Remote Share](../../doc/controllers/files-remote.md#files-remote-share)
* [Files Remote Update](../../doc/controllers/files-remote.md#files-remote-update)


# Files Remote Add

Adds a file from a remote service

API method documentation: [https://api.slack.com/methods/files.remote.add](https://api.slack.com/methods/files.remote.add)

```python
def files_remote_add(self,
                    token=None,
                    external_id=None,
                    title=None,
                    filetype=None,
                    external_url=None,
                    preview_image=None,
                    indexable_file_contents=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `external_id` | `str` | Form, Optional | Creator defined GUID for the file. |
| `title` | `str` | Form, Optional | Title of the file being shared. |
| `filetype` | `str` | Form, Optional | type of file |
| `external_url` | `str` | Form, Optional | URL of the remote file. |
| `preview_image` | `str` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexable_file_contents` | `str` | Form, Optional | A text file (txt, pdf, doc, etc.) containing textual search terms that are used to improve discovery of the remote file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = files_remote_api.files_remote_add()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Files Remote Info

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.info](https://api.slack.com/methods/files.remote.info)

```python
def files_remote_info(self,
                     token=None,
                     file=None,
                     external_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `file` | `str` | Query, Optional | Specify a file by providing its ID. |
| `external_id` | `str` | Query, Optional | Creator defined GUID for the file. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = files_remote_api.files_remote_info()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Files Remote List

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.list](https://api.slack.com/methods/files.remote.list)

```python
def files_remote_list(self,
                     token=None,
                     channel=None,
                     ts_from=None,
                     ts_to=None,
                     limit=None,
                     cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `channel` | `str` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `ts_from` | `float` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `ts_to` | `float` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `limit` | `int` | Query, Optional | The maximum number of items to return. |
| `cursor` | `str` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = files_remote_api.files_remote_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Files Remote Remove

Remove a remote file.

API method documentation: [https://api.slack.com/methods/files.remote.remove](https://api.slack.com/methods/files.remote.remove)

```python
def files_remote_remove(self,
                       token=None,
                       file=None,
                       external_id=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `str` | Form, Optional | Specify a file by providing its ID. |
| `external_id` | `str` | Form, Optional | Creator defined GUID for the file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = files_remote_api.files_remote_remove()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Files Remote Share

Share a remote file into a channel.

API method documentation: [https://api.slack.com/methods/files.remote.share](https://api.slack.com/methods/files.remote.share)

```python
def files_remote_share(self,
                      token=None,
                      file=None,
                      external_id=None,
                      channels=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `remote_files:share` |
| `file` | `str` | Query, Optional | Specify a file registered with Slack by providing its ID. Either this field or `external_id` or both are required. |
| `external_id` | `str` | Query, Optional | The globally unique identifier (GUID) for the file, as set by the app registering the file with Slack.  Either this field or `file` or both are required. |
| `channels` | `str` | Query, Optional | Comma-separated list of channel IDs where the file will be shared. |

## Requires scope

### slackAuth

`remote_files:share`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = files_remote_api.files_remote_share()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Files Remote Update

Updates an existing remote file.

API method documentation: [https://api.slack.com/methods/files.remote.update](https://api.slack.com/methods/files.remote.update)

```python
def files_remote_update(self,
                       token=None,
                       file=None,
                       external_id=None,
                       title=None,
                       filetype=None,
                       external_url=None,
                       preview_image=None,
                       indexable_file_contents=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `str` | Form, Optional | Specify a file by providing its ID. |
| `external_id` | `str` | Form, Optional | Creator defined GUID for the file. |
| `title` | `str` | Form, Optional | Title of the file being shared. |
| `filetype` | `str` | Form, Optional | type of file |
| `external_url` | `str` | Form, Optional | URL of the remote file. |
| `preview_image` | `str` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexable_file_contents` | `str` | Form, Optional | File containing contents that can be used to improve searchability for the remote file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = files_remote_api.files_remote_update()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

