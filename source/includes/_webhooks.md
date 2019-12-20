# Webhooks

La API de Centry permite crear, ver, actualizar y eliminar webhooks individualmente.

Los webhooks pueden ser administrados desde la [plataforma web de Centry](https://www.centry.cl/integraciones/webhooks) o usando los endpoints de la API REST.

Todos los webhooks tienen los siguientes datos:

* `topic`: determina cuál evento de recurso gatilla la notificación.

Mientras que, por los siguientes tópicos, contiene la siguiente información:

* `on_product_save` ó `on_product_delete`
  * `product_id`: Identificador del producto involucrado en el evento.
* `on_order_save` ó `on_order_delete`
  * `order_id`: Identificador de la orden involucrada en el evento.
* `on_integration_config_delete` ó `on_integration_config_save`
  * `integration_config_id`: Identificador de la integración involucrada en el evento.

### Topics

El tópico es una combinación entre un recurso (ej. order) y un evento (ej. delete), esto se traduce a un nombre de hook (ej. `on_order_delete`).

Los tópicos base de Centry son:

* Orders: `on_order_save` y `on_order_delete`.
* Products: `on_product_save`, `on_product_delete`.
* Integration Configs: `on_integration_config_delete`, `on_integration_config_save`.

### Entrega e insistencias

La entrega es realizada por Centry inmediatamente después de que ocurre el evento usando él método POST de HTTP.

Centry espera que el receptor de la notificación responda con un código 200 en menos de 15 segundos, de lo contrario volverá a insistir 5 minutos más tarde. Estas insistencias pueden perdurar hasta 48 horas, donde finalmente se desiste de notificar el evento.

El contenido de la notificación está codificado en un JSON e incluye el mínimo de información posible de modo que el receptor tenga consultar a Centry por los datos que necesite.

```json
{
  "topic":"on_product_save",
  "product_id":"59c285f81746bf2096000001"
}
```

### Logging

Las solicitudes de notificaciones y sus respuestas son registradas en un log que contiene los siguientes datos:

* `callback_url`: URL configurada en el webhook al momento de realizar la notificación
* `intent`: Número correlativo al numero de intento partiendo siempre desde el 1 y pudiendo terminar en el 576
* `response`: El contenido de la respuesta. Se guarda cómo como referencia porque no se usa para nada.
* `accepted`: Un booblean que indica si la notificación fue recibida correctamente o no.
* `topic`: El tópico involucrado en la notificación.
* `data`: El contenido completo que fue enviado en la notificación.

### Interfáz visual

La administración de los webhooks así como el sus registros del log pueden ser accedidos directamente desde la [plataforma web de Centry](https://www.centry.cl/integraciones/webhooks).

## Parámetros

| Atributo                       | Tipo    | Descripción                                                                                         |
| ------------------------------ | ------- | --------------------------------------------------------------------------------------------------- |
| `_id`                          | string  | Identificador del webhook <i class="label label-info">sólo lectura</i>                              |
| `callback_url`                 | string  | URL a la cual se le enviarán las notificaciones                                                     |
| `on_product_save`              | boolean | Flag que indica si se requiere recibir notificaciones del tipo "actualización de producto"          |
| `on_product_delete`            | boolean | Flag que indica si se requiere recibir notificaciones del tipo "eliminación de producto"            |
| `on_order_save`                | boolean | Flag que indica si se requiere recibir notificaciones del tipo "actualización de pedido"            |
| `on_order_delete`              | boolean | Flag que indica si se requiere recibir notificaciones del tipo "eliminación de pedido"              |
| `on_integration_config_save`   | boolean | Flag que indica si se requiere recibir notificaciones del tipo "actualización de integración"       |
| `on_integration_config_delete` | boolean | Flag que indica si se requiere recibir notificaciones del tipo "eliminación de integración"         |
| `company_id`                   | string  | Identificador de empresa <i class="label label-info">sólo lectura</i>                               |
| `created_at`                   | string  | Fecha de creación del webhook en Centry <i class="label label-info">sólo lectura</i>                |
| `updated_at`                   | string  | Fecha de la última modificación del webhook en Centry  <i class="label label-info">sólo lectura</i> |

## Listar los webhooks de la cuenta

Este endpoint entrega todos los webhooks registrados en la cuenta.

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
        "on_integration_config_delete": true,
        "on_integration_config_save": false,
        "updated_at": "2017-09-22T11:10:18.174-03:00"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede precisar la request agregando parámetros a la URL de la forma https://www.centry.cl/conexion/v1/webhooks.json?&lt;filter&gt;=&lt;valor&gt; como se muestra en el capítulo **Filters** al final de la documentación. Además, de ser necesario algunos filtros pueden ser concatenados de la forma https://www.centry.cl/conexion/v1/webhooks.json?&lt;filter&gt;=&lt;valor&gt;&&lt;filter&gt;=&lt;valor&gt;&...

## Obtener un webhook específico

Este endpoint entrega un webhook específico.


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
    "on_integration_config_delete": true,
    "on_integration_config_save": false,
    "updated_at": "2017-09-22T11:10:18.174-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/&lt;webhook_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | ----------------------------------------
`webhook_id` | El identificador del webhook a recuperar

## Crear un webhook

Este endpoint permite crear webhook nuevo.


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
    "on_integration_config_delete": true,
    "on_integration_config_save": false,
    "updated_at": "2017-09-25T19:37:33.016-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks.json </h6>
  </div>
</div>

## Actualizar un webhook

Este endpoint permite modificar un webhook específico.


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
    "on_integration_config_delete": true,
    "on_integration_config_save": false,
    "updated_at": "2017-09-25T19:41:16.604-03:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/&lt;webhook_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | -----------------------------------------
`webhook_id` | El identificador del webhook a actualizar

## Eliminar un webhook

Este endpoint elimina permanentemente un webhook específico.

```shell
curl -X DELETE \
  https://www.centry.cl/conexion/v1/webhooks/59c9852d1746bf1d93000001.json \
  -H 'authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/&lt;webhook_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro    | Descripción
------------ | ---------------------------------------
`webhook_id` | El identificador del webhook a eliminar
