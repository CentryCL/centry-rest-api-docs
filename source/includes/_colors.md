# Colors

## Parámetros

| Atributo               | Tipo   | Descripción                                        |
| ---------------------- | ------ | -------------------------------------------------- |
| `_id`                  | string | Identificador del color                            |
| `created_at`           | string | Regristro de creación de color en Centry           |
| `dafiti`               | string | Identificador de color equivalente  en Dafiti      |
| `linio`                | string | Identificador de color equivalente en Linio        |
| `mercadolibre`         | string | Identificador de color equivalente en mercadoLibre |
| `mercadolibre_attr_id` | string | Atributo color en mercadoLibre                     |   
| `name`                 | string | Nombre de color en Centry                          |
| `updated_at`           | string | Registro de última actualización                   |
| `vestirsebien`         | string | Nombre de color equivalente en VestirseBien        |

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
        "dafiti": "Morado",
        "linio": "Morado",
        "mercadolibre": "09ed564",
        "mercadolibre_attr_id": "83000",
        "name": "Violeta oscuro",
        "updated_at": "2016-10-01T00:00:00.000Z",
        "vestirsebien": null
    },
    {
        "_id": "588a28c40fb756a249fd0c77",
        "created_at": "2016-10-01T00:00:00.000Z",
        "dafiti": "Verde Petróleo",
        "linio": "Verde",
        "mercadolibre": "dc7f392",
        "mercadolibre_attr_id": "83000",
        "name": "Verde oscuro",
        "updated_at": "2016-10-01T00:00:00.000Z",
        "vestirsebien": null
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
    "dafiti": "Morado",
    "linio": "Morado",
    "mercadolibre": "09ed564",
    "mercadolibre_attr_id": "83000",
    "name": "Violeta oscuro",
    "updated_at": "2016-10-01T00:00:00.000Z",
    "vestirsebien": null
}
```

### Parámetros URL

Parámtetro | Descripción
---------- | ----------------------------------------
`color_id` | El identificador de la orden a recuperar
