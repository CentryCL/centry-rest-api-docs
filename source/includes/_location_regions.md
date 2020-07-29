# Regions

## Parámetros

Atributo     | Tipo    | Descripción                                                                            
------------ | ------- | -----------
`_id`        | string  | Identificador de la región <i class="label label-info">sólo lectura</i>
`name`       | string  | Nombre de la región en Centry <i class="label label-info">sólo lectura</i>
`country_id` | string  | Identificador de la región al que pertenece la región <i class="label label-info">sólo lectura</i>
`position`   | integer | Posición de la región dentro del listado perteneciente a una región <i class="label label-info">sólo lectura</i>
`created_at` | string  | Fecha de creación de la región en Centry <i class="label label-info">sólo lectura</i>
`updated_at` | string  | Fecha de la última actualización <i class="label label-info">sólo lectura</i>

## Todas las regiones

Este endpoint entrega todas las regiones de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/locations/regions.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5769714df82f456e80000001",
        "country_id": "5769714df82f456e80000000",
        "created_at": "2016-06-21T12:54:37.370-04:00",
        "name": "Región Metropolitana",
        "position": 1,
        "updated_at": "2016-06-21T12:54:37.370-04:00"
    },
    {
        "_id": "5769714df82f456e8000000e",
        "country_id": "5769714df82f456e80000000",
        "created_at": "2016-06-21T12:54:37.389-04:00",
        "name": "XIV Región: Los Ríos",
        "position": 14,
        "updated_at": "2016-06-21T12:54:37.389-04:00"
    },
    {
        "_id": "5769714df82f456e8000000d",
        "country_id": "5769714df82f456e80000000",
        "created_at": "2016-06-21T12:54:37.388-04:00",
        "name": "XII Región: Magallanes",
        "position": 13,
        "updated_at": "2016-06-21T12:54:37.388-04:00"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/locations/regions.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar la request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/locations/regions.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro       | Descripción                                         | Ejemplo
------------ | --------------------------------------------------- | -------
`country_id` | Busca regiones que pertenezcan a una región específica | https://www.centry.cl/conexion/v1/locations/regions.json?country_id=5769714df82f456e80000000
`name`       | Busca regiones por el nombre el nombre exacto       | https://www.centry.cl/conexion/v1/locations/regions.json?name=Región%20Metropolitana
`position`   | Busca regiones que tengan una posición específica   | https://www.centry.cl/conexion/v1/locations/regions.json?position=3

## Obtener una región específica

Este endpoint entrega una región específica.

```shell
curl "https://www.centry.cl/conexion/v1/locations/regions/<region_id>.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5769714df82f456e80000001",
    "country_id": "5769714df82f456e80000000",
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
    <h6> https://www.centry.cl/conexion/v1/locations/regions/&lt;region_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro   | Descripción
----------- | -----------
`region_id` | El identificador de la región a recuperar
