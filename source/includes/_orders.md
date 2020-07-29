# Orders

## Parámetros

| Atributo             | Tipo      | Descripción                                                                                                                                   |
| -------------------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `_id`                | string    | Identificador de orden  <i class="label label-info">sólo lectura</i>                                                                          |
| `_status`            | string    | Estado de la orden. Las opciones son `pending`, `shipped`, `received`, `cancelled`, `cancelled_before_shipping` o `cancelled_after_shipping`. |
| `status_origin`      | string    | Etiqueta con el estado del pedido según la plataforma de origen.                                                                              |
| `address_billing`    | object    | Dirección de facturación. Ver [Formulario de direcciones](#formulario-de-direcciones)                                                             |
| `address_shipping`   | object    | Dirección de despacho. Ver [Formulario de direcciones](#formulario-de-direcciones)                                                             |
| `buyer_dni`          | string    | Número de identificación nacional del cliente (ej. en Chile es el RUN)                                                                        |
| `buyer_email`        | string    | Email de Cliente                                                                                                                              |
| `buyer_first_name`   | string    | Nombre de Cliente                                                                                                                             |
| `buyer_last_name`    | string    | Apellido de Cliente                                                                                                                           |
| `buyer_phone`        | string    | Número de teléfono (preferentemente fijo)                                                                                                     |
| `buyer_mobilephone`  | string    | Número de teléfono (preferentemente móvil)                                                                                                    |
| `buyer_birthdate`    | string    | Fecha de nacimiento del cliente.                                                                                                              |
| `_buyer_gender`      | string    | Género del comprador. Las opciones son `undefined`, `male`, `female` u `other.                                                                |
| `_payment_mode`      | string    | Tipo de pago empleado por el comprador. Las opciones son `undefined`, `cash`, `credit_card`, `debit_card` o `transfer`.                       |
| `items`              | array     | Lista de ítems a comprar. Ver [Atributos de los ítems](#atributos-de-los-items)                                                               |
| `origin`             | string    | Origen de donde fue importada la orden                                                                                                        |
| `original_data`      | string    | Es un JSON codificado como string con toda la información tal cual como viene en la plataforma de origen                                      |
| `id_origin`          | string    | Identificador del pedido en la plataforma de Origen                                                                                           |
| `number_origin`      | string    | Número del pedido con el que se maneja la orden en la plataforma de origen                                                                    |
| `id_pack`            | string    | Identificador de paquete asociado al pedido                                                                                                   |
| `url_origin`         | string    | URL desde la cual puede ser accedida la orden en la plataforma de origen                                                                      |
| `total_amount`       | float     | Monto total de los productos comprados                                                                                                        |
| `shipping_amount`    | float     | Costo del despacho del pedido                                                                                                                 |
| `discount_amount`    | float     | Suma total de los descuentos aplicados a los productos del pedido                                                                             |
| `paid_amount` [^1]   | float     | Monto total pagado por el cliente. En un caso ideal es igual a `total_amount + shipping_amount - discount_amount`                             |
| `date_for_delivery`  | date-time | Fecha estimada en la que se espera despachar el pedido                                                                                        |
| `date_for_reception` | date-time | Fecha estimada en la que se espera que el cliente reciba el pedido                                                                            |
| `received_date`      | date-time | Fecha en el que el cliente recibe la orden                                                                                                    |
| `shipped_date`       | date-time | Fecha en el que se despacha la orden                                                                                                          |
| `cancelled_date`     | date-time | Fecha en que la orden fue anulada                                                                                                             |
| `company_id`         | string    | Identificador de la empresa <i class="label label-info">sólo lectura</i>                                                                      |
| `created_at`         | date-time | Fecha de creación de la orden en Centry <i class="label label-info">sólo lectura</i>                                                          |
| `updated_at`         | date-time | Fecha de la ultima actualización a la orden en Centry <i class="label label-info">sólo lectura</i>                                            |
| `created_at_origin`  | date-time | Fecha de creación de la orden en la plataforma de origen <i class="label label-info">sólo lectura</i>                                         |
| `updated_at_origin`  | date-time | Fecha de la ultima actualización a la orden en la plataforma de origen <i class="label label-info">sólo lectura</i>                           |

[^1]: Si el atributo `paid_amount` tiene un valor, quiere decir que el pedido está pagado total o parcialmente.

### Formulario de direcciones

#### Estos datos pueden variar y son consistentes para los parámetros address_billing y address_shipping

Este recurso almacena tanto información de una dirección como de una persona de contacto asociada a esta locación.

| Atributo     | Tipo      | Descripción                                                                         |
| ------------ | --------- | ----------------------------------------------------------------------------------- |
| `_id`        | string    | Identificador de formulario <i class="label label-info">sólo lectura</i>            |
| `email`      | string    | Email de la persona de contacto                                                     |
| `first_name` | string    | Nombre(s) de la persona de contacto                                                 |
| `last_name`  | string    | Apellido(s) de la persona de contacto                                               |
| `phone1`     | string    | Numero telefónico principal                                                         |
| `phone2`     | string    | Número telefónico alternativo                                                       |
| `line1`      | string    | Dirección principal. Ej: "Aurelio González 3838"                                    |
| `line2`      | string    | Complemento de la línea 1. Ej: "Oficina 02"                                         |
| `zip_code`   | string    | Código postal. Ej: "7630354"                                                        |  
| `county`     | string    | Nombre de la comuna. Ej "Vitacura"                                                  |
| `city`       | string    | Nombre de la ciudad. Ej "Santiago"                                                  |
| `state`      | string    | Estado o región. Ej: "Región Metropolitana"                                         |
| `country`    | string    | Nombre del país. Ej: "Chile"                                                        |  
| `created_at` | string    | Fecha de la realización del formulario <i class="label label-info">sólo lectura</i> |  
| `updated_at` | date-time | Fecha de actualización de formulario <i class="label label-info">sólo lectura</i>   |

### Atributos de los ítems

| Atributo             |   Tipo    | Descripción                                                                     |
| -------------------- | --------- | ------------------------------------------------------------------------------- |
| `_id`                | string    | Identificador de conjunto de ítems <i class="label label-info">sólo lectura</i> |
| `id_origin`          | string    | Identificador de la línea en la plataforma de origen                            |
| `sku`                | string    | SKU del producto involucrado según lo informado por la plataforma de origen     |
| `name`               | string    | Nombre del producto                                                             |
| `unit_price`         | float     | Precio unitario                                                                 |
| `paid_price`         | float     | Monto pagado                                                                    |
| `tax_amount`         | float     | Cantidad de impuesto                                                            |
| `discount_amount`    | float     | Descuentos aplicado al producto                                                 |
| `shipping_amount`    | float     | Costo del despacho                                                              |
| `currency`           | string    | Tipo de moneda en el que se paga                                                |
| `quantity`           | integer   | Número de unidades solicitadas originalmente                                    |
| `quantity_restocked` | integer   | Unidades repuestas                                                              |
| `shipment_provider`  | string    | Empresa encargada del despacho                                                  |
| `shipping_type`      | string    | Tipo de despacho                                                                |
| `tracking_code`      | string    | Código de seguimiento                                                           |
| `tracking_code_pre`  | string    |                                                                                 |
| `tracking_url`       | string    | URL con información del seguimiento del despacho                                |
| `variant_id`         | integer   | Identificador de variante registrada en Centry                                  |
| `created_at`         | date-time | Fecha de creación de este elemento <i class="label label-info">sólo lectura</i> |
| `updated_at`         | date-time | Fecha de actualización <i class="label label-info">sólo lectura</i>             |

## Todas las órdenes de la cuenta

Este endpoint entrega todas las ordenes de la cuenta.

```shell
curl "https://www.centry.cl/conexion/v1/orders.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {
        "_buyer_gender": "undefined",
        "_id": "57bf36a08b5bc7a24920c8b4",
        "_payment_mode": "undefined",
        "_status": "received",
        "address_billing": {
            "_id": "57bf3610915bc7a23920c8ba",
            "city": "",
            "country": "Chile",
            "county": null,
            "created_at": null,
            "email": null,
            "first_name": "Cliente genérico",
            "last_name": null,
            "line1": "",
            "line2": "",
            "phone1": "",
            "phone2": "",
            "state": "",
            "updated_at": null,
            "zip_code": ""
        },
        "address_shipping": {
            "_id": "57bf3610925bc7a23920c8ba",
            "city": "",
            "country": "Chile",
            "county": null,
            "created_at": null,
            "email": null,
            "first_name": null,
            "last_name": null,
            "line1": "",
            "line2": null,
            "phone1": null,
            "phone2": null,
            "state": "",
            "updated_at": null,
            "zip_code": ""
        },
        "buyer_birthdate": null,
        "buyer_dni": null,
        "buyer_email": null,
        "buyer_first_name": "Cliente genérico",
        "buyer_last_name": null,
        "buyer_mobilephone": null,
        "buyer_phone": null,
        "cancelled_date": null,
        "company_id": "501f5000000588f5b5ef82f4",
        "created_at": "2018-10-17T17:57:29.888-03:00",
        "date_for_delivery": null,
        "date_for_reception": null,
        "discount_amount": null,
        "id_origin": "4234",
        "id_woocommerce": null,
        "integrations": {},
        "items": [
            {
                "_id": "5bc7a23920c8ba57bf36108c",
                "created_at": null,
                "currency": null,
                "discount_amount": null,
                "id_origin": null,
                "name": "Carcasa para celular Tamaño Único, Multicolor",
                "paid_price": null,
                "quantity": 1,
                "quantity_restocked": null,
                "shipment_provider": null,
                "shipping_amount": null,
                "shipping_type": null,
                "sku": null,
                "tax_amount": null,
                "tracking_code": null,
                "tracking_code_pre": null,
                "tracking_url": null,
                "unit_price": 2900,
                "updated_at": null,
                "variant_id": "5942afc1f82f4566c60000a2"
            }
        ],
        "number_origin": null,
        "origin": "relBase",
        "original_data": null,
        "paid_amount": 2900,
        "received_date": null,
        "shipment_label": null,
        "shipped_date": null,
        "shipping_amount": 0,
        "status_origin": null,
        "tax_amount": null,
        "total_amount": 2900,
        "updated_at": "2018-10-17T17:57:29.888-03:00",
        "url_origin": "http://app.relbase.cl/dtes/boletas/10000"
    },
    {
        "_buyer_gender": "undefined",
        "_id": "096ef853335bc7e6df20c8ba",
        "_payment_mode": "undefined",
        "_status": "received",
        "address_billing": {
            "_id": "5017ec39705bcc2fb820c8ba",
            "city": "Vitacura",
            "country": "CL",
            "county": null,
            "created_at": "2018-10-21T04:50:16.456-03:00",
            "email": null,
            "first_name": "John",
            "last_name": "Doe",
            "line1": "Aurelio González",
            "line2": "Of 02",
            "phone1": "+56232716362",
            "phone2": null,
            "state": "REG.METROPOLITANA",
            "updated_at": "2018-10-21T04:50:16.456-03:00",
            "zip_code": null
        },
        "address_shipping": {
            "_id": "5017ec39715bcc2fb820c8ba",
            "city": "Vitacura",
            "country": "CL",
            "county": null,
            "created_at": "2018-10-21T04:50:16.456-03:00",
            "email": null,
            "first_name": "John",
            "last_name": "Doe",
            "line1": "Aurelio González",
            "line2": "Of 02",
            "phone1": "+56232716362",
            "phone2": null,
            "state": "REG.METROPOLITANA",
            "updated_at": "2018-10-21T04:50:16.456-03:00",
            "zip_code": null
        },
        "buyer_birthdate": null,
        "buyer_dni": "19",
        "buyer_email": null,
        "buyer_first_name": "John",
        "buyer_last_name": "Doe",
        "buyer_mobilephone": null,
        "buyer_phone": null,
        "cancelled_date": null,
        "company_id": "588f5b5ef82f4501f5000000",
        "created_at": "2018-10-17T22:50:23.515-03:00",
        "date_for_delivery": null,
        "date_for_reception": null,
        "discount_amount": 0,
        "id_origin": "47304624-J",
        "integrations": {},
        "items": [
            {
                "_id": "5017ec398c5bcc2fb920c8ba",
                "created_at": "2018-10-21T04:50:17.862-03:00",
                "currency": null,
                "discount_amount": null,
                "id_origin": "80417610",
                "name": "POSA VASOS | Talla Unica | Negro  PVS1001",
                "paid_price": 16860,
                "quantity": 3,
                "quantity_restocked": null,
                "shipment_provider": "DHL e-Commerce",
                "shipping_amount": 3990,
                "shipping_type": null,
                "sku": null,
                "tax_amount": null,
                "tracking_code": "5118102013583578",
                "tracking_code_pre": null,
                "tracking_url": null,
                "unit_price": 12870,
                "updated_at": "2018-10-21T04:50:17.862-03:00",
                "variant_id": "5a69de14f82f45596a000224"
            }
        ],
        "number_origin": null,
        "origin": "Ripley",
        "original_data": "{\"acceptance_decision_date\":\"2018-10-17T19:49:45Z\",\"can_cancel\":false,\"channel\":null,\"commercial_id\":\"...\"}",
        "paid_amount": 16860,
        "received_date": null,
        "shipment_label": null,
        "shipped_date": null,
        "shipping_amount": 3990,
        "status_origin": "RECEIVED",
        "tax_amount": null,
        "total_amount": 12870,
        "updated_at": "2018-10-19T17:00:27.770-03:00",
        "url_origin": null
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders.json </h6>
  </div>
</div>

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede precisar la request agregando parámetros a la URL de la forma https://www.centry.cl/conexion/v1/orders.json?&lt;filter&gt;=&lt;valor&gt; como se muestra en el capítulo **Filters** al final de la documentación. Además, de ser necesario algunos filtros pueden ser concatenados de la forma https://www.centry.cl/conexion/v1/orders.json?&lt;filter&gt;=&lt;valor&gt;&&lt;filter&gt;=&lt;valor&gt;&...

### Filtros especiales

Solo pueden ser ocupados para este endpoint en particular.

Filtro          | Descripción                                     | Ejemplo
--------------- | ----------------------------------------------- | -------
`status`        | Corresponde al estado del pedido, sus posibles valores pueden ser: `pending`, `shipped`, `received`, `cancelled`, `cancelled_before_shipping`, `cancelled_after_shipping`  | https://www.centry.cl/conexion/v1/orders.json?status=received
`origin`        | Corresponde al origen del pedido, por ejemplo: Ripley, MercadoLibre, Dafiti, etc. | https://www.centry.cl/conexion/v1/orders.json?origin=Ripley
`expand`        | Sirve para incluir la información completa de las variantes en los items del pedido | https://www.centry.cl/conexion/v1/orders.json?status=pending&expand
`id_origin`     | Filtra los resultados en base al identificador de origen | https://www.centry.cl/conexion/v1/orders.json?id_origin=100001
`number_origin` | Filtra los resultados en base el número del pedido. Es importante tener presente de que no todas las integraciones entregan este dato | https://www.centry.cl/conexion/v1/orders.json?number_origin=5840001

## Obtener una orden específica

Este endpoint entrega una orden específica.

```shell
curl "https://www.centry.cl/conexion/v1/orders/096ef853335bc7e6df20c8ba.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_buyer_gender": "undefined",
    "_id": "096ef853335bc7e6df20c8ba",
    "_payment_mode": "undefined",
    "_status": "received",
    "address_billing": {
        "_id": "5017ec39705bcc2fb820c8ba",
        "city": "Vitacura",
        "country": "CL",
        "county": null,
        "created_at": "2018-10-21T04:50:16.456-03:00",
        "email": null,
        "first_name": "John",
        "last_name": "Doe",
        "line1": "Aurelio González",
        "line2": "Of 02",
        "phone1": "+56232716362",
        "phone2": null,
        "state": "REG.METROPOLITANA",
        "updated_at": "2018-10-21T04:50:16.456-03:00",
        "zip_code": null
    },
    "address_shipping": {
        "_id": "5017ec39715bcc2fb820c8ba",
        "city": "Vitacura",
        "country": "CL",
        "county": null,
        "created_at": "2018-10-21T04:50:16.456-03:00",
        "email": null,
        "first_name": "John",
        "last_name": "Doe",
        "line1": "Aurelio González",
        "line2": "Of 02",
        "phone1": "+56232716362",
        "phone2": null,
        "state": "REG.METROPOLITANA",
        "updated_at": "2018-10-21T04:50:16.456-03:00",
        "zip_code": null
    },
    "buyer_birthdate": null,
    "buyer_dni": "19",
    "buyer_email": null,
    "buyer_first_name": "John",
    "buyer_last_name": "Doe",
    "buyer_mobilephone": null,
    "buyer_phone": null,
    "cancelled_date": null,
    "company_id": "588f5b5ef82f4501f5000000",
    "created_at": "2018-10-17T22:50:23.515-03:00",
    "date_for_delivery": null,
    "date_for_reception": null,
    "discount_amount": 0,
    "id_origin": "47304624-J",
    "integrations": {},
    "items": [
        {
            "_id": "5017ec398c5bcc2fb920c8ba",
            "created_at": "2018-10-21T04:50:17.862-03:00",
            "currency": null,
            "discount_amount": null,
            "id_origin": "80417610",
            "name": "POSA VASOS | Talla Unica | Negro  PVS1001",
            "paid_price": 16860,
            "quantity": 3,
            "quantity_restocked": null,
            "shipment_provider": "DHL e-Commerce",
            "shipping_amount": 3990,
            "shipping_type": null,
            "sku": null,
            "tax_amount": null,
            "tracking_code": "5118102013583578",
            "tracking_code_pre": null,
            "tracking_url": null,
            "unit_price": 12870,
            "updated_at": "2018-10-21T04:50:17.862-03:00",
            "variant_id": "5a69de14f82f45596a000224"
        }
    ],
    "number_origin": null,
    "origin": "Ripley",
    "original_data": "{\"acceptance_decision_date\":\"2018-10-17T19:49:45Z\",\"can_cancel\":false,\"channel\":null,\"commercial_id\":\"...\"}",
    "paid_amount": 16860,
    "received_date": null,
    "shipment_label": null,
    "shipped_date": null,
    "shipping_amount": 3990,
    "status_origin": "RECEIVED",
    "tax_amount": null,
    "total_amount": 12870,
    "updated_at": "2018-10-19T17:00:27.770-03:00",
    "url_origin": null
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ----------------------------------------
`order_id` | El identificador de la orden a recuperar

## Crear una orden

Este endpoint crea una orden.

```shell
curl -X POST https://www.centry.cl/conexion/v1/orders.json \
 -H "Authorization: Bearer <access_token>"\
    -H "Content-Type: application/json" \
    -d '{  
 "address_billing":{
  "city":"Santiago",
  "country":"Chile",
  "email":"Email@Factura.cl",
  "first_name":"Vía cUrl",
  "last_name":"Apellido Factura",
  "line1":"Dirección Cliente",
  "line2":"Direccion alternativa",
  "phone1":"89668063",
  "phone2":"75927583",
  "state":"EstadoFactura",
  "zip_code":"2948513"
  },
 "address_shipping":{
  "city":"Santiago",
  "country":"Chile",
  "email":"Email@Envío.cl",
  "first_name":"Nombre Envio",
  "last_name":"Apellido Envío",
  "line1":"Dirección Cliente",
  "line2":"Dirección alternativa",
  "phone1":"89668063",
  "phone2":"89765482",
  "state":"EstadoFactura",
  "zip_code":"2948513"
  },
 "total_amount": 6950493,
 "buyer_email":"Email@Cliente.cl",
 "buyer_first_name":"Vía cURl",
 "buyer_last_name":"Apellido Cliente",
 "origin":"cUrl app",
 "items":
  [{
   "name":"L, Café",
   "quantity":5,
   "unit_price":19999.0,
   "variant_id":"597906591d41c80b2e000010"
   }]
 }'
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders.json </h6>
  </div>
</div>

## Eliminar una orden

Este endpoint elimina una orden.

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/orders/096ef853335bc7e6df20c8ba.json \
    -H "Authorization: Bearer <access_token>" > deleteResponse.json
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
true
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ---------------------------------------
`order_id` | El identificador de la Orden a eliminar

## Obtener etiquetas de despacho

Este endpoint recibe identificadores de pedidos y retorna un listado de documentos codificados en Base64.

```shell
curl "https://www.centry.cl/conexion/v1/orders/shipping_labels.json?ids[]=096ef853335bc7e6df20c8ba"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "orders": [
            {
                "_id": "5ccc461a1a61bb184c11d18a",
                "origin": "MercadoLibre",
                "id_origin": "2032305225",
                "extras": {
                    "shipping": {
                        "id": 27895575952
                    }
                }
            }
        ],
        "files": [
            {
                "content_type": "application/pdf",
                "filename": "labels_and_manifest.pdf",
                "content_base_64": "..."
            }
        ]
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/shipping_labels.json?ids[]=&lt;order_id_1&gt;&ids[]=&lt;order_id_2&gt;&... </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ----------------------------------------
`ids`      | Es un listado de identificadores de pedidos de Centry

La respuesta entrega un arreglo de objetos estructurados de la siguiente manera:

Llave  | Descripción
---------- | ----------------------------------------
`orders`      | Un arreglo de objetos con información de los los pedidos involucrados en los documentos adjuntos, esta información es: `_id`: identificador del pedido en centry, `origin`: Nombre de la plataforma de desde donde se origió el pedido, `id_origin`: identificador del pedido en la plataforma de origen, `extras` información relevante que pudiera servir para cada integración. Este último campo vaía de plataforma en plataforma, por ejemplo para mercado libre entrega un objeto `shipping` con el identificador del despacho, mientras que en Dafiti o Linio entrega un arreglo llamado `order_item_ids` con los identificadores de las líneas del pedido.
`files` | un listado de objetos con los documentos asociados, estos objetos están compuesto de 3 campos: `content_type` el mime type del archivo adjunto, `filename` un nombre de fantasía que describe el documento, `content_base_64` el contenidop del documento codifficado en base 64.
