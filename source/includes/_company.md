# Companies

## Parámetros

Atributo | Tipo  | Descripción
-------- | ----- | -----------
`_id` | string | Identificador de la empresa
`_keywords` |
`address` | string | Dirección de la empresa
`bio` | string | Biografía de la empresa
`created_at` | date-time | Fecha de creación
`logo_content_type` | string |
`logo_file_name` | string | Nombre del archivo del logo
`logo_file_size` | string | Tamaño del archivo del logo
`logo_fingerprint` | string |
`logo_updated_at` | date-time | Fecha de actualización del logo
`main_warehouse_id` | string |
`name` | string | Nombre de la empresa
`sector` | string | Sector de la empresa
`social_facebook` | string | Página social de Facebook de la empresa
`social_instagram` | string | Página social de Instagram de la empresa
`social_linkedin` | string | Página social de LinkedIn de la empresa
`social_pinterest` | string | Página social de Pinterest de la empresa
`social_twitter` | string | Página social de Twitter de la empresa
`updated_at` | date-time | Fecha de actualización
`url` | string | Página de la empresa
`users_count` | integer |

## Obtener información de la empresa

Este endpoint entrega los detalles de la empresa

```shell
curl -X GET https://www.centry.cl/conexion/v1/company_info.json \
  -H 'Authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
    "_id": "5c2d1ae68f26c638ca60dc02",
    "_keywords": [],
    "address": "Dirección",
    "bio": "Ecommerce",
    "created_at": "2019-01-02T17:11:18.687-03:00",
    "logo_content_type": null,
    "logo_file_name": null,
    "logo_file_size": null,
    "logo_fingerprint": null,
    "logo_updated_at": null,
    "main_warehouse_id": "5c2d1ae68f26c638ca60dc03",
    "name": "Empresa Normie",
    "sector": null,
    "social_facebook": "fb.com/empresa",
    "social_instagram": "ig.com/empresa",
    "social_linkedin": "lkin.com/empresa",
    "social_pinterest": "ptrst.com/empresa",
    "social_twitter": "tw.com/empresa",
    "updated_at": "2019-01-02T17:11:18.709-03:00",
    "url": "www.empresa_genérica_1.cl",
    "users_count": 4
}
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/company_info.json </h6>
  </div>
</div>
