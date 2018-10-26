# Task Activities

## Get Task Activities

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/activities"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "3",
      "type": "activities",
      "attributes":{
        "type_of": "create_module",
        "message": "<i>Admin</i> created task <strong>Experiment design</strong>."
      },
      "relationships":{
        "project":{
          "data":{
            "id": "1",
            "type": "projects"
          }
        },
        "task":{
          "data":{
            "id": "1",
            "type": "tasks"
          }
        },
        "user":{
          "data":{
            "id": "1",
            "type": "users"
          }
        }
      }
    },
    {
      "id": "4",
      "type": "activities",
      "attributes":{
        "type_of": "assign_user_to_module",
        "message": "<i>Admin</i> was added to task <strong>Experiment design</strong> by <i>Admin</i>."
      },
      "relationships":{
        "project":{
          "data":{
            "id": "1",
            "type": "projects"
          }
        },
        "task":{
          "data":{
            "id": "1",
            "type": "tasks"
          }
        },
        "user":{
          "data":{
            "id": "1",
            "type": "users"
          }
        }
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all activities from specific task.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/activities`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve task from
TASK_ID | The ID of the task to retrieve activities from
