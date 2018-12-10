# Task Inventory Items

## Get Task Inventory Items

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/items"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
  "data":[
    {
      "id": "1",
      "type": "inventory_items",
      "attributes":{
        "name": "BOX/1"
      },
      "relationships":{
        "inventory_cells":{
          "data":[
            {
              "id": "1",
              "type": "inventory_cells"
            },
            {
              "id": "2",
              "type": "inventory_cells"
            }
          ]
        },
        "inventory":{
          "data":{
            "id": "1",
            "type": "inventories"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "inventory_items",
      "attributes":{
        "name": "BOX/2"
      },
      "relationships":{
        "inventory_cells":{
          "data":[
            {
              "id": "3",
              "type": "inventory_cells"
            },
            {
              "id": "4",
              "type": "inventory_cells"
            }
          ]
        },
        "inventory":{
          "data":{
            "id": "1",
            "type": "inventories"
          }
        }
      }
    }
  ],
  "links":{
    "self": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/items?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "first": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/items?page%5Bnumber%5D=1&page%5Bsize%5D=10",
    "prev": null,
    "next": null,
    "last": "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/items?page%5Bnumber%5D=1&page%5Bsize%5D=10"
  }
}
```

This endpoint retrieves all Inventory Items, that are assigned to the specified task.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/items`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve task from
TASK_ID | The ID of the task to retrieve inventory items from

## Get Task Inventory Item

```shell
curl "http://<server-name>/api/v1/teams/1/projects/1/experiments/1/tasks/2/items/1"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
  "data":{
    "id": "1",
    "type": "inventory_items",
    "attributes":{
      "name": "BOX/1"
    },
    "relationships":{
      "inventory_cells":{
        "data":[
          {
            "id": "1",
            "type": "inventory_cells"
          },
          {
            "id": "2",
            "type": "inventory_cells"
          }
        ]
      },
      "inventory":{
        "data":{
          "id": "1",
          "type": "inventories"
        }
      }
    }
  },
  "included":[
    {
      "id": "1",
      "type": "inventory_cells",
      "attributes":{
        "value_type": "list",
        "value":{
          "inventory_list_item_id": 1,
          "inventory_list_item_name": "Potato leaves"
        },
        "column_id": 1
      }
    },
    {
      "id": "2",
      "type": "inventory_cells",
      "attributes":{
        "value_type": "list",
        "value":{
          "inventory_list_item_id": 6,
          "inventory_list_item_name": "Seed"
        },
        "column_id": 2
      }
    },
    {
      "id": "1",
      "type": "inventories",
      "attributes":{
        "name": "Samples"
      },
      "relationships":{
        "created_by":{
          "data":{
            "id": "1",
            "type": "users"
          }
        }
      }
    }
  ]
}
```

This endpoint retrieves a specific inventory item, that is assigned to the specific task.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/projects/<PROJECT_ID>/experiments/<EXPERIMENT_ID>/tasks/<TASK_ID>/items/<ITEM_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve project from
PROJECT_ID | The ID of the project to retrieve experiment from
EXPERIMENT_ID | The ID of the experiment to retrieve task from
TASK_ID | The ID of the task to retrieve inventory item from
ITEM_ID | The ID of the inventory item to retrieve
