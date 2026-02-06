# Rtm

```python
rtm_api = client.rtm
```

## Class Name

`RtmApi`


# Rtm Connect

Starts a Real Time Messaging session.

API method documentation: [https://api.slack.com/methods/rtm.connect](https://api.slack.com/methods/rtm.connect)

```python
def rtm_connect(self,
               token,
               batch_presence_aware=None,
               presence_sub=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `str` | Query, Required | Authentication token. Requires scope: `rtm:stream` |
| `batch_presence_aware` | `bool` | Query, Optional | Batch presence deliveries via subscription. Enabling changes the shape of `presence_change` events. See [batch presence](/docs/presence-and-status#batching). |
| `presence_sub` | `bool` | Query, Optional | Only deliver presence events when requested by subscription. See [presence subscriptions](/docs/presence-and-status#subscriptions). |

## Requires scope

### slackAuth

`rtm:stream`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`RtmConnectSchema`](../../doc/models/rtm-connect-schema.md).

## Example Usage

```python
token = 'token6'

result = rtm_api.rtm_connect(token)

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RtmConnectErrorSchemaException`](../../doc/models/rtm-connect-error-schema-exception.md) |

