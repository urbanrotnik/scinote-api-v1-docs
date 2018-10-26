# Reports

## Get Reports

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/reports"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "reports",
      "attributes":{
        "name": "Report 1",
        "description": "My report"
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
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/reports?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/reports?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/reports?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves reports from specific project.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/reports`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve reports from

## Get Report

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/reports/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "reports",
    "attributes":{
      "name": "Report 1",
      "description": "My report"
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

This endpoint retrieves a specific report from specific project.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/reports/<REPORT_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve report from
REPORT_ID | The ID of the report to retrieve
