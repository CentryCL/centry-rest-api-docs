# Variants

## Parámetros

Atributo        | Tipo      | Descripción
----------------| --------- | -----------
`id`            | string    | Identificador de la variante <i class="label label-info">sólo lectura</i>
`barcode`       | string    | Código de barras
`bulk_upload`   | boolean   |
`color_id`      | string    | Identificador del color
`color_name`    | string    | Nombre del color <i class="label label-info">sólo lectura</i>
`company_id`    | string    | Identificador de la compañía <i class="label label-info">sólo lectura</i>
`created_at`    | date-time | Fecha en formato UTC de la creación de la variante <i class="label label-info">sólo lectura</i>
`created_by_id` | string    | Identificador del usuario que creó por el registro <i class="label label-info">sólo lectura</i>
`id_shopify`    | string    |
`integrations`  | object    | Diccionario con información especializada para algunas integraciones
`modifier_id`   | string    |
`original_data` | string    |
`position`      | integer   | Posición de una variante en relación a las otras que pertenecen al mismo producto
`price`         | string    |
`price_compare` | string    |
`product_id`    | string    | Identificar del producto al cual pertenece la variante
`quantity`      | integer   | Stock de la variante <i class="label label-info">deprecado</i>
`size_id`       | string    | Identificador de la talla
`size_name`     | string    | Nombre de la talla <i class="label label-info">sólo lectura</i>
`sku`           | string    | SKU de la variante
`updated_at`    | string    | Fecha de la última modificación del registro en Centry <i class="label label-info">sólo lectura</i>
`updated_by_id` | string    | Identificador del usuario que modificó por última vez el registro <i class="label label-info">sólo lectura</i>
`version`       | int       | Numero de versión del registro, va aumentando en la medida que se registran actualizaciones <i class="label label-info">sólo lectura</i>

## Todas las variantes de la cuenta

Este endpoint entrega todas las variantes de los productos de la cuenta.

```shell
curl "https://www.centry.cl/conexion/v1/variants.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
    "_id": "5c2e07488f26c638ca60dc0b",
    "barcode": "123456789",
    "bulk_upload": false,
    "color_id": "580450f61746bf79030001d6",
    "color_name": "Azul",
    "company_id": null,
    "created_at": "2019-01-03T09:59:52.852-03:00",
    "created_by_id": "5c2d1ae68f26c638ca60dc04",
    "custom_data": null,
    "description": "Descripción detallada de la variante del producto",
    "id_mercadolibre": null,
    "id_shopify": null,
    "id_woocommerce": null,
    "integrations": {},
    "modifier_id": null,
    "original_data": null,
    "position": 0,
    "price": null,
    "price_compare": null,
    "product_id": "5c2e07488f26c638ca60dc0a",
    "quantity": 20,
    "size_id": "5804ad46b831a33ada0f5f93",
    "size_name": "S",
    "sku": "variante_12345",
    "updated_at": "2019-01-03T12:29:19.387-03:00",
    "updated_by_id": "5c2d1ae68f26c638ca60dc04",
    "version": 1
  }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variants.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede precisar la request agregando parámetros a la URL de la forma https://www.centry.cl/conexion/v1/variants.json?&lt;filter&gt;=&lt;valor&gt; como se muestra en el capítulo **Filters** al final de la documentación. Además, de ser necesario algunos filtros pueden ser concatenados de la forma https://www.centry.cl/conexion/v1/variants.json?&lt;filter&gt;=&lt;valor&gt;&&lt;filter&gt;=&lt;valor&gt;&...

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro       | Descripción                                     | Ejemplo
------------ | ----------------------------------------------- | -------
`sku`        | El sku de la variante que se desea recuperar    | https://www.centry.cl/conexion/v1/variants.json?sku=00_1

## Crear una variante

Este endpoint crea una variante de un producto.

```shell
curl -X POST \
  https://www.centry.cl/conexion/v1/variants.json \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "barcode": "<Código de barras de la nueva variante>",
    "color_id": "<Identificador del color de la nueva variante>",
    "product_id": "<Identificador del producto al cual pertenece la nueva variante>",
    "quantity": Stock de la nueva variante,
    "size_id": "<Identificador de la talla de la nueva variante>",
    "sku": "<SKU de la nueva variante>",
    "updated_at": "2017-10-19T12:24:30.029-03:00",
    "updated_by_id": "580450f81746bf7903000216",
    "version": 7
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/variants.json </h6>
  </div>
</div>

## Obtener una variante específica

Este endpoint entrega una variante en específico.

```shell
curl "https://www.centry.cl/conexion/v1/variants/<variant_id>.json" -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "<Identificador de la variante>",
  "barcode": "<Código de barras de la variante>",
  "bulk_upload": false,
  "color_id": "<Identificador del color>",
  "color_name": "Azul",
  "company_id": null,
  "created_at": "2019-01-03T09:59:52.852-03:00",
  "created_by_id": "5c2d1ae68f26c638ca60dc04",
  "custom_data": null,
  "description": "<Descripción>",
  "id_mercadolibre": null,
  "id_shopify": null,
  "id_woocommerce": null,
  "integrations": {},
  "modifier_id": null,
  "original_data": null,
  "position": 0,
  "price": null,
  "price_compare": null,
  "product_id": "<Identificador del producto>",
  "quantity": 20,
  "size_id": "<Identificador de la talla>",
  "size_name": "S",
  "sku": "<SKU de la variante>",
  "updated_at": "2019-01-03T12:29:19.387-03:00",
  "updated_by_id": "5c2d1ae68f26c638ca60dc04",
  "version": 1
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | -----------------------------------------
`variant_id` | El identificador de la variante a recuperar

## Actualizar una variante

Este endpoint actualiza una variante.

```shell
curl -X PUT \
  https://www.centry.cl/conexion/v1/variants/<variant_id>.json \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "quantity": 30
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | ------------------------------------------
`variant_id` | El identificador de la variante a actualizar

## Actualizar por SKU

Este endpoint actualiza la variante de un producto.

```shell
curl -X PUT https://www.centry.cl/conexion/v1/variants/sku.json \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "sku": "<SKU de la variante a actualizar>",
    "quantity": 20
}'
```
### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/variants/sku.json </h6>
  </div>
</div>

## Eliminar una variante

Este endpoint elimina una variante.

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/variants/<variant_id>.json \
    -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | ------------------------------------------
`variant_id` | El identificador de la variante a eliminar



## Todos los historiales de sincronización de una variante

Este endpoint entrega todos los historiales de sincronización de variante.

```shell
curl -X GET https://www.centry.cl/conexion/v1/variants/<variant_id>/synchronization_histories.json \
    -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "6034137c84c6e1418eb6d62a",
    "action": "Product update",
    "company_id": "5776daa1f82f454fa8000000",
    "created_at": "2021-02-22T17:26:36.833-03:00",
    "description_messages": {
        "_id": "6034137c84c6e1418eb6d62b",
        "mistakes": [
            "error_description_1",
            "error_description_2"
        ],
        "warnings": [
            "warning_description_1",
            "warning_description_1"
        ]
    },
    "integration_config_id": "6012c3c784c6e179b53043f5",
    "is_last": null,
    "marketplace": "centry-test-local-v2",
    "messages": {
        "_id": "6034137c84c6e1418eb6d62c",
        "mistakes": [
            "mistake_1",
            "mistake_2"
        ],
        "warnings": [
            "warning_1",
            "warning_2"
        ]
    },
    "product_id": "5a16c0bcf82f45273b000054",
    "request": "{}",
    "request_response_id": null,
    "response": "{\"_id\":\"6034137c84c6e1418eb6d62a\",\"action\":\"Product update\",\"company_id\":\"5776daa1f82f454fa8000000\",\"created_at\":null,\"description_messages\":{\"_id\":\"6034137c84c6e1418eb6d62b\",\"mistakes\":[\"error_description_1\",\"error_description_2\"],\"warnings\":[\"warning_description_1\",\"warning_description_1\"]},\"integration_config_id\":\"6012c3c784c6e179b53043f5\",\"is_last\":null,\"marketplace\":\"centry-test-local-v2\",\"messages\":{\"_id\":\"6034137c84c6e1418eb6d62c\",\"mistakes\":[\"error_general_1\",\"error_general_2\"],\"warnings\":[\"warning_general_1\",\"warning_general_2\"]},\"product_id\":\"5a16c0bcf82f45273b000054\",\"request\":\"{}\",\"request_response_id\":null,\"response\":null,\"sku_messages\":{\"_id\":\"6034137c84c6e1418eb6d62d\",\"mistakes\":[\"error_sku_1\",\"error_sku_2\"],\"warnings\":[\"warning_sku_1\",\"warning_sku_1\"]},\"success\":null,\"updated_at\":null,\"variant_id\":\"5a16c0bdf82f45273b000056\"}",
    "sku_messages": {
        "_id": "6034137c84c6e1418eb6d62d",
        "mistakes": [
            "error_sku_1",
            "error_sku_2"
        ],
        "warnings": [
            "warning_sku_1",
            "warning_sku_2"
        ]
    },
    "success": false,
    "updated_at": "2021-02-22T17:26:36.833-03:00",
    "variant_id": "5a16c0bdf82f45273b000056"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`variant_id` | El identificador de la relación variante de la que se desea obtener el historial de sincronizaciones




## Crear historiales de sincronización de una variante

Este endpoint entrega todos los historiales de sincronización de variante.

```shell
curl -L -X POST 'https://www.centry.cl/conexion/v1/variants/5a16c0bdf82f45273b000056/synchronization_histories.json' \
-H 'Authorization: Bearer <access_token>' \
-H 'Content-Type: application/json' \
--data-raw '{
    "action":"Product update",
    "description_messages":{
        "warnings":["warning_description_1","warning_description_1"],
        "mistakes": ["error_description_1", "error_description_2"]
    },
    "sku_messages":{
        "warnings":["warning_sku_1","warning_sku_1"],
        "mistakes": ["error_sku_1", "error_sku_2"]
    },
    "messages":{
        "warnings":["warning_general_1","warning_general_2"],
        "mistakes": ["error_general_1", "error_general_2"]
    }
}'
```



> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "603409fa84c6e1418eb6d5b7",
  "action": "Product create",
  "company_id": "5776daa1f82f454fa8000000",
  "created_at": "2021-02-22T16:46:02.649-03:00",
  "integration_config_id": "6012c3c784c6e179b53043f5",
  "is_last": null,
  "marketplace": "centry-test-local-v2",
  "quantity_messages": {
      "_id": "603409fa84c6e1418eb6d5b9",
      "mistakes": [
          "error_quantity_messages_1"
      ],
      "warnings": [
          "warning_quantity_messages_1"
      ]
  },
  "messages": {
      "_id": "603409fa84c6e1418eb6d5b8",
      "mistakes": [
          "error_messages_1",
          "error_messages_2"
      ],
      "warnings": [
          "warning_messages_1"
      ]
  },
  "product_id": "5a16c0bcf82f45273b000054",
  "request": "{}",
  "request_response_id": null,
  "response": "{\"_id\":\"603409fa84c6e1418eb6d5b7\",\"action\":\"Product create\",\"company_id\":\"5776daa1f82f454fa8000000\",\"created_at\":null,\"integration_config_id\":\"6012c3c784c6e179b53043f5\",\"is_last\":null,\"marketplace\":\"centry-test-local-v2\",\"messages\":{\"_id\":\"603409fa84c6e1418eb6d5b8\",\"mistakes\":[\"error_messages_1\",\"error_messages_2\"],\"warnings\":[\"warning_messages_1\"]},\"product_id\":\"5a16c0bcf82f45273b000054\",\"quantity_messages\":{\"_id\":\"603409fa84c6e1418eb6d5b9\",\"mistakes\":[\"error_quantity_messages_1\",\"error_quantity_messages_2\",\"error_quantity_messages_3\"],\"warnings\":[\"warning_quantity_messages_1\"]},\"request\":\"{}\",\"request_response_id\":null,\"response\":null,\"success\":null,\"updated_at\":null,\"variant_id\":\"5a16c0bdf82f45273b000056\",\"variant_warehouse_id\":\"5a16d9a1f82f45273b001576\"}",
  "success": false,
  "updated_at": "2021-02-22T16:46:02.649-03:00",
  "variant_id": "5a16c0bdf82f45273b000056",
  "variant_warehouse_id": "5a16d9a1f82f45273b001576"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante de la que se desea obtener el historial de sincronizaciones

### Parámetros Data

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`success`        | Indicado el estado de la petición, campo se calcula de manera automática de acuerdo a la presencia de `mistakes` <i class="label label-info">sólo lectura</i>
`action` | Listado de acciones disponibles: ["Product save", "Product create", "Product update", "Product unpublish", "Product delete", "Image save", "Description update", "Active Meli Flex", "Deactive Meli Flex"]
`mistakes` | Listado de errores de un campo en específico que no permitieron que la petición haya resultado exitosa
`warnings` | Listado de advertencias u oportinidades de mejora de un campo en específico que ha pesar de no ser óptimas la petición se realizó de manera exitosa
`description_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `description`
`sku_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `sku`
`messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados en general con el modelo `variant_warehouse`
