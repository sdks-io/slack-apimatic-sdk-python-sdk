# Oauth

```python
oauth_api = client.oauth
```

## Class Name

`OauthApi`

## Methods

* [Oauth Access](../../doc/controllers/oauth.md#oauth-access)
* [Oauth Token](../../doc/controllers/oauth.md#oauth-token)


# Oauth Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.access](https://api.slack.com/methods/oauth.access)

```python
def oauth_access(self,
                client_id=None,
                client_secret=None,
                code=None,
                redirect_uri=None,
                single_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client_id` | `str` | Query, Optional | Issued when you created your application. |
| `client_secret` | `str` | Query, Optional | Issued when you created your application. |
| `code` | `str` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirect_uri` | `str` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `single_channel` | `bool` | Query, Optional | Request the user to add your app only to a single channel. Only valid with a [legacy workspace app](https://api.slack.com/legacy-workspace-apps). |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = oauth_api.oauth_access()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Oauth Token

Exchanges a temporary OAuth verifier code for a workspace token.

API method documentation: [https://api.slack.com/methods/oauth.token](https://api.slack.com/methods/oauth.token)

```python
def oauth_token(self,
               client_id=None,
               client_secret=None,
               code=None,
               redirect_uri=None,
               single_channel=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `client_id` | `str` | Query, Optional | Issued when you created your application. |
| `client_secret` | `str` | Query, Optional | Issued when you created your application. |
| `code` | `str` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirect_uri` | `str` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `single_channel` | `bool` | Query, Optional | Request the user to add your app only to a single channel. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
result = oauth_api.oauth_token()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

