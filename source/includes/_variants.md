#Variants

##Parámetros

| Atributo               | Tipo      | Descripción                                                                                              |
| ---------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| `id`                   | string    | Identificador de la variante <i class="label label-info">sólo lectura</i>                                  |
| `barcode`              | string    | Código de barras                                                                                         |
| `bulk_upload`          | boolean    |                                                                                  |
| `color_id`     | string    | Identificador del color |
| `color_name`            | string    | Nombre del color                                              |
| `company_id`             | string    | Identificador de la compañía                                                                                |
| `created_at`          | date-time | Fecha en formato UTC de la creación de la variante <i class="label label-info">sólo lectura</i>                                                            |
| `created_by_id`   | string    |                             |
| `custom_data`      | string    |                              |
| `description`      | string   | Descripción de la variante                               |
| `id_mercadolibre`    | string    |                              |
| `id_shopify`     | string |                |
| `id_woocommerce`            | string    |                                                                               |
| `integrations` | hash   |                                           |
| `modifier_id`            | string    |                                                                    |
| `original_data`   | string   |                                                 |
| `position`        | integer   |                                                             |
| `price`        | string   |                                                                |
| `price_compare`        | string   |                                                                |
| `product_id`         | string   | Identificar del producto al cual pertenece la variante                                                                 |
| `quantity`        | integer   | Stock de la variante                                                                                            |
| `size_id`                | string   |      Identificador de la talla                                                                                    |
| `size_name`        | string | Nombre de la talla                                                                            |
| `sku`          | string | SKU de la variante                                                                     |
| `updated_at`               | string    |                                                   |
| `updated_by_id`           | string   |                                                                                |
| `version`            | int    |                                                    |

### Atributos de las Integraciones


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

## Todas las Variantes de la cuenta

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

## Crear una Variante

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

## Obtener una Variante específica

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

## Actualizar una Variante

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

## Eliminar una Variante

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
------------ | ----------------------------------------
`variant_id` | El identificador de la variante a eliminar
