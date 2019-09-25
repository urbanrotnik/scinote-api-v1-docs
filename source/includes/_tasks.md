# Tasks

## Get Tasks

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "tasks",
      "attributes":{
        "name": "Experiment design",
        "due_date": "2018-10-25T13:30:54.315Z",
        "description": null,
        "state": "uncompleted",
        "archived": false
      },
      "relationships": {
        "outputs": {
          "data": [
            {
              "id": "2",
              "type": "tasks"
            }
          ]
        }
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
      },
      "relationships": {
        "outputs": {
          "data": [
            {
              "id": "3",
              "type": "tasks"
            }
          ]
        },
        "inputs": {
          "data": [
            {
              "id": "1",
              "type": "tasks"
            }
          ]
        }
      }
    },
    {
      "id": "3",
      "type": "tasks",
      "attributes":{
        "name": "RNA isolation",
        "due_date": "2018-11-22T13:30:54.594Z",
        "description": null,
        "state": "uncompleted",
        "archived": false
      },
      "relationships": {
        "inputs": {
          "data": [
            {
              "id": "2",
              "type": "tasks"
            }
          ]
        }
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all tasks from a specific experiment. Task inputs/outputs can be included as relationships.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from

## Get Task

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "tasks",
    "attributes":{
      "name": "Experiment design",
      "due_date": "2018-10-25T13:30:54.315Z",
      "description": null,
      "state": "uncompleted",
      "archived": false
    },
    "relationships": {
      "outputs": {
        "data": [
          {
            "id": "2",
            "type": "tasks"
          }
        ]
      }
    }
  }
}
```

This endpoint retrieves a specific task from a specific experiment. Task inputs/outputs can be included as relationships.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve task from.
TASK_ID | The ID of the task to retrieve


## Create Task

```shell
curl -X POST \
  https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
    "data": {
      "type": "tasks",
      "attributes": {
        "name": "My task 1",
        "description": "Description of the task",
        "x": 1,
        "y": 8
      }
    }
  }'
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "tasks",
    "attributes": {
      "name": "My task 1",
      "due_date": null,
      "description": "Description of the task",
      "state": "uncompleted",
      "archived": false
    },
    "relationships": {
      "outputs": {
        "data": []
      },
      "inputs": {
        "data": []
      }
    }
  }
}

```

This endpoint creates new task in the experiment.

### HTTP Request

`POST https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks`

### URL Parameters

Parameter     | Description
------------- | -----------
TEAM_ID       | The ID of the team to retrieve projects from
PROJECT_ID    | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment

> Request body

```json
{
  "data": {
    "type": "tasks",
    "attributes": {
      "name": "My task 1",
      "description": "Description of the task",
      "x": 1,
      "y": 8
    }
  }
}
```

### Inventory attributes

Attribute   | Mandatory | Description
----------- | --------- | -----------
name        | yes       | Name of the task
description | no        | Description of the task
x           | yes       | x position on canvas
y           | yes       | y position on canvas
