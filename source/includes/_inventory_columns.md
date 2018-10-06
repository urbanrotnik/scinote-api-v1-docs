# Inventory Columns

## Get Columns

```shell
curl "https://<server-name>/api/v1/teams/1/inventories/1/columns"
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
                "data_type": "RepositoryTextValue"
            },
        },
        {
            "id": "2",
            "type": "inventory_columns",
            "attributes": {
                "name": "File Column",
                "data_type": "RepositoryAssetValue"
            },
        },
        {
            "id": "3",
            "type": "inventory_columns",
            "attributes": {
                "name": "List Column",
                "data_type": "RepositoryListValue"
            }
        }
    ],
    "links": {
        "self": "https://<server-name>/api/v1/teams/1/inventories/1/columns?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "first": "https://<server-name>/api/v1/teams/1/inventories/1/columns?page%5Bnumber%5D=1&page%5Bsize%5D=10",
        "prev": null,
        "next": null,
        "last": "https://<server-name>/api/v1/teams/1/inventories/1/columns?page%5Bnumber%5D=1&page%5Bsize%5D=10"
    }
}
```

This endpoint retrieves columns from specific inventory.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/columns`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve column from

## Get Column

```shell
curl "https://<server-name>/api/v1/teams/1/inventories/1/columns/1"
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample type",
            "data_type": "RepositoryListValue"
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
    },
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
}
```

This endpoint retrieves specific column from inventory. For list type columns (`RepositoryListValue`), related list items are also included.

### HTTP Request

`GET https://<server-name>/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/columns/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve column from
ID | The ID of the column

## Create Column

```shell
curl -X POST \
  https://<server-name>/api/v1/teams/1/inventories/1/columns \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
    "data": {
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample",
            "data_type": "RepositoryTextValue"
        }
    }
  }'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample",
            "data_type": "RepositoryTextValue"
        },
    }
}
```

This endpoint creates new column in the inventory.

### HTTP Request

`POST https://<server-name>/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/columns`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve column from

> Request body

```json
{
    "data": {
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample",
            "data_type": "RepositoryTextValue"
        }
    }
}
```

### Inventory column attributes

Attribute | Mandatory| Description
--------- | -------- | -----------
name | yes | Name of the column
data_type | yes | Data type of the column - one of the following: `RepositoryTextValue`, `RepositoryListValue` or `RepositoryFileValue`

## Update Column

```shell
curl -X PATCH \
  https://<server-name>/api/v1/teams/1/inventories/1/columns/1 \
  -H 'Authorization: Bearer qwerty123456...' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
    "data": {
        "id": "1",
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample 2"
        }
    }
  }'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "1",
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample 2",
            "data_type": "RepositoryTextValue"
        }
    }
}
```

This endpoint updates existing list item in selected inventory column. Updating of `data_type` attribute is not permitted.
If submitted attributes are the same and no changes are made for the item, server returns empty body with response code 204.

### HTTP Request

`PATCH https://<server-name>/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/columns/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve column from
ID | The ID of the column

### Request body

```json
{
    "data": {
        "id": "1",
        "type": "inventory_columns",
        "attributes": {
            "name": "Sample 2"
        }
    }
}
```

### Inventory column attributes

Attribute | Mandatory| Description
--------- | -------- | -----------
name | no | Name of the column

## Delete Column

```shell
curl -X DELETE \
  https://<server-name>/api/v1/teams/1/inventories/1/columns/1 \
  -H "Authorization: Bearer qwerty123456..."
```

> The above command returns empty body with status code 200

This endpoint deletes specific column from the inventory.

### HTTP Request

`DELETE https://<server-name>/api/v1/teams/<TEAM_ID>/inventories/<INVENTORY_ID>/columns/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
TEAM_ID | The ID of the team to retrieve inventory from
INVENTORY_ID | The ID of the inventory to retrieve column from
ID | The ID of the column
