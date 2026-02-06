# Reminders

```python
reminders_api = client.reminders
```

## Class Name

`RemindersApi`

## Methods

* [Reminders Add](../../doc/controllers/reminders.md#reminders-add)
* [Reminders Complete](../../doc/controllers/reminders.md#reminders-complete)
* [Reminders Delete](../../doc/controllers/reminders.md#reminders-delete)
* [Reminders Info](../../doc/controllers/reminders.md#reminders-info)
* [Reminders List](../../doc/controllers/reminders.md#reminders-list)


# Reminders Add

Creates a reminder.

API method documentation: [https://api.slack.com/methods/reminders.add](https://api.slack.com/methods/reminders.add)

```python
def reminders_add(self,
                 token,
                 text,
                 time,
                 user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `reminders:write` |
| `text` | `str` | Form, Required | The content of the reminder |
| `time` | `str` | Form, Required | When this reminder should happen: the Unix timestamp (up to five years from now), the number of seconds until the reminder (if within 24 hours), or a natural language description (Ex. "in 15 minutes," or "every Thursday") |
| `user` | `str` | Form, Optional | The user who will receive the reminder. If no user is specified, the reminder will go to user who created it. |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RemindersAddSchema`](../../doc/models/reminders-add-schema.md).

## Example Usage

```python
token = 'token6'

text = 'text0'

time = 'time0'

result = reminders_api.reminders_add(
    token,
    text,
    time
)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersAddErrorSchemaException`](../../doc/models/reminders-add-error-schema-exception.md) |


# Reminders Complete

Marks a reminder as complete.

API method documentation: [https://api.slack.com/methods/reminders.complete](https://api.slack.com/methods/reminders.complete)

```python
def reminders_complete(self,
                      token=None,
                      reminder=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `str` | Form, Optional | The ID of the reminder to be marked as complete |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RemindersCompleteSchema`](../../doc/models/reminders-complete-schema.md).

## Example Usage

```python
result = reminders_api.reminders_complete()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersCompleteErrorSchemaException`](../../doc/models/reminders-complete-error-schema-exception.md) |


# Reminders Delete

Deletes a reminder.

API method documentation: [https://api.slack.com/methods/reminders.delete](https://api.slack.com/methods/reminders.delete)

```python
def reminders_delete(self,
                    token=None,
                    reminder=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `str` | Form, Optional | The ID of the reminder |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RemindersDeleteSchema`](../../doc/models/reminders-delete-schema.md).

## Example Usage

```python
result = reminders_api.reminders_delete()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersDeleteErrorSchemaException`](../../doc/models/reminders-delete-error-schema-exception.md) |


# Reminders Info

Gets information about a reminder.

API method documentation: [https://api.slack.com/methods/reminders.info](https://api.slack.com/methods/reminders.info)

```python
def reminders_info(self,
                  token=None,
                  reminder=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `reminders:read` |
| `reminder` | `str` | Query, Optional | The ID of the reminder |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RemindersInfoSchema`](../../doc/models/reminders-info-schema.md).

## Example Usage

```python
result = reminders_api.reminders_info()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersInfoErrorSchemaException`](../../doc/models/reminders-info-error-schema-exception.md) |


# Reminders List

Lists all reminders created by or for a given user.

API method documentation: [https://api.slack.com/methods/reminders.list](https://api.slack.com/methods/reminders.list)

```python
def reminders_list(self,
                  token=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Optional | Authentication token. Requires scope: `reminders:read` |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RemindersListSchema`](../../doc/models/reminders-list-schema.md).

## Example Usage

```python
result = reminders_api.reminders_list()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersListErrorSchemaException`](../../doc/models/reminders-list-error-schema-exception.md) |

