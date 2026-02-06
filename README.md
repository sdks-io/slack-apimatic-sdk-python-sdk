
# Getting Started with Slack Web API

## Introduction

One way to interact with the Slack platform is its HTTP RPC-based Web API, a collection of methods requiring OAuth 2.0-based user, bot, or workspace tokens blessed with related OAuth scopes.

Learn more about the Slack Web API: [https://api.slack.com/web](https://api.slack.com/web)

## Install the Package

The package is compatible with Python versions `3.7+`.
Install the package from PyPi using the following pip command:

```bash
pip install slack-apimatic-sdk-sdk==1.0.0
```

You can also view the package at:
https://pypi.python.org/pypi/slack-apimatic-sdk-sdk/1.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| http_client_instance | `Union[Session, HttpClientProvider]` | The Http Client passed from the sdk user for making requests |
| override_http_client_configuration | `bool` | The value which determines to override properties of the passed Http Client from the sdk user |
| http_call_back | `HttpCallBack` | The callback value that is invoked before and after an HTTP call is made to an endpoint |
| timeout | `float` | The value to use for connection timeout. <br> **Default: 30** |
| max_retries | `int` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| backoff_factor | `float` | A backoff factor to apply between attempts after the second try. <br> **Default: 2** |
| retry_statuses | `Array of int` | The http statuses on which retry is to be done. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| retry_methods | `Array of string` | The http methods on which retry is to be done. <br> **Default: ["GET", "PUT"]** |
| proxy_settings | [`ProxySettings`](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/proxy-settings.md) | Optional proxy configuration to route HTTP requests through a proxy server. |
| logging_configuration | [`LoggingConfiguration`](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/logging-configuration.md) | The SDK logging configuration for API calls |
| authorization_code_auth_credentials | [`AuthorizationCodeAuthCredentials`](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/auth/oauth-2-authorization-code-grant.md) | The credential object for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

### Code-Based Client Initialization

```python
import logging

from slackwebapi.configuration import Environment
from slackwebapi.http.auth.o_auth_2 import AuthorizationCodeAuthCredentials
from slackwebapi.logging.configuration.api_logging_configuration import LoggingConfiguration
from slackwebapi.logging.configuration.api_logging_configuration import RequestLoggingConfiguration
from slackwebapi.logging.configuration.api_logging_configuration import ResponseLoggingConfiguration
from slackwebapi.models.o_auth_scope import OAuthScope
from slackwebapi.slackwebapi_client import SlackwebapiClient

client = SlackwebapiClient(
    authorization_code_auth_credentials=AuthorizationCodeAuthCredentials(
        o_auth_client_id='OAuthClientId',
        o_auth_client_secret='OAuthClientSecret',
        o_auth_redirect_uri='OAuthRedirectUri',
        o_auth_scopes=[
            OAuthScope.ADMIN,
            OAuthScope.ADMIN_APPSREAD
        ]
    ),
    environment=Environment.PRODUCTION,
    logging_configuration=LoggingConfiguration(
        log_level=logging.INFO,
        request_logging_config=RequestLoggingConfiguration(
            log_body=True
        ),
        response_logging_config=ResponseLoggingConfiguration(
            log_headers=True
        )
    )
)
```

### Environment-Based Client Initialization

```python
from slackwebapi.slackwebapi_client import SlackwebapiClient

# Specify the path to your .env file if it’s located outside the project’s root directory.
client = SlackwebapiClient.from_environment(dotenv_path='/path/to/.env')
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| PRODUCTION | **Default** |

## Authorization

This API uses the following authentication schemes.

* [`slackAuth (OAuth 2 Authorization Code Grant)`](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/auth/oauth-2-authorization-code-grant.md)

## List of APIs

* [Admin Apps](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-apps.md)
* [Admin Apps Approved](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-apps-approved.md)
* [Admin Apps Requests](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-apps-requests.md)
* [Admin Apps Restricted](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-apps-restricted.md)
* [Admin Conversations](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-conversations.md)
* [Admin Conversations Ekm](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-conversations-ekm.md)
* [Admin Conversations Restrict Access](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-conversations-restrict-access.md)
* [Admin Emoji](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-emoji.md)
* [Admin Invite Requests](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-invite-requests.md)
* [Admin Invite Requests Approved](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-invite-requests-approved.md)
* [Admin Invite Requests Denied](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-invite-requests-denied.md)
* [Admin Teams Admins](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-teams-admins.md)
* [Admin Teams](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-teams.md)
* [Admin Teams Owners](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-teams-owners.md)
* [Admin Teams Settings](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-teams-settings.md)
* [Admin Usergroups](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-usergroups.md)
* [Admin Users](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-users.md)
* [Admin Users Session](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/admin-users-session.md)
* [Api](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/api.md)
* [Apps Event Authorizations](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/apps-event-authorizations.md)
* [Apps Permissions](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/apps-permissions.md)
* [Apps Permissions Resources](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/apps-permissions-resources.md)
* [Apps Permissions Scopes](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/apps-permissions-scopes.md)
* [Apps Permissions Users](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/apps-permissions-users.md)
* [Apps](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/apps.md)
* [Auth](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/auth.md)
* [Bots](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/bots.md)
* [Calls](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/calls.md)
* [Calls Participants](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/calls-participants.md)
* [Chat](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/chat.md)
* [Chat Scheduled Messages](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/chat-scheduled-messages.md)
* [Conversations](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/conversations.md)
* [Dialog](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/dialog.md)
* [Dnd](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/dnd.md)
* [Emoji](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/emoji.md)
* [Files Comments](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/files-comments.md)
* [Files](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/files.md)
* [Files Remote](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/files-remote.md)
* [Migration](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/migration.md)
* [Oauth](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/oauth.md)
* [Oauth V 2](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/oauth-v-2.md)
* [Pins](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/pins.md)
* [Reactions](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/reactions.md)
* [Reminders](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/reminders.md)
* [Rtm](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/rtm.md)
* [Search](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/search.md)
* [Stars](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/stars.md)
* [Team](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/team.md)
* [Team Profile](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/team-profile.md)
* [Usergroups](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/usergroups.md)
* [Usergroups Users](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/usergroups-users.md)
* [Users](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/users.md)
* [Users Profile](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/users-profile.md)
* [Views](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/views.md)
* [Workflows](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/controllers/workflows.md)

## SDK Infrastructure

### Configuration

* [ProxySettings](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/proxy-settings.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/environment-based-client-initialization.md)
* [AbstractLogger](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/abstract-logger.md)
* [LoggingConfiguration](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/logging-configuration.md)
* [RequestLoggingConfiguration](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/request-logging-configuration.md)
* [ResponseLoggingConfiguration](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/response-logging-configuration.md)

### HTTP

* [HttpResponse](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/http-response.md)
* [HttpRequest](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/api-response.md)
* [ApiHelper](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/api-helper.md)
* [HttpDateTime](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/http-date-time.md)
* [RFC3339DateTime](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/rfc3339-date-time.md)
* [UnixDateTime](https://www.github.com/sdks-io/slack-apimatic-sdk-python-sdk/tree/1.0.0/doc/unix-date-time.md)

