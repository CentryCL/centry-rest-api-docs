# Webhooks

## Parámetros

| Atributo            | Tipo    | Descripción                                                                                |
| ------------------- | ------- | ------------------------------------------------------------------------------------------ |
| `_id`               | string  | Identificador del webhook                                                                  |
| `callback_url`      | string  | URL a la cual se le enviarán las notificaciones                                            |
| `on_product_save`   | boolean | Flag que indica si se requiere recibir notificaciones del tipo "actualización de producto" |
| `on_product_delete` | boolean | Flag que indica si se requiere recibir notificaciones del tipo "eliminación de producto"   |
| `on_order_save`     | boolean | Flag que indica si se requiere recibir notificaciones del tipo "actualización de pedido"   |
| `on_order_delete`   | boolean | Flag que indica si se requiere recibir notificaciones del tipo "eliminación de pedido"     |
| `company_id`        | string  | Identificador de empresa                                                                   |
| `updated_at`        | string  | Fecha de la última modificación del webhook en Centry                                      |
| `created_at`        | string  | Fecha de creación del webhook en Centry                                                    |

## Listar los webhooks de la cuenta

Este endpoint entrega todos los webhooks registrados en la cuenta.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks.json </h6>
  </div>
</div>

```shell
curl -X GET \
  https://www.centry.cl/conexion/v1/webhooks.json \
  -H 'authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "59c427f71746bf5a70000005",
        "callback_url": "http://mi-aplicacion.com/CentryWebhookTest/index.php",
        "company_id": "59355c1b1746bf25a8000000",
        "created_at": "2017-09-21T17:58:31.494-03:00",
        "on_order_delete": true,
        "on_order_save": true,
        "on_product_delete": true,
        "on_product_save": true,
        "updated_at": "2017-09-22T11:10:18.174-03:00"
    }
]
```

## Obtener un webhook específico

Este endpoint entrega un webhook específico.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/&lt;webhook_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X GET \
  https://www.centry.cl/conexion/v1/webhooks/59c427f71746bf5a70000005.json \
  -H 'authorization: Bearer <access_token>' \
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "59c427f71746bf5a70000005",
    "callback_url": "http://mi-aplicacion.com/CentryWebhookTest/index.php",
    "company_id": "59355c1b1746bf25a8000000",
    "created_at": "2017-09-21T17:58:31.494-03:00",
    "on_order_delete": true,
    "on_order_save": true,
    "on_product_delete": true,
    "on_product_save": true,
    "updated_at": "2017-09-22T11:10:18.174-03:00"
}
```

### Parámetros URL

Parámtetro   | Descripción
------------ | ----------------------------------------
`webhook_id` | El identificador del webhook a recuperar

## Crear un webhook

Este endpoint permite crear webhook nuevo.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks.json </h6>
  </div>
</div>

```shell
curl -X POST \
  https://www.centry.cl/conexion/v1/webhooks.json \
  -H 'authorization: Bearer <access_token>' \
  -H 'content-type: application/json' \
  -d '{
    "callback_url": "http://192.168.0.1/CentryWebhookTest/index.phps",
    "on_order_delete": true,
    "on_product_save": false
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "59c9852d1746bf1d93000001",
    "callback_url": "http://192.168.0.1/CentryWebhookTest/index.phps",
    "company_id": "59355c1b1746bf25a8000000",
    "created_at": "2017-09-25T19:37:33.016-03:00",
    "on_order_delete": true,
    "on_order_save": false,
    "on_product_delete": false,
    "on_product_save": false,
    "updated_at": "2017-09-25T19:37:33.016-03:00"
}
```

## Actualizar un webhook

Este endpoint permite modificar un webhook específico.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/&lt;webhook_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X PUT \
  https://www.centry.cl/conexion/v1/webhooks/59c9852d1746bf1d93000001.json \
  -H 'authorization: Bearer <access_token>' \
  -H 'content-type: application/json' \
  -d '{
    "callback_url": "http://localhost/CentryWebhookTest/index.phps",
    "on_product_save": true
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "59c9852d1746bf1d93000001",
    "callback_url": "http://localhost/CentryWebhookTest/index.phps",
    "company_id": "59355c1b1746bf25a8000000",
    "created_at": "2017-09-25T19:37:33.016-03:00",
    "on_order_delete": true,
    "on_order_save": false,
    "on_product_delete": false,
    "on_product_save": true,
    "updated_at": "2017-09-25T19:41:16.604-03:00"
}
```

### Parámetros URL

Parámtetro  | Descripción
----------- | -----------------------------------------
`webhook_id`| El identificador del webhook a actualizar

## Eliminar un webhook

Este endpoint elimina permanentemente un webhook específico.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/webhook/&lt;webhook_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X DELETE \
  https://www.centry.cl/conexion/v1/webhooks/59c9852d1746bf1d93000001.json \
  -H 'authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### Parámetros URL

Parámtetro   | Descripción
------------ | ---------------------------------------
`webhook_id` | El identificador del webhook a eliminar
