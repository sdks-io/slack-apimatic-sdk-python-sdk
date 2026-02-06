# Admin Invite Requests Approved

```python
admin_invite_requests_approved_api = client.admin_invite_requests_approved
```

## Class Name

`AdminInviteRequestsApprovedApi`


# Admin Invite Requests Approved List

List all approved workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.approved.list](https://api.slack.com/methods/admin.inviteRequests.approved.list)

```python
def admin_invite_requests_approved_list(self,
                                       token,
                                       team_id=None,
                                       cursor=None,
                                       limit=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `admin.invites:read` |
| `team_id` | `str` | Query, Optional | ID for the workspace where the invite requests were made. |
| `cursor` | `str` | Query, Optional | Value of the `next_cursor` field sent as part of the previous API response |
| `limit` | `int` | Query, Optional | The number of results that will be returned by the API on each invocation. Must be between 1 - 1000, both inclusive |

## Requires scope

### slackAuth

`admin.invites:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = admin_invite_requests_approved_api.admin_invite_requests_approved_list(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

