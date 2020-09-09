# BuyerRates

## Parámetros

Atributo      | Tipo    | Descripción                                                                            
------------- | ------- | -----------
`_id`         | string  | Identificador de la calificación del comprador <i class="label label-info">sólo lectura</i>
`name`        | string  | Nombre de la calificación del comprador en Centry <i class="label label-info">sólo lectura</i>
`description` | string  | Texto que describe con mayor detalle cada item <i class="label label-info">sólo lectura</i>

## Todas las calificaciones de comprador

Este endpoint entrega todas las calificaciones de comprador de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/buyer_rates.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un Jcalificación del compradorSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5e4d26431a61bb54b678a15b",
        "name": "Neutra",
        "description": "No es posible calificar al comprador o es indiferente"
    },
    {
        "_id": "5e4d26431a61bb54b678a15d",
        "name": "Negativa",
        "description": "No es un un buen comprador."
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/buyer_rates.json </h6>
  </div>
</div>

## Obtener una calificación de comprador específica

Este endpoint entrega una calificación de comprador específica.

```shell
curl "https://www.centry.cl/conexion/v1/buyer_rates/5e4d26431a61bb54b678a15b.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "5e4d26431a61bb54b678a15b",
  "name": "Neutra",
  "description": "No es posible calificar al comprador o es indiferente"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/buyer_rates/&lt;buyer_rate_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro       | Descripción
--------------- | -----------
`buyer_rate_id` | El identificador de la calificación del comprador a recuperar
