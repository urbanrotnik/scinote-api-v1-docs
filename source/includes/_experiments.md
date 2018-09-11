# Experiments

## Get All Experiments from the specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "experiments",
         "attributes" : {
            "name" : "My first experiment",
            "description" : "This is my very first experiment",
            "created_by_id" : 1,
            "archived" : false
         },
         "id" : "1"
      }
   ],
   "links" : {
      "first" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "self" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "last" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null
   }
}
```

This endpoint retrieves all experiments from the specified team and project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<ID>/experiments`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
ID | The ID of the project to retrieve experiments from

## Get a Specific Experiment from the specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "experiments",
      "id" : "1",
      "attributes" : {
         "created_by_id" : 1,
         "archived" : false,
         "name" : "My first experiment",
         "description" : "This is my very first experiment"
      }
   }
}
```

This endpoint retrieves a specific experiment.

### HTTP Request

`GET http://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from
ID | The ID of the experiment to retrieve

## Get Tasks from a specific experiment

The task endpoints are described [Below](#tasks) under the Tasks category.


## Get Task Groups from specific experiment

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/task_groups"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "id" : "1",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         },
         "type" : "task_groups",
         "attributes" : {
            "created_by_id" : null,
            "experiment_id" : 1
         }
      }
   ],
   "links" : {
      "self" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments/1/task_groups?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments/1/task_groups?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "last" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments/1/task_groups?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null
   }
}
```

This endpoint retrieves task groups from specific experiment.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/task_groups`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve comments from
EXPERIMENT_ID | The ID of the experiment to retrieve task groups from

## Get a specific Task Group from a specific Experiment

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/task_groups/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "task_groups",
      "relationships" : {
         "experiment" : {
            "data" : {
               "type" : "experiments",
               "id" : "1"
            }
         }
      },
      "attributes" : {
         "created_by_id" : null,
         "experiment_id" : 1
      },
      "id" : "1"
   }
}
```

This endpoint retrieves a specific task group from a specific experiment.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/task_groups/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of experiment to retrieve task groups from
ID | The ID of the task group to retrieve

## Get Task Connections from a specific experiment.

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/connections"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "reports",
         "relationships" : {
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            }
         },
         "attributes" : {
            "description" : "My first report description!",
            "project_id" : 1,
            "name" : "My very first report"
         },
         "id" : "2"
      }
   ],
   "links" : {
      "next" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/reports?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/reports?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/reports?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}

```

This endpoint retrieves canvas task connections from an experiment, (the flow of tasks from the experiment canvas view).

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/connections`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve connections from

## Get a specific Task Connection from specific experiment

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/connections/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "attributes" : {
         "output_id" : 1,
         "input_id" : 2
      },
      "id" : "1",
      "type" : "connections"
   }
}
```

This endpoint retrieves a specific canvas task connection from an experiment, (the flow of tasks from the experiment canvas view).


### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/connections/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve connections from
ID | The ID of the connection to retrieve
