# Orders

## Parámetros

| Atributo           | Tipo      | Descripción                                                                       |
| ------------------ | --------- | --------------------------------------------------------------------------------- |
| `id`               | string    | Identificador de orden  <i class="label label-info">sólo lectura</i>              |
| `_status`          | string    | Estado de la orden. Las opciones son `pending`, `shipped`, `received`, `cancelled`, `cancelled_before_shipping` o `cancelled_after_shipping`. |
| `address_billing`  | object    | Información del pago. Ver [Formulario de direcciones](#formulario-de-direcciones) |
| `address_shipping` | object    | Información de envío. Ver [Formulario de direcciones](#formulario-de-direcciones) |
| `buyer_dni`        | string    | Número de identificación nacional del cliente (ej. en Chile es el RUN)            |
| `buyer_email`      | string    | Email de Cliente                                                                  |
| `buyer_first_name` | string    | Nombre de Cliente                                                                 |
| `buyer_last_name`  | string    | Apellido de Cliente                                                               |
| `buyer_phone`      | string    | Número de teléfono (preferentemente fijo)                                         |
| `buyer_mobilephone`| string    | Número de teléfono (preferentemente móvil)                                        |
| `buyer_birthdate`  | string    | Fecha de nacimiento del cliente.                                                  |
| `items`            | array     | Lista de ítems a comprar. Ver [Atributos de los ítems](#atributos-de-los-items)   |
| `origin`           | string    | Origen de donde fue importada la orden                                            |
| `original_data`    | string    | Datos sin editar que fueron importados                                            |
| `id_origin`        | string    | Identificador de Origen de donde fue importada                                    |
| `number_origin`    | string    | Número del pedido con el que se maneja la orden en la plataforma de origen        |
| `url_origin`       | string    | URL desde la cual puede ser accedida la orden en la plataforma de origen          |
| `total_amount`     | float     | Monto total de los productos comprados                                            |
| `shipping_amount`  | float     | Costo del despacho del pedido                                                     |
| `discount_amount`  | float     | Suma total de los descuentos aplicados a los productos del pedido                 |
| `paid_amount`      | float     | Monto total pagado por el cliente. En un caso ideal es igual a total_amount + shipping_amount - discount_amount                   |
| `received_date`    | date-time | Fecha en el que el cliente recibe su orden                                        |
| `shipped_date`     | date-time | Fecha en el que se despacha la orden                                              |
| `cancelled_date`   | date-time | Fecha en formato UTC de Pago de la orden                                          |
| `company_id`       | string    | Identificador de la empresa <i class="label label-info">sólo lectura</i>          |
| `created_at`       | date-time | Fecha en formato UTC que registra la realizacion de la orden <i class="label label-info">sólo lectura</i> |
| `updated_at`       | date-time | Fecha en el que se realizó una actualización a la orden <i class="label label-info">sólo lectura</i> |

### Formulario de direcciones

#### Estos datos pueden variar y son consistentes para los parámetros address_billing y address_shipping

| Atributo     | Tipo      | Descripción                                                                         |
| ------------ | --------- | ----------------------------------------------------------------------------------- |
| `_id`        | string    | Identificador de formulario <i class="label label-info">sólo lectura</i>            |
| `city`       | string    | Nombre de la ciudad                                                                 |
| `country`    | string    | Nombre del País                                                                     |  
| `email`      | string    | Email del cliente                                                                   |
| `first_name` | string    | Nombre(s) del cliente                                                               |
| `last_name`  | string    | Apellido(s) del cliente                                                             |
| `line1`      | string    | Dirección principal del cliente                                                     |
| `line2`      | string    | Dirección alternativa del cliente                                                   |
| `phone1`     | string    | Numero telefónico principal                                                         |
| `phone2`     | string    | Número telefónico Alternativo del cliente                                           |
| `state`      | string    | Estado del Cliente                                                                  |
| `zip_code`   | string    | Numero del código postal                                                            |  
| `created_at` | string    | Fecha de la realización del formulario <i class="label label-info">sólo lectura</i> |  
| `updated_at` | date-time | Fecha de actualización de formulario <i class="label label-info">sólo lectura</i>   |

### Atributos de los items

| Atributo            |   Tipo    | Descripción                                                                     |
| ------------------- | --------- | ------------------------------------------------------------------------------- |
| `_id`               | string    | Identificador de conjunto de ítems <i class="label label-info">sólo lectura</i> |
| `currency`          | string    | Tipo de moneda en el que se pagará                                              |
| `name`              | string    | Nombre del producto                                                             |
| `paid_price`        | float     | Monto a pagar                                                                   |
| `quantity`          | integer   | Cantidad de ítems                                                               |
| `shipment_provider` | string    | Empresa encargada del despacho                                                  |
| `shipping_amount`   | float     | Valor monetario del despacho                                                    |
| `shipping_type`     | string    | Tipo de despacho                                                                |
| `tax_amount`        | float     | Cantidad de impuesto                                                            |
| `tracking_code`     | string    | Código de rastreo                                                               |
| `tracking_code_pre` | string    | Código de rastreo                                                               |
| `unit_price`        | float     | Precio unitario                                                                 |
| `variant_id`        | integer   | Identificador de variante registrada en Centry                                  |
| `created_at`        | date-time | Fecha de creación de este elemento <i class="label label-info">sólo lectura</i> |
| `updated_at`        | date-time | Fecha de actualización <i class="label label-info">sólo lectura</i>             |

## Todas las Ordenes de la cuenta

Este endpoint entrega todas las ordenes de la cuenta

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/orders.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
	{
		"_id":"5977483f1d41c81248000003",
		"_status":"pending",
		"address_billing":{
			"_id":"5977483f1d41c81248000005",
			"city":"Santiago",
			"country":"Chile",
			"created_at":null,
			"email":"Email@Factura.cl",
			"first_name":"Nombre Factura",
			"last_name":"Apellido Factura",
			"line1":"Dirección Cliente",
			"line2":"",
			"phone1":"89668063",
			"phone2":"",
			"state":"EstadoFactura",
			"updated_at":null,
			"zip_code":"2948513"
		},
		"address_shipping":{
			"_id":"5977483f1d41c81248000006",
			"city":"Santiago",
			"country":"Chile",
			"created_at":null,
			"email":"Email@Envío.cl",
			"first_name":"Nombre Envio",
			"last_name":"Apellido Envío",
			"line1":"Dirección Cliente",
			"line2":"",
			"phone1":"89668063",
			"phone2":"",
			"state":"EstadoFactura",
			"updated_at":null,
			"zip_code":"2948513"
		},
		"buyer_email":"Email@Cliente.cl",
		"buyer_first_name":"Nombre Cliente",
		"buyer_last_name":"Apellido Cliente",
		"cancelled_date":null,
		"company_id":"597643ab1d41c846ea000001",
		"created_at":"2017-07-25T13:31:43.133Z",
		"id_b_sale":null,
		"id_origin":null,
		"id_woocommerce":null,
		"items": [
			{
				"_id":"5977483f1d41c81248000004",
				"created_at":null,
				"currency":null,
				"name":"L, Café",
				"paid_price":null,
				"quantity":5,
				"shipment_provider":null,
				"shipping_amount":null,
				"shipping_type":null,
				"tax_amount":null,
				"tracking_code":null,
				"tracking_code_pre":null,
				"unit_price":19999.0,
				"updated_at":null,
				"variant_id":"597649201d41c846ea000009"
			}
		],
		"origin":"Centry",
		"original_data":null,
		"received_date":null,
		"shipped_date":null,
		"total_amount":99995.0,
		"updated_at":"2017-07-25T13:31:43.133Z"
	}
]
```

## Obtener una Orden específica

Este endpoint entrega una orden específica.

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;.json </h6>
  </div>
</div>

```shell
curl "https://www.centry.cl/conexion/v1/orders/<order_id>.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
	"_id":"5977483f1d41c81248000003",
	"_status":"pending",
	"address_billing":{
		"_id":"5977483f1d41c81248000005",
		"city":"Santiago",
		"country":"Chile",
		"created_at":null,
		"email":"Email@Factura.cl",
		"first_name":"Nombre Factura",
		"last_name":"Apellido Factura",
		"line1":"Dirección Cliente",
		"line2":"",
		"phone1":"89668063",
		"phone2":"",
		"state":"EstadoFactura",
		"updated_at":null,
		"zip_code":"2948513"
	},
	"address_shipping":{
		"_id":"5977483f1d41c81248000006",
		"city":"Santiago",
		"country":"Chile",
		"created_at":null,
		"email":"Email@Envío.cl",
		"first_name":"Nombre Envio",
		"last_name":"Apellido Envío",
		"line1":"Dirección Cliente",
		"line2":"",
		"phone1":"89668063",
		"phone2":"",
		"state":"EstadoFactura",
		"updated_at":null,
		"zip_code":"2948513"
	},
	"buyer_email":"Email@Cliente.cl",
	"buyer_first_name":"Nombre Cliente",
	"buyer_last_name":"Apellido Cliente",
	"cancelled_date":null,
	"company_id":"597643ab1d41c846ea000001",
	"created_at":"2017-07-25T13:31:43.133Z",
	"id_b_sale":null,
	"id_origin":null,
	"id_woocommerce":null,
	"items": [
		{
			"_id":"5977483f1d41c81248000004",
			"created_at":null,
			"currency":null,
			"name":"L, Café",
			"paid_price":null,
			"quantity":5,
			"shipment_provider":null,
			"shipping_amount":null,
			"shipping_type":null,
			"tax_amount":null,
			"tracking_code":null,
			"tracking_code_pre":null,
			"unit_price":19999.0,
			"updated_at":null,
			"variant_id":"597649201d41c846ea000009"
		}
	],
	"origin":"Centry",
	"original_data":null,
	"received_date":null,
	"shipped_date":null,
	"total_amount":99995.0,
	"updated_at":"2017-07-25T13:31:43.133Z"
}
```

### Parámetros URL

Parámetro  | Descripción
---------- | ----------------------------------------
`order_id` | El identificador de la orden a recuperar

## Crear una Orden

Este endpoint crea una orden

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders.json </h6>
  </div>
</div>

```shell
curl -X POST https://www.centry.cl/conexion/v1/orders.json \
 -H "Authorization: Bearer 077b4b3e9ec372cc09f3488d56a6b97c0e6c8595a08bbde8ac4c01517a9afe6f"\
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

## Eliminar una Orden

Este endpoint elimina una orden

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/orders/&lt;order_id&gt;.json </h6>
  </div>
</div>

```shell
curl -X DELETE https://www.centry.cl/conexion/v1/orders/<order_id>;.json.json?force=true \
    -H "Authorization: Bearer <access_token>" > deleteResponse.json
```

### Parámetros URL

Parámetro  | Descripción
---------- | ---------------------------------------
`order_id` | El identificador de la Orden a eliminar
