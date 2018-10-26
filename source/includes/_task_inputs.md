# Task Inputs

## Get Task Inputs

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs"
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
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all inputs from a specified task.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/inputs`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve task from
TASK_ID | The ID of the task to retrieve inputs from
