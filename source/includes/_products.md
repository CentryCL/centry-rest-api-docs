# Products

## Parámetros




## Todos los Productos de la cuenta
```

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

`GET https://www.centry.cl/conexion/v1/products/`




## Obtener un Producto específico

```shell
curl "https://www.centry.cl/conexion/v1/products/2"
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