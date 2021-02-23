# Products

## Parámetros

| Atributo               | Tipo      | Descripción                                                                                              |
| ---------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| `id`                   | string    | Identificador del producto <i class="label label-info">sólo lectura</i>                                  |
| `name`                 | string    | Nombre del producto                                                                                      |
| `sku`                  | string    | SKU del producto                                                                                         |
| `barcode`              | string    | Código de barras                                                                                         |
| `description`          | string    | Descripción del producto                                                                                 |
| `shortdescription`     | string    | Listado de características del producto del producto. Se recomienda el uso de viñetas HTML sin orden, ie, `<ul><li></li></ul>`. |
| `condition`            | string    | Describe la condición del producto (Nuevo, usado, renovado)                                              |
| `brand_id`             | string    | Identificador de la marca                                                                                |
| `category_id`          | integer   | Identificador de categoría a la que pertenece                                                            |
| `cover_content_type`   | string    | Extensión de la imagen principal <i class="label label-info">sólo lectura</i>                            |
| `cover_file_name`      | string    | Nombre de la imagen principal <i class="label label-info">sólo lectura</i>                               |
| `cover_file_size`      | integer   | Tamaño de la imagen principal <i class="label label-info">sólo lectura</i>                               |
| `cover_fingerprint`    | string    | CheckSum de la imagen principal <i class="label label-info">sólo lectura</i>                             |
| `cover_updated_at`     | date-time | Fecha de actualización de la imagen principal <i class="label label-info">sólo lectura</i>               |
| `cover_url`            | string    | URL de la imagen principal.                                                                              |
| `assets`               | array     | Listado de imágenes secundarias del producto. Ver [Atributos de imágenes](#atributos-de-las-im-genes)                                                                      |
| `deliverytimesupplier` | integer   | Valor aproximado en días, de la llegada del producto al cliente                                          |
| `gender_id`            | string    | Identificador del genero del producto                                                                    |
| `is_fullproductname`   | boolean   | Indica si el nombre del producto está completo o acortado                                                |
| `packageheight`        | integer   | Valor en centímetros de la altura del paquete                                                            |
| `packagelength`        | integer   | Valor en centímetros del largo del paquete                                                               |
| `packageweight`        | integer   | Valor en centímetros del ancho del paquete                                                               |
| `packagewidth`         | integer   | Valor en kilogramos del peso del paquete                                                                 |
| `price_compare`        | integer   | Precio normal                                                                                            |
| `price`                | integer   | Precio de oferta                                                                                         |
| `salestartdate`        | date-time | Fecha de término de la oferta                                                                            |
| `saleenddate`          | date-time | Fecha de inicio del precio de oferta                                                                     |
| `season`               | string    | Temporada a la que pertenece el producto. Ej "Invierno"                                                  |
| `seasonyear`           | integer   | Indica el año del producto                                                                               |
| `seo_title`            | string    | Meta título del producto. Usado para optimización SEO.                                                   |
| `seo_description`      | string    | Meta descripción del producto. Usado para optimización SEO.                                              |
| `status`               | boolean   | Estado del producto. `true`: Activo; `false`: Pausado.                                                   |
| `variants`             | array     | Lista de variantes del producto. Ver [Atributos de variantes](#atributos-de-las-variantes)                   |
| `warranty`             | integer   | Descripción de la garantía del producto                                                                  |
| `company_id`           | integer   | Identificador de la compañía a la que pertenece el producto <i class="label label-info">sólo lectura</i> |
| `created_at`           | date-time | Fecha de creación del producto en Centry <i class="label label-info">sólo lectura</i>                    |
| `updated_at`           | date-time | Fecha de última actualización del producto en Centry <i class="label label-info">sólo lectura</i>        |

###Atributos de las variantes

| Atributo          | Tipo      | Descripción                                                                                             |
| ----------------- | --------- | ------------------------------------------------------------------------------------------------------- |
| `_id`             | string    | Identificador de la variante <i class="label label-info">sólo lectura</i>                               |
| `sku`             | string    | SKU de la variante                                                                                      |
| `barcode`         | string    | Código de barras                                                                                        |
| `product_id`      | integer   | Identificador del producto en Centry <i class="label label-info">sólo lectura</i>                       |
| `size_id`         | integer   | Identificador de la talla                                                                               |
| `quantity`        | integer   | Stock de la variante. <i class="label label-info">deprecado</i>                                         |
| `color_id`        | integer   | Identificador del color                                                                                 |
| `company_id`      | integer   | Identificador de la empresa a la que pertenece la variante <i class="label label-info">sólo lectura</i> |
| `created_at`      | date-time | Fecha en formato UTC de la creación de la variante <i class="label label-info">sólo lectura</i>         |
| `updated_at`      | date-time | Registro de actualización en fecha formato UTC <i class="label label-info">sólo lectura</i>             |

###Atributos de las imágenes
| Atributo              | Tipo      | Descripción                                                                                             |
| --------------------- | --------- | --------------------------------------------------------------------------------------------------------|
| `_id`                 | string    | Identificador de la imagen. <i class="label label-info">sólo lectura</i>                                |
| `url`                 | string    | URL de la imagen.                                                                                       |                  
| `image_content_type`  | string    | Es el tipo de contenido de la imagen. Ej: "image/jpeg". <i class="label label-info">sólo lectura</i>    |
| `image_file_name`     | string    | Nombre del archivo de imagen. <i class="label label-info">sólo lectura</i>                              |
| `image_file_size`     | integer   | Tamaño de la imagen. <i class="label label-info">sólo lectura</i>                                       |
| `image_fingerprint`   | string    | CheckSum de la imagen. <i class="label label-info">sólo lectura</i>                                     |
| `image_updated_at`    | date-time | Fecha de la última actualización del archivo de imagen. <i class="label label-info">sólo lectura</i>    |
| `position`            | integer   | Posición de la imagen en el arreglo de imágenes.                                                        |
| `created_at`          | date-time | Fecha en formato UTC de la creación de la variante <i class="label label-info">sólo lectura</i>         |
| `updated_at`          | date-time | Registro de actualización en fecha formato UTC <i class="label label-info">sólo lectura</i>             |

## Todos los productos de la cuenta

Este endpoint entrega todos los productos de la cuenta.

```shell
curl "https://www.centry.cl/conexion/v1/products.json"/
 -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
    "_id":"597644781d41c846ea000006",
    "barcode":"12345655349384",
    "brand_id":"57f63ffe4c266d1dec1edfb6",
    "category_id":"5769714df82f456e800001aa",
    "color":null,
    "company_id":"597643ab1d41c846ea000001",
    "condition":"new",
    "cover_content_type":null,
    "cover_file_name":null,
    "cover_file_size":null,
    "cover_fingerprint":null,
    "cover_updated_at":null,
    "cover_url":"/images/defaults/products/missing_original.png",
    "created_at":"2017-07-24T19:03:20.245Z",
    "deliverytimesupplier":3,
    "description":"\u003cp\u003eDescripcón detallada del producto donde se explican todos sus atributos y propiedades.\u003c/p\u003e",
    "gender_id":"57ee86e911326899bc8f3f58",
    "id_mercadolibre":null,
    "id_shopify":null,
    "id_woocommerce":null,
    "is_fullproductname":null,
    "listing_type":null,
    "name":"ResTProduct",
    "original_data":null,
    "packageheight":"20",
    "packagelength":"40",
    "packageweight":"1",
    "packagewidth":"20",
    "price":null,
    "price_compare":19999,
    "publish":true,
    "quantity":1000,
    "saleenddate":null,
    "salestartdate":null,
    "season":"Centry 2019",
    "seasonyear":"2015",
    "seo_description":"Meta descripción del producto",
    "seo_title":"Meta título del producto",
    "shortdescription":"\u003cul\u003e\u003cli\u003easdasdasdasd\u003c/li\u003e\u003c/ul\u003e",
    "sku":"CENTSER954",
    "skusupplierconfig":"CENTSER954",
    "status":true,
    "updated_at":"2017-07-24T19:03:20.245Z",
    "variants":[
      {
        "_id":"597649201d41c846ea000009",
        "barcode":"123456553493842",
        "color_id":"57bdc991f82f453f680001d9",
        "created_at":"2017-07-24T19:23:12.919Z",
        "original_data":null,
        "price":null,
        "price_compare":null,
        "product_id":"597644781d41c846ea000006",
        "quantity":9995,
        "size_id":"5851b0c4b2c85e8282262a45",
        "sku":"CENTSER9542",
        "updated_at":"2017-07-24T19:23:12.947Z"
      }
    ],
    "warranty":"2"
  }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede precisar la request agregando parámetros a la URL de la forma https://www.centry.cl/conexion/v1/products.json?&lt;filter&gt;=&lt;valor&gt; como se muestra en el capítulo **Filters** al final de la documentación. Además, de ser necesario algunos filtros pueden ser concatenados de la forma https://www.centry.cl/conexion/v1/products.json?&lt;filter&gt;=&lt;valor&gt;&&lt;filter&gt;=&lt;valor&gt;&...

## Obtener un producto específico

Este endpoint entrega un producto en específico.

```shell
curl "https://www.centry.cl/conexion/v1/products/<product_id>.json" -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id":"597644781d41c846ea000006",
  "barcode":"12345655349384",
  "brand_id":"57f63ffe4c266d1dec1edfb6",
  "category_id":"5769714df82f456e800001aa",
  "color":null,
  "company_id":"597643ab1d41c846ea000001",
  "condition":"new",
  "cover_content_type":null,
  "cover_file_name":null,
  "cover_file_size":null,
  "cover_fingerprint":null,
  "cover_updated_at":null,
  "cover_url":"/images/defaults/products/missing_original.png",
  "created_at":"2017-07-24T19:03:20.245Z",
  "deliverytimesupplier":3,
  "description":"\u003cp\u003eDescripcón detallada del producto donde se explican todos sus atributos y propiedades.\u003c/p\u003e",
  "gender_id":"57ee86e911326899bc8f3f58",
  "id_mercadolibre":null,
  "id_shopify":null,
  "id_woocommerce":null,
  "is_fullproductname":null,
  "listing_type":null,
  "name":"ResTProduct",
  "original_data":null,
  "packageheight":"20",
  "packagelength":"40",
  "packageweight":"1",
  "packagewidth":"20",
  "price":null,
  "price_compare":19999,
  "publish":true,
  "quantity":1000,
  "saleenddate":null,
  "salestartdate":null,
  "season":"Centry 2019",
  "seasonyear":"2015",
  "seo_description":"Meta descripción del producto",
  "seo_title":"Meta título del producto",
  "shortdescription":"\u003cul\u003e\u003cli\u003eListado de características separadas por viñetas}\u003c/li\u003e\u003c/ul\u003e",
  "sku":"CENTSER954",
  "skusupplierconfig":"CENTSER954",
  "status":true,
  "updated_at":"2017-07-24T19:03:20.245Z",
  "variants":[
    {
      "_id":"597649201d41c846ea000009",
      "barcode":"123456553493842",
      "color_id":"57bdc991f82f453f680001d9",
      "company_id":null,
      "created_at":"2017-07-24T19:23:12.919Z",
      "original_data":null,
      "price":null,
      "price_compare":null,
      "product_id":"597644781d41c846ea000006",
      "quantity":9995,
      "size_id":"5851b0c4b2c85e8282262a45",
      "sku":"CENTSER9542",
      "updated_at":"2017-07-24T19:23:12.947Z"
    }
  ],
  "warranty":"2"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | -----------------------------------------
`product_id` | El identificador del producto a recuperar

## Crear un producto

Este endpoint crea un producto.

```shell
curl -X POST https://www.centry.cl/conexion/v1/products.json \
    -H "Authorization: Bearer  <access_token"\
    -H "Content-Type: application/json" \
    -d '{
    "barcode":"123456789",
    "brand_id":"57f63ffe4c266d1dec1edfb6",
    "category_id":"5769714df82f456e800001aa",
    "cover_url": "https://placehold.it/800x1160",
    "deliverytimesupplier":3,
    "description":"Describiendo el asombroso producto que venderás",
    "name":"Un Nombre Fantástico, para un producto fantástico",
    "packageheight":"20",
    "packagelength":"40",
    "packageweight":"1",
    "packagewidth":"20",
    "price":10000,
    "seasonyear":"2015",
    "seo_description":"Descripción",
    "seo_title":"Título asombroso",
    "shortdescription":"\u003cul\u003e\u003cli\u003easdasdasdasd\u003c/li\u003e\u003c/ul\u003e",
    "sku":"YOS0YUN54U",
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/products.json </h6>
  </div>
</div>

## Actualizar un producto

Este endpoint actualiza un producto.

```shell
curl -X PUT https://www.centry.cl/conexion/v1/products/<product_id>.json \
    -H "Authorization: Bearer  <access_token> "\
    -H "Content-Type: application/json" \
    -d '{
  "price_compare": 19990,
  "seo_title":"Calefactor de pantuflas"
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | ------------------------------------------
`product_id` | El identificador del producto a actualizar

## Eliminar un producto

Este endpoint elimina un producto.

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/products/<product_id>.json \
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
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;.json </h6>
  </div>
</div>


### Parámetros URL

Parámetro    | Descripción
------------ | ----------------------------------------
`product_id` | El identificador del producto a eliminar

## Contar los productos

Este endpoint entrega la cantidad de productos.


```shell
curl -X GET https://www.centry.cl/conexion/v1/products/count.json \
  -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
8
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/count.json </h6>
  </div>
</div>


## Todos los historiales de sincronización de un producto

Este endpoint entrega todos los historiales de sincronización de un producto.

```shell
curl -X GET https://www.centry.cl/conexion/v1/products/<product_id>/synchronization_histories.json \
    -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "603402fe84c6e1418eb6d579",
    "action": "Description update",
    "barcode_messages": {
        "_id": "603402fe84c6e1418eb6d57a",
        "mistakes": [
            "error_barcode_messages_1"
        ],
        "warnings": [
            "warning_barcode_messages_1"
        ]
    },
    "brand_messages": {
        "_id": "603402fe84c6e1418eb6d57b",
        "mistakes": [
            "error_brand_messages_1"
        ],
        "warnings": [
            "warning_brand_messages_1"
        ]
    },
    "category_messages": {
        "_id": "603402fe84c6e1418eb6d57c",
        "mistakes": [
            "error_category_messages_1"
        ],
        "warnings": [
            "warning_category_messages_1"
        ]
    },
    "company_id": "5776daa1f82f454fa8000000",
    "condition_messages": {
        "_id": "603402fe84c6e1418eb6d57d",
        "mistakes": [
            "error_condition_messages_1"
        ],
        "warnings": [
            "warning_condition_messages_1"
        ]
    },
    "created_at": "2021-02-22T16:16:14.393-03:00",
    "deliverytimesupplier_messages": {
        "_id": "603402fe84c6e1418eb6d57e",
        "mistakes": [
            "error_deliverytimesupplier_messages_1"
        ],
        "warnings": [
            "warning_deliverytimesupplier_messages_1"
        ]
    },
    "description_messages": {
        "_id": "603402fe84c6e1418eb6d57f",
        "mistakes": [
            "error_description_messages_1"
        ],
        "warnings": [
            "warning_description_messages_1"
        ]
    },
    "gender_messages": {
        "_id": "603402fe84c6e1418eb6d580",
        "mistakes": [
            "error_gender_messages_1"
        ],
        "warnings": [
            "warning_gender_messages_1"
        ]
    },
    "integration_config_id": "6012c3c784c6e179b53043f5",
    "is_fullproductname_messages": {
        "_id": "603402fe84c6e1418eb6d581",
        "mistakes": [
            "error_is_fullproductname_messages_1"
        ],
        "warnings": [
            "warning_is_fullproductname_messages_1"
        ]
    },
    "is_last": null,
    "marketplace": "centry-test-local-v2",
    "messages": {
        "_id": "603402fe84c6e1418eb6d582",
        "mistakes": [
            "error_messages_1"
        ],
        "warnings": [
            "warning_messages_1"
        ]
    },
    "name_messages": {
        "_id": "603402fe84c6e1418eb6d583",
        "mistakes": [
            "error_name_messages_1"
        ],
        "warnings": [
            "warning_name_messages_1"
        ]
    },
    "packageheight_messages": {
        "_id": "603402fe84c6e1418eb6d584",
        "mistakes": [
            "error_packageheight_messages_1"
        ],
        "warnings": [
            "warning_packageheight_messages_1"
        ]
    },
    "packagelength_messages": {
        "_id": "603402fe84c6e1418eb6d585",
        "mistakes": [
            "error_packagelength_messages_1"
        ],
        "warnings": [
            "warning_packagelength_messages_1"
        ]
    },
    "packagewidth_messages": {
        "_id": "603402fe84c6e1418eb6d586",
        "mistakes": [
            "error_packagewidth_messages_1"
        ],
        "warnings": [
            "warning_packagewidth_messages_1"
        ]
    },
    "price_compare_messages": {
        "_id": "603402fe84c6e1418eb6d587",
        "mistakes": [
            "error_price_compare_messages_1"
        ],
        "warnings": [
            "warning_price_compare_messages_1"
        ]
    },
    "price_messages": {
        "_id": "603402fe84c6e1418eb6d588",
        "mistakes": [
            "error_price_messages_1"
        ],
        "warnings": [
            "warning_price_messages_1"
        ]
    },
    "product_id": "5a16c0bcf82f45273b000054",
    "request": "{}",
    "request_response_id": null,
    "response": "{\"_id\":\"603402fe84c6e1418eb6d579\",\"action\":\"Description update\",\"barcode_messages\":{\"_id\":\"603402fe84c6e1418eb6d57a\",\"mistakes\":[\"error_barcode_messages_1\"],\"warnings\":[\"warning_barcode_messages_1\"]},\"brand_messages\":{\"_id\":\"603402fe84c6e1418eb6d57b\",\"mistakes\":[\"error_brand_messages_1\"],\"warnings\":[\"warning_brand_messages_1\"]},\"category_messages\":{\"_id\":\"603402fe84c6e1418eb6d57c\",\"mistakes\":[\"error_category_messages_1\"],\"warnings\":[\"warning_category_messages_1\"]},\"company_id\":\"5776daa1f82f454fa8000000\",\"condition_messages\":{\"_id\":\"603402fe84c6e1418eb6d57d\",\"mistakes\":[\"error_condition_messages_1\"],\"warnings\":[\"warning_condition_messages_1\"]},\"created_at\":null,\"deliverytimesupplier_messages\":{\"_id\":\"603402fe84c6e1418eb6d57e\",\"mistakes\":[\"error_deliverytimesupplier_messages_1\"],\"warnings\":[\"warning_deliverytimesupplier_messages_1\"]},\"description_messages\":{\"_id\":\"603402fe84c6e1418eb6d57f\",\"mistakes\":[\"error_description_messages_1\"],\"warnings\":[\"warning_description_messages_1\"]},\"gender_messages\":{\"_id\":\"603402fe84c6e1418eb6d580\",\"mistakes\":[\"error_gender_messages_1\"],\"warnings\":[\"warning_gender_messages_1\"]},\"integration_config_id\":\"6012c3c784c6e179b53043f5\",\"is_fullproductname_messages\":{\"_id\":\"603402fe84c6e1418eb6d581\",\"mistakes\":[\"error_is_fullproductname_messages_1\"],\"warnings\":[\"warning_is_fullproductname_messages_1\"]},\"is_last\":null,\"marketplace\":\"centry-test-local-v2\",\"messages\":{\"_id\":\"603402fe84c6e1418eb6d582\",\"mistakes\":[\"error_messages_1\"],\"warnings\":[\"warning_messages_1\"]},\"name_messages\":{\"_id\":\"603402fe84c6e1418eb6d583\",\"mistakes\":[\"error_name_messages_1\"],\"warnings\":[\"warning_name_messages_1\"]},\"packageheight_messages\":{\"_id\":\"603402fe84c6e1418eb6d584\",\"mistakes\":[\"error_packageheight_messages_1\"],\"warnings\":[\"warning_packageheight_messages_1\"]},\"packagelength_messages\":{\"_id\":\"603402fe84c6e1418eb6d585\",\"mistakes\":[\"error_packagelength_messages_1\"],\"warnings\":[\"warning_packagelength_messages_1\"]},\"packagewidth_messages\":{\"_id\":\"603402fe84c6e1418eb6d586\",\"mistakes\":[\"error_packagewidth_messages_1\"],\"warnings\":[\"warning_packagewidth_messages_1\"]},\"price_compare_messages\":{\"_id\":\"603402fe84c6e1418eb6d587\",\"mistakes\":[\"error_price_compare_messages_1\"],\"warnings\":[\"warning_price_compare_messages_1\"]},\"price_messages\":{\"_id\":\"603402fe84c6e1418eb6d588\",\"mistakes\":[\"error_price_messages_1\"],\"warnings\":[\"warning_price_messages_1\"]},\"product_id\":\"5a16c0bcf82f45273b000054\",\"request\":\"{}\",\"request_response_id\":null,\"response\":null,\"saleenddate_messages\":{\"_id\":\"603402fe84c6e1418eb6d589\",\"mistakes\":[\"error_saleenddate_messages_1\"],\"warnings\":[\"warning_saleenddate_messages_1\"]},\"salestartdate_messages\":{\"_id\":\"603402fe84c6e1418eb6d58a\",\"mistakes\":[\"error_salestartdate_messages_1\"],\"warnings\":[\"warning_salestartdate_messages_1\"]},\"season_messages\":{\"_id\":\"603402fe84c6e1418eb6d58b\",\"mistakes\":[\"error_season_messages_1\"],\"warnings\":[\"warning_season_messages_1\"]},\"seasonyear_messages\":{\"_id\":\"603402fe84c6e1418eb6d58c\",\"mistakes\":[\"error_seasonyear_messages_1\"],\"warnings\":[\"warning_seasonyear_messages_1\"]},\"seo_description_messages\":{\"_id\":\"603402fe84c6e1418eb6d58d\",\"mistakes\":[\"error_seo_description_messages_1\"],\"warnings\":[\"warning_seo_description_messages_1\"]},\"seo_title_messages\":{\"_id\":\"603402fe84c6e1418eb6d58e\",\"mistakes\":[\"error_seo_title_messages_1\"],\"warnings\":[\"warning_seo_title_messages_1\"]},\"shortdescription_messages\":{\"_id\":\"603402fe84c6e1418eb6d58f\",\"mistakes\":[\"error_shortdescription_messages_1\"],\"warnings\":[\"warning_shortdescription_messages_1\"]},\"sku_messages\":{\"_id\":\"603402fe84c6e1418eb6d590\",\"mistakes\":[\"error_sku_messages_1\"],\"warnings\":[\"warning_sku_messages_1\"]},\"status_messages\":{\"_id\":\"603402fe84c6e1418eb6d591\",\"mistakes\":[\"error_status_messages_1\"],\"warnings\":[\"warning_status_messages_1\"]},\"success\":null,\"updated_at\":null,\"warranty_messages\":{\"_id\":\"603402fe84c6e1418eb6d592\",\"mistakes\":[\"error_warranty_messages_1\"],\"warnings\":[\"warning_warranty_messages_1\"]}}",
    "saleenddate_messages": {
        "_id": "603402fe84c6e1418eb6d589",
        "mistakes": [
            "error_saleenddate_messages_1"
        ],
        "warnings": [
            "warning_saleenddate_messages_1"
        ]
    },
    "salestartdate_messages": {
        "_id": "603402fe84c6e1418eb6d58a",
        "mistakes": [
            "error_salestartdate_messages_1"
        ],
        "warnings": [
            "warning_salestartdate_messages_1"
        ]
    },
    "season_messages": {
        "_id": "603402fe84c6e1418eb6d58b",
        "mistakes": [
            "error_season_messages_1"
        ],
        "warnings": [
            "warning_season_messages_1"
        ]
    },
    "seasonyear_messages": {
        "_id": "603402fe84c6e1418eb6d58c",
        "mistakes": [
            "error_seasonyear_messages_1"
        ],
        "warnings": [
            "warning_seasonyear_messages_1"
        ]
    },
    "seo_description_messages": {
        "_id": "603402fe84c6e1418eb6d58d",
        "mistakes": [
            "error_seo_description_messages_1"
        ],
        "warnings": [
            "warning_seo_description_messages_1"
        ]
    },
    "seo_title_messages": {
        "_id": "603402fe84c6e1418eb6d58e",
        "mistakes": [
            "error_seo_title_messages_1"
        ],
        "warnings": [
            "warning_seo_title_messages_1"
        ]
    },
    "shortdescription_messages": {
        "_id": "603402fe84c6e1418eb6d58f",
        "mistakes": [
            "error_shortdescription_messages_1"
        ],
        "warnings": [
            "warning_shortdescription_messages_1"
        ]
    },
    "sku_messages": {
        "_id": "603402fe84c6e1418eb6d590",
        "mistakes": [
            "error_sku_messages_1"
        ],
        "warnings": [
            "warning_sku_messages_1"
        ]
    },
    "status_messages": {
        "_id": "603402fe84c6e1418eb6d591",
        "mistakes": [
            "error_status_messages_1"
        ],
        "warnings": [
            "warning_status_messages_1"
        ]
    },
    "success": false,
    "updated_at": "2021-02-22T16:16:14.393-03:00",
    "warranty_messages": {
        "_id": "603402fe84c6e1418eb6d592",
        "mistakes": [
            "error_warranty_messages_1"
        ],
        "warnings": [
            "warning_warranty_messages_1"
        ]
    }
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`product_id` | El identificador de la relación producto de la que se desea obtener el historial de sincronizaciones




## Crear historiales de sincronización de un producto

Este endpoint entrega todos los historiales de sincronización de producto.

```shell
curl -L -X POST 'https://www.centry.cl/conexion/v1/products/<product_id>/synchronization_histories.json' \
-H 'Authorization: Bearer <access_token>' \
-H 'Content-Type: application/json' \
--data-raw '{
    "action":"Product update",
    "name_messages":{
        "warnings":["warning_name_messages_1"],
        "mistakes": ["error_name_messages_1"]
    },
    "description_messages":{
        "warnings":["warning_description_messages_1"],
        "mistakes": ["error_description_messages_1"]
    },
    "price_messages":{
        "warnings":["warning_price_messages_1"],
        "mistakes": ["error_price_messages_1"]
    },
    "price_compare_messages":{
        "warnings":["warning_price_compare_messages_1"],
        "mistakes": ["error_price_compare_messages_1"]
    },
    "barcode_messages":{
        "warnings":["warning_barcode_messages_1"],
        "mistakes": ["error_barcode_messages_1"]
    },
    "status_messages":{
        "warnings":["warning_status_messages_1"],
        "mistakes": ["error_status_messages_1"]
    },
    "seo_title_messages":{
        "warnings":["warning_seo_title_messages_1"],
        "mistakes": ["error_seo_title_messages_1"]
    },
    "seo_description_messages":{
        "warnings":["warning_seo_description_messages_1"],
        "mistakes": ["error_seo_description_messages_1"]
    },
    "packageheight_messages":{
        "warnings":["warning_packageheight_messages_1"],
        "mistakes": ["error_packageheight_messages_1"]
    },
    "packagewidth_messages":{
        "warnings":["warning_packagewidth_messages_1"],
        "mistakes": ["error_packagewidth_messages_1"]
    },
    "packagelength_messages":{
        "warnings":["warning_packagelength_messages_1"],
        "mistakes": ["error_packagelength_messages_1"]
    },
    "shortdescription_messages":{
        "warnings":["warning_shortdescription_messages_1"],
        "mistakes": ["error_shortdescription_messages_1"]
    },
    "salestartdate_messages":{
        "warnings":["warning_salestartdate_messages_1"],
        "mistakes": ["error_salestartdate_messages_1"]
    },
    "saleenddate_messages":{
        "warnings":["warning_saleenddate_messages_1"],
        "mistakes": ["error_saleenddate_messages_1"]
    },
    "condition_messages":{
        "warnings":["warning_condition_messages_1"],
        "mistakes": ["error_condition_messages_1"]
    },
    "seasonyear_messages":{
        "warnings":["warning_seasonyear_messages_1"],
        "mistakes": ["error_seasonyear_messages_1"]
    },
    "season_messages":{
        "warnings":["warning_season_messages_1"],
        "mistakes": ["error_season_messages_1"]
    },
    "sku_messages":{
        "warnings":["warning_sku_messages_1"],
        "mistakes": ["error_sku_messages_1"]
    },
    "deliverytimesupplier_messages":{
        "warnings":["warning_deliverytimesupplier_messages_1"],
        "mistakes": ["error_deliverytimesupplier_messages_1"]
    },
    "is_fullproductname_messages":{
        "warnings":["warning_is_fullproductname_messages_1"],
        "mistakes": ["error_is_fullproductname_messages_1"]
    },
    "category_messages":{
        "warnings":["warning_category_messages_1"],
        "mistakes": ["error_category_messages_1"]
    },
    "brand_messages":{
        "warnings":["warning_brand_messages_1"],
        "mistakes": ["error_brand_messages_1"]
    },
    "gender_messages":{
        "warnings":["warning_gender_messages_1"],
        "mistakes": ["error_gender_messages_1"]
    },
    "warranty_messages":{
        "warnings":["warning_warranty_messages_1"],
        "mistakes": ["error_warranty_messages_1"]
    },
    "messages":{
        "warnings":["warning_messages_1"],
        "mistakes": ["error_messages_1"]
    }
}'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`product` | El identificador de la relación producto de la que se desea obtener el historial de sincronizaciones

### Parámetros Data

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`action` | Listado de acciones disponibles: ["Product save", "Product create", "Product update", "Product unpublish", "Product delete", "Image save", "Description update", "Active Meli Flex", "Deactive Meli Flex"]
`mistakes` | Listado de errores de un campo en específico que no permitieron que la petición haya resultado exitosa
`warnings` | Listado de advertencias u oportinidades de mejora de un campo en específico que ha pesar de no ser óptimas la petición se realizó de manera exitosa
`name_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `name`
`description_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `description`
`price_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `price`
`price_compare_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `price_compare`
`barcode_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `barcode`
`status_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `status`
`seo_title_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `seo_title`
`seo_description_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `seo_description`
`packageheight_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `packageheight`
`packagewidth_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `packagewidth`
`packagelength_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `packagelength`
`shortdescription_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `shortdescription`
`salestartdate_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `salestartdate`
`saleenddate_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `saleenddate`
`condition_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `condition`
`seasonyear_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `seasonyear`
`season_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `season`
`sku_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `sku`
`deliverytimesupplier_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `deliverytimesupplier`
`is_fullproductname_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `is_fullproductname`
`category_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `category`
`brand_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `brand`
`gender_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `gender`
`warranty_messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados con el atributo `warranty`
`messages` | Objeto con el listado de `mistakes` y/o `warnings` relacionados en general con el modelo `product`



## Todos los assets de un producto

Este endpoint entrega todos los assets de un producto.

```shell
curl -X GET https://www.centry.cl/conexion/v1/products/<product_id>/assets.json \
    -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5fe9fec484c6e1ec5a67d7b8",
        "alt": null,
        "created_at": "2020-12-28T12:50:28.559-03:00",
        "image_content_type": "image/jpeg",
        "image_file_name": "imagen.jpg",
        "image_file_size": 26136,
        "image_fingerprint": "5d3869297ae3e258fa302c1f6d37d54c",
        "image_processing": false,
        "image_updated_at": "2020-12-28T12:50:30.831-03:00",
        "integrations": {},
        "locked_at": null,
        "locked_until": null,
        "name": null,
        "position": 0,
        "updated_at": "2021-02-12T13:11:27.404-03:00"
    },
    {
        "_id": "5fe9fec484c6e1ec5a67d7c02",
        "alt": null,
        "created_at": "2020-12-28T12:51:40.800-03:00",
        "image_content_type": "imagen_2/jpeg",
        "image_file_name": "imagen_2.jpg",
        "image_file_size": 28465,
        "image_fingerprint": "5d3869297ae3e258fa302c1f6d37d56b",
        "image_processing": false,
        "image_updated_at": "2020-12-28T12:51:40.800-03:00",
        "integrations": {},
        "locked_at": null,
        "locked_until": null,
        "name": null,
        "position": 0,
        "updated_at": "2020-12-28T12:51:40.800-03:00"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;/assets.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`product_id` | El identificador de la relación producto de la que se desea obtener sus assets

## Obtener un asset específico de un producto

Este endpoint entrega un asset en específico de un producto.

```shell
curl -X GET https://www.centry.cl/conexion/v1/products/<product_id>/assets/<asset_id>.json \
    -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5fe9fec484c6e1ec5a67d7b8",
    "alt": null,
    "created_at": "2020-12-28T12:50:28.559-03:00",
    "image_content_type": "image/jpeg",
    "image_file_name": "imagen.jpg",
    "image_file_size": 26136,
    "image_fingerprint": "5d3869297ae3e258fa302c1f6d37d54c",
    "image_processing": false,
    "image_updated_at": "2020-12-28T12:50:30.831-03:00",
    "integrations": {},
    "locked_at": null,
    "locked_until": null,
    "name": null,
    "position": 0,
    "updated_at": "2021-02-12T13:11:27.404-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;/assets/&lt;asset_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`product_id` | El identificador de la relación producto de la que se desea obtener sus assets
`asset_id` | El identificador del asset que se quiere obtener del producto


## Todos los historiales de sincronización de un asset

Este endpoint entrega todos los historiales de sincronización de un asset.

```shell
curl -X GET https://www.centry.cl/conexion/v1/products/<product_id>/assets/<asset_id>/synchronization_histories.json \
    -H "Authorization: Bearer  <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
        "_id": "6034fa2c84c6e1418eb6d79c",
        "action": "Product update",
        "alt_messages": {
            "_id": "6034fa2c84c6e1418eb6d79d",
            "mistakes": [
                "errors_alt_messages_1"
            ],
            "warnings": [
                "warning_alt_messages_1"
            ]
        },
        "messages": {
            "_id": "6034fa2c84c6e1418eb6d79e",
            "mistakes": [
                "errors_messages_1"
            ],
            "warnings": [
                "warning_messages_1"
            ]
        },
        "name_messages": {
            "_id": "6034fa2c84c6e1418eb6d79f",
            "mistakes": [
                "errors_name_messages_1"
            ],
            "warnings": [
                "warning_name_messages_1"
            ]
        },
        "position_messages": {
            "_id": "6034fa2c84c6e1418eb6d7a0",
            "mistakes": [
                "errors_position_messages_1"
            ],
            "warnings": [
                "warning_position_messages_1"
            ]
        },
        "url_messages": {
            "_id": "6034fa2c84c6e1418eb6d7a1",
            "mistakes": [
                "errors_url_messages_1"
            ],
            "warnings": [
                "warning_url_messages_1"
            ]
        },
        "asset_id": "5fe9fec484c6e1ec5a67d7b8",
        "company_id": "5776daa1f82f454fa8000000",
        "created_at": "2021-02-23T09:50:52.992-03:00",
        "integration_config_id": "6012c3c784c6e179b53043f5",
        "is_last": null,
        "marketplace": "centry-test-local-v2",
        "product_id": "5a16c0bcf82f45273b000054",
        "request": "{}",
        "request_response_id": null,
        "response": "{\"_id\":\"6034fa2c84c6e1418eb6d79c\",\"action\":\"Product update\",\"alt_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d79d\",\"mistakes\":[\"errors_alt_messages_1\"],\"warnings\":[\"warning_alt_messages_1\"]},\"asset_id\":\"5fe9fec484c6e1ec5a67d7b8\",\"company_id\":\"5776daa1f82f454fa8000000\",\"created_at\":null,\"integration_config_id\":\"6012c3c784c6e179b53043f5\",\"is_last\":null,\"marketplace\":\"centry-test-local-v2\",\"messages\":{\"_id\":\"6034fa2c84c6e1418eb6d79e\",\"mistakes\":[\"errors_messages_1\"],\"warnings\":[\"warning_messages_1\"]},\"name_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d79f\",\"mistakes\":[\"errors_name_messages_1\"],\"warnings\":[\"warning_name_messages_1\"]},\"position_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d7a0\",\"mistakes\":[\"errors_position_messages_1\"],\"warnings\":[\"warning_position_messages_1\"]},\"product_id\":\"5a16c0bcf82f45273b000054\",\"request\":\"{}\",\"request_response_id\":null,\"response\":null,\"success\":null,\"updated_at\":null,\"url_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d7a1\",\"mistakes\":[\"errors_url_messages_1\"],\"warnings\":[\"warning_url_messages_1\"]}}",
        "success": false,
        "updated_at": "2021-02-23T09:50:52.992-03:00"

    }
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;/assets/&lt;asset_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`product_id` | El identificador de la relación producto de la que se desea obtener el historial de sincronizaciones de un asset
`asset_id` | El identificador de la relación producto/asset de la que se desea obtener el historial de sincronizaciones de un asset específico


## Crear historial de sincronización de un asset

Este endpoint entrega todos los historiales de sincronización de un asset.

```shell
curl -L -X POST 'https://www.centry.cl/conexion/v1/products/<product_id>/assets/<asset_id>/synchronization_histories.json' \
-H 'Authorization: Bearer c5b91075622352558f1cfcee548c524bcab3a63b67bdfae0883458f628f9ae0c' \
-H 'Content-Type: application/json' \
--data-raw '{
    "action":"Product update",
    "name_messages":{
  "warnings":["warning_name_messages_1"],
  "mistakes":["errors_name_messages_1"]
},
"alt_messages":{
  "warnings":["warning_alt_messages_1"],
  "mistakes":["errors_alt_messages_1"]
},
"position_messages":{
  "warnings":["warning_position_messages_1"],
  "mistakes":["errors_position_messages_1"]
},
"url_messages":{
  "warnings":["warning_url_messages_1"],
  "mistakes":["errors_url_messages_1"]
},
"messages":{
  "warnings":["warning_messages_1"],
  "mistakes":["errors_messages_1"]
}
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "6034fa2c84c6e1418eb6d79c",
    "action": "Product update",
    "alt_messages": {
        "_id": "6034fa2c84c6e1418eb6d79d",
        "mistakes": [
            "errors_alt_messages_1"
        ],
        "warnings": [
            "warning_alt_messages_1"
        ]
    },
    "asset_id": "5fe9fec484c6e1ec5a67d7b8",
    "company_id": "5776daa1f82f454fa8000000",
    "created_at": "2021-02-23T09:50:52.992-03:00",
    "integration_config_id": "6012c3c784c6e179b53043f5",
    "is_last": null,
    "marketplace": "centry-test-local-v2",
    "messages": {
        "_id": "6034fa2c84c6e1418eb6d79e",
        "mistakes": [
            "errors_messages_1"
        ],
        "warnings": [
            "warning_messages_1"
        ]
    },
    "name_messages": {
        "_id": "6034fa2c84c6e1418eb6d79f",
        "mistakes": [
            "errors_name_messages_1"
        ],
        "warnings": [
            "warning_name_messages_1"
        ]
    },
    "position_messages": {
        "_id": "6034fa2c84c6e1418eb6d7a0",
        "mistakes": [
            "errors_position_messages_1"
        ],
        "warnings": [
            "warning_position_messages_1"
        ]
    },
    "product_id": "5a16c0bcf82f45273b000054",
    "request": "{}",
    "request_response_id": null,
    "response": "{\"_id\":\"6034fa2c84c6e1418eb6d79c\",\"action\":\"Product update\",\"alt_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d79d\",\"mistakes\":[\"errors_alt_messages_1\"],\"warnings\":[\"warning_alt_messages_1\"]},\"asset_id\":\"5fe9fec484c6e1ec5a67d7b8\",\"company_id\":\"5776daa1f82f454fa8000000\",\"created_at\":null,\"integration_config_id\":\"6012c3c784c6e179b53043f5\",\"is_last\":null,\"marketplace\":\"centry-test-local-v2\",\"messages\":{\"_id\":\"6034fa2c84c6e1418eb6d79e\",\"mistakes\":[\"errors_messages_1\"],\"warnings\":[\"warning_messages_1\"]},\"name_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d79f\",\"mistakes\":[\"errors_name_messages_1\"],\"warnings\":[\"warning_name_messages_1\"]},\"position_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d7a0\",\"mistakes\":[\"errors_position_messages_1\"],\"warnings\":[\"warning_position_messages_1\"]},\"product_id\":\"5a16c0bcf82f45273b000054\",\"request\":\"{}\",\"request_response_id\":null,\"response\":null,\"success\":null,\"updated_at\":null,\"url_messages\":{\"_id\":\"6034fa2c84c6e1418eb6d7a1\",\"mistakes\":[\"errors_url_messages_1\"],\"warnings\":[\"warning_url_messages_1\"]}}",
    "success": false,
    "updated_at": "2021-02-23T09:50:52.992-03:00",
    "url_messages": {
        "_id": "6034fa2c84c6e1418eb6d7a1",
        "mistakes": [
            "errors_url_messages_1"
        ],
        "warnings": [
            "warning_url_messages_1"
        ]
    }
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;/assets/&lt;asset_id&gt;/synchronization_histories.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro              | Descripción
---------------------- | ----------------------------------------------------------
`product_id` | El identificador de la relación producto de la que se desea obtener el historial de sincronizaciones de un asset
`asset_id` | El identificador de la relación producto/asset de la que se desea obtener el historial de sincronizaciones de un asset específico
