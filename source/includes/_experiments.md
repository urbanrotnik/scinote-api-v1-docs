# Experiments

## Get Experiments

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "experiments",
      "attributes":{
        "name": "My first experiment",
        "description": "This is my very first experiment",
        "archived": false
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/experiments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/experiments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/experiments?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all experiments from the specified project.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from

## Get Experiment

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "experiments",
    "attributes":{
      "name": "My first experiment",
      "description": "This is my very first experiment",
      "archived": false
    }
  }
}
```

This endpoint retrieves a specific experiment from the specified project.

### HTTP Request

`GET http://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve
