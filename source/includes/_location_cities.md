# Cities

## Parámetros

Atributo     | Tipo    | Descripción                                                                            
------------ | ------- | -----------
`_id`        | string  | Identificador de la ciudad <i class="label label-info">sólo lectura</i>
`name`       | string  | Nombre de la ciudad en Centry <i class="label label-info">sólo lectura</i>
`region_id`  | string  | Identificador de la región a la que pertenece la ciudad <i class="label label-info">sólo lectura</i>
`created_at` | string  | Fecha de creación de la ciudad en Centry <i class="label label-info">sólo lectura</i>
`updated_at` | string  | Fecha de la última actualización <i class="label label-info">sólo lectura</i>

## Todas los paises

Este endpoint entrega todas las ciudades de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/locations/cities.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5769714df82f456e8000003f",
        "created_at": "2016-06-21T12:54:37.440-04:00",
        "name": "Maipo",
        "region_id": "5769714df82f456e80000001",
        "updated_at": "2016-06-21T12:54:37.440-04:00"
    },
    {
        "_id": "5769714df82f456e8000003d",
        "created_at": "2016-06-21T12:54:37.438-04:00",
        "name": "Cordillera",
        "region_id": "5769714df82f456e80000001",
        "updated_at": "2016-06-21T12:54:37.438-04:00"
    },
    {
        "_id": "5769714df82f456e8000003e",
        "created_at": "2016-06-21T12:54:37.439-04:00",
        "name": "Chacabuco",
        "region_id": "5769714df82f456e80000001",
        "updated_at": "2016-06-21T12:54:37.439-04:00"
    },
    {
        "_id": "5769714df82f456e8000003c",
        "created_at": "2016-06-21T12:54:37.437-04:00",
        "name": "Santiago",
        "region_id": "5769714df82f456e80000001",
        "updated_at": "2016-06-21T12:54:37.437-04:00"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/locations/cities.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar la request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/locations/cities.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro      | Descripción                                            | Ejemplo
----------- | ------------------------------------------------------ | -------
`region_id` | Busca ciudades que pertenezcan a una región específica | https://www.centry.cl/conexion/v1/locations/cities.json?region_id=5769714df82f456e80000001
`name`      | Busca ciudades por el nombre el nombre exacto          | https://www.centry.cl/conexion/v1/locations/cities.json?name=Santiago

## Obtener un país específico

Este endpoint entrega una ciudad específica.

```shell
curl "https://www.centry.cl/conexion/v1/locations/cities/<city_id>.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5769714df82f456e80000001",
    "region_id": "5769714df82f456e80000000",
    "created_at": "2016-06-21T12:54:37.370-04:00",
    "name": "Región Metropolitana",
    "position": 1,
    "updated_at": "2016-06-21T12:54:37.370-04:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/locations/cities/&lt;city_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro | Descripción
--------- | -----------
`city_id` | El identificador de la ciudad a recuperar
