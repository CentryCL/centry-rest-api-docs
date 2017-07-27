# Brands

## Parámetros


| Atributo              |   Tipo  |                                      Descripción                                      |
| ---------             | ------- | ------------------------------------------------------------------------------------- |
| `_id`                 | string  | Identificador de la marca                      |
| `dafiti`             	| string  | Nombre de la marca en Dafiti     |
| `linio`            	| string  | Nombre de la marca en Linio         |
| `mercadolibre`        | string  | Nombre de la marca en Mercado Libre|
| `name`         		| string  | Nombre de la marca en Centry|
| `updated_at`          | string  | Registro de última actualización |
| `vestirsebien`        | string  | Nombre de la marca en VestirseBien |



## Todas las Marcas 

Este endpoint entrega todas las marcas de Centry

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/brands </h6>
  </div>
</div>



```shell
curl "https://www.centry.cl/conexion/v1/brands.json"/
 -H "Authorization: Bearer  <Access_code> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[

	{
        "_id": "57f63ffe4c266d1dec1edfb6",
        "created_at": "2016-08-28T16:21:37.882Z",
        "dafiti": "Bata",
        "linio": null,
        "mercadolibre": null,
        "name": "Bata",
        "updated_at": "2016-08-28T16:21:37.882Z",
        "vestirsebien": null
    },
    {
        "_id": "58124d68fd246926928fed3c",
        "created_at": "2016-10-01T19:35:14.734Z",
        "dafiti": "Bobbies",
        "linio": "Bobbies",
        "mercadolibre": "Bobbies",
        "name": "Bobbies",
        "updated_at": "2016-10-01T19:35:14.734Z",
        "vestirsebien": null
    }
    ]


```


## Obtener una Categoria específica



Este endpoint entrega una categoria específico.

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/brands/<brand_id> </h6>
  </div>
</div>


```shell
curl "https://www.centry.cl/conexion/v1/brands/<brand_id>.json"/
 -H "Authorization: Bearer  <Access_code> "  > response.json
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
   
    {
        "_id": "58124d68fd246926928fed3c",
        "created_at": "2016-10-01T19:35:14.734Z",
        "dafiti": "Bobbies",
        "linio": "Bobbies",
        "mercadolibre": "Bobbies",
        "name": "Bobbies",
        "updated_at": "2016-10-01T19:35:14.734Z",
        "vestirsebien": null
    }


```



### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`brand_id` | El identificador de la orden a recuperar



