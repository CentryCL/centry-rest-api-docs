# Categories

## Parámetros

| Atributo     | Tipo   | Descripción                                                                        |
| ------------ | ------ | ---------------------------------------------------------------------------------- |
| `_id`        | string | Identificador de la categoría  <i class="label label-info">sólo lectura</i>        |
| `name`       | string | Nombre de la categoría en Centry <i class="label label-info">sólo lectura</i>      |
| `created_at` | string | Registro de creación de la categoría <i class="label label-info">sólo lectura</i>  |
| `updated_at` | string | Registro de última actualización <i class="label label-info">sólo lectura</i>      |

## Todas las categorías

Este endpoint entrega todas las categorías de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/categories.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5769714df82f456e809571a7",
        "created_at": "2016-06-21T16:54:37.823Z",
        "name": "Accesorios / Accesorios Femeninos / Anteojos",
        "updated_at": "2016-06-21T16:54:37.823Z"
    },
    {
        "_id": "5769714df82f456e809381a5",
        "created_at": "2016-06-21T16:54:37.821Z",
        "name": "Accesorios / Accesorios Femeninos / Bijuteria / Anillos",
        "updated_at": "2016-06-21T16:54:37.821Z"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/categories.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede precisar la request agregando parámetros a la URL de la forma https://www.centry.cl/conexion/v1/categories.json?&lt;filter&gt;=&lt;valor&gt; como se muestra en el capítulo **Filters** al final de la documentación. Además, de ser necesario algunos filtros pueden ser concatenados de la forma https://www.centry.cl/conexion/v1/categories.json?&lt;filter&gt;=&lt;valor&gt;&&lt;filter&gt;=&lt;valor&gt;&...

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro       | Descripción                                     | Ejemplo
------------ | ----------------------------------------------- | -------
`filtered_used_by_company`        | Muestra sólo las categorías usadas actualmente por la empresa    | https://www.centry.cl/conexion/v1/categories.json?created_at=2017-09-13T21:00:00.000-03:00&filtered_used_by_company

## Obtener una categoría específica

Este endpoint entrega una categoría específica.

```shell
curl "https://www.centry.cl/conexion/v1/categories/<category_id>.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5769714df82f456e809381a5",
    "created_at": "2016-06-21T16:54:37.821Z",
    "name": "Accesorios / Accesorios Femeninos / Bijuteria / Anillos",
    "updated_at": "2016-06-21T16:54:37.821Z"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/categories/&lt;category_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro     | Descripción
------------- | --------------------------------------------
`category_id` | El identificador de la categoría a recuperar
