# VariantAssets

Este modelo es el encargado de relacionar las variantes de un producto con las
imágenes del producto.

## Parámetros

Atributo       | Tipo    | Descripción
---------------| ------- | -----------
`_id`          | string  | Identificador de la relación variante-imagen <i class="label label-info">sólo lectura</i>
`variant_id`   | string  | Identificador de la variante. Ver endpoint [Variants](#variants)
`asset_id`     | string  | Identificador de la imagen. Ver endpoint [Warehouses](#warehouses)
`product_id`   | integer | Identificador del producto. Ver endpoint [Products](#products)
`position`     | string  | Posición de la imagen en la variante.
`created_at`   | string  | Fecha de creación del registro en Centry <i class="label label-info">sólo lectura</i>
`updated_at`   | string  | Fecha de la última modificación del registro en Centry <i class="label label-info">sólo lectura</i>

## Todas las variante-imágenes de la variante

Este endpoint entrega todas las relaciones variante-imagen de una variante.

```shell
curl "https://www.centry.cl/conexion/v1/variants/<variant_id>/assets.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5ac23e71f82f455978672393",
        "created_at": "2018-04-02T11:30:09.723-03:00",
        "position": 0,
        "updated_at": "2019-10-03T13:55:09.068-03:00",
        "variant_id": "5ac23e71f82f455978672392",
        "product_id": "577eb7b8f82f456ef4000002",
        "asset_id": "577eb7b8f82f456ef4000001"
    },
    {
        "_id": "5ac23e71f82f455978672394",
        "created_at": "2018-04-02T11:30:09.723-03:00",
        "position": 0,
        "updated_at": "2019-10-03T13:55:09.068-03:00",
        "variant_id": "5ac23e71f82f455978672392",
        "product_id": "577eb7b8f82f456ef4000002",
        "asset_id": "577eb7b8f82f456ef4000002"
    },
    {
        "_id": "5ac23e71f82f455978672395",
        "created_at": "2018-04-02T11:30:09.723-03:00",
        "position": 0,
        "updated_at": "2019-10-03T13:55:09.068-03:00",
        "variant_id": "5ac23e71f82f455978672392",
        "product_id": "577eb7b8f82f456ef4000002",
        "asset_id": "577eb7b8f82f456ef4000003"
    },
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/assets.json </h6>
  </div>
</div>

### Parámetros URL
Parámetro              | Descripción
---------------------- | -----------------------------------------------------------
`variant_id`           | El identificador de la variante.


### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar el request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/assets.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.


## Crear una variante-imagen

Este endpoint crea una relación variante-imagen.

```shell
curl -X POST \
  https://www.centry.cl/conexion/v1/variants/<variant_id>/assets.json \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-Type: application/json' \
  -d '{
    "asset_id": "577eb7b8f82f456ef4000001"
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/assets.json </h6>
  </div>
</div>

### Parámetros URL
Parámetro              | Descripción
---------------------- | -----------------------------------------------------------
`variant_id`           | El identificador de la variante.


## Obtener una variante-imagen específica

Este endpoint entrega una relación variante-imagen en específica.

```shell
curl "https://www.centry.cl/conexion/v1/variants/<variant_id>/assets/<variant_asset_id>.json" -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5ac23e71f82f455978672394",
    "created_at": "2018-04-02T11:30:09.723-03:00",
    "position": 0,
    "updated_at": "2019-10-03T13:55:09.068-03:00",
    "variant_id": "5ac23e71f82f455978672392",
    "product_id": "577eb7b8f82f456ef4000002",
    "asset_id": "577eb7b8f82f456ef4000002"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/assets/&lt;variant_asset_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL
Parámetro              | Descripción
---------------------- | -----------------------------------------------------------
`variant_id`           | El identificador de la variante.
`variant_asset_id`      | El identificador de la relación variante-imagen a recuperar


## Eliminar una relacion variante imagen

Este endpoint elimina una relación variante-imagen.

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/variants/<variant_id>/assets/<variant_asset_id>.json \
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
    <h6> https://www.centry.cl/conexion/v1/variants/&lt;variant_id&gt;/assets/&lt;variant_asset_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | -----------------------------------------------------------
`variant_id`           | El identificador de la variante.
`variant_asset_id`      | El identificador de la relación variante-imagen a recuperar
