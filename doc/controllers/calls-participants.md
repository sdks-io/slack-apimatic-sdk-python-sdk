# Calls Participants

```python
calls_participants_api = client.calls_participants
```

## Class Name

`CallsParticipantsApi`

## Methods

* [Calls Participants Add](../../doc/controllers/calls-participants.md#calls-participants-add)
* [Calls Participants Remove](../../doc/controllers/calls-participants.md#calls-participants-remove)


# Calls Participants Add

Registers new participants added to a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.add](https://api.slack.com/methods/calls.participants.add)

```python
def calls_participants_add(self,
                          token,
                          id,
                          users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `str` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `str` | Form, Required | The list of users to add as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

id = 'id0'

users = 'users6'

result = calls_participants_api.calls_participants_add(
    token,
    id,
    users
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


# Calls Participants Remove

Registers participants removed from a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.remove](https://api.slack.com/methods/calls.participants.remove)

```python
def calls_participants_remove(self,
                             token,
                             id,
                             users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `str` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `str` | Form, Required | The list of users to remove as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

id = 'id0'

users = 'users6'

result = calls_participants_api.calls_participants_remove(
    token,
    id,
    users
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

