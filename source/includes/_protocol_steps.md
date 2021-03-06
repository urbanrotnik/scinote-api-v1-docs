# Protocol Steps

## Get Steps

```shell
curl "https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "4196",
      "type": "steps",
      "attributes": {
        "name": "Step name",
        "description": "Description about step",
        "position": 32,
        "completed": true,
        "completed_on": "2019-09-16T13:47:22.069Z"
      },
      "relationships": {
        "protocol": {
          "data": {
            "id": "1",
            "type": "protocols"
          }
        }
      }
    },
    {
      "id": "4195",
      "type": "steps",
      "attributes": {
        "name": "Step name",
        "description": "Description about step",
        "position": 31,
        "completed": false
      },
      "relationships": {
        "protocol": {
          "data": {
            "id": "1",
            "type": "protocols"
          }
        }
      }
    },
    {
      "id": "4194",
      "type": "steps",
      "attributes": {
        "name": "Step name",
        "description": "Description about step",
        "position": 30,
        "completed": false
      },
      "relationships": {
        "protocol": {
          "data": {
            "id": "1",
            "type": "protocols"
          }
        }
      }
    }
  ],
  "links": {
    "self": "https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": "https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps?page%5Bnumber%5D=4&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves steps from specific protocol.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/protocols/<PROTOCOL_ID>/steps`
### URL Parameters

Parameter       | Description
--------------- | -----------
TEAM_ID         | The ID of the team to retrieve project from
PROJECT_ID      | The ID of the project to retrieve experiment from
EXPERIMENT_ID   | The ID of the experiment to retrieve task from
TASK_ID         | The ID of the task to retrieve protocol from
PROTOCOL_ID     | The ID of the protocol to retrieve steps from

## Get Step

```shell
curl "https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps/1"
  -H "Authorization: Bearer qwerty123456..."
  
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "steps",
    "attributes": {
      "name": "Step name",
      "description": "Description about step",
      "position": 1,
      "completed": true,
      "completed_on": "2019-09-16T13:47:22.069Z"
    },
    "relationships": {
      "protocol": {
        "data": {
          "id": "1",
          "type": "protocols"
        }
      }
    }
  }
}
```

This endpoint retrieves specific step from the protocol.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/protocols/<PROTOCOL_ID>/steps/<ID>`

### URL Parameters

Parameter       | Description
--------------- | -----------
TEAM_ID         | The ID of the team to retrieve project from
PROJECT_ID      | The ID of the project to retrieve experiment from
EXPERIMENT_ID   | The ID of the experiment to retrieve task from
TASK_ID         | The ID of the task to retrieve protocol from
PROTOCOL_ID     | The ID of the protocol to retrieve steps from
ID              | The ID of the step

## Create Step

```shell
curl -X POST \
  https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
	"data": {
		"type": "steps",
		"attributes": {
			"name": "Step name",
			"description": "Description about step"
		}
	}
}'
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "1",
    "type": "steps",
    "attributes": {
      "name": "Step name",
      "description": "Description about step",
      "position": 1,
      "completed": false
    },
    "relationships": {
      "protocol": {
        "data": {
          "id": "1",
          "type": "protocols"
        }
      }
    }
  }
}
```

This endpoint creates new step in the protocol.

### HTTP Request

`POST https://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1/steps`

### URL Parameters

Parameter       | Description
--------------- | -----------
TEAM_ID         | The ID of the team to retrieve project from
PROJECT_ID      | The ID of the project to retrieve experiment from
EXPERIMENT_ID   | The ID of the experiment to retrieve task from
TASK_ID         | The ID of the task to retrieve protocol from
PROTOCOL_ID     | The ID of the protocol to retrieve steps from

> Request body

```json
{
  "data": {
    "type": "steps",
    "attributes": {
      "name": "Step name",
      "description": "Description about step"
    }
  }
}
```

### Inventory item attributes

Attribute   | Mandatory| Description
---------   | -------- | -----------
name        | yes      | Name of the step
description | no       | Description of the step
