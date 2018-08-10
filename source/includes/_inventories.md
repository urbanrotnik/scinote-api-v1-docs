# Inventories

## Get All Inventories from the specific team

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/inventories"
  -H "Authorization: Bearer qwerty123456..."
```
> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "1",
            "type": "inventories",
            "attributes": {
                "name": "Inventory 1"
            }
        },
        {
            "id": "2",
            "type": "inventories",
            "attributes": {
                "name": "Inventory 2"
            }
        }
    ],
    "links": {
        "self": "https://my-test.scinote.net/api/v1/teams/1/inventories?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://my-test.scinote.net/api/v1/teams/1/inventories?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://my-test.scinote.net/api/v1/teams/1/inventories?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves all inventories from the specified team.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/inventories`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventories from

## Get a Specific Inventory

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/inventories/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "inventories",
        "attributes": {
            "name": "Inventory 1"
        }
    }
}
```

This endpoint retrieves a specific inventory.

### HTTP Request

`GET http://my-test.scinote.net/api/v1/teams/<TEAM_ID>/inventories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
ID | The ID of the inventory to retrieve

## Get Columns from specific inventory

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/inventories/1/columns"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "1",
            "type": "inventory_columns",
            "attributes": {
                "name": "Text Column",
                "data_type": "text"
            },
            "relationships": {
                "inventory_list_items": {
                    "data": []
                }
            }
        },
        {
            "id": "2",
            "type": "inventory_columns",
            "attributes": {
                "name": "File Column",
                "data_type": "file"
            },
            "relationships": {
                "inventory_list_items": {
                    "data": []
                }
            }
        },
        {
            "id": "3",
            "type": "inventory_columns",
            "attributes": {
                "name": "List Column",
                "data_type": "list"
            },
            "relationships": {
                "inventory_list_items": {
                    "data": [
                      {
                        "id": "1",
                        "type": "inventory_list_items"
                      },
                      {
                        "id": "2",
                        "type": "inventory_list_items"
                      }
                    ]
                }
            }
        }
    ],
    "included": [
        {
            "id": "1",
            "type": "inventory_list_items",
            "attributes": {
                "data": "ASF"
            }
        },
        {
            "id": "2",
            "type": "inventory_list_items",
            "attributes": {
                "data": "GDD"
            }
        }
    ],
    "links": {
        "self": "https://my-test.scinote.net/api/v1/teams/1/inventories/1/columns?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://my-test.scinote.net/api/v1/teams/1/inventories/1/columns?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://my-test.scinote.net/api/v1/teams/1/inventories/1/columns?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves columns from specific inventory.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/columns`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve columns from

## Get Items from specific inventory

```shell
curl "http://my-test.scinote.net/api/v1/teams/1/inventories/1/items"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
    "data": [
      {
            "id": "1",
            "type": "inventory_items",
            "attributes": {
                "name": "PHH/1"
            },
            "relationships": {
                "inventory_cells": {
                    "data": [
                        {
                            "id": "1",
                            "type": "inventory_cells"
                        }
                    ]
                }
            }
        },
        {
            "id": "2",
            "type": "inventory_items",
            "attributes": {
                "name": "PHH/2"
            },
            "relationships": {
                "inventory_cells": {
                    "data": [
                        {
                            "id": "2",
                            "type": "inventory_cells"
                        }
                    ]
                }
            }
        }
    ],
    "included": [
        {
            "id": "1",
            "type": "inventory_cells",
            "attributes": {
                "data_type": "list",
                "data": {
                    "value": "ASF",
                    "inventory_list_item_id": 1
                },
                "column_id": 3
            }
        },
        {
            "id": "2",
            "type": "inventory_cells",
            "attributes": {
                "data_type": "text",
                "data": {
                    "value": "VEGB"
                },
                "column_id": 1
            }
        }
    ],
    "links": {
        "self": "https://my-test.scinote.net/api/v1/teams/1/inventories/1/items?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://my-test.scinote.net/api/v1/teams/1/inventories/1/items?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://my-test.scinote.net/api/v1/teams/1/inventories/1/items?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves items from specific inventory.

### HTTP Request

`GET https://my-test.scinote.net/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/items`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve items from
