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
| `name`					| string  | Nombre del producto                                                                   |
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








## Todas las Órdenes de la cuenta

```shell
curl "https://www.centry.cl/conexion/v1/orders"
  -H "Authorization: tu_centry_api_key"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
  {...}
]
```

Este endpoint entrega todas las órdenes de la cuenta.

### HTTP Request

`GET https://www.centry.cl/conexion/v1/orders/`




## Obtener una Orden específica

```shell
curl "https://www.centry.cl/conexion/v1/orders/2"
  -H "Authorization: tu_centry_api_key"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{...}
```

Este endpoint entrega un producto específico.

### HTTP Request

`GET https://www.centry.cl/conexion/v1/products/<ID>`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
ID | El identificador de la orden a recuperar




## Crear una Orden

### HTTP Request

`POST https://www.centry.cl/conexion/v1/orders`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------




## Actualizar una Orden

### HTTP Request

`PUT https://www.centry.cl/conexion/v1/orders`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
_id | El identificador de la orden a actualizar





## Eliminar una Orden

### HTTP Request

`DELETE https://www.centry.cl/conexion/v1/orders/<ID>`

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
ID | El identificador de la Orden a eliminar