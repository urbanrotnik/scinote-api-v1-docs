# Project Users

## Get Project Users

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/users"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "user_projects",
      "attributes":{
        "role": "owner"
      },
      "relationships":{
        "user":{
          "data":{
            "id": "1",
            "type": "users"
          }
        }
      }
    }
  ],
  "included":[
    {
      "id": "1",
      "type": "users",
      "attributes":{
        "full_name": "Admin",
        "initials": "A",
        "email": "admin@scinote.net"
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/users?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/users?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/users?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all users who are members of the specified project.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/users`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve users from

## Get Project User

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/users/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "user_projects",
    "attributes":{
      "role": "owner"
    },
    "relationships":{
      "user":{
        "data":{
          "id": "1",
          "type": "users"
        }
      }
    }
  },
  "included":[
    {
      "id": "1",
      "type": "users",
      "attributes":{
        "full_name": "Admin",
        "initials": "A",
        "email": "admin@scinote.net"
      }
    }
  ]
}
```

This endpoint retrieves a specific user who is a member of the specified project.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/users/<USER_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve user from
USER_ID | The ID of the user to retrieve
