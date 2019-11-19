# Communes

## Parámetros

Atributo     | Tipo    | Descripción                                                                            
------------ | ------- | -----------
`_id`        | string  | Identificador de la comuna <i class="label label-info">sólo lectura</i>
`name`       | string  | Nombre de la comuna en Centry <i class="label label-info">sólo lectura</i>
`city_id`    | string  | Identificador de la ciudad a la que pertenece la comuna <i class="label label-info">sólo lectura</i>
`created_at` | string  | Fecha de creación de la comuna en Centry <i class="label label-info">sólo lectura</i>
`updated_at` | string  | Fecha de la última actualización <i class="label label-info">sólo lectura</i>

## Todas los paises

Este endpoint entrega todas las comunas de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/locations/communes.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5769714df82f456e80000048",
        "city_id": "5769714df82f456e80000011",
        "created_at": "2016-06-21T12:54:37.449-04:00",
        "name": "Pozo Almonte",
        "region_id": "5769714df82f456e80000002",
        "updated_at": "2016-06-21T12:54:37.449-04:00"
    },
    {
        "_id": "5769714df82f456e8000004c",
        "city_id": "5769714df82f456e80000011",
        "created_at": "2016-06-21T12:54:37.453-04:00",
        "name": "Pica",
        "region_id": "5769714df82f456e80000002",
        "updated_at": "2016-06-21T12:54:37.453-04:00"
    },
    {
        "_id": "5769714df82f456e8000004b",
        "city_id": "5769714df82f456e80000011",
        "created_at": "2016-06-21T12:54:37.452-04:00",
        "name": "Huara",
        "region_id": "5769714df82f456e80000002",
        "updated_at": "2016-06-21T12:54:37.452-04:00"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/locations/communes.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar la request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/locations/communes.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro    | Descripción                                           | Ejemplo
--------- | ----------------------------------------------------- | -------
`city_id` | Busca comunas que pertenezcan a una ciudad específica | https://www.centry.cl/conexion/v1/locations/communes.json?city_id=5769714df82f456e80000011
`name`    | Busca comunas por el nombre el nombre exacto          | https://www.centry.cl/conexion/v1/locations/communes.json?name=Pica

## Obtener un país específico

Este endpoint entrega una comuna específica.

```shell
curl "https://www.centry.cl/conexion/v1/locations/communes/<commune_id>.json"/
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
    <h6> https://www.centry.cl/conexion/v1/locations/communes/&lt;commune_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | -----------
`commune_id` | El identificador de la comuna a recuperar
