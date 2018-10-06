# Inventories

## Get Inventories

```shell
curl "http://<server-name>/api/v1/teams/1/inventories"
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
            },
            "relationships": {
                "created_by": {
                    "data": {
                        "id": "1",
                        "type": "users"
                    }
                }
            }
        },
        {
            "id": "2",
            "type": "inventories",
            "attributes": {
                "name": "Inventory 2"
            },
            "relationships": {
                "created_by": {
                    "data": {
                        "id": "2",
                        "type": "users"
                    }
                }
            }
        }
    ],
    "links": {
        "self": "https://<server-name>/api/v1/teams/1/inventories?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://<server-name>/api/v1/teams/1/inventories?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://<server-name>/api/v1/teams/1/inventories?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves all inventories from the specified team.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/inventories`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventories from

## Get Inventory

```shell
curl "http://<server-name>/api/v1/teams/1/inventories/1"
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
        },
        "relationships": {
            "created_by": {
                "data": {
                    "id": "1",
                    "type": "users"
                }
            }
        }
    },
    included": [
        {
            "id": "1",
            "type": "users",
            "attributes": {
                <user-attributes>
            }
        }
    ]
}
```

This endpoint retrieves a specific inventory.

### HTTP Request

`GET http://<server-name>/api/v1/teams/<TEAM_ID>/inventories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
ID | The ID of the inventory to retrieve

## Get Items from specific inventory

```shell
curl "http://server-name/api/v1/teams/1/inventories/1/items"
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
        "self": "https://<server-name>/api/v1/teams/1/inventories/1/items?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://<server-name>/api/v1/teams/1/inventories/1/items?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://<server-name>/api/v1/teams/1/inventories/1/items?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves items from specific inventory.
Also by default includes inventory cells.

### HTTP Request

`GET https://server-name/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/items`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve items from

## Create Inventory

```shell
curl -X POST \
  https://<server-name>/api/v1/teams/1/inventories \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
    "data": {
        "type": "inventories",
        "attributes": {
            "name": "Samples"
        }
    }
  }'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "inventories",
        "attributes": {
            "name": "Samples"
        }
    },
    "relationships": {
        "created_by": {
            "data": {
                "id": "1",
                "type": "users"
            }
        }
    }
}
```

This endpoint creates new inventory in the team.

### HTTP Request

`POST https://<server-name>/api/v1/teams/<TEAM_ID>/inventories`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from

> Request body

```json
{
    "data": {
        "type": "inventories",
        "attributes": {
            "name": "Samples"
        }
    }
}
```

### Inventory attributes

Attribute | Mandatory| Description
--------- | -------- | -----------
name | yes | Name of the column

## Update Inventory

```shell
curl -X PATCH \
  https://server-name/api/v1/teams/1/inventories/1 \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
    "data": {
        "id": "1",
        "type": "inventories",
        "attributes": {
            "name": "Samples 2"
        }
    }
  }'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "inventories",
        "attributes": {
            "name": "Samples 2"
        }
    }
}
```

This endpoint updates existing inventory in the selected team.
If submitted attributes are the same and no changes are made for the inventory, server returns empty body with response code 204.

### HTTP Request

`PATCH https://server-name/api/v1/teams/<TEAM_ID>/inventories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
ID | The ID of the inventory

### Request body

```json
{
    "data": {
        "id": "1",
        "type": "inventories",
        "attributes": {
            "name": "Samples 2"
        }
    }
}
```

### Inventory column attributes

Attribute | Mandatory| Description
--------- | -------- | -----------
name | yes | Name of the column


## Delete Inventory

```shell
curl -X DELETE \
  https://server-name/api/v1/teams/1/inventories/1 \
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns empty body with status code 200

This endpoint deletes specific inventory.

### HTTP Request

`DELETE https://server-name/api/v1/teams/<TEAM_ID>/inventories/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
ID | The ID of the inventory
