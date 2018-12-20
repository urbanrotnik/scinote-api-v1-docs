# Projects

## Get Projects

```shell
curl "http://<server-name>/api/v1/teams/1/projects"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "projects",
      "attributes":{
        "name": "Demo project - qPCR",
        "visibility": "hidden",
        "start_date": null,
        "archived": false
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}

```

This endpoint retrieves all projects from the specified team.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from

## Get Project

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "projects",
    "attributes":{
      "name": "Demo project - qPCR",
      "visibility": "hidden",
      "start_date": null,
      "archived": false
    }
  }
}
```

This endpoint retrieves a specific project from a specific team.

### HTTP Request

`GET http://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve
