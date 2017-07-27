# Webhooks



## Parámetros


| Atributo           |   Tipo  |                                      Descripción                                      |
| ---------          | ------- | ------------------------------------------------------------------------------------- |
| `_id`              | string  | Identificador del webhook                    |
| `created_at`       | string  | Regristro de creación del webhook en Centry                     |
| `callback_url`     | string  | Url de retorno                      |
| `events`           | string  | Eventos pendientes a describir               |
| `app_id`       	 | string  | Identificador de aplicación asociada     |
| `company_id`  	 | string  | Identificador de empresa       |   











## Todas los webhooks de la cuenta

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks </h6>
  </div>
</div>



```shell

```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json


```


## Obtener un webhook  específico



Este endpoint entrega u webhook  específico.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/<webhook_id> </h6>
  </div>
</div>


```shell

```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json


	

```



### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`webhook_id` | El identificador del webhook  a recuperar




## Crear un webhook 

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks </h6>
  </div>
</div>

```shell

```



## Actualizar un webhook 

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/webhooks/(webhook_ID) </h6>
  </div>
</div>

```shell


```

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`webhook_ID`| El identificador del webhook  a actualizar





## Eliminar un webhook 

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-delete">DELETE</i>
    <h6> https://www.centry.cl/conexion/v1/webhook/(webhook_ID) </h6>
  </div>
</div>
```shell
curl -X DELETE https://www.centry.cl/conexion/v1/webhooks/(webhook_ID).json?force=true \
    -H "Authorization: Bearer <Access_code>" > deleteResponse.json
```


### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`webhook_ID` | El identificador de l webhook  a eliminar








##Traspadar a Ordenes 


## Actualizar una Orden

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-put">PUT</i>
    <h6> https://www.centry.cl/conexion/v1/orders/(order_ID) </h6>
  </div>
</div>

```shell

curl -X PUT https://www.centry.cl/conexion/v1//orders/(order_ID).json \
    -H "Authorization: Bearer  <Access_code> "\
    -H "Content-Type: application/json" \
    -d '{
  "parametro_a_editar": "nuevo_valor",
  "first_name":"Pedro cUrl"
}'
```

### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`order_ID`| El identificador de la orden a actualizar
