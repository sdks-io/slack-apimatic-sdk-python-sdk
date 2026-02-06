# Auth

```python
auth_api = client.auth
```

## Class Name

`AuthApi`

## Methods

* [Auth Revoke](../../doc/controllers/auth.md#auth-revoke)
* [Auth Test](../../doc/controllers/auth.md#auth-test)


# Auth Revoke

Revokes a token.

API method documentation: [https://api.slack.com/methods/auth.revoke](https://api.slack.com/methods/auth.revoke)

```python
def auth_revoke(self,
               token,
               test=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `none` |
| `test` | `bool` | Query, Optional | Setting this parameter to `1` triggers a _testing mode_ where the specified token will not actually be revoked. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AuthRevokeSchema`](../../doc/models/auth-revoke-schema.md).

## Example Usage

```python
token = 'token6'

result = auth_api.auth_revoke(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AuthRevokeErrorSchemaException`](../../doc/models/auth-revoke-error-schema-exception.md) |


# Auth Test

Checks authentication & identity.

API method documentation: [https://api.slack.com/methods/auth.test](https://api.slack.com/methods/auth.test)

```python
def auth_test(self,
             token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Header, Required | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`AuthTestSuccessSchema`](../../doc/models/auth-test-success-schema.md).

## Example Usage

```python
token = 'token6'

result = auth_api.auth_test(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`AuthTestErrorSchemaException`](../../doc/models/auth-test-error-schema-exception.md) |

