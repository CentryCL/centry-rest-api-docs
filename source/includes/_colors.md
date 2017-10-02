# Colors

## Parámetros

| Atributo     | Tipo   | Descripción                                                                           |
| ------------ | ------ | ------------------------------------------------------------------------------------- |
| `_id`        | string | Identificador del color <i class="label label-info">sólo lectura</i>                  |
| `name`       | string | Nombre de color en Centry <i class="label label-info">sólo lectura</i>                |
| `created_at` | string | Registro de creación de color en Centry <i class="label label-info">sólo lectura</i>  |
| `updated_at` | string | Registro de última actualización <i class="label label-info">sólo lectura</i>         |

## Todos los Colores

Este endpoint entrega todos los colores de Centry

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/colors.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/colors.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "588a28c40fb756a249fd0c78",
        "created_at": "2016-10-01T00:00:00.000Z",
        "name": "Violeta oscuro",
        "updated_at": "2016-10-01T00:00:00.000Z"
    },
    {
        "_id": "588a28c40fb756a249fd0c77",
        "created_at": "2016-10-01T00:00:00.000Z",
        "name": "Verde oscuro",
        "updated_at": "2016-10-01T00:00:00.000Z"
    }
]

```

## Obtener una Color específico

Este endpoint entrega un color específico.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/colors/&lt;color_id&gt;.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/colors/<color_id>.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "588a28c40fb756a249fd0c78",
    "created_at": "2016-10-01T00:00:00.000Z",
    "name": "Violeta oscuro",
    "updated_at": "2016-10-01T00:00:00.000Z"
}
```

### Parámetros URL

Parámetro  | Descripción
---------- | --------------------------------------
`color_id` | El identificador del color a recuperar
