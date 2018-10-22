# Users

## Get a Specific User

```shell
curl "https://<server-name>/api/v1/users/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "users",
        "attributes": {
            "full_name": "Sample User",
            "initials": "SU",
            "email": "sample@example.com"
        }
    }
}
```

This endpoint retrieves a specific user.
Only users who are members of the same teams as current user can be read.

### HTTP Request

`GET https://<server-name>/api/v1/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve
