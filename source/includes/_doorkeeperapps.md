#Doorkeeperapps



## Parámetros


| Atributo           |   Tipo  |                                      Descripción                                      |
| ---------          | ------- | ------------------------------------------------------------------------------------- |
| `_id`              | string  | Identificador del Aplicación                    |
| `created_at`       | string  | Regristro de creación del Aplicación en Centry                     |
| `callback_url`     | string  | Url de retorno                      |
| `platform`         | string  | Plataforma de aplicación               |
| `master`           | Boolean | Describe si aplicación está actuando o no como maestro               |
| `app_id`       	 | string  | Identificador de aplicación asociada     |
| `company_id`  	 | string  | Identificador de empresa       |   




## Crear un Doorkeeper

### HTTP Request


<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6> https://www.centry.cl/conexion/v1/doorkeeper_apps </h6>
  </div>
</div>
```shell

curl -X POST https://www.centry.cl/conexion/v1/doorkeeper_apps.json \
	-H "Authorization: Bearer <access_code> "\
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
