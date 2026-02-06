# Admin Teams Owners

```python
admin_teams_owners_api = client.admin_teams_owners
```

## Class Name

`AdminTeamsOwnersApi`


# Admin Teams Owners List

List all of the owners on a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.owners.list](https://api.slack.com/methods/admin.teams.owners.list)

```python
def admin_teams_owners_list(self,
                           token,
                           team_id,
                           limit=None,
                           cursor=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin.teams:read` |
| `team_id` | `str` | Query, Required | - |
| `limit` | `int` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `str` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

team_id = 'team_id6'

result = admin_teams_owners_api.admin_teams_owners_list(
    token,
    team_id
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

