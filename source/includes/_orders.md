# Orders

## Parámetros

| Atributo             | Tipo      | Descripción                                                                                                                                   |
| -------------------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `_id`                | string    | Identificador de orden  <i class="label label-info">sólo lectura</i>                                                                          |
| `_status`            | string    | Estado de la orden. Las opciones son `pending`, `shipped`, `received`, `cancelled`, `cancelled_before_shipping` o `cancelled_after_shipping`. |
| `status_origin`      | string    | Etiqueta con el estado del pedido según la plataforma de origen.                                                                              |
| `address_billing`    | object    | Dirección de facturación. Ver [Formulario de direcciones](#formulario-de-direcciones)                                                         |
| `address_shipping`   | object    | Dirección de despacho. Ver [Formulario de direcciones](#formulario-de-direcciones)                                                            |
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
| `billable`           | boolean   | Indica si el pedido deber ser facturado por el seller (`true`) o no (`false`).                                                                |
| `invoice_required`   | boolean   | Indica si el pedido requiere una factura (`true`) o no (`false`).                                                                             |
| `modify_stock`       | boolean   | Indica si el registro del pedido modificó el stock (`true`) o no (`false`).                                                                   |
| `own_shipment`       | boolean   | Indica si el pedido debe ser despachado con una flota propia del seller (`true`) o no (`false`).                                              |
| `fraud_risk_detected`| boolean   | Indica el el marketplace ha detectado que podría ser un fraude (`true`) o no (`false`).                                                       |
| `priority_shipping`  | boolean   | Indica si el pedido debe ser despachado con prioridad (`true`) o no (`false`).                                                                |
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
 -H "Authorization: Bearer  <access_token>"
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
 -H "Authorization: Bearer  <access_token>"
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
  "line2":"Dirección alternativa",
  "phone1":"89668063",
  "phone2":"75927583",
  "state":"EstadoFactura",
  "zip_code":"2948513"
  },
 "address_shipping":{
  "city":"Santiago",
  "country":"Chile",
  "email":"Email@Envío.cl",
  "first_name":"Nombre Envío",
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
 -H "Authorization: Bearer  <access_token>"
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
                "content_base_64": "...",
                "confirmation_box_id": "66290d46606d7237e304635d"
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
`orders`      | Un arreglo de objetos con información de los los pedidos involucrados en los documentos adjuntos, esta información es: `_id`: identificador del pedido en centry, `origin`: Nombre de la plataforma de desde donde se originó el pedido, `id_origin`: identificador del pedido en la plataforma de origen, `extras` información relevante que pudiera servir para cada integración. Este último campo varía de plataforma en plataforma, por ejemplo para mercado libre entrega un objeto `shipping` con el identificador del despacho, mientras que en Dafiti o Linio entrega un arreglo llamado `order_item_ids` con los identificadores de las líneas del pedido.
`files` | un listado de objetos con los documentos asociados, estos objetos están compuesto de 3 campos: `content_type` el mime type del archivo adjunto, `filename` un nombre de fantasía que describe el documento, `content_base_64` el contenido del documento codificado en base 64, `confirmation_box_id` el ID del confirmation_box (aparece cuando el pedido se confirma por partes).

## Confirmación de un pedido pendiente

Este endpoint permite confirmar que se entregará un pedido pendiente para aquellas integraciones que así lo admiten. Estas integraciones son:

* Falabella Marketplace
* Mercado Libre: división de paquetes

```shell
curl "https://www.centry.cl/conexion/v1/orders/5eece46148f039166bf5ffad/order_status/confirmations.json" \
     -H "Authorization: Bearer  <access_token>" \
     -d '{
    "reason_id": "627d45751a61bb7eba979e95", 
    "boxes": [
        {
            "dimensions": {
                "length": 10.0,
                "width": 11.0,
                "height": 12.0,
                "weight": 1.5
            },
            "items": {
                "sku_ejemplo_1": 1,
                "sku_ejemplo_2": 1
            },
            "package_id": "10000"
        }
    ]
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "5eece7c248f0390feef121c4",
  "boxes": [
    {
      "_id": "5f119e7948f03956a204f3bf",
      "skus": [
        {
          "_id": "5f119e8f48f03956a204f3c0",
          "sku": "sku_ejemplo_1",
          "quantity": 1
        },
        {
          "_id": "5f119e8f48f03956a204f3c1",
          "sku": "sku_ejemplo_2",
          "quantity": 1
        }
      ],
      "l": 10.0,
      "w": 11.0,
      "h": 12.0,
      "e": 1.5,
      "pid": "10000",
      "reason_id": "5e45b03c48f0392442dbd1a6",
    }
  ],
  "order_id": "5eece46148f039166bf5ffad",
  "success_response": {
    any success response
  },
  "failed_attempts": [],
  "created_at": "2020-06-19T08:28:50.880-08:00"
}
```

> Ejemplos de "any success response":

> Para Falabella

```json
{
	"uuid": "e8352482-1acb-4997-9759-cf5f4b3ceb8b",
	"status": "DONE",
	"errors": []
},
```

> Para MercadoLibre

```json
{
	"respose": "empty response"
}
```

> Ejemplos de respuestas de error

> El pedido ya fué confirmado/dividido a través de este endpoint:

```json
{
    "error": "Order already confirmed",
    "confirmation": {
        "_id": "6286a6cc606d72463551d771",
        "boxes": [
            {
                "_id": "6286a6cc606d72463551d772",
                "e": 1.5,
                "h": 12.0,
                "l": 10.0,
                "pid": "10000",
                "skus": [
                    {
                        "_id": "6286a6cc606d72463551d773",
                        "sku": "sku_ejemplo_1",
                        "quantity": 1
                    }
                ],
                "w": 11.0
            },
            {
                "_id": "6286a6cc606d72463551d774",
                "e": 1.5,
                "h": 12.0,
                "l": 10.0,
                "pid": "10001",
                "skus": [
                    {
                        "_id": "6286a6cc606d72463551d775",
                        "sku": "sku_ejemplo_2",
                        "quantity": 2
                    }
                ],
                "w": 11.0
            }
        ],
        "order_id": "6286a41f606d72638813ccf5",
        "reason_id": "62617fda606d72ad5f126268",
        "success_response": {
            "respose": "empty response"
        },
        "failed_attempts": [],
        "created_at": "2022-05-19T12:21:32.869-08:00"
    }
}
```

> Las cajas no contienen el total de los ítemes (existe ítemes que quedaron sin caja, o hay más ítemes en cajas que los contenidos en el pedido)

```json
{
    "boxes": [
        "Las cajas deben incluir exactamente todos los ítemes"
    ]
}
```

> (MercadoLibre) El pedido no puede dividirse, por que proviene ya de una división de un pedido padre.

```json
{
    "_id": "628be852606d7224185748f4",
    "boxes": [
        {
            "_id": "628be852606d7224185748f5",
            "e": null,
            "h": null,
            "l": null,
            "pid": "10000",
            "skus": [
                {
                    "_id": "628be852606d7224185748f6",
                    "sku": "sku_ejemplo_1",
                    "quantity": 1
                }
            ],
            "w": null
        },
        {
            "_id": "628be852606d7224185748f6",
            "e": null,
            "h": null,
            "l": null,
            "pid": "10001",
            "skus": [
                {
                    "_id": "628be852606d7224185748f6",
                    "sku": "sku_ejemplo_2",
                    "quantity": 1
                }
            ],
            "w": null
        }
    ],
    "order_id": "6286a77d606d72e6adb19ec2",
    "reason_id": "62617fda606d72ad5f126268",
    "success_response": null,
    "failed_attempts": [
        {
            "timestamp": "2022-05-23T16:02:28-04:00",
            "response": {
                "error": "Shipment 41385645354 has only one item and can't be splitted"
            }
        }
    ],
    "created_at": "2022-05-23T12:02:26.830-08:00"
}
```


> (MercadoLibre) La división de pedidos debe contener exactamente dos cajas (no es posible utilizar más cajas, por limitación de MercadoLibre)

```json
{
    "_id": "628bec7f606d7224185748f8",
    "boxes": [
        {
            "_id": "628bec7f606d7224185748f9",
            "e": null,
            "h": null,
            "l": null,
            "pid": "10000",
            "skus": [
                {
                    "_id": "628bec7f606d7224185748fa",
                    "sku": "sku_ejemplo_1",
                    "quantity": 1
                }
            ],
            "w": null
        },
        {
            "_id": "628bec7f606d7224185748fb",
            "e": null,
            "h": null,
            "l": null,
            "pid": "10001",
            "skus": [
                {
                    "_id": "628bec7f606d7224185748fc",
                    "sku": "sku_ejemplo_2",
                    "quantity": 2
                }
            ],
            "w": null
        },
        {
            "_id": "628bec7f606d7224185748fd",
            "e": null,
            "h": null,
            "l": null,
            "pid": "10002",
            "skus": [
                {
                    "_id": "628bec7f606d7224185748fe",
                    "sku": "sku_ejemplo_2",
                    "quantity": 1
                }
            ],
            "w": null
        }
    ],
    "order_id": "628bec53606d7250f717ad7c",
    "reason_id": "62617fda606d72ad5f126268",
    "success_response": null,
    "failed_attempts": [
        {
            "timestamp": "2022-05-23T16:20:17-04:00",
            "response": {
                "error": "Pack count should be between 2, 2"
            }
        }
    ],
    "created_at": "2022-05-23T12:20:15.727-08:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders/<order_id>/order_status/confirmations.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ------------------------------------
`order_id` | Identificador de un pedido en Centry

### Body request

Parámetro | Descripción
--------- | ------------------------------------
`reason_id` | Identificador del motivo por el cual el pedido se requiere esta división. Sólo MercadoLibre admite este atributo y es obligatorio. [ConfirmationReasons](#confirmationreasons-pronto)
`boxes` | Listado de cajas, paquetes o bultos que componen el pedido.
`boxes.dimensions` | Diccionario con las longitudes y peso del bulto. Sólo Falabella admite este diccionario.
`boxes.dimensions.length` | Largo del bulto medido en centímetros.
`boxes.dimensions.width` | Ancho del bulto medido en centímetros.
`boxes.dimensions.height` | Alto del bulto medido en centímetros.
`boxes.dimensions.weight` | Peso del bulto medido en kilogramos.
`boxes.package_id` | Código para identificar la caja. Sólo MercadoLibre admite este atributo y es opcional.
`boxes.items` | Diccionario con el listado de todos los productos que componen el bulto. Cada llave es el SKU del producto y los valores son las unidades de cada SKU

### Body response

Parámetro | Descripción
--------- | ------------------------------------
`_id` | Identificador de la confirmación en Centry
`order_id` | Identificador del pedido asociado a esta confirmación
`boxes` | Listado de cajas, paquetes o bultos que componen el pedido
`success_response` | Diccionario con la respuesta entregada por la plataforma de origen del pedido. No existe un formato predefinido para este campo, depende de cada integración y puede cambiar sin previo aviso. Lo más relevante es que su presencia indica que la confirmación ha resultado exitosa.
`failed_attempts` | Listado con todos los intentos fallidos que ha tenido esta confirmación en la plataforma de origen del pedido.
`created_at` | fecha de creación de la confirmación

## Reagendamiento de un pedido pendiente

Este endpoint permite reagendar un pedido pendiente para aquellas integraciones que así lo admiten. Estas integraciones son:

* Falabella Marketplace

```shell
curl "https://www.centry.cl/conexion/v1/orders/5eece46148f039166bf5ffad/order_status/reschedules.json" \
     -H "Authorization: Bearer  <access_token>" \
     -d '{
    "date": "2021-02-31"
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "5eeba37348f03925389e5a20",
  "order_id": "5eeba0ad48f039354aa785ac",
  "success_response": {
    "uuid": "0f2ca23b-10be-4237-bf03-74f521fb1ee8",
    "status": "DONE",
    "errors": []
  },
  "failed_attempts": [],
  "created_at": "2020-06-18T09:25:07.451-08:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders/<order_id>/order_status/reschedules.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ------------------------------------
`order_id` | Identificador de un pedido en Centry

### Body request

Parámetro | Descripción
----------| ------------------------------------
`date` | Nueva fecha con la que se quiere reagendar el pedido.

### Body response

Parámetro | Descripción
--------- | ------------------------------------
`_id` | Identificador del reagendamiento en Centry
`order_id` | Identificador del pedido asociado a este reagendamiento
`date` | Fecha solicitada para reagendar
`success_response` | Diccionario con la respuesta entregada por la plataforma de origen del pedido. No existe un formato predefinido para este campo, depende de cada integración y puede cambiar sin previo aviso. Lo más relevante es que su presencia indica que el reagendamiento ha resultado exitoso.
`failed_attempts` | Listado con todos los intentos fallidos que ha tenido este reagendamiento en la plataforma de origen del pedido.
`created_at` | fecha de creación del reagendamiento

## Anulación de un pedido pendiente

Este endpoint permite anular un pedido pendiente para aquellas integraciones que así lo admiten. Estas integraciones son:

* Falabella Marketplace
* Mercado Libre
* Dafiti
* Linio
* Shopify

```shell
curl "https://www.centry.cl/conexion/v1/orders/5eece46148f039166bf5ffad/order_status/cancellations.json" \
     -H "Authorization: Bearer  <access_token>" \
     -d '{
    "buyer_rate_id": "5e45b03d48f0392442dbd1bc",
    "reason_id": "5e45b03c48f0392442dbd1a6",
    "message": "Solicitud del cliente",
    "restock": true
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "5eeba37348f03925389e5a20",
  "buyer_rate_id": "5e45b03d48f0392442dbd1bc",
  "order_id": "5eeba0ad48f039354aa785ac",
  "reason_id": "5e45b03c48f0392442dbd1a6",
  "message": "Solicitud del cliente",
  "restock": true,
  "success_response": {
    "uuid": "0f2ca23b-10be-4237-bf03-74f521fb1ee8",
    "status": "DONE",
    "errors": []
  },
  "failed_attempts": [],
  "created_at": "2020-06-18T09:25:07.451-08:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders/<order_id>/order_status/cancellations.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ------------------------------------
`order_id` | Identificador de un pedido en Centry

### Body request

Parámetro | Descripción
----------| ------------------------------------
`buyer_rate_id` | Identificado de la calificación del comprador [BuyerRates](#buyerrates)
`reason_id` | Identificador del motivo de anulación [CancellationReasons](#cancellationreasons)
`message` | Texto con la justificación de la anulación del pedido
`restock` | Boolean que indica si se requiere reponer (`true`) o no (`false`) el stock. Está opción se puede usar dependiendo de si lo admite el motivo de anulación

### Body response

Parámetro  | Descripción
---------- | ------------------------------------
`_id` | Identificador de la anulación en Centry
`order_id` | Identificador del pedido asociado a esta anulación
`buyer_rate_id` | Identificado de la calificación del comprador
`reason_id` | Identificador del motivo de anulación
`message` | Texto con la justificación de la anulación del pedido
`restock` | Boolean que indica si se requiere reponer (`true`) o no (`false`) el stock.
`success_response` | Diccionario con la respuesta entregada por la plataforma de origen del pedido. No existe un formato predefinido para este campo, depende de cada integración y puede cambiar sin previo aviso. Lo más relevante es que su presencia indica que la anulación ha resultado exitosa.
`failed_attempts` | Listado con todos los intentos fallidos que ha tenido esta anulación en la plataforma de origen del pedido.
`created_at` | fecha de creación de la anulación

## Confirmación de entrega de un pedido pendiente

Este endpoint permite confirmar la entrega de un pedido pendiente para aquellas integraciones que así lo admiten. Estas integraciones son:

* Mercado Libre

```shell
curl "https://www.centry.cl/conexion/v1/orders/5eece46148f039166bf5ffad/order_status/delivery_confirmations.json" \
     -H "Authorization: Bearer  <access_token>" \
     -d '{
    "buyer_rate_id": "5e45b03d48f0392442dbd1bc",
    "message": "Solicitud del cliente"
}'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "5eeba37348f03925389e5a20",
  "buyer_rate_id": "5e45b03d48f0392442dbd1bc",
  "order_id": "5eeba0ad48f039354aa785ac",
  "message": "Solicitud del cliente",
  "success_response": {
     "reason": null,
     "reply_status": null,
     "date_created": "2020-10-07T13:34:29.601-04:00",
     "fulfilled": true,
     "rating": "NEUTRAL",
     "visibility_date": null,
     "message": "Solicitud del cliente",
     "cust_role": "seller",
     "site_id": "MLC",
     "id": 9041211809440,
     "cust_from": 526176909,
     "reply": null,
     "cust_to": 628867579,
     "order_id": 4083462417,
     "status": "hidden",
     "reply_date": null
  },
  "failed_attempts": [],
  "created_at": "2020-06-18T09:25:07.451-08:00"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders/<order_id>/order_status/delivery_confirmations.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ------------------------------------
`order_id` | Identificador de un pedido en Centry

### Body request

Parámetro | Descripción
----------| ------------------------------------
`buyer_rate_id` | Identificado de la calificación del comprador [BuyerRates](#buyerrates)
`message` | Texto con la justificación de la confirmación de entrega del pedido

### Body response

Parámetro  | Descripción
---------- | ------------------------------------
`_id` | Identificador de la confirmación de entrega en Centry
`order_id` | Identificador del pedido asociado a esta confirmación de entrega
`buyer_rate_id` | Identificado de la calificación del comprador
`message` | Texto con la justificación de la confirmación de entrega del pedido
`success_response` | Diccionario con la respuesta entregada por la plataforma de origen del pedido. No existe un formato predefinido para este campo, depende de cada integración y puede cambiar sin previo aviso. Lo más relevante es que su presencia indica que la confirmación de entrega ha resultado exitosa.
`failed_attempts` | Listado con todos los intentos fallidos que ha tenido esta confirmación de entrega en la plataforma de origen del pedido.
`created_at` | fecha de creación de la confirmación de entrega


## Todas las notas de un pedido

Este endpoint permite obtener todas las notas de pedido de un pedido en particular:


```shell
curl -L -X GET 'https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/order_notes.json' \
-H 'Authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "6035671984c6e1147fa0dca2",
        "created_at": "2021-02-23T17:35:37.060-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 4",
        "updated_at": "2021-02-23T17:35:37.060-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "6035665784c6e111b4d19f49",
        "created_at": "2021-02-23T17:32:23.935-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 3",
        "updated_at": "2021-02-23T17:32:23.935-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "603565e184c6e111b4d19f44",
        "created_at": "2021-02-23T17:30:25.049-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 2",
        "updated_at": "2021-02-23T17:30:25.049-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "603565d784c6e111b4d19f41",
        "created_at": "2021-02-23T17:30:15.074-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 1",
        "updated_at": "2021-02-23T17:30:15.074-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/order_notes.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ------------------------------------
`order_id` | Identificador de un pedido en Centry


### Body response

Parámetro  | Descripción
---------- | ------------------------------------
`_id` | Identificador de la nota del pedido
`order_id` | Identificador del pedido asociado a esta nota de pedido
`user_id` | Identificador del usuario que realizó la nota de pedido <i class="label label-info">Asignado de manera automática</i>
`text` | Texto correspondiente a la nota de pedido





## Crear una nota de pedido

Este endpoint permite crear una nota de pedido para un pedido en particular:


```shell

curl -L -X POST 'https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/order_notes.json' \
-H 'Authorization: Bearer <access_token>' \
-H 'Content-Type: application/json' \
--data-raw '{
    "text": "Nota pedido 5"
}'

```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "603567f384c6e1147fa0dcad",
        "created_at": "2021-02-23T17:39:15.279-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 5",
        "updated_at": "2021-02-23T17:39:15.279-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "6035671984c6e1147fa0dca2",
        "created_at": "2021-02-23T17:35:37.060-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 4",
        "updated_at": "2021-02-23T17:35:37.060-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "6035665784c6e111b4d19f49",
        "created_at": "2021-02-23T17:32:23.935-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 3",
        "updated_at": "2021-02-23T17:32:23.935-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "603565e184c6e111b4d19f44",
        "created_at": "2021-02-23T17:30:25.049-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 2",
        "updated_at": "2021-02-23T17:30:25.049-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    },
    {
        "_id": "603565d784c6e111b4d19f41",
        "created_at": "2021-02-23T17:30:15.074-03:00",
        "order_id": "602bd13084c6e18fca85b820",
        "text": "Nota pedido 1",
        "updated_at": "2021-02-23T17:30:15.074-03:00",
        "user_id": "5fd0e51784c6e117832602cd"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/order_notes.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
---------- | ------------------------------------
`order_id` | Identificador de un pedido en Centry

### Body request

Parámetro | Descripción
----------| ------------------------------------
`text` | Texto correspondiente a la nota del pedido


### Body response

Parámetro  | Descripción
---------- | ------------------------------------
`_id` | Identificador de la nota del pedido
`order_id` | Identificador del pedido asociado a esta nota de pedido
`user_id` | Identificador del usuario que realizó la nota de pedido <i class="label label-info">Asignado de manera automática</i>
`text` | Texto correspondiente a la nota de pedido



## Todos los documentos de un pedido

Este endpoint permite obtener todos los documentos de un pedido en particular:


```shell
curl -L -X GET 'https://www.centry.cl/conexion/v1/orders/<order_id>/documents.json' \
-H 'Authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_document_type": "invoice",
        "number": "800566",
        "_id": "6052202e84c6e19ccecb1966",
        "c_at": "2021-03-17T12:28:46.171-03:00",
        "file_content_type": "application/pdf",
        "file_file_name": "nombre_archivo.pdf",
        "file_file_size": 35517,
        "file_fingerprint": "f69fd4473948e0bb7aa8e0d71610e1a5",
        "file_updated_at": "2021-03-17T10:32:24.412-03:00",
        "order_id": "6048df5184c6e187a31a6200"
    },
    {
        "_document_type": "invoice",
        "number": "",
        "_id": "6052203884c6e19ccecb1968",
        "c_at": "2021-03-17T12:28:56.384-03:00",
        "file_content_type": "application/pdf",
        "file_file_name": "nombre_archivo.pdf",
        "file_file_size": 82419,
        "file_fingerprint": "f69fd4473948e0bb7aa8e0d71610e1a5",
        "file_updated_at": "2021-03-17T10:28:56.307-03:00",
        "order_id": "6048df5184c6e187a31a6200"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/documents.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
------------ | ------------------------------------
`order_id` | Identificador de un pedido en Centry


### Body response

Parámetro             | Descripción
--------------------- | ------------------------------------
`_id`                 | Identificador de la nota del pedido
`order_id`            | Identificador del pedido asociado a esta nota de pedido
`file_file_name`      | Nombre del archivo del documento
`_document_type`      | Tipo de documento: [bill invoice credit_note debit_note shipping_guide other]
`file_file_size`      | Tamaño del archivo en KB
`number`              | Número de folio del documento (Opcional)
`confirmation_box_id` | Identificador de un bulto en caso de que el pedido haya sido confirmado parcialmente (Opcional)


## Mostrar un documento de un pedido

Este endpoint permite obtener un documento específico de un pedido en particular:


```shell
curl -L -X GET 'https://www.centry.cl/conexion/v1/orders/<order_id>/documents/<document_id>.json' \
-H 'Authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
  {
      "_document_type": "invoice",
      "number": "800566",
      "_id": "6052203884c6e19ccecb1968",
      "c_at": "2021-03-17T12:28:56.384-03:00",
      "file_content_type": "application/pdf",
      "file_file_name": "nombre_archivo.pdf",
      "file_file_size": 82419,
      "file_fingerprint": "f69fd4473948e0bb7aa8e0d71610e1a5",
      "file_updated_at": "2021-03-17T10:28:56.307-03:00",
      "order_id": "6048df5184c6e187a31a6200",
      "confirmation_box_id": "6048df5184c6e187a31b5673"
  }
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/documents/&lt;document_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
------------ | ------------------------------------
`order_id` | Identificador de un pedido en Centry
`document_id` | Identificador de un documento en Centry

### Body response

Parámetro             | Descripción
--------------------- | ------------------------------------
`_id`                 | Identificador de la nota del pedido
`order_id`            | Identificador del pedido asociado a esta nota de pedido
`file_file_name`      | Nombre del archivo del documento
`_document_type`      | Tipo de documento: [bill invoice credit_note debit_note shipping_guide other]
`file_file_size`      | Tamaño del archivo en KB
`number`              | Número de folio del documento (Opcional)
`confirmation_box_id` | Identificador de un bulto en caso de que el pedido haya sido confirmado parcialmente (Opcional)

## Crear un documento de un pedido

Este endpoint cargar un documento y asociarlo a un pedido en particular:

```shell
curl -L -X POST 'www.centry.cl/conexion/v1/orders/<order_id>/documents.json' \
-H 'Authorization: Bearer  <access_token>' \
-F 'document_type=invoice' \
-F 'file=@/Users/nameuser/Documents/nombre_archivo.pdf'
-F 'number=800566'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_document_type": "invoice",
    "number": "800566",
    "_id": "6052203884c6e19ccecb1968",
    "c_at": "2021-03-17T12:28:56.384-03:00",
    "file_content_type": "application/pdf",
    "file_file_name": "nombre_archivo.pdf",
    "file_file_size": 82419,
    "file_fingerprint": "f69fd4473948e0bb7aa8e0d71610e1a5",
    "file_updated_at": "2021-03-17T10:28:56.307-03:00",
    "order_id": "6048df5184c6e187a31a6200",
    "confirmation_box": null
}
```

> Mismo ejemplo anterior, pero ahora indicando un `confirmation_box_id`:

```shell
curl -L -X POST 'www.centry.cl/conexion/v1/orders/<order_id>/documents.json' \
-H 'Authorization: Bearer  <access_token>' \
-F 'document_type=invoice' \
-F 'file=@/Users/nameuser/Documents/nombre_archivo.pdf'
-F 'number=800566'
-F 'confirmation_box_id=6048df5184c6e187a31b5673'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_document_type": "invoice",
    "number": "800566",
    "_id": "6052203884c6e19ccecb1968",
    "c_at": "2021-03-17T12:28:56.384-03:00",
    "file_content_type": "application/pdf",
    "file_file_name": "nombre_archivo.pdf",
    "file_file_size": 82419,
    "file_fingerprint": "f69fd4473948e0bb7aa8e0d71610e1a5",
    "file_updated_at": "2021-03-17T10:28:56.307-03:00",
    "order_id": "6048df5184c6e187a31a6200",
    "confirmation_box": "6048df5184c6e187a31b5673"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/documents.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
------------ | ------------------------------------
`order_id` | Identificador de un pedido en Centry

### Body form-data

Parámetro | Descripción | Tipo
------------| ------------------------------------|----------
`file` | Archivo del documento a anexar al pedido | File
`document_type` | Tipo de documento: [bill, invoice, credit_note, debit_note, shipping_guide, other] | Text
`number` | Número de folio del documento (Opcional) | Text

### Body response

Parámetro  | Descripción
---------------- | ---------------------------------
`_id` | Identificador de la nota del pedido
`order_id` | Identificador del pedido asociado a esta nota de pedido
`file_file_name` | Nombre del archivo del documento
`_document_type` | Tipo de documento: [bill invoice credit_note debit_note shipping_guide other]
`file_file_size` | Tamaño del archivo en KB
`number` | Número de folio del documento (Opcional)

## Eliminar un documento de un pedido

Este endpoint permite eliminar un documento específico de un pedido en particular:

```shell
curl -L -X DELETE 'https://www.centry.cl/conexion/v1/orders/<order_id>/documents/<document_id>.json' \
-H 'Authorization: Bearer <access_token>'
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "message": "Document deleted"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;/documents/&lt;document_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro  | Descripción
------------ | ------------------------------------
`order_id` | Identificador de un pedido en Centry
`document_id` | Identificador de un documento en Centry

### Body response

Parámetro  | Descripción
------------------ | ------------------------------------
`message` | Mensaje de respuesta del servidor
