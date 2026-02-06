# Oauth V 2

```python
oauth_v_2_api = client.oauth_v_2
```

## Class Name

`OauthV2Api`


# Oauth V 2 Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.v2.access](https://api.slack.com/methods/oauth.v2.access)

```python
def oauth_v_2_access(self,
                    code,
                    client_id=None,
                    client_secret=None,
                    redirect_uri=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `str` | Query, Required | The `code` param returned via the OAuth callback. |
| `client_id` | `str` | Query, Optional | Issued when you created your application. |
| `client_secret` | `str` | Query, Optional | Issued when you created your application. |
| `redirect_uri` | `str` | Query, Optional | This must match the originally submitted URI (if one was sent). |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```python
code = 'code8'

result = oauth_v_2_api.oauth_v_2_access(code)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

