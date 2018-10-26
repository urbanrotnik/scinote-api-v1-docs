# Task Connections

## Get Task Connections

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/connections"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "connections",
      "relationships":{
        "input_task":{
          "data":{
            "id": "1",
            "type": "tasks"
          }
        },
        "output_task":{
          "data":{
            "id": "2",
            "type": "tasks"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "connections",
      "relationships":{
        "input_task":{
          "data":{
            "id": "2",
            "type": "tasks"
          }
        },
        "output_task":{
          "data":{
            "id": "3",
            "type": "tasks"
          }
        }
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/connections?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/connections?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/connections?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all connections between tasks from specific experiment.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/connections`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve connection from

## Get Task Connection

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/connections/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "connections",
    "relationships":{
      "input_task":{
        "data":{
          "id": "1",
          "type": "tasks"
        }
      },
      "output_task":{
        "data":{
          "id": "2",
          "type": "tasks"
        }
      }
    }
  },
  "included":[
    {
      "id": "1",
      "type": "tasks",
      "attributes":{
        "name": "Experiment design",
        "due_date": "2018-10-25T13:30:54.315Z",
        "description": null,
        "state": "uncompleted",
        "archived": false
      }
    },
    {
      "id": "2",
      "type": "tasks",
      "attributes":{
        "name": "Sampling biological material",
        "due_date": "2018-11-08T13:30:54.520Z",
        "description": null,
        "state": "uncompleted",
        "archived": false
      }
    }
  ]
}
```

This endpoint retrieves a specific connection between tasks from specific experiment.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/connections/<CONNECTION_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve connection from
CONNECTION_ID | The ID of the connection to retrieve
