# Project Activities

## Get Project Activities

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/activities"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "activities",
      "attributes":{
        "type_of": "create_project",
        "message": "<i>Admin</i> created project <strong>Demo project - qPCR</strong>."
      },
      "relationships":{
        "project":{
          "data":{
            "id": "1",
            "type": "projects"
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
      "id": "2",
      "type": "activities",
      "attributes":{
        "type_of": "add_comment_to_project",
        "message": "<i>Admin</i> commented on project <strong>Demo project - qPCR</strong>."
      },
      "relationships":{
        "project":{
          "data":{
            "id": "1",
            "type": "projects"
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
    "self": "http://<server-name>/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": "http://<server-name>/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=2&page%5Bsize%5D=10",
    "last": "http://<server-name>/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=8&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all activities from specific project.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/activities`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve activities from
