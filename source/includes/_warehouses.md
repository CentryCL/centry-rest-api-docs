# Warehouses

## Parámetros

| Atributo       | Tipo   | Descripción                                                                                         |
| ---------------| ------ | --------------------------------------------------------------------------------------------------- |
| `_id`          | string | Identificador del warehouse <i class="label label-info">sólo lectura</i>                              |
| `name`         | string | Nombre con el cual se puede reconocer la bodega                                                     |
| `address`      | string | Dirección donde se encuentra ubicada la bodega                                                      |
| `country_id`   | string | Identificador del país. Ver endpoint [Countries](#countries)                                        |
| `region_id`    | string | Identificador de la región. Ver endpoint [Regions](#regions)                                        |
| `city_id`      | string | Identificador de la ciudad. Ver endpoint [Cities](#cities)                                          |
| `commune_id`   | string | Identificador de la comuna. Ver endpoint [Communes](#communes)                                      |
| `latitude`     | string | Número decimal con la latitud de la ubicación geográfica de la bodega                               |
| `longitude`    | string | Número decimal con la longitud de la ubicación geográfica de la bodega                              |
| `integrations` | object | Diccionario con información especializada para algunas integraciones                                |
| `company_id`   | string | Identificador de empresa <i class="label label-info">sólo lectura</i>                               |
| `created_at`   | string | Fecha de creación del warehouse en Centry <i class="label label-info">sólo lectura</i>                |
| `updated_at`   | string | Fecha de la última modificación del warehouse en Centry  <i class="label label-info">sólo lectura</i> |

## Listar las bodegas de la cuenta

Este endpoint entrega todas las bodegas registradas en la cuenta.

```shell
curl -X GET \
  https://www.centry.cl/conexion/v1/warehouses.json \
  -H 'authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "577eb7b8f82f456ef4000001",
        "address": "Aurelio González 3838, oficina 02",
        "city_id": null,
        "commune_id": "5769714df82f456e80000169",
        "company_id": "577eb7b8f82f456ef4000000",
        "country_id": null,
        "created_at": "2016-07-07T16:12:40.079-04:00",
        "integrations": {},
        "latitude": "",
        "longitude": "",
        "name": "Casa matriz",
        "region_id": "5769714df82f456e80000001",
        "updated_at": "2019-09-24T13:39:44.792-03:00"
    },
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/warehouses.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar el request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/warehouses.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.

### Filtros especiales

Sólo pueden ser ocupados para este endpoint en particular.

Filtro       | Descripción                                            | Ejemplo
------------ | ------------------------------------------------------ | -------
`name`       | Buscar por el nombre exacto de una bodega              | https://www.centry.cl/conexion/v1/warehouses.json?name=Casa%20matriz
`address`    | Buscar por la dirección exacta de una bodega           | https://www.centry.cl/conexion/v1/warehouses.json?address=Aurelio20González203838,20oficina2002
`latitude`   | Buscar por la latitud geográfica exacta de una bodega  | https://www.centry.cl/conexion/v1/warehouses.json?latitude=
`longitude`  | Buscar por la longitud geográfica exacta de una bodega | https://www.centry.cl/conexion/v1/warehouses.json?longitude=

## Obtener una bodega específica

Este endpoint entrega una bodega específica.

```shell
curl -X GET \
  https://www.centry.cl/conexion/v1/warehouses/577eb7b8f82f456ef4000001.json \
  -H 'authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "577eb7b8f82f456ef4000001",
    "address": "Badajoz 100, oficina 407",
    "city_id": null,
    "commune_id": "5769714df82f456e80000169",
    "company_id": "577eb7b8f82f456ef4000000",
    "country_id": null,
    "created_at": "2016-07-07T16:12:40.079-04:00",
    "integrations": {},
    "latitude": "",
    "longitude": "",
    "name": "Casa matriz",
    "region_id": "5769714df82f456e80000001",
    "updated_at": "2019-09-24T13:39:44.792-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/warehouses/&lt;warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro      | Descripción
-------------- | -----------------------------------------
`warehouse_id` | El identificador de la bodega a recuperar

## Crear una bodega

Este endpoint permite crear una bodega nueva.


```shell
curl -X POST \
  https://www.centry.cl/conexion/v1/warehouses.json \
  -H 'authorization: Bearer <access_token>' \
  -H 'content-type: application/json' \
  -d '{
    "name": "Demo",
    "address": "Calle principal 5500",
    "latitude": 70.04,
    "longitude": -30.43
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5dd2f56a48f0393d1d17f984",
    "address": "Calle principal 5500",
    "city_id": null,
    "commune_id": null,
    "company_id": "577eb7b8f82f456ef4000000",
    "country_id": null,
    "created_at": "2019-11-18T16:47:54.309-03:00",
    "latitude": "70.04",
    "longitude": "-30.43",
    "name": "Demo",
    "region_id": null,
    "updated_at": "2019-11-18T16:47:54.309-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/warehouses.json </h6>
  </div>
</div>

## Actualizar una bodega

Este endpoint permite modificar una bodega específica.


```shell
curl -X PUT \
  https://www.centry.cl/conexion/v1/warehouses/5dd2f56a48f0393d1d17f984.json \
  -H 'authorization: Bearer <access_token>' \
  -H 'content-type: application/json' \
  -d '{
    "address": "Nuevo nombre",
    "longitude": 25.05
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5dd2f56a48f0393d1d17f984",
    "address": "Calle principal 5500",
    "city_id": null,
    "commune_id": null,
    "company_id": "577eb7b8f82f456ef4000000",
    "country_id": null,
    "created_at": "2019-11-18T16:47:54.309-03:00",
    "latitude": "70.04",
    "longitude": "25.05",
    "name": "Nuevo nombre",
    "region_id": null,
    "updated_at": "2019-11-18T16:47:54.309-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/warehouses/&lt;warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro      | Descripción
-------------- | ------------------------------------------
`warehouse_id` | El identificador de la bodega a actualizar

## Eliminar un warehouse

Este endpoint elimina permanentemente una bodega específica.

```shell
curl -X DELETE \
  https://www.centry.cl/conexion/v1/warehouses/59c9852d1746bf1d93000001.json \
  -H 'authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/warehouses/&lt;warehouse_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro      | Descripción
-------------- | ----------------------------------------
`warehouse_id` | El identificador de la bodega a eliminar
