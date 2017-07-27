# Orders

## Parámetros



| Atributo             		|   Tipo  |                                      Descripción                                      |
| ---------            		| ------- | ------------------------------------------------------------------------------------- |
| `id`                 		| string  |  Identificador de orden                           						|
| `_status`            		| string  |  Descripción del estado de la orden                                     |
| `address_billing`			| object  |  Información del pago. Ver [Formulario de direcciones](#formulario-de-direcciones)|
| `address_shipping`		| object  |  Información de envío. Ver [Formulario de direcciones](#formulario-de-direcciones)|
| `buyer_email`				| string  |  Email de Cliente                                                      |
| `buyer_first_name`		| string  |  Nombre de Cliente                                                      |
| `buyer_last_name`			| string  |  Apellido de Cliente                                                    |
| `cancelled_date`			|date-time|  Fecha en formato UTC de Pago de la orden                               |
| `company_id`				| integer |  Identificador de la empresa                                            |
| `created_at`				|date-time|  Fecha en formato UTC que registra la realizacion de la orden           |
| `id_b_sale`				| integer |  Identificador de la orden en caso de realizarse por Bsale              |
| `id_origin`				| string  |  Identificador de Origen de donde fue importada                                       |
| `id_woocommerce`			| integer |  Identificador de la orden en caso de realizarse por Woocommerce        |
| `items`			   		| array   |  Lista de items a comprar. Ver [Atributos de los items](#atributos-de-los-items)|
| `origin`			   		| string  |  Origen de donde fue importada la orden                                                            |
| `original_data`			| string  |  Datos sin editar que fueron importados                                                             |
| `received_date`			|date-time|  Fecha en el que el cliente recibe su orden                             |
| `shipped_date`			|date-time|  Fecha en el que se despacha la orden                                   |
| `total_amount`			|  float  |  Valor monetario del monto total de la orden                            |
| `updated_at`				|date-time|  Fecha en el que se realizó una actualización a la orden                |
| `quantity`				| integer |  Cantidad de items en la orden                |



### Formulario de direcciones

#### Estos datos pueden variar y son consistentes para los parametros address_billing y address_shipping

| Atributo             		|   Tipo  |                                      Descripción                                      |
| ---------            		| ------- | ------------------------------------------------------------------------------------- |
| `_id`          			| string  | Identificador de formulario                                                           |
| `city`         			| string  | Nombre de la ciudad 				                                                  |
| `country`					| string  | Nombre del País                                                                       |  
| `created_at`				| string  | Fecha de la realización del formulario                                                |  
| `email`					| string  | Email del cliente                                                                     |
| `first_name`				| string  | Nombre(s) del cliente                                                                 |
| `last_name`				| string  | Apellido(s) del cliente                                                               |
| `line1`					| string  | Dirección principal del cliente                                                       |
| `line2`					| string  | Dirección alternativa del cliente                                                     |
| `phone1`					| string  | Numero telefónico principal                                                           |
| `phone2`					| string  | Número telefónico Alternativo del cliente                                             |
| `state`					| string  | Estado del Cliente	                                                                  |
| `updated_at`				|date-time| Fecha de actualización de formulario                                                  |
| `zip_code`				| string  | Numero del código postal                                                              |  




### Atributos de los items

| Atributo             		|   Tipo  |                                      Descripción                                      |
| ---------            		| ------- | ------------------------------------------------------------------------------------- |
| `_id`               		| string | Identificador de conjunto de items                                                    |
| `created_at`        		|date-time| Fecha de creación de este elemento                                                   |
| `currency`				| string  | Tipo de moneda en el que se pagará                                                    |
| `name`					| string  | Nombre del ordero                                                                   |
| `paid_price`				| float   | Monto a pagar                                                                         |
| `quantity`				| integer | Cantidad de items                                                                     |
| `shipment_provider`		| string  | Empresa encargada del despacho                                                        |
| `shipping_amount`			| float   | Valor monetario del despacho                                                          |
| `shipping_type`			| string  | Tipo de despacho                                                                  |
| `tax_amount`				| float   | Cantidad de impuesto                                                                 |
| `tracking_code`			| string  | Código de rastreo                                                                     |
| `tracking_code_pre`		| string  | Código de rastreo                                                                     |
| `unit_price`				| float   | Precio unitario                                                                      |
| `updated_at`				|date-time| Fecha de actualización                                                                |
| `variant_id`				| integer | Identificador de variante registrada en Centry                                        |








## Todas las Ordenes de la cuenta

Este endpoint entrega todas las ordenes de la cuenta

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders </h6>
  </div>
</div>



```shell
curl "https://www.centry.cl/conexion/v1/orders.json"/
 -H "Authorization: Bearer  <Access_code> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
  [
  {"_id":"5977483f1d41c81248000003",
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
			}],
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



Este endpoint entrega un orden específico.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/orders/<order_id> </h6>
  </div>
</div>


```shell
curl "https://www.centry.cl/conexion/v1/orders/<order_id>.json"/
 -H "Authorization: Bearer  <Access_code> "  > response.json
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json

  
  {"_id":"5977483f1d41c81248000003",
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
			}],
	"origin":"Centry",
	"original_data":null,
	"received_date":null,
	"shipped_date":null,
	"total_amount":99995.0,
	"updated_at":"2017-07-25T13:31:43.133Z"
}

	

```



### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`order_id` | El identificador de la orden a recuperar




## Crear una Orden
Este endpoint crea una orden
### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/orders </h6>
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
	}' > createdOrder.json
```






## Eliminar una Orden
Este endpoint elimina una orden 
### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/order/(order_ID) </h6>
  </div>
</div>
```shell
curl -X DELETE https://www.centry.cl/conexion/v1/orders/(order_ID).json?force=true \
    -H "Authorization: Bearer <Access_code>" > deleteResponse.json
```


### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`order_ID` | El identificador de la Orden a eliminar