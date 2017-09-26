# Brands

## Parámetros

| Atributo     | Tipo   | Descripción                                                                              |
| ------------ | ------ | ---------------------------------------------------------------------------------------- |
| `_id`        | string | Identificador de la marca <i class="label label-info">sólo lectura</i>                   |
| `name`       | string | Nombre de la marca en Centry <i class="label label-info">sólo lectura</i>                |
| `created_at` | string | Regristro de creación de la marca en Centry <i class="label label-info">sólo lectura</i> |
| `updated_at` | string | Registro de última actualización <i class="label label-info">sólo lectura</i>            |

## Todas las Marcas 

Este endpoint entrega todas las marcas de Centry

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/brands.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/brands.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[

	{
        "_id": "57f63ffe4c266d1dec1edfb6",
        "created_at": "2016-08-28T16:21:37.882Z",
        "name": "Bata",
        "updated_at": "2016-08-28T16:21:37.882Z"
    },
    {
        "_id": "58124d68fd246926928fed3c",
        "created_at": "2016-10-01T19:35:14.734Z",
        "name": "Bobbies",
        "updated_at": "2016-10-01T19:35:14.734Z"
    }
]
```

## Obtener una Categoria específica

Este endpoint entrega una categoria específico.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/brands/&lt;brand_id&gt;.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/brands/<brand_id>.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "58124d68fd246926928fed3c",
    "created_at": "2016-10-01T19:35:14.734Z",
    "name": "Bobbies",
    "updated_at": "2016-10-01T19:35:14.734Z"
}
```

### Parámetros URL

Parámtetro | Descripción
---------- | ----------------------------------------
`brand_id` | El identificador de la marca a recuperar
