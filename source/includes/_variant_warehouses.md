#VariantWarehouses

Este modelo es el encargado de relacionar las variantes de un producto con las
bodegas para llevar el control del stock.

##Parámetros

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

## Todas las VarianteBodegas de la cuenta

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

## Crear un VarianteBodega

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

## Obtener una Variante específica

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

## Actualizar una Variante

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

## Eliminar una Variante

Este endpoint elimina una relación variante-bodega.

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/variant_warehouses/<variant_warehouse_id>.json \
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
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`variant_warehouse_id` | El identificador de la relación variante-bodega a eliminar
