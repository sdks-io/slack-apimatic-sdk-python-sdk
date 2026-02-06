# Api

```python
api = client.api
```

## Class Name

`Api`


# Api Test

Checks API calling code.

API method documentation: [https://api.slack.com/methods/api.test](https://api.slack.com/methods/api.test)

```python
def api_test(self,
            error=None,
            foo=None)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | `str` | Query, Optional | Error response to return |
| `foo` | `str` | Query, Optional | example property to return |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `body` property of this instance returns the response data which is of type [`ApiTestSuccessSchema`](../../doc/models/api-test-success-schema.md).

## Example Usage

```python
result = api.api_test()

if result.is_success():
    print(result.body)
elif result.is_error():
    print(result.errors)
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Artificial error response | [`ApiTestErrorSchemaException`](../../doc/models/api-test-error-schema-exception.md) |

