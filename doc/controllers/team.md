# Team

```python
team_api = client.team
```

## Class Name

`TeamApi`

## Methods

* [Team Access Logs](../../doc/controllers/team.md#team-access-logs)
* [Team Billable Info](../../doc/controllers/team.md#team-billable-info)
* [Team Info](../../doc/controllers/team.md#team-info)
* [Team Integration Logs](../../doc/controllers/team.md#team-integration-logs)


# Team Access Logs

Gets the access logs for the current team.

API method documentation: [https://api.slack.com/methods/team.accessLogs](https://api.slack.com/methods/team.accessLogs)

```python
def team_access_logs(self,
                    token,
                    before=None,
                    count=None,
                    page=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin` |
| `before` | `str` | Query, Optional | End of time range of logs to include in results (inclusive). |
| `count` | `str` | Query, Optional | - |
| `page` | `str` | Query, Optional | - |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TeamAccessLogsSchema`](../../doc/models/team-access-logs-schema.md).

## Example Usage

```python
token = 'token6'

result = team_api.team_access_logs(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | A workspace must be on a paid plan to use this method, otherwise the `paid_only` error is thrown: | [`TeamAccessLogsErrorSchemaException`](../../doc/models/team-access-logs-error-schema-exception.md) |


# Team Billable Info

Gets billable users information for the current team.

API method documentation: [https://api.slack.com/methods/team.billableInfo](https://api.slack.com/methods/team.billableInfo)

```python
def team_billable_info(self,
                      token,
                      user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin` |
| `user` | `str` | Query, Optional | A user to retrieve the billable information for. Defaults to all users. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
token = 'token6'

result = team_api.team_billable_info(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Team Info

Gets information about the current team.

API method documentation: [https://api.slack.com/methods/team.info](https://api.slack.com/methods/team.info)

```python
def team_info(self,
             token,
             team=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `team:read` |
| `team` | `str` | Query, Optional | Team to get info on, if omitted, will return information about the current team. Will only return team that the authenticated token is allowed to see through external shared channels |

## Requires scope

### slackAuth

`team:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TeamInfoSchema`](../../doc/models/team-info-schema.md).

## Example Usage

```python
token = 'token6'

result = team_api.team_info(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamInfoErrorSchemaException`](../../doc/models/team-info-error-schema-exception.md) |


# Team Integration Logs

Gets the integration logs for the current team.

API method documentation: [https://api.slack.com/methods/team.integrationLogs](https://api.slack.com/methods/team.integrationLogs)

```python
def team_integration_logs(self,
                         token,
                         app_id=None,
                         change_type=None,
                         count=None,
                         page=None,
                         service_id=None,
                         user=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `admin` |
| `app_id` | `str` | Query, Optional | Filter logs to this Slack app. Defaults to all logs. |
| `change_type` | `str` | Query, Optional | Filter logs with this change type. Defaults to all logs. |
| `count` | `str` | Query, Optional | - |
| `page` | `str` | Query, Optional | - |
| `service_id` | `str` | Query, Optional | Filter logs to this service. Defaults to all logs. |
| `user` | `str` | Query, Optional | Filter logs generated by this user’s actions. Defaults to all logs. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`TeamIntegrationLogsSchema`](../../doc/models/team-integration-logs-schema.md).

## Example Usage

```python
token = 'token6'

result = team_api.team_integration_logs(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamIntegrationLogsErrorSchemaException`](../../doc/models/team-integration-logs-error-schema-exception.md) |

