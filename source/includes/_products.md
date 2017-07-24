# Products

## Parámetros


| Atributo              |   Tipo  |                                      Descripción                                      |
| ---------             | ------- | ------------------------------------------------------------------------------------- |
| `id`                  | integer | Identificador del producto                        |
| `barcode`             | string  | Información almacenada en el codigo de barras     |
| `brand_id`            | string  | Identificador de la marca         |
| `bulk_upload`         | Boolean | Valor sensible en carga masiva** default: false |
| `category_id`         | integer | Identificador de categoría a la que pertenece |
| `color`               | String  | Describe el color del producto |
| `company_id`          | integer | Identificador de la compañia a la que pertenece el producto |
| `condition`           | String  | Describe la condición del producto (Nuevo, usado,renovado) |
| `cover_content_type`  | String  | Almacena extensión de la imagen de cover |
| `cover_file_name`     | String  | Nombre de imagen de cover|
| `cover_file_size`     | integer | Tamaño de imagen de cover|
| `cover_fingerprint`   | String  | CheckSum  de cover de imagen |
| `cover_updated_at`    | DateTime| Almacena fecha en formato UTC de actualización de la imagen de cover |
| `cover_url`           | String  | Almacena url de imagen descruptiva del producto |
| `created_at`          | DateTime| Almacena fecha en formato UTC de creación de producto |
| `deliverytimesupplier`| integer | Valor aproximado en días, de la llegada del producto al cliente |
| `description`         | String  | Descripción del producto |
| `gender_id`           | integer | Identificador del genero del producto |
| `id_mercadolibre`     | integer | Identificador de producto en integración mercadolibre |
| `id_shopify`          | integer | Identificador de producto en integración shopify |
| `id_woocommerce`      | integer | Identificador de producto en integración woocommerce |
| `is_fullproductname`  | Boolean | Indica si el nombre del producto está completo o acortado |
| `listing_type`        | String  | Valor usado para integración de mercadolibre |
| `name`                | String  | Nombre del producto |
| `options`             | String  | Opciones del producto (talla, color, etc) |
| `original_data`       | String  | Valor usado en integración Woocommerce |
| `packageheight`       | integer | Valor en centimetros de la altura del paquete |
| `packagelength`       | integer | Valor en centimetros del largo del paquete |
| `packageweight`       | integer | Valor en centimetros del ancho del paquete  |
| `packagewidth`        | integer | Valor en kilogramos del peso del paquete  |
| `price`               | integer | Valor monetario del producto |
| `price_compare`       | integer | Valor monetario de comparación del producto |
| `publish`             | Boolean | Describe si el producto ha sido publicado para la venta. Default true |
| `quantity`            | integer | Stock del producto |
| `saleenddate`         | DateTime| Fecha en formato UTC que indica el fin de oferta |
| `salestartdate`       | DateTime| Fecha en formato UTC que indica el inicio de oferta |
| `season`              | String  | Describe temporada a la que pertenece el producto|
| `seasonyear`          | integer | Indica el año del producto |
| `seo_description`     | String  | Descripción extendida del la temporada  |
| `seo_title`           | String  | Título de la temporada |
| `shortdescription`    | String  | Descripción acotada del producto |
| `sku`                 | String  | sku del producto |
| `skusupplierconfig`   | String | Shows the quantity of products in this term |
| `status`              | Boolean | Shows the quantity of products in this term |
| `updated_at`          | DateTime| Fecha de última actualización del producto |
| `variants`            | array   | Lista de variantes del producto. Ver [Atributos de variantes](#atributos-de-variantes) |
| `warranty`            | integer | Valor en meses de la garantía del producto  |






### Atributos de variantes

| Atributo          |   Tipo  |                                      Descripción                                      |
| ---------         | ------- | ------------------------------------------------------------------------------------- |
| `_id`             | integer | Shows the quantity of products in this term |
| `barcode`         | integer | Shows the quantity of products in this term |
| `bulk_upload`     | integer | Shows the quantity of products in this term |
| `color_id`        | integer | Shows the quantity of products in this term |
| `company_id`      | integer | Shows the quantity of products in this term |
| `created_at`      | integer | Shows the quantity of products in this term |
| `description`     | integer | Shows the quantity of products in this term |
| `id_b_sale`       | integer | Shows the quantity of products in this term |
| `id_mercadolibre` | integer | Shows the quantity of products in this term |
| `id_shopify`      | integer | Shows the quantity of products in this term |
| `id_woocommerce`  | integer | Shows the quantity of products in this term |
| `original_data`   | integer | Shows the quantity of products in this term |
| `price`           | integer | Shows the quantity of products in this term |
| `price_compare`   | integer | Shows the quantity of products in this term |
| `product_id`      | integer | Shows the quantity of products in this term |
| `quantity`        | integer | Shows the quantity of products in this term |
| `size_id`         | integer | Shows the quantity of products in this term |
| `sku`             | integer | Shows the quantity of products in this term |
| `updated_at`      | integer | Shows the quantity of products in this term |



## Todos los Productos de la cuenta


```shell
curl "https://www.centry.cl/conexion/v1/products"
  -H "Authorization: tu_centry_api_key"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Este endpoint entrega todos los productos de la cuenta.

### HTTP Request

`GET https://www.centry.cl/conexion/v1/products.json`




## Obtener un Producto específico

```shell
curl "https://www.centry.cl/conexion/v1/products/<product_id>.json"
  -H "Authorization: tu_centry_api_key"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Este endpoint entrega un producto específico.

### HTTP Request

`GET https://www.centry.cl/conexion/v1/products/<ID>`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
ID | El identificador del producto a recuperar




## Crear un Product

### HTTP Request

`POST https://www.centry.cl/conexion/v1/products`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------




## Actualizar un Product

### HTTP Request

`PUT https://www.centry.cl/conexion/v1/products`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
_id | El identificador del producto a actualizar





## Eliminar un Product

### HTTP Request

`DELETE https://www.centry.cl/conexion/v1/products/<ID>`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
ID | El identificador del producto a eliminar