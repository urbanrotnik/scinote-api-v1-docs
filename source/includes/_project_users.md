# Project Users

## Get Project Users

```shell
curl "https://<server-name>/api/v1/teams/1/projects/1/users"
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
        "email": "admin@scinote.net",
        "avatar_url" : "http://example.com/avatar.png",
        "avatar_file_size" : 16181,
        "avatar_file_name" : "avatar.png"
      }
    }
  ],
  "links":{
    "self": "https://<server-name>/api/v1/teams/1/projects/1/users?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "https://<server-name>/api/v1/teams/1/projects/1/users?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "https://<server-name>/api/v1/teams/1/projects/1/users?page%5Bnumber%5D=1&page%5Bsize%5D=10"
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
curl "https://<server-name>/api/v1/teams/1/projects/1/users/1"
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
        "email": "admin@scinote.net",
        "avatar_url" : "http://example.com/avatar.png",
        "avatar_file_size" : 16181,
        "avatar_file_name" : "avatar.png"
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


## Create Project User assignment

```shell
curl -X POST \
  https://<server-name>/api/v1/teams/1/projects/1/users \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
    "data": {
      "type": "user_projects",
      "attributes": {
        "user_id": "1",
        "role": "normal_user"
      }
    }
  }'
```

> The above command returns JSON structured like this:
```json
{
  "data": {
    "id": "1",
    "type": "user_projects",
    "attributes": {
      "role": "normal_user"
    },
    "relationships": {
      "user": {
        "data": {
          "id": "1",
          "type": "users"}
        }
      }
    }
  }
}
```
This endpoint creates a new user assignment in the project.

### HTTP Request

`POST https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/users`

### URL Parameters

Parameter     | Description
------------- | -----------
TEAM_ID       | The ID of the team to retrieve project from
PROJECT_ID    | The ID of the project to assign user to

> Request body
```json
{
  "data": {
    "type": "user_projects",
    "attributes": {
      "user_id": "1",
      "role": "normal_user"
    }
  }
}
```
### Project User attributes

Attribute   | Mandatory | Description
----------- | --------- | -----------
user_id     | yes       | ID of the user
role        | yes       | Role on the project

## Update Project User

```shell
curl -X PATCH \
  https://<server-name>/api/v1/teams/1/projects/1/users/1 \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
        "data": {
          "type": "user_projects",
          "attributes": {
            "role": "technician"
          }
      }
  }'
```

> The above command returns JSON structured like this:
```json
{
  "data": {
    "id": "1",
    "type": "user_projects",
    "attributes": {
      "role": "technician"
    },
    "relationships": {
      "user": {
        "data": {
          "id": "1",
          "type": "users"}
        }
      }
    }
  }
}
```
This endpoint updates existing user assignment in the project.
If submitted attributes are the same and no changes are made for the user assignment, server returns empty body with response code 204.

### HTTP Request

`PATCH https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/users/<ID>`

### URL Parameters

Parameter       | Description
--------------- | -----------
TEAM_ID         | The ID of the team to retrieve project from
PROJECT_ID      | The ID of the project to retrieve user assignment from
ID              | The ID of the user assignment

### Request body

```json
{
  "data": {
    "type": "user_projects",
    "attributes": {
      "role": "technician"
    }
  }
}
```

### Project User attributes

Attribute   | Mandatory | Description
----------- | --------- | -----------
role        | yes       | Role on the project

## Delete Project User assignment

```shell
curl -X DELETE \
  https://<server-name>/api/v1/teams/1/projects/1/users/1 \
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns empty body with status code 200

This endpoint deletes specific user assignment from the project.

### HTTP Request

`DELETE https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/users/<ID>`

### URL Parameters

Parameter       | Description
--------------- | -----------
TEAM_ID         | The ID of the team to retrieve project from
PROJECT_ID      | The ID of the project to retrieve user assignment from
ID              | The ID of the user assignment
