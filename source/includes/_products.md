# Products

## Parámetros

| Atributo               | Tipo      | Descripción                                                                                              |
| ---------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| `id`                   | string    | Identificador del producto <i class="label label-info">sólo lectura</i>                                  |
| `name`                 | string    | Nombre del producto                                                                                      |
| `sku`                  | string    | SKU del producto                                                                                         |
| `barcode`              | string    | Código de barras                                                                                         |
| `description`          | string    | Descripción del producto                                                                                 |
| `shortdescription`     | string    | Listado de características del producto del producto. Se recomienda el uso de viñetas HTML sin orden, ie, "<ul><li></li></ul>". |
| `condition`            | string    | Describe la condición del producto (Nuevo, usado, renovado)                                              |
| `brand_id`             | string    | Identificador de la marca                                                                                |
| `category_id`          | integer   | Identificador de categoría a la que pertenece                                                            |
| `cover_content_type`   | string    | Extensión de la imagen principal <i class="label label-info">sólo lectura</i>                            |
| `cover_file_name`      | string    | Nombre de la imagen principal <i class="label label-info">sólo lectura</i>                               |
| `cover_file_size`      | integer   | Tamaño de la imagen principal <i class="label label-info">sólo lectura</i>                               |
| `cover_fingerprint`    | string    | CheckSum de la imagen principal <i class="label label-info">sólo lectura</i>                             |
| `cover_updated_at`     | date-time | Fecha de actualización de la imagen principal <i class="label label-info">sólo lectura</i>               |
| `cover_url`            | string    | URL de la imagen principal.                                                                              |
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
| `variants`             | array     | Lista de variantes del producto. Ver [Atributos de variantes](#atributos-de-variantes)                   |
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
| `product_id`      | integer   | Identificador del Producto en Centry <i class="label label-info">sólo lectura</i>                       |
| `size_id`         | integer   | Identificador de la talla                                                                               |
| `quantity`        | integer   | Stock de la variante.                                                                               |
| `color_id`        | integer   | Identificador del color                                                                                 |
| `company_id`      | integer   | Identificador de la empresa a la que pertenece la variante <i class="label label-info">sólo lectura</i> |
| `created_at`      | date-time | Fecha en formato UTC de la creación de la variante <i class="label label-info">sólo lectura</i>         |
| `updated_at`      | date-time | Registro de actualización en fecha formato UTC <i class="label label-info">sólo lectura</i>             |

## Todos los Productos de la cuenta

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

## Obtener un Producto específico

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

## Crear un Producto

Este endpoint crea un producto.

```shell
curl -X POST https://www.centry.cl/conexion/v1/products.json \
    -H "Authorization: Bearer  <access_token"\
    -H "Content-Type: application/json" \
    -d '{
    "barcode":"123456789",
    "brand_id":"57f63ffe4c266d1dec1edfb6",
    "category_id":"5769714df82f456e800001aa",
    "company_id":<ID_de_tu_empresa>,
    "cover_url":<imagen_producto>,
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

## Actualizar un Producto

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

## Eliminar un Producto

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

## Contar los Productos

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
