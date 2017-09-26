# Categories

## Parámetros

| Atributo                 | Tipo   | Descripción                                   |
| ------------------------ | ------ | --------------------------------------------- |
| `_id`                    | string | Identificador de la categoría                 |
| `name`                   | string | Nombre de la categoría en Centry              |
| `dafiti`                 | string | Identificador de categoría en Dafiti          |
| `dafiti_name_in_product` | string | Nombre de la categoría en Dafiti              |
| `linio`                  | string | Identificador de categoría en Linio           |
| `linio_name_in_product`  | string | Nombre de la categoría en Linio               |
| `mercadolibre`           | string | Identificador de la categoría en mercadoLibre |
| `options`                | string | Opciones de la categoría                      |
| `vestirsebien`           | string | Nombre de la categoría en VestirseBien        |
| `updated_at`             | string | Registro de última actualización              |
| `created_at`             | string | Regristro de creación de la categoría         |

## Todas las Categorias 

Este endpoint entrega todas las categorias de Centry

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
        "dafiti": "107",
        "dafiti_name_in_product": null,
        "linio": "7164",
        "linio_name_in_product": null,
        "mercadolibre": "MLC66190",
        "name": "Accesorios / Accesorios Femeninos / Anteojos",
        "options": null,
        "updated_at": "2016-06-21T16:54:37.823Z",
        "vestirsebien": null
    },
    {
        "_id": "5769714df82f456e809381a5",
        "created_at": "2016-06-21T16:54:37.821Z",
        "dafiti": "606",
        "dafiti_name_in_product": null,
        "linio": "6937",
        "linio_name_in_product": null,
        "mercadolibre": "MLC25840",
        "name": "Accesorios / Accesorios Femeninos / Bijuteria / Anillos",
        "options": null,
        "updated_at": "2016-06-21T16:54:37.821Z",
        "vestirsebien": null
    }
]
```

## Obtener una Categoria específica

Este endpoint entrega una categoria específico.

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
    "dafiti": "606",
    "dafiti_name_in_product": null,
    "linio": "6937",
    "linio_name_in_product": null,
    "mercadolibre": "MLC25840",
    "name": "Accesorios / Accesorios Femeninos / Bijuteria / Anillos",
    "options": null,
    "updated_at": "2016-06-21T16:54:37.821Z",
    "vestirsebien": null
}
```

### Parámetros URL

Parámtetro    | Descripción
------------- | --------------------------------------------
`category_id` | El identificador de la categoría a recuperar
