# Sizes

## Parámetros

| Atributo     | Tipo   | Descripción                                                                             |
| ------------ | ------ | --------------------------------------------------------------------------------------- |
| `_id`        | string | Identificador del tamaño <i class="label label-info">sólo lectura</i>                   |
| `name`       | string | Nombre de tamaño en Centry <i class="label label-info">sólo lectura</i>                 |
| `created_at` | string | Regristro de creación del tamaño en Centry <i class="label label-info">sólo lectura</i> |
| `updated_at` | string | Registro de última actualización <i class="label label-info">sólo lectura</i>           |

## Todas las Tallas

Este endpoint entrega todas las tallas de Centry

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/sizes.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/sizes.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5851b0c2b2c85e8282262a3e",
        "created_at": "2016-10-01T00:00:00.000Z",
        "name": "Tamaño Único",
        "updated_at": "2016-10-01T00:00:00.000Z"
    },
    {
        "_id": "5851b0c2b2c85e8282262a3f",
        "created_at": "2016-10-01T00:00:00.000Z",
        "name": "XXS",
        "updated_at": "2016-10-01T00:00:00.000Z"
    }
]
```

## Obtener una Talla específica

Este endpoint entrega una talla  específica

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/sizes/&lt;size_id&gt;.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/sizes/<size_id>.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5851b0c2b2c85e8282262a3f",
    "created_at": "2016-10-01T00:00:00.000Z",
    "name": "XXS",
    "updated_at": "2016-10-01T00:00:00.000Z"
}
```

### Parámetros URL

Parámtetro | Descripción
---------- | ----------------------------------------
`size_id`  | El identificador de la talla a recuperar

