# Sizes

## Parámetros


| Atributo                      |   Tipo  |                                      Descripción                                      |
| ---------                     | ------- | ------------------------------------------------------------------------------------- |
| `_id`                         | string  | Identificador del tamaño                    |
| `created_at`                  | string  | Regristro de creación del tamaño en Centry                     |
| `dafiti`                      | string  | Identificador de tamaño equivalente  en Dafiti                      |
| `linio`                       | string  | Identificador de tamaño equivalente en Linio               |
| `mercadolibre`                | string  | Identificador de tamaño equivalente en mercadoLibre     |
| `mercadolibre_attr_id`        | string  | Atributo tamaño en mercadoLibre       |   
| `name`                        | string  | Nombre de tamaño en Centry 						|
| `updated_at`                  | string  | Registro de última actualización 						|
| `vestirsebien`                | string  | Nombre de tamaño equivalente en VestirseBien |


## Todas las Tallas
Este endpoint entrega todas las tallas de Centry
### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/sizes </h6>
  </div>
</div>



```shell
curl "https://www.centry.cl/conexion/v1/sizes.json"/
 -H "Authorization: Bearer  <Access_code> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5851b0c2b2c85e8282262a3e",
        "created_at": "2016-10-01T00:00:00.000Z",
        "dafiti": "Tamaño Único",
        "linio": "Talla Única",
        "mercadolibre": "[{\"group\"=>\"73003\", \"id\"=>\"73003-69691c\"}]",
        "mercadolibre_attr_id": null,
        "name": "Tamaño Único",
        "updated_at": "2016-10-01T00:00:00.000Z",
        "vestirsebien": null
    },
    {
        "_id": "5851b0c2b2c85e8282262a3f",
        "created_at": "2016-10-01T00:00:00.000Z",
        "dafiti": "XXS",
        "linio": "XS",
        "mercadolibre": "[{\"group\"=>\"73003\", \"id\"=>\"73003-4e51ce\"}]",
        "mercadolibre_attr_id": null,
        "name": "XXS",
        "updated_at": "2016-10-01T00:00:00.000Z",
        "vestirsebien": null
    }
]


```


## Obtener una Talla específica



Este endpoint entrega una talla  específica

### HTTP Request
<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/sizes/<size_id> </h6>
  </div>
</div>


```shell
curl "https://www.centry.cl/conexion/v1/sizes/<size_id>.json"/
 -H "Authorization: Bearer  <Access_code> "  > response.json
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json

   {
        "_id": "5851b0c2b2c85e8282262a3f",
        "created_at": "2016-10-01T00:00:00.000Z",
        "dafiti": "XXS",
        "linio": "XS",
        "mercadolibre": "[{\"group\"=>\"73003\", \"id\"=>\"73003-4e51ce\"}]",
        "mercadolibre_attr_id": null,
        "name": "XXS",
        "updated_at": "2016-10-01T00:00:00.000Z",
        "vestirsebien": null
    }


```



### Parámetros URL

Parámtetro | Descripción
---------- | -----------
`size_id` | El identificador de la orden a recuperar




