# Products

## Parámetros


| Atributo              |   Tipo  |                                      Descripción                                      |
| ---------             | ------- | ------------------------------------------------------------------------------------- |
| `id`                  | string | Identificador del producto                        |
| `barcode`             | string  | Información almacenada en el codigo de barras     |
| `brand_id`            | string  | Identificador de la marca         |
| `bulk_upload`         | boolean | Valor sensible en carga masiva** default: false |
| `category_id`         | integer | Identificador de categoría a la que pertenece |
| `color`               | string  | Describe el color del producto |
| `company_id`          | integer | Identificador de la compañia a la que pertenece el producto |
| `condition`           | string  | Describe la condición del producto (Nuevo, usado,renovado) |
| `cover_content_type`  | string  | Almacena extensión de la imagen de cover |
| `cover_file_name`     | string  | Nombre de imagen de cover|
| `cover_file_size`     | integer | Tamaño de imagen de cover|
| `cover_fingerprint`   | string  | CheckSum  de cover de imagen |
| `cover_updated_at`    |date-time| Almacena fecha en formato UTC de actualización de la imagen de cover |
| `cover_url`           | string  | Almacena url de imagen descruptiva del producto |
| `created_at`          |date-time| Almacena fecha en formato UTC de creación de producto |
| `deliverytimesupplier`| integer | Valor aproximado en días, de la llegada del producto al cliente |
| `description`         | string  | Descripción del producto |
| `gender_id`           | integer | Identificador del genero del producto |
| `id_mercadolibre`     | integer | Identificador de producto en integración mercadolibre |
| `id_shopify`          | integer | Identificador de producto en integración shopify |
| `id_woocommerce`      | integer | Identificador de producto en integración woocommerce |
| `is_fullproductname`  | boolean | Indica si el nombre del producto está completo o acortado |
| `listing_type`        | string  | Valor usado para integración de mercadolibre |
| `name`                | string  | Nombre del producto |
| `options`             | string  | Opciones del producto (talla, color, etc) |
| `original_data`       | string  | Valor usado en integración Woocommerce |
| `packageheight`       | integer | Valor en centimetros de la altura del paquete |
| `packagelength`       | integer | Valor en centimetros del largo del paquete |
| `packageweight`       | integer | Valor en centimetros del ancho del paquete  |
| `packagewidth`        | integer | Valor en kilogramos del peso del paquete  |
| `price`               | integer | Valor monetario del producto |
| `price_compare`       | integer | Valor monetario de comparación del producto |
| `publish`             | boolean | Describe si el producto ha sido publicado para la venta. Default true |
| `quantity`            | integer | Stock del producto |
| `saleenddate`         |date-time| Fecha en formato UTC que indica el fin de oferta |
| `salestartdate`       |date-time| Fecha en formato UTC que indica el inicio de oferta |
| `season`              | string  | Describe temporada a la que pertenece el producto|
| `seasonyear`          | integer | Indica el año del producto |
| `seo_description`     | string  | Descripción extendida del la temporada  |
| `seo_title`           | string  | Título de la temporada |
| `shortdescription`    | string  | Descripción acotada del producto |
| `sku`                 | string  | sku del producto |
| `skusupplierconfig`   | string  | Shows the quantity of products in this term |
| `status`              | boolean | Shows the quantity of products in this term |
| `updated_at`          |date-time| Fecha de última actualización del producto |
| `variants`            | array   | Lista de variantes del producto. Ver [Atributos de variantes](#atributos-de-variantes) |
| `warranty`            | integer | Valor en meses de la garantía del producto  |






### Atributos de variantes

| Atributo          |   Tipo  |                                      Descripción                                      |
| ---------         | ------- | ------------------------------------------------------------------------------------- |
| `_id`             | string | Identificador de la variante               |
| `barcode`         | string  | Información del código de barras            |
| `bulk_upload`     | boolean | Carga masiva                                |
| `color_id`        | integer | Identificador del color                     |
| `company_id`      | integer | Identificador de compañia                  |
| `created_at`      |date-time| Fecha en formato UTC de la creación de la variante |
| `description`     | string  | Descripción de la variante                 |
| `id_b_sale`       | integer | Identificador de variante Bsale en caso de ser Importada|
| `id_mercadolibre` | string  | Identificador de variante Mercado libre en caso de ser importada|
| `id_shopify`      | string  | Identificador de variante Shopify en caso de ser importada      |
| `id_woocommerce`  | integer | Identificador de variante Woocommerce en caso de ser importada  |
| `original_data`   | string  | Información total entregada por una variente en caso de ser importada|
| `price`           | integer | Valor monetario real del producto          |
| `price_compare`   | integer | Valor monetario de comparación del producto |
| `product_id`      | integer | Identificador del Producto en Centry       |
| `quantity`        | integer | Stock de productos de esta variante |
| `size_id`         | integer | Identificador de las dimensiones del producto|
| `sku`             | string  | Información de sku                          |
| `updated_at`      |date-time| Registro de actualización en fecha formato UTC |



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
ID | El identificador del producto a <eliminar class=""></eliminar>