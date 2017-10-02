# Integration Configs

La API de Centry permite listar, ver, y eliminar integraciones a marketplaces y/o ecommerces individualmente.

Las integraciones pueden ser administradas desde la [plataforma web de Centry](https://www.centry.cl/empresas/integraciones) o parcialmente usando los endpoints de la API REST.

## Parámetros

### Parámetros comunes a todas las integraciones

| Atributo                | Tipo    | Descripción                                                                                              |
| ----------------------- | ------- | -------------------------------------------------------------------------------------------------------- |
| `_id`                   | string  | Identificador de la integración                             <i class="label label-info">sólo lectura</i> |
| `_delete_status`        | string  | Sólo admite los valores `unpublish` y `delete` y definen el comportamiento de la publicación del producto después de que se elimine de Centry: `unpublish` lo pausa o despublica, mientras que `delete` lo intenta eliminar permanentemente. |
| `_use`                  | string  | Sólo admite los valores `slave` y `master` y definen quién es el cargado de llevar el control del catálogo e inventario: Centry (`slave`) o la integración (`master`). Sólo algunas integraciones admiten el modo `master`. |
| `target`                | string  | Indica el tipo de integración a la que pertenece (Ej: Dafiti, Linio MercadoLibre, etc.)                  |
| `name`                  | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `description`           | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `shortdescription`      | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `price_compare`         | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `price`                 | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `price_factor`          | float   | Factor por el cual se multiplicarán los precios para esta integración.                                   |
| `price_round`           | int     | Número al cual se aproximarán los precios.                                                               |
| `stock_discount`        | int     | Numero de unidades por variantes que se dejarán de publicar para esta integración.                       |
| `condition`             | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `package_dimensions`    | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `package_weight`        | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `warranty`              | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `barcode`               | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `sku`                   | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `sku_prefix`            | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `images`                | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `images`                | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `category`              | boolean | Flag que indica si Centry enviará este campo cada vez que se sincronicen productos con esta integración. |
| `excluded_brand_ids`    | array   | Listado de marcas que serán excluidas de la la sincronización de productos para esta integración.        |
| `excluded_category_ids` | array   | Listado de categorías que serán excluidas de la la sincronización de productos para esta integración.    |
| `excluded_product_ids`  | array   | Listado de producto que serán excluidas de la la sincronización de productos para esta integración.      |
| `enabled`               | boolean | Flag que indica si esta integración está disponible.        <i class="label label-info">sólo lectura</i> |
| `company_id`            | string  | Identificador de empresa                                    <i class="label label-info">sólo lectura</i> |
| `created_at`            | string  | Fecha de creación de la integración en Centry               <i class="label label-info">sólo lectura</i> |
| `updated_at`            | string  | Fecha de la última modificación de la integración en Centry <i class="label label-info">sólo lectura</i> |

### Parámetros específicos para cada integración

| Atributo            | Tipo    | Integraciones    | Descripción                                                                                |
| ------------------- | ------- | ---------------- | ------------------------------------------------------------------------------------------ |
|                     |         |                  |                                                                                            |
|                     |         |                  |                                                                                            |
|                     |         |                  |                                                                                            |
|                     |         |                  |                                                                                            |
|                     |         |                  |                                                                                            |

## Listar las integraciones de la cuenta

Este endpoint entrega todas las integraciones registradas en la cuenta.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/integration_configs.json </h6>
  </div>
</div>

```shell
curl -X GET \
  https://www.centry.cl/conexion/v1/integration_configs.json \
  -H 'authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
      "_delete_status": "unpublish",
      "_id": "59d295351746bf7fa9000003",
      "_use": "slave",
      "api_key": "linio_api_key",
      "barcode": true,
      "category": true,
      "company_id": "59355c1b1746bf25a8000000",
      "condition": true,
      "created_at": "2017-10-02T16:36:21.588-03:00",
      "description": true,
      "enabled": true,
      "excluded_brand_ids": [
          "580450f61746bf79030001eb",
          "59baccbf133b5a34d452a33c"
      ],
      "excluded_category_ids": [
          "580450f61746bf79030001a7"
      ],
      "excluded_product_ids": [
          "59d242ae1746bf33f4000000"
      ],
      "images": true,
      "name": true,
      "package_dimensions": true,
      "package_weight": true,
      "price": true,
      "price_compare": true,
      "price_factor": 1,
      "price_round": 0,
      "shortdescription": true,
      "sku": true,
      "sku_prefix": "",
      "stock_discount": 0,
      "target": "Linio",
      "updated_at": "2017-10-02T16:37:00.426-03:00",
      "username": "linio_usuario",
      "warranty": true
  }
]
```

## Obtener una integración específica

Este endpoint entrega una integración específica.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/integration_configs/&lt;ic_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X GET \
  https://www.centry.cl/conexion/v1/integration_configs/59d295351746bf7fa9000003.json \
  -H 'authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_delete_status": "unpublish",
    "_id": "59d295351746bf7fa9000003",
    "_use": "slave",
    "api_key": "linio_api_key",
    "barcode": true,
    "category": true,
    "company_id": "59355c1b1746bf25a8000000",
    "condition": true,
    "created_at": "2017-10-02T16:36:21.588-03:00",
    "description": true,
    "enabled": true,
    "excluded_brand_ids": [
        "580450f61746bf79030001eb",
        "59baccbf133b5a34d452a33c"
    ],
    "excluded_category_ids": [
        "580450f61746bf79030001a7"
    ],
    "excluded_product_ids": [
        "59d242ae1746bf33f4000000"
    ],
    "images": true,
    "name": true,
    "package_dimensions": true,
    "package_weight": true,
    "price": true,
    "price_compare": true,
    "price_factor": 1,
    "price_round": 0,
    "shortdescription": true,
    "sku": true,
    "sku_prefix": "",
    "stock_discount": 0,
    "target": "Linio",
    "updated_at": "2017-10-02T16:37:00.426-03:00",
    "username": "linio_usuario",
    "warranty": true
}
```

### Parámetros URL

Parámetro  | Descripción
-----------| ----------------------------------------------
`ic_id`    | El identificador de la integración a recuperar

## Eliminar una integración

Este endpoint elimina permanentemente una integración específica.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/integration_configs/&lt;ic_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X DELETE \
  https://www.centry.cl/conexion/v1/integration_configs/59d295351746bf7fa9000003.json \
  -H 'authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### Parámetros URL

Parámetro  | Descripción
-----------| ---------------------------------------------
`ic_id`    | El identificador de la integración a eliminar
