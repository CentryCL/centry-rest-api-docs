#Doorkeeperapps

## Parámetros

| Atributo       |   Tipo  | Descripción                                                               |
| -------------- | ------- | ------------------------------------------------------------------------- |
| `_id`          | string  | Identificador del Aplicación <i class="label label-info">sólo lectura</i> |
| `callback_url` | string  | Url de retorno                                                            |
| `platform`     | string  | Plataforma de aplicación                                                  |
| `master`       | boolean | Describe si aplicación está actuando o no como maestro                    |
| `app_id`       | string  | Identificador de aplicación asociada                                      |
| `company_id`   | string  | Identificador de empresa <i class="label label-info">sólo lectura</i>     |
| `created_at`   | string  | Registro de creación del Aplicación en Centry                             |
| `updated_at`   | string  | Registro de actualización del Aplicación en Centry                        |

## Crear un Doorkeeper

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/doorkeeper_apps.json </h6>
  </div>
</div>

```shell

curl -X POST https://www.centry.cl/conexion/v1/doorkeeper_apps.json \
 -H "Authorization: Bearer <access_token> "\
    -H "Content-Type: application/json" \
    -d '{  

     "callback_url": "https://www.myurl.cl/callback/",
  "platform": "Prestashop",
  "master": "false"

 }'\
  > createdDoorkeeperApp.json

```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "597a01471d41c81ae7000007",
    "app_id": "59764a2d1d41c846ea00000b",
    "callback_url": "https://www.myurl.cl/callback/",
    "company_id": "597643ab1d41c846ea000001",
    "created_at": "2017-07-27T15:05:43.086Z",
    "master": false,
    "platform": "Prestashop",
    "updated_at": "2017-07-27T15:05:43.086Z"
}
```
