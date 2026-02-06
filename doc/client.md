
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| http_client_instance | `Union[Session, HttpClientProvider]` | The Http Client passed from the sdk user for making requests |
| override_http_client_configuration | `bool` | The value which determines to override properties of the passed Http Client from the sdk user |
| http_call_back | `HttpCallBack` | The callback value that is invoked before and after an HTTP call is made to an endpoint |
| timeout | `float` | The value to use for connection timeout. <br> **Default: 30** |
| max_retries | `int` | The number of times to retry an endpoint call if it fails. <br> **Default: 0** |
| backoff_factor | `float` | A backoff factor to apply between attempts after the second try. <br> **Default: 2** |
| retry_statuses | `Array of int` | The http statuses on which retry is to be done. <br> **Default: [408, 413, 429, 500, 502, 503, 504, 521, 522, 524]** |
| retry_methods | `Array of string` | The http methods on which retry is to be done. <br> **Default: ["GET", "PUT"]** |
| proxy_settings | [`ProxySettings`](../doc/proxy-settings.md) | Optional proxy configuration to route HTTP requests through a proxy server. |
| logging_configuration | [`LoggingConfiguration`](../doc/logging-configuration.md) | The SDK logging configuration for API calls |
| authorization_code_auth_credentials | [`AuthorizationCodeAuthCredentials`](auth/oauth-2-authorization-code-grant.md) | The credential object for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

## Code-Based Client Initialization

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

## Environment-Based Client Initialization

```python
from slackwebapi.slackwebapi_client import SlackwebapiClient

# Specify the path to your .env file if it’s located outside the project’s root directory.
client = SlackwebapiClient.from_environment(dotenv_path='/path/to/.env')
```

See the [Environment-Based Client Initialization](../doc/environment-based-client-initialization.md) section for details.

## Slack Web API Client

The gateway for the SDK. This class acts as a factory for the Apis and also holds the configuration of the SDK.

## Apis

| Name | Description |
|  --- | --- |
| admin_apps | Gets AdminAppsApi |
| admin_apps_approved | Gets AdminAppsApprovedApi |
| admin_apps_requests | Gets AdminAppsRequestsApi |
| admin_apps_restricted | Gets AdminAppsRestrictedApi |
| admin_conversations | Gets AdminConversationsApi |
| admin_conversations_ekm | Gets AdminConversationsEkmApi |
| admin_conversations_restrict_access | Gets AdminConversationsRestrictAccessApi |
| admin_emoji | Gets AdminEmojiApi |
| admin_invite_requests | Gets AdminInviteRequestsApi |
| admin_invite_requests_approved | Gets AdminInviteRequestsApprovedApi |
| admin_invite_requests_denied | Gets AdminInviteRequestsDeniedApi |
| admin_teams_admins | Gets AdminTeamsAdminsApi |
| admin_teams | Gets AdminTeamsApi |
| admin_teams_owners | Gets AdminTeamsOwnersApi |
| admin_teams_settings | Gets AdminTeamsSettingsApi |
| admin_usergroups | Gets AdminUsergroupsApi |
| admin_users | Gets AdminUsersApi |
| admin_users_session | Gets AdminUsersSessionApi |
| api | Gets Api |
| apps_event_authorizations | Gets AppsEventAuthorizationsApi |
| apps_permissions | Gets AppsPermissionsApi |
| apps_permissions_resources | Gets AppsPermissionsResourcesApi |
| apps_permissions_scopes | Gets AppsPermissionsScopesApi |
| apps_permissions_users | Gets AppsPermissionsUsersApi |
| apps | Gets AppsApi |
| auth | Gets AuthApi |
| bots | Gets BotsApi |
| calls | Gets CallsApi |
| calls_participants | Gets CallsParticipantsApi |
| chat | Gets ChatApi |
| chat_scheduled_messages | Gets ChatScheduledMessagesApi |
| conversations | Gets ConversationsApi |
| dialog | Gets DialogApi |
| dnd | Gets DndApi |
| emoji | Gets EmojiApi |
| files_comments | Gets FilesCommentsApi |
| files | Gets FilesApi |
| files_remote | Gets FilesRemoteApi |
| migration | Gets MigrationApi |
| oauth | Gets OauthApi |
| oauth_v_2 | Gets OauthV2Api |
| pins | Gets PinsApi |
| reactions | Gets ReactionsApi |
| reminders | Gets RemindersApi |
| rtm | Gets RtmApi |
| search | Gets SearchApi |
| stars | Gets StarsApi |
| team | Gets TeamApi |
| team_profile | Gets TeamProfileApi |
| usergroups | Gets UsergroupsApi |
| usergroups_users | Gets UsergroupsUsersApi |
| users | Gets UsersApi |
| users_profile | Gets UsersProfileApi |
| views | Gets ViewsApi |
| workflows | Gets WorkflowsApi |
| o_auth_authorization | Gets OAuthAuthorizationApi |

