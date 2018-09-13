# Tasks


## Get Tasks from specific experiment

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "attributes" : {
            "name" : "Experiment design",
            "description" : null,
            "due_date" : "2018-09-14T13:43:06.044Z",
            "state" : "uncompleted",
            "my_module_group_id" : 1,
            "nr_of_assigned_samples" : 0
         },
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         },
         "id" : "1"
      },
      {
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         },
         "attributes" : {
            "due_date" : "2018-09-28T13:43:06.204Z",
            "description" : null,
            "name" : "Sampling biological material",
            "my_module_group_id" : 1,
            "nr_of_assigned_samples" : 4,
            "state" : "uncompleted"
         },
         "id" : "2"
      },
      {
         "id" : "3",
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "id" : "1",
                  "type" : "experiments"
               }
            }
         },
         "attributes" : {
            "my_module_group_id" : 1,
            "nr_of_assigned_samples" : 4,
            "state" : "uncompleted",
            "due_date" : "2018-10-12T13:43:06.269Z",
            "description" : null,
            "name" : "RNA isolation"
         }
      },
      {
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         },
         "attributes" : {
            "due_date" : "2018-10-26T13:43:06.317Z",
            "description" : null,
            "name" : "RNA quality & quantity - BIOANALYSER",
            "state" : "uncompleted",
            "my_module_group_id" : 1,
            "nr_of_assigned_samples" : 4
         },
         "id" : "4"
      },
      {
         "id" : "5",
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         },
         "attributes" : {
            "state" : "uncompleted",
            "my_module_group_id" : 1,
            "nr_of_assigned_samples" : 4,
            "due_date" : "2018-11-09T13:43:06.358Z",
            "name" : "Reverse transcription",
            "description" : null
         }
      },
      {
         "attributes" : {
            "nr_of_assigned_samples" : 4,
            "my_module_group_id" : 1,
            "state" : "uncompleted",
            "due_date" : "2018-11-23T13:43:06.396Z",
            "description" : "PCR is a method where an enzyme\n      (thermostable DNA polymerase, originally isolated in 1960s\n      from bacterium Thermus aquaticus, growing in hot lakes of\n      Yellowstone park, USA) amplifies a short specific part of\n      the template DNA (amplicon) in cycles. In every cycle the\n      number of short specific sections of DNA is doubled, leading\n      to an exponential amplification of targets. More on how\n      conventional PCR works can be found here.",
            "name" : "qPCR"
         },
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         },
         "type" : "tasks",
         "id" : "6"
      },
      {
         "attributes" : {
            "state" : "uncompleted",
            "nr_of_assigned_samples" : 4,
            "my_module_group_id" : 1,
            "name" : "Data quality control",
            "description" : null,
            "due_date" : "2018-12-07T13:43:06.438Z"
         },
         "relationships" : {
            "experiment" : {
               "data" : {
                  "id" : "1",
                  "type" : "experiments"
               }
            }
         },
         "type" : "tasks",
         "id" : "7"
      },
      {
         "id" : "8",
         "attributes" : {
            "nr_of_assigned_samples" : 4,
            "my_module_group_id" : 1,
            "state" : "uncompleted",
            "description" : null,
            "name" : "Data analysis - ddCq",
            "due_date" : "2018-12-21T13:43:06.477Z"
         },
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "id" : "1",
                  "type" : "experiments"
               }
            }
         }
      },
      {
         "type" : "tasks",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "id" : "1",
                  "type" : "experiments"
               }
            }
         },
         "attributes" : {
            "my_module_group_id" : null,
            "nr_of_assigned_samples" : 0,
            "state" : "uncompleted",
            "due_date" : "2018-09-14T13:43:06.515Z",
            "name" : "Data analysis - Pfaffl method",
            "description" : null
         },
         "id" : "9"
      }
   ],
   "links" : {
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "next" : null,
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves tasks from a specific experiment.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from

## Get a specific Task from a specific Experiment

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
   "data" : {
      "id" : "1",
      "relationships" : {
         "experiment" : {
            "data" : {
               "id" : "1",
               "type" : "experiments"
            }
         }
      },
      "type" : "tasks",
      "attributes" : {
         "due_date" : "2018-09-14T13:43:06.044Z",
         "name" : "Experiment design",
         "nr_of_assigned_samples" : 0,
         "state" : "uncompleted",
         "description" : null,
         "my_module_group_id" : 1
      }
   }
}
```

This endpoint retrieves a specific task from a specific experiment.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from.
ID | The ID of the task to retrieve

## Get Task Inventory Rows from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_inventory_rows"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "attributes" : {
            "my_module_id" : 1,
            "repository_row_id" : 1
         },
         "id" : "36",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "1"
               }
            }
         },
         "type" : "task_inventory_rows"
      },
      {
         "attributes" : {
            "my_module_id" : 1,
            "repository_row_id" : 2
         },
         "id" : "37",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "id" : "1",
                  "type" : "tasks"
               }
            }
         },
         "type" : "task_inventory_rows"
      }
   ],
   "links" : {
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_inventory_rows?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_inventory_rows?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null,
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_inventory_rows?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves all Inventory rows, that are assigned to the specified task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/task_inventory_rows`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve inventory rows from

## Get a specific Task Inventory Row from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_inventory_rows/37"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "relationships" : {
         "my_module" : {
            "data" : {
               "id" : "1",
               "type" : "tasks"
            }
         }
      },
      "id" : "37",
      "attributes" : {
         "my_module_id" : 1,
         "repository_row_id" : 2
      },
      "type" : "task_inventory_rows"
   }
}
```

This endpoint retrieves a specific inventory row, that is assigned to the specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/task_inventory_rows/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve inventory rows from
ID | The ID of the inventory row to retrieve


## Get User Tasks relations data from Tasks

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/user_tasks"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "id" : "1",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "id" : "1",
                  "type" : "tasks"
               }
            }
         },
         "type" : "user_tasks",
         "attributes" : {
            "my_module_id" : 1,
            "user_id" : 1
         }
      }
   ],
   "links" : {
      "next" : null,
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/user_tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/user_tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/user_tasks?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves all User Task relations from a specified task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/user_tasks`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve User Task relations from

## Get a specific User Task relation data from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/user_tasks/1"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "user_tasks",
      "relationships" : {
         "my_module" : {
            "data" : {
               "type" : "tasks",
               "id" : "1"
            }
         }
      },
      "id" : "1",
      "attributes" : {
         "user_id" : 1,
         "my_module_id" : 1
      }
   }
}
```

This endpoint retrieves a specific User Task relation, that belongs to a specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/user_tasks/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve User Task relations from
ID | The ID of the User Task relation to retrieve

## Get Task Tags from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_tags"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "id" : "1",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "1"
               }
            }
         },
         "type" : "task_tags",
         "attributes" : {
            "my_module_id" : 1,
            "tag_id" : 1
         }
      }
   ],
   "links" : {
      "next" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_tags?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_tags?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_tags?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves all task tags, that are assigned to the specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/task_tags`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve task tags from

## Get a specific Task Tag from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/task_tags/1"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "id" : "1",
      "relationships" : {
         "my_module" : {
            "data" : {
               "id" : "1",
               "type" : "tasks"
            }
         }
      },
      "attributes" : {
         "my_module_id" : 1,
         "tag_id" : 1
      },
      "type" : "task_tags"
   }
}
```

This endpoint retrieves a specific task tag, that is assigned to a specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/task_tags/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve task tags from
ID | The ID of the task tag to retrieve


## Get Protocols from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "protocols",
         "relationships" : {
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "1"
               }
            }
         },
         "attributes" : {
            "nr_of_linked_children" : 0,
            "protocol_type" : "unlinked",
            "authors" : null,
            "team_id" : 1,
            "my_module_id" : 1,
            "name" : null,
            "description" : null
         },
         "id" : "1"
      }
   ],
   "links" : {
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null,
      "prev" : null,
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves all protocols that are assigned to a specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/protocols`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve protocols from

## Get a specific Protocol from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/1/protocols/1"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "id" : "1",
      "attributes" : {
         "name" : null,
         "team_id" : 1,
         "protocol_type" : "unlinked",
         "authors" : null,
         "nr_of_linked_children" : 0,
         "my_module_id" : 1,
         "description" : null
      },
      "type" : "protocols",
      "relationships" : {
         "my_module" : {
            "data" : {
               "type" : "tasks",
               "id" : "1"
            }
         }
      }
   }
}
```

This endpoint retrieves a specific protocol that is assigned to a specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/protocols/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve protocols from
ID | The ID of the protocol to retrieve


## Get Results from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/results"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "relationships" : {
            "my_module" : {
               "data" : {
                  "id" : "1",
                  "type" : "tasks"
               }
            }
         },
         "attributes" : {
            "result_text" : null,
            "my_module_id" : 1,
            "result_table" : {
               "result_id" : 1,
               "table_id" : 1,
               "id" : 1
            },
            "result_asset" : null,
            "user_id" : 1,
            "name" : "Experimental design",
            "archived" : false
         },
         "type" : "results",
         "id" : "1"
      },
      {
         "attributes" : {
            "user_id" : 1,
            "name" : "Terrific result",
            "result_text" : {
               "result_id" : 6,
               "id" : 3,
               "text" : "<!DOCTYPE html PUBLIC \"-//W3C//DTD HTML 4.0 Transitional//EN\" \"http://www.w3.org/TR/REC-html40/loose.dtd\">\n<html><body><p>amazing work team, really solid work</p></body></html>"
            },
            "my_module_id" : 1,
            "result_asset" : null,
            "result_table" : null,
            "archived" : false
         },
         "relationships" : {
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "1"
               }
            }
         },
         "type" : "results",
         "id" : "6"
      },
      {
         "id" : "7",
         "type" : "results",
         "attributes" : {
            "my_module_id" : 1,
            "result_text" : null,
            "result_asset" : {
               "id" : 1,
               "asset_id" : 1,
               "result_id" : 7
            },
            "result_table" : null,
            "user_id" : 1,
            "name" : "Im including an image of the gene doing gene things.",
            "archived" : false
         },
         "relationships" : {
            "my_module" : {
               "data" : {
                  "type" : "tasks",
                  "id" : "1"
               }
            }
         }
      }
   ],
   "links" : {
      "prev" : null,
      "last" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments/1/tasks/1/results?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "self" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments/1/tasks/1/results?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null,
      "first" : "http://0.0.0.0:3000/api/v1/teams/1/projects/1/experiments/1/tasks/1/results?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves all results (includes attributes from text, asset and table result if present), that are part of a specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/results`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve results from

## Get a specific Result from a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/results/2"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "relationships" : {
         "my_module" : {
            "data" : {
               "type" : "tasks",
               "id" : "2"
            }
         }
      },
      "id" : "2",
      "attributes" : {
         "archived" : false,
         "name" : "Number of samples",
         "result_table" : null,
         "result_text" : {
            "result_id" : 2,
            "id" : 1,
            "text" : "There are many biological replicates we harvested for each type of sample (code-names):\n\n* OSH/5\n\n* DWO/1\n\n* DWO/5\n\n* OSH/1"
         },
         "user_id" : 1,
         "my_module_id" : 2,
         "result_asset" : null
      },
      "type" : "results"
   }
}
```

This endpoint retrieves a specific result (includes attributes from text, asset and table result if present), that are part of a specific task.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/results/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve results from
ID | The ID of the result to retrieve


## Get Task children (outputs) of a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/outputs"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "attributes" : {
            "description" : null,
            "name" : "RNA isolation",
            "state" : "uncompleted",
            "my_module_group_id" : 1,
            "due_date" : "2018-10-12T13:43:06.269Z",
            "nr_of_assigned_samples" : 4
         },
         "type" : "tasks",
         "id" : "3",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "id" : "1",
                  "type" : "experiments"
               }
            }
         }
      }
   ],
   "links" : {
      "prev" : null,
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/outputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/outputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/outputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "next" : null
   }
}
```

This endpoint retrieves all Tasks (children) that the specified task is parent of (These relations are visible from experiments canvas)

Clarification Below (Relations category)

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/outputs`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve outputs (children) from

## Get a specific Task child (output) of a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/outputs/3"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "relationships" : {
         "experiment" : {
            "data" : {
               "id" : "1",
               "type" : "experiments"
            }
         }
      },
      "attributes" : {
         "name" : "RNA isolation",
         "my_module_group_id" : 1,
         "description" : null,
         "state" : "uncompleted",
         "nr_of_assigned_samples" : 4,
         "due_date" : "2018-10-12T13:43:06.269Z"
      },
      "id" : "3",
      "type" : "tasks"
   }
}
```

This endpoint retrieves a task (a child) that the specified task is a parent of (These relations are visible from experiments canvas).

Clarification Below (Relations category)

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/outputs/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve children from
ID | The ID of the child task to retrieve



## Get Task parents (inputs) of a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : [
      {
         "type" : "tasks",
         "attributes" : {
            "nr_of_assigned_samples" : 0,
            "my_module_group_id" : 1,
            "description" : null,
            "due_date" : "2018-09-14T13:43:06.044Z",
            "name" : "Experiment design",
            "state" : "uncompleted"
         },
         "id" : "1",
         "relationships" : {
            "experiment" : {
               "data" : {
                  "type" : "experiments",
                  "id" : "1"
               }
            }
         }
      }
   ],
   "links" : {
      "next" : null,
      "self" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "prev" : null,
      "first" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs?page%5Bnumber%5D=1&page%5Bsize%5D=10",
      "last" : "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs?page%5Bnumber%5D=1&page%5Bsize%5D=10"
   }
}
```

This endpoint retrieves tasks (parents) that the specified task is a child of (These relations are visible from experiments canvas).

Clarification Below (Relations category)

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/inputs`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve inputs (parents) from

## Get a specific Task parent (input) of a specific Task

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/projects/1/experiments/1/tasks/2/inputs/1"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
   "data" : {
      "type" : "tasks",
      "attributes" : {
         "state" : "uncompleted",
         "description" : null,
         "nr_of_assigned_samples" : 0,
         "my_module_group_id" : 1,
         "name" : "Experiment design",
         "due_date" : "2018-09-14T13:43:06.044Z"
      },
      "relationships" : {
         "experiment" : {
            "data" : {
               "type" : "experiments",
               "id" : "1"
            }
         }
      },
      "id" : "1"
   }
}
```

This endpoint retrieves a task (a parent) that the specified task is a child of (These relations are visible from experiments canvas).

Clarification Below (Relations category)

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/inputs/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve projects from
PROJECT_ID | The ID of the project to retrieve experiments from
EXPERIMENT_ID | The ID of the experiment to retrieve tasks from
TASK_ID | The ID of the task to retrieve parents from
ID | The ID of the parent task to retrieve


## Relations

If our experiment canvas consists of 4 tasks, in a simple relation:

Task1 -> Task2 -> Task3 -> Task4

Where -> signifies that the left task is the parent of the right connecting task.
Then the get call for outputs of Task1, would give us Task2, and then inputs call for the same task wouldn't return anything, because Task1 doesn't have any parent tasks.
By the same logic, the outputs call to Task4 wouldn't return anything, because Task4 does not have children, but the inputs call to it would return Task3
The outputs call to Task3 would return Task4, because Task3 has a child and its Task4, and the inputs call to Task3 would return Task2, because Task2 is a parent of Task3.
