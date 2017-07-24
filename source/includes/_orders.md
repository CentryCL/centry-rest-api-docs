# Orders

## Parámetros




## Todas las Órdenes de la cuenta

```shell
curl "https://www.centry.cl/conexion/v1/orders"
  -H "Authorization: tu_centry_api_key"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {...}
]
```

Este endpoint entrega todas las órdenes de la cuenta.

### HTTP Request

`GET https://www.centry.cl/conexion/v1/orders/`




## Obtener una Orden específica

```shell
curl "https://www.centry.cl/conexion/v1/orders/2"
  -H "Authorization: tu_centry_api_key"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{...}
```

Este endpoint entrega un producto específico.

### HTTP Request

`GET https://www.centry.cl/conexion/v1/products/<ID>`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
ID | El identificador de la orden a recuperar




## Crear una Orden

### HTTP Request

`POST https://www.centry.cl/conexion/v1/orders`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------




## Actualizar una Orden

### HTTP Request

`PUT https://www.centry.cl/conexion/v1/orders`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
_id | El identificador de la orden a actualizar





## Eliminar una Orden

### HTTP Request

`DELETE https://www.centry.cl/conexion/v1/orders/<ID>`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
ID | El identificador de la Orden a eliminar