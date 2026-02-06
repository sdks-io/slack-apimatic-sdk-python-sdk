# Bots

```python
bots_api = client.bots
```

## Class Name

`BotsApi`


# Bots Info

Gets information about a bot user.

API method documentation: [https://api.slack.com/methods/bots.info](https://api.slack.com/methods/bots.info)

```python
def bots_info(self,
             token,
             bot=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `users:read` |
| `bot` | `str` | Query, Optional | Bot user to get info on |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`BotsInfoSchema`](../../doc/models/bots-info-schema.md).

## Example Usage

```python
token = 'token6'

result = bots_api.bots_info(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | When no bot can be found, it returns an error. | [`BotsInfoErrorSchemaException`](../../doc/models/bots-info-error-schema-exception.md) |

