# Teams

## Get All Teams

```shell
curl "https://my-test.scinote.net/api/v1/teams"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "1",
            "type": "teams",
            "attributes": {
                "name": "Team 1",
                "description": "This is team 1",
                "space_taken": 805809574
            }
        },
        {
            "id": "2",
            "type": "teams",
            "attributes": {
                "name": "Team 2",
                "description": "This is team 2",
                "space_taken": 24370008357
            }
        }
    ],
    "links": {
        "self": "https://my-test.scinote.net/api/v1/teams?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://my-test.scinote.net/api/v1/teams?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://my-test.scinote.net/api/v1/teams?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves all teams user is member of.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams`

## Get a Specific Team

```shell
curl "https://my-test.scinote.net/api/v1/teams/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "teams",
        "attributes": {
            "name": "Team 1",
            "description": "This is team 1",
            "space_taken": 805809574
        }
    }
}
```

This endpoint retrieves a specific team.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the team to retrieve
