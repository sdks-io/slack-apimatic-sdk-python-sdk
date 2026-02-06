# Migration

```python
migration_api = client.migration
```

## Class Name

`MigrationApi`


# Migration Exchange

For Enterprise Grid workspaces, map local user IDs to global user IDs

API method documentation: [https://api.slack.com/methods/migration.exchange](https://api.slack.com/methods/migration.exchange)

```python
def migration_exchange(self,
                      token,
                      users,
                      team_id=None,
                      to_old=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `tokens.basic` |
| `users` | `str` | Query, Required | A comma-separated list of user ids, up to 400 per request |
| `team_id` | `str` | Query, Optional | Specify team_id starts with `T` in case of Org Token |
| `to_old` | `bool` | Query, Optional | Specify `true` to convert `W` global user IDs to workspace-specific `U` IDs. Defaults to `false`. |

## Requires scope

### slackAuth

`tokens.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`MigrationExchangeSuccessSchema`](../../doc/models/migration-exchange-success-schema.md).

## Example Usage

```python
token = 'token6'

users = 'users6'

result = migration_api.migration_exchange(
    token,
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
| Default | Typical error response when there are no mappings to provide | [`MigrationExchangeErrorSchemaException`](../../doc/models/migration-exchange-error-schema-exception.md) |

