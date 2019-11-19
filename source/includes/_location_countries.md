# Countries

## Parámetros

Atributo     | Tipo   | Descripción                                                                            
------------ | ------ | -----------
`_id`        | string | Identificador del país <i class="label label-info">sólo lectura</i>
`name`       | string | Nombre del país en Centry <i class="label label-info">sólo lectura</i>
`iso_code`   | string | Código del país según la norma ISO <i class="label label-info">sólo lectura</i>
`language`   | string | Código que identifica el idioma principal del país <i class="label label-info">sólo lectura</i>
`created_at` | string | Fecha de creación del país en Centry <i class="label label-info">sólo lectura</i>
`updated_at` | string | Fecha de la última actualización <i class="label label-info">sólo lectura</i>

## Todas los paises

Este endpoint entrega todas los países de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/locations/countries.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5769714df82f456e80000000",
        "created_at": "2016-06-21T12:54:37.367-04:00",
        "iso_code": "CL",
        "language": "es",
        "name": "Chile",
        "updated_at": "2016-06-21T12:54:37.367-04:00"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/locations/countries.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede
precisar la request agregando parámetros a la URL de la forma
https://www.centry.cl/conexion/v1/locations/countries.json?&lt;filter&gt;=&lt;valor&gt;
como se muestra en el capítulo [Filters](#filters) al final de la documentación.

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro     | Descripción                                 | Ejemplo
---------- | ------------------------------------------- | -------
`iso_code` | Busca paises por el código iso exacto       | https://www.centry.cl/conexion/v1/locations/countries.json?iso_code=CL
`language` | Busca países por el código de idioma exacto | https://www.centry.cl/conexion/v1/locations/countries.json?language=es
`name`     | Busca países por el nombre el nombre exacto | https://www.centry.cl/conexion/v1/locations/countries.json?name=Chile

## Obtener un país específico

Este endpoint entrega un país específico.

```shell
curl "https://www.centry.cl/conexion/v1/locations/countries/<country_id>.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5769714df82f456e80000000",
    "created_at": "2016-06-21T12:54:37.367-04:00",
    "iso_code": "CL",
    "language": "es",
    "name": "Chile",
    "updated_at": "2016-06-21T12:54:37.367-04:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/locations/countries/&lt;country_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ----------------------------------------
`country_id` | El identificador del país a recuperar
