#Users

##Parámetros

Atributo | Tipo  | Descripción
-------- | ----- | -----------
`_id` | string | Identificador del usuario
`address` | string | Dirección del usuario
`address_cont` | string |
`avatar_content_type` | string |
`avatar_file_name` | string | Nombre del archivo avatar
`avatar_file_size` | string | Tamaño del archivo avatar
`avatar_fingerprint` | string |
`avatar_updated_at` | date-time | Fecha de actualización del avatar
`bio` | string | Biografía
`birthday` | string | Fecha de nacimiento
`commune_id` | string |
`company_api_id` | string | Identificador de la API de la empresa
`company_id` | string | Identificador de la empresa
`company_ids` |  |
`created_at` | date-time | Fecha de creación
`email` | string | Email del usuario
`first_name` | string | Primer nombre del usuario
`gender` | string | Género del usuario
`job_title` | string | Título de trabajo
`last_name` | string | Apellido
`phone` | string | Número de celular
`region_id` | string | Identificador de la región
`role` | interger |
`roles_mask` | interger |
`rut` | string | RUT del usuario
`show_wizard` | boolean |
`status` | interger |
`telephone` | string | Número de Teléfono
`updated_at` | date-time | Fecha de actualización
`user_group_id` | string |

##Obtener información del usuario

Este endpoint entrega los detalles del usuario

```shell
curl -X GET https://www.centry.cl/conexion/v1/user_info.json \
  -H 'Authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
    "_id": "5c2d1ae68f26c638ca60dc04",
    "address": "Dirección",
    "address_cont": null,
    "avatar_content_type": null,
    "avatar_file_name": null,
    "avatar_file_size": null,
    "avatar_fingerprint": null,
    "avatar_updated_at": null,
    "bio": "Biografía",
    "birthday": "1/1/1990",
    "commune_id": null,
    "company_api_id": null,
    "company_id": "5c2d1ae68f26c638ca60dc02",
    "company_ids": [],
    "created_at": "2019-01-02T17:11:18.696-03:00",
    "email": "nombre@correo.cl",
    "first_name": "Nombre",
    "gender": "Undefined",
    "job_title": "Trabajo genérico",
    "last_name": "Apellido",
    "phone": "6666666",
    "region_id": null,
    "role": 1,
    "roles_mask": 0,
    "rut": null,
    "show_wizard": false,
    "status": 1,
    "telephone": null,
    "updated_at": "2019-01-02T17:14:03.997-03:00",
    "user_group_id": null
}
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/user_info.json </h6>
  </div>
</div>
