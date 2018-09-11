# Projects

## Get All Projects from the specific team

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "attributes" : {
            "archived" : false,
            "visibility" : "hidden",
            "experiments_order" : null,
            "due_date" : null,
            "name" : "Demo project - qPCR"
         },
         "type" : "projects",
         "relationships" : {
            "team" : {
               "data" : {
                  "id" : "1",
                  "type" : "teams"
               }
            }
         },
         "id" : "1"
      }
   ],
   "links" : {
      "last" : "https://my-test.scinote.net/api/v1/teams/1/projects?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "next" : null,
      "self" : "https://my-test.scinote.net/api/v1/teams/1/projects?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "https://my-test.scinote.net/api/v1/teams/1/projects?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}

```

This endpoint retrieves all projects from the specified team.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from

## Get a Specific Project from the specific team

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "projects",
      "attributes" : {
         "due_date" : null,
         "archived" : false,
         "visibility" : "hidden",
         "experiments_order" : null,
         "name" : "Demo project - qPCR"
      },
      "id" : "1",
      "relationships" : {
         "team" : {
            "data" : {
               "type" : "teams",
               "id" : "1"
            }
         }
      }
   }
}

```

This endpoint retrieves a specific project.

### HTTP Request

`GET http://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
ID | The ID of the project to retrieve

## Get UserProject entities from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/user_projects"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "user_projects",
         "attributes" : {
            "user_id" : 1,
            "role" : "owner"
         },
         "relationships" : {
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            }
         },
         "id" : "1"
      }
   ],
   "links" : {
      "next" : null,
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/user_projects?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/user_projects?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/user_projects?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}

```

This endpoint retrieves UserProject entities (users related to project data) from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/user_projects`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve UserProject entities from

## Get a specific UserProject entity from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/user_projects/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "user_projects",
      "relationships" : {
         "project" : {
            "data" : {
               "id" : "1",
               "type" : "projects"
            }
         }
      },
      "id" : "1",
      "attributes" : {
         "role" : "owner",
         "user_id" : 1
      }
   }
}
```

This endpoint retrieves a specific UserProject entity (users related to project data) from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/user_projects/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve UserProject entities from
ID | The ID of the UserProject entity to retrieve.

## Get Comments from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/project_comments"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "project_comments",
         "id" : "1",
         "relationships" : {
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            }
         },
         "attributes" : {
            "associated_id" : 1,
            "message" : "I've created a demo project",
            "type" : "ProjectComment",
            "user_id" : 1
         }
      }
   ],
   "links" : {
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/project_comments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/project_comments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/project_comments?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null
   }
}

```

This endpoint retrieves comments from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/comments`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve comments from

## Get a specific Comment from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/project_comments/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "project_comments",
      "attributes" : {
         "message" : "I've created a demo project",
         "associated_id" : 1,
         "type" : "ProjectComment",
         "user_id" : 1
      },
      "id" : "1",
      "relationships" : {
         "project" : {
            "data" : {
               "id" : "1",
               "type" : "projects"
            }
         }
      }
   }
}
```

This endpoint retrieves a specific comment from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/project_comments/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve comments from
ID | The ID of the comment to retrieve.

## Get Reports from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/reports"
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

This endpoint retrieves reports from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/reports`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve reports from

## Get a specific Report from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/reports/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "id" : "1",
      "type" : "reports",
      "relationships" : {
         "project" : {
            "data" : {
               "id" : "1",
               "type" : "projects"
            }
         }
      },
      "attributes" : {
         "project_id" : 1,
         "name" : "My very first report",
         "description" : "My first report description!"
      }
   }
}

```

This endpoint retrieves a specific report from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/reports/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve reports from
ID | The ID of the report to retrieve.

## Get Activities from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/activities"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "activities",
         "attributes" : {
            "user_id" : 1,
            "experiment_id" : null,
            "type_of" : "create_project",
            "project_id" : 1,
            "message" : "<i>Admin</i> created project <strong>Demo project - qPCR</strong>.",
            "my_module_id" : null
         },
         "relationships" : {
            "experiment" : {
               "data" : null
            },
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            },
            "my_module" : {
               "data" : null
            }
         },
         "id" : "1"
      },
      {
         "attributes" : {
            "user_id" : 1,
            "type_of" : "add_comment_to_project",
            "project_id" : 1,
            "message" : "<i>Admin</i> commented on project <strong>Demo project - qPCR</strong>.",
            "my_module_id" : null,
            "experiment_id" : null
         },
         "type" : "activities",
         "id" : "2",
         "relationships" : {
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            },
            "my_module" : {
               "data" : null
            },
            "experiment" : {
               "data" : null
            }
         }
      },
      {
         "type" : "activities",
         "attributes" : {
            "user_id" : 1,
            "my_module_id" : 1,
            "message" : "<i>Admin</i> created task <strong>Experiment design</strong>.",
            "project_id" : 1,
            "type_of" : "create_module",
            "experiment_id" : null
         },
         "relationships" : {
            "experiment" : {
               "data" : null
            },
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            },
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "1"
               }
            }
         },
         "id" : "3"
      },
      {
         "relationships" : {
            "experiment" : {
               "data" : null
            },
            "my_module" : {
               "data" : {
                  "id" : "1",
                  "type" : "tasks"
               }
            },
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            }
         },
         "id" : "4",
         "type" : "activities",
         "attributes" : {
            "user_id" : 1,
            "experiment_id" : null,
            "my_module_id" : 1,
            "project_id" : 1,
            "message" : "<i>Admin</i> was added to task <strong>Experiment design</strong> by <i>Admin</i>.",
            "type_of" : "assign_user_to_module"
         }
      },
      {
         "id" : "5",
         "relationships" : {
            "experiment" : {
               "data" : null
            },
            "my_module" : {
               "data" : {
                  "id" : "2",
                  "type" : "tasks"
               }
            },
            "project" : {
               "data" : {
                  "id" : "1",
                  "type" : "projects"
               }
            }
         },
         "attributes" : {
            "experiment_id" : null,
            "my_module_id" : 2,
            "type_of" : "create_module",
            "project_id" : 1,
            "message" : "<i>Admin</i> created task <strong>Sampling biological material</strong>.",
            "user_id" : 1
         },
         "type" : "activities"
      },
      {
         "type" : "activities",
         "attributes" : {
            "user_id" : 1,
            "experiment_id" : null,
            "my_module_id" : 2,
            "message" : "<i>Admin</i> was added to task <strong>Sampling biological material</strong> by <i>Admin</i>.",
            "project_id" : 1,
            "type_of" : "assign_user_to_module"
         },
         "relationships" : {
            "experiment" : {
               "data" : null
            },
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            },
            "my_module" : {
               "data" : {
                  "id" : "2",
                  "type" : "tasks"
               }
            }
         },
         "id" : "6"
      },
      {
         "id" : "7",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "3"
               }
            },
            "project" : {
               "data" : {
                  "id" : "1",
                  "type" : "projects"
               }
            },
            "experiment" : {
               "data" : null
            }
         },
         "attributes" : {
            "user_id" : 1,
            "project_id" : 1,
            "type_of" : "create_module",
            "message" : "<i>Admin</i> created task <strong>RNA isolation</strong>.",
            "my_module_id" : 3,
            "experiment_id" : null
         },
         "type" : "activities"
      },
      {
         "attributes" : {
            "user_id" : 1,
            "my_module_id" : 3,
            "message" : "<i>Admin</i> was added to task <strong>RNA isolation</strong> by <i>Admin</i>.",
            "project_id" : 1,
            "type_of" : "assign_user_to_module",
            "experiment_id" : null
         },
         "type" : "activities",
         "id" : "8",
         "relationships" : {
            "experiment" : {
               "data" : null
            },
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "3"
               }
            },
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            }
         }
      },
      {
         "attributes" : {
            "user_id" : 1,
            "experiment_id" : null,
            "project_id" : 1,
            "message" : "<i>Admin</i> created task <strong>RNA quality & quantity - BIOANALYSER</strong>.",
            "type_of" : "create_module",
            "my_module_id" : 4
         },
         "type" : "activities",
         "id" : "9",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "id" : "4",
                  "type" : "tasks"
               }
            },
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            },
            "experiment" : {
               "data" : null
            }
         }
      },
      {
         "attributes" : {
            "user_id" : 1,
            "my_module_id" : 4,
            "type_of" : "assign_user_to_module",
            "project_id" : 1,
            "message" : "<i>Admin</i> was added to task <strong>RNA quality & quantity - BIOANALYSER</strong> by <i>Admin</i>.",
            "experiment_id" : null
         },
         "type" : "activities",
         "id" : "10",
         "relationships" : {
            "project" : {
               "data" : {
                  "type" : "projects",
                  "id" : "1"
               }
            },
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "4"
               }
            },
            "experiment" : {
               "data" : null
            }
         }
      }
   ],
   "links" : {
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=2&page%5Bsize%5D=10",
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/activities?page%5Bnumber%5D=7&page%5Bsize%5D=10",
      "prev" : null
   }
}

```

This endpoint retrieves logged activities from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/activities`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve activities from

## Get a specific Activity from specific project

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/activities/2"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "attributes" : {
         "message" : "<i>Admin</i> commented on project <strong>Demo project - qPCR</strong>.",
         "type_of" : "add_comment_to_project",
         "my_module_id" : null,
         "project_id" : 1,
         "user_id" : 1,
         "experiment_id" : null
      },
      "id" : "2",
      "type" : "activities",
      "relationships" : {
         "project" : {
            "data" : {
               "type" : "projects",
               "id" : "1"
            }
         },
         "my_module" : {
            "data" : null
         },
         "experiment" : {
            "data" : null
         }
      }
   }
}

```

This endpoint retrieves a specific activity from specific project.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/activities/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve activities from
ID | The ID of the activity to retrieve.


## Get Experiments from specific project


This endpoint is specified below: [Experiments](#experiments)
