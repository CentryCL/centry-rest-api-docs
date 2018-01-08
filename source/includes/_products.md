# Products

## Parámetros

| Atributo               | Tipo      | Descripción                                                                            |
| ---------------------- | --------- | -------------------------------------------------------------------------------------- |
| `id`                   | string    | Identificador del producto <i class="label label-info">sólo lectura</i>                |
| `barcode`              | string    | Información almacenada en el código de barras                                          |
| `brand_id`             | string    | Identificador de la marca                                                              |
| `bulk_upload`          | boolean   | Valor sensible en carga masiva** default: false                                        |
| `category_id`          | integer   | Identificador de categoría a la que pertenece                                          |
| `color`                | string    | Describe el color del producto                                                         |
| `company_id`           | integer   | Identificador de la compañía a la que pertenece el producto <i class="label label-info">sólo lectura</i> |
| `condition`            | string    | Describe la condición del producto (Nuevo, usado,renovado)                             |
| `cover_content_type`   | string    | Almacena extensión de la imagen de cover                                               |
| `cover_file_name`      | string    | Nombre de imagen de cover                                                              |
| `cover_file_size`      | integer   | Tamaño de imagen de cover                                                              |
| `cover_fingerprint`    | string    | CheckSum  de cover de imagen                                                           |
| `cover_updated_at`     | date-time | Almacena fecha en formato UTC de actualización de la imagen de cover                   |
| `cover_url`            | string    | Almacena URL de imagen descriptiva del producto                                        |
| `deliverytimesupplier` | integer   | Valor aproximado en días, de la llegada del producto al cliente                        |
| `description`          | string    | Descripción del producto                                                               |
| `gender_id`            | integer   | Identificador del genero del producto                                                  |
| `is_fullproductname`   | boolean   | Indica si el nombre del producto está completo o acortado                              |
| `name`                 | string    | Nombre del producto                                                                    |
| `options`              | string    | Opciones del producto (talla, color, etc)                                              |
| `original_data`        | string    | Campo usado para almacenar toda la información del producto según su origen.           |
| `packageheight`        | integer   | Valor en centímetros de la altura del paquete                                          |
| `packagelength`        | integer   | Valor en centímetros del largo del paquete                                             |
| `packageweight`        | integer   | Valor en centímetros del ancho del paquete                                             |
| `packagewidth`         | integer   | Valor en kilogramos del peso del paquete                                               |
| `price`                | integer   | Valor monetario del producto                                                           |
| `price_compare`        | integer   | Valor monetario de comparación del producto                                            |
| `publish`              | boolean   | Describe si el producto ha sido publicado para la venta. Default true                  |
| `quantity`             | integer   | Stock del producto                                                                     |
| `saleenddate`          | date-time | Fecha en formato UTC que indica el fin de oferta                                       |
| `salestartdate`        | date-time | Fecha en formato UTC que indica el inicio de oferta                                    |
| `season`               | string    | Describe temporada a la que pertenece el producto                                      |
| `seasonyear`           | integer   | Indica el año del producto                                                             |
| `seo_description`      | string    | Descripción extendida del la temporada                                                 |
| `seo_title`            | string    | Título de la temporada                                                                 |
| `shortdescription`     | string    | Descripción acotada del producto                                                       |
| `sku`                  | string    | sku del producto                                                                       |
| `skusupplierconfig`    | string    | Shows the quantity of products in this term                                            |
| `status`               | boolean   | Shows the quantity of products in this term                                            |
| `variants`             | array     | Lista de variantes del producto. Ver [Atributos de variantes](#atributos-de-variantes) |
| `warranty`             | integer   | Valor en meses de la garantía del producto                                             |
| `created_at`           | date-time | Almacena fecha en formato UTC de creación de producto <i class="label label-info">sólo lectura</i> |
| `updated_at`           | date-time | Fecha de última actualización del producto <i class="label label-info">sólo lectura</i> |

### Atributos de variantes

| Atributo          | Tipo      | Descripción                                                                                     |
| ----------------- | --------- | ----------------------------------------------------------------------------------------------- |
| `_id`             | string    | Identificador de la variante <i class="label label-info">sólo lectura</i>                       |
| `barcode`         | string    | Información del código de barras                                                                |
| `bulk_upload`     | boolean   | Carga masiva                                                                                    |
| `color_id`        | integer   | Identificador del color                                                                         |
| `company_id`      | integer   | Identificador de compañía <i class="label label-info">sólo lectura</i>                          |
| `description`     | string    | Descripción de la variante                                                                      |
| `original_data`   | string    | Información total entregada por una variante en caso de ser importada                           |
| `price`           | integer   | Valor monetario real del producto                                                               |
| `price_compare`   | integer   | Valor monetario de comparación del producto                                                     |
| `product_id`      | integer   | Identificador del Producto en Centry                                                            |
| `quantity`        | integer   | Stock de productos de esta variante                                                             |
| `size_id`         | integer   | Identificador de las dimensiones del producto                                                   |
| `sku`             | string    | Información de sku                                                                              |
| `created_at`      | date-time | Fecha en formato UTC de la creación de la variante <i class="label label-info">sólo lectura</i> |
| `updated_at`      | date-time | Registro de actualización en fecha formato UTC <i class="label label-info">sólo lectura</i>     |

## Todos los Productos de la cuenta

Este endpoint entrega todos los productos de la cuenta.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/products.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
    "_id":"597644781d41c846ea000006",
    "barcode":"12345655349384",
    "brand_id":"57f63ffe4c266d1dec1edfb6",
    "bulk_upload":false,
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
    "description":"\u003cp\u003easdasdsadsad\u003c/p\u003e",
    "gender_id":"57ee86e911326899bc8f3f58",
    "id_mercadolibre":null,
    "id_shopify":null,
    "id_woocommerce":null,
    "is_fullproductname":null,
    "listing_type":null,
    "name":"ResTProduct",
    "options":"Talla,Color",
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
    "seo_description":"asdsadas",
    "seo_title":"sadasdd",
    "shortdescription":"\u003cul\u003e\u003cli\u003easdasdasdasd\u003c/li\u003e\u003c/ul\u003e",
    "sku":"CENTSER954",
    "skusupplierconfig":"CENTSER954",
    "status":true,
    "updated_at":"2017-07-24T19:03:20.245Z",
    "variants":[
      {
        "_id":"597649201d41c846ea000009",
        "barcode":"123456553493842",
        "bulk_upload":false,
        "color_id":"57bdc991f82f453f680001d9",
        "company_id":null,
        "created_at":"2017-07-24T19:23:12.919Z",
        "description":"L,Café",
         "id_b_sale":null,
        "id_mercadolibre":null,
        "id_shopify":null,
        "id_woocommerce":null,
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

## Obtener un Producto específico

Este endpoint entrega un producto en específico

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/products/<product_id>.json" -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id":"597644781d41c846ea000006",
  "barcode":"12345655349384",
  "brand_id":"57f63ffe4c266d1dec1edfb6",
  "bulk_upload":false,
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
  "description":"\u003cp\u003easdasdsadsad\u003c/p\u003e",
  "gender_id":"57ee86e911326899bc8f3f58",
  "id_mercadolibre":null,
  "id_shopify":null,
  "id_woocommerce":null,
  "is_fullproductname":null,
  "listing_type":null,
  "name":"ResTProduct",
  "options":"Talla,
  Color",
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
  "seo_description":"asdsadas",
  "seo_title":"sadasdd",
  "shortdescription":"\u003cul\u003e\u003cli\u003easdasdasdasd\u003c/li\u003e\u003c/ul\u003e",
  "sku":"CENTSER954",
  "skusupplierconfig":"CENTSER954",
  "status":true,
  "updated_at":"2017-07-24T19:03:20.245Z",
  "variants":[
    {
      "_id":"597649201d41c846ea000009",
      "barcode":"123456553493842",
      "bulk_upload":false,
      "color_id":"57bdc991f82f453f680001d9",
      "company_id":null,
      "created_at":"2017-07-24T19:23:12.919Z",
      "description":"L,
       Café",
      "id_b_sale":null,
      "id_mercadolibre":null,
      "id_shopify":null,
      "id_woocommerce":null,
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

Este endpoint entrega un producto específico.

### Parámetros URL

Parámetro    | Descripción
------------ | -----------------------------------------
`product_id` | El identificador del producto a recuperar

## Crear un Producto

Este endpoint crea un producto.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/products.json </h6>
  </div>
</div>

```shell
curl -X POST https://www.centry.cl/conexion/v1/products.json \
    -H "Authorization: Bearer  dac351af298e8d410a56a6aa3b01acb47e810852e163413cec45aa005669c423"\
    -H "Content-Type: application/json" \
    -d '{
    "barcode":"123456789",
    "brand_id":"57f63ffe4c266d1dec1edfb6",
    "category_id":"5769714df82f456e800001aa",
    "company_id":<ID_de_tu_empresa>,
    "cover_url":<imagen_producto>,
    "deliverytimesupplier":3,
    "description":"describiendo el asombroso producto que vendaras",
    "name":"Un Nombre Fantastico, para un producto fantastico",
    "packageheight":"20",
    "packagelength":"40",
    "packageweight":"1",
    "packagewidth":"20",
    "price":10000,
    "seasonyear":"2015",
    "seo_description":"Descripcion",
    "seo_title":"Título asombroso",
    "shortdescription":"\u003cul\u003e\u003cli\u003easdasdasdasd\u003c/li\u003e\u003c/ul\u003e",
    "sku":"YOS0YUN54U",
}'
```

## Actualizar un Producto

Este endpoint actualiza un producto.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X PUT https://www.centry.cl/conexion/v1/products/<product_id>.json \
    -H "Authorization: Bearer  <access_token> "\
    -H "Content-Type: application/json" \
    -d '{
  "parametro_a_editar": "nuevo_valor",
  "seo_description":"Descripción bonita vía cUrl"
}'
```

### Parámetros URL

Parámetro    | Descripción
------------ | ------------------------------------------
`product_id` | El identificador del producto a actualizar

## Eliminar un Producto

Este endpoint elimina un producto

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/products/&lt;product_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/products/<product_id>.json \
    -H "Authorization: Bearer  <access_token> "
```

### Parámetros URL

Parámetro    | Descripción
------------ | ----------------------------------------
`product_id` | El identificador del producto a eliminar