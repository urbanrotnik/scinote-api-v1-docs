# Status

## Status

```shell
curl "https://<server-name>/api/status"
```

> The above command returns JSON structured like this:

```json
{
  "message":"Ok",
  "versions": [
    {
      "version": "v1",
      "baseUrl": "/api/v1/"
    }
  ]
}
```

This endpoint returns status of API and index of all running API versions.

### HTTP Request

`GET https://<server-name>/api/status`

## Health

```shell
curl "https://<server-name>/api/health"
```
> The above command returns a plain text:

```
RUNNING
```

This endpoint returns `RUNNING` response along with the 200 status code
if the API is running.

### HTTP Request

`GET https://<server-name>/api/health`
