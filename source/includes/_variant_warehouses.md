# VariantWarehouses

Este modelo es el encargado de relacionar las variantes de un producto con las
bodegas para llevar el control del stock.

## Parámetros

Atributo       | Tipo    | Descripción
---------------| ------- | -----------
`_id`          | string  | Identificador de la relación variante-bodega <i class="label label-info">sólo lectura</i>
`variant_id`   | string  | Identificador de la variante. Ver endpoint [Variants](#variants)
`warehouse_id` | string  | Identificador de la bodega. Ver endpoint [Warehouses](#warehouses)
`quantity`     | integer | Stock que registra la variante en una bodega
`created_by_id`| string  | Identificador del usuario que creó por el registro <i class="label label-info">sólo lectura</i>
`modifier_id`  | string  | Identificador del usuario que modificó por última vez el registro <i class="label label-info">sólo lectura</i>
`created_at`   | string  | Fecha de creación del registro en Centry <i class="label label-info">sólo lectura</i>
`updated_at`   | string  | Fecha de la última modificación del registro en Centry <i class="label label-info">sólo lectura</i>
`version`      | integer | Numero de versión del registro, va aumentando en la medida que se registran actualizaciones <i class="label label-info">sólo lectura</i>

## Todas las variante-bodegas de la cuenta

Este endpoint entrega todas las relaciones variante-bodega de la cuenta.

```shell
curl "https://www.centry.cl/conexion/v1/variant_warehouses.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5ac23e71f82f455978672393",
        "created_at": "2018-04-02T11:30:09.723-03:00",
        "created_by_id": null,
        "modifier_id": null,
        "quantity": 2,
        "updated_at": "2019-10-03T13:55:09.068-03:00",
        "updated_by_id": "577eb7b8f82f456ef4000002",
        "variant_id": "5ac23e71f82f455978672392",
        "version": 11,
        "warehouse_id": "577eb7b8f82f456ef4000001"
    },
    {
        "_id": "5cc36d8748f039156b45f78d",
        "created_at": "2019-04-26T16:43:51.125-04:00",
        "created_by_id": "577eb7b8f82f456ef4000002",
        "modifier_id": null,
        "quantity": 2,
        "updated_at": "2019-10-17T19:06:45.114-03:00",
        "updated_by_id": "577eb7b8f82f456ef4000002",
        "variant_id": "5cc36d8748f039156b45f78c",
        "version": 9,
        "warehouse_id": "577eb7b8f82f456ef4000001"
    },
    {
        "_id": "5cc36d8748f039156b45f78f",
        "created_at": "2019-04-26T16:43:51.152-04:00",
        "created_by_id": "577eb7b8f82f456ef4000002",
        "modifier_id": null,
        "quantity": 2,
        "updated_at": "2019-10-17T19:06:45.072-03:00",
        "updated_by_id": "577eb7b8f82f456ef4000002",
        "variant_id": "5cc36d8748f039156b45f78e",
        "version": 8,
        "warehouse_id": "577eb7b8f82f456ef4000001"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variant_warehouses.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar el request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/variant_warehouses.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.

### Filtros especiales

Sólo pueden ser ocupados para este endpoint en particular.

Filtro         | Descripción                                            | Ejemplo
-------------- | ------------------------------------------------------ | -------
`variant_id`   | El identificador de la variante que se desea recuperar | https://www.centry.cl/conexion/v1/variant_warehouses.json?variant_id=5cc36d8748f039156b45f78e
`warehouse_id` | El identificador de la bodega que se desea recuperar   | https://www.centry.cl/conexion/v1/variant_warehouses.json?warehouse_id=577eb7b8f82f456ef4000001

## Crear una variante-bodega

Este endpoint crea una relación variante-bodega en la cuenta.

```shell
curl -X POST \
  https://www.centry.cl/conexion/v1/variant_warehouses.json \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "quantity": 2,
    "variant_id": "5cc36d8748f039156b45f78e",
    "warehouse_id": "577eb7b8f82f456ef4000001"
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/variant_warehouses.json </h6>
  </div>
</div>

## Obtener una variante-bodega específica

Este endpoint entrega una relación variante-bodega en específica.

```shell
curl "https://www.centry.cl/conexion/v1/variant_warehouses/<variant_warehouse_id>.json" -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5cc36d8748f039156b45f78f",
    "created_at": "2019-04-26T16:43:51.152-04:00",
    "created_by_id": "577eb7b8f82f456ef4000002",
    "modifier_id": null,
    "quantity": 2,
    "updated_at": "2019-10-17T19:06:45.072-03:00",
    "updated_by_id": "577eb7b8f82f456ef4000002",
    "variant_id": "5cc36d8748f039156b45f78e",
    "version": 8,
    "warehouse_id": "577eb7b8f82f456ef4000001"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variant_warehouses/&lt;variant_warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL
Parámetro              | Descripción
---------------------- | -----------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante-bodega a recuperar

## Actualizar una variante-bodega

Este endpoint actualiza una relación variante-bodega.

```shell
curl -X PUT \
  https://www.centry.cl/conexion/v1/variant_warehouses/<variant_warehouse_id>.json \
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
    <h6> https://www.centry.cl/conexion/v1/variant_warehouses/&lt;variant_warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ------------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante-bodega a actualizar

## Eliminar una Variante-Bodega

Este endpoint elimina una relación variante-bodega.

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/variant_warehouses/<variant_warehouse_id>.json \
    -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante-bodega a eliminar


## Todos los historiales de sincronización de una variante-bodega

Este endpoint entrega todos los historiales de sincronización de variante-bodega.

```shell
curl -X GET https://www.centry.cl/conexion/v1/variant_warehouses/<variant_warehouse_id>/synchronization_histories.json \
    -H "Authorization: Bearer  <access_token>"
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
   "quantity_messages": {
       "_id": "603409fa84c6e1418eb6d5b9",
       "mistakes": [
           "error_quantity_messages_1",
           "error_quantity_messages_2",
           "error_quantity_messages_3"
       ],
       "warnings": [
           "warning_quantity_messages_1"
       ]
   },
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
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_warehouse_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante-bodega de la que se desea obtener el historial de sincronizaciones




## Crear historiales de sincronización de una variante-bodega

Este endpoint entrega todos los historiales de sincronización de variante-bodega.

```shell
curl -X POST 'https://www.centry.cl/conexion/v1/variant_warehouses/<variant_warehouse_id>/synchronization_histories.json' \
--header 'Authorization: Bearer  <access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "action":"Product create",
    "quantity_messages":{
        "warnings":["warning_quantity_messages_1"],
        "mistakes": ["error_quantity_messages_1"]
    },
    "messages":{
        "warnings":["warning_messages_1"],
        "mistakes": ["error_messages_1"]
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
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_warehouse_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante-bodega de la que se desea obtener el historial de sincronizaciones

### Parámetros Data

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`success`        | Indicado el estado de la petición, campo se calcula de manera automática de acuerdo a la presencia de `mistakes` <i class="label label-info">sólo lectura</i>
`action` | Listado de acciones disponibles: ["Product save", "Product create", "Product update", "Product unpublish", "Product delete", "Image save", "Description update", "Active Meli Flex", "Deactive Meli Flex"]
`mistakes` | Listado de errores de un campo en específico que no permitieron que la petición haya resultado exitosa
`warnings` | Listado de advertencias u oportinidades de mejora de un campo en específico que ha pesar de no ser óptimas la petición se realizó de manera exitosa
`quantity_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `quantity`
`messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados en general con el modelo `variant_warehouse`
