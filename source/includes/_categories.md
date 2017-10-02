# Categories

## Parámetros

| Atributo     | Tipo   | Descripción                                                                        |
| ------------ | ------ | ---------------------------------------------------------------------------------- |
| `_id`        | string | Identificador de la categoría  <i class="label label-info">sólo lectura</i>        |
| `name`       | string | Nombre de la categoría en Centry <i class="label label-info">sólo lectura</i>      |
| `created_at` | string | Registro de creación de la categoría <i class="label label-info">sólo lectura</i>  |
| `updated_at` | string | Registro de última actualización <i class="label label-info">sólo lectura</i>      |

## Todas las Categorías

Este endpoint entrega todas las categorías de Centry

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/categories.json </h6>
  </div>
</div>

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

## Obtener una Categoría específica

Este endpoint entrega una categoría específico.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/categories/&lt;category_id&gt;.json </h6>
  </div>
</div>

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

### Parámetros URL

Parámetro     | Descripción
------------- | --------------------------------------------
`category_id` | El identificador de la categoría a recuperar
