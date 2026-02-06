# Team Profile

```python
team_profile_api = client.team_profile
```

## Class Name

`TeamProfileApi`


# Team Profile Get

Retrieve a team's profile.

API method documentation: [https://api.slack.com/methods/team.profile.get](https://api.slack.com/methods/team.profile.get)

```python
def team_profile_get(self,
                    token,
                    visibility=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `visibility` | `str` | Query, Optional | Filter by visibility. |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TeamProfileGetSuccessSchema`](../../doc/models/team-profile-get-success-schema.md).

## Example Usage

```python
token = 'token6'

result = team_profile_api.team_profile_get(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamProfileGetErrorSchemaException`](../../doc/models/team-profile-get-error-schema-exception.md) |

