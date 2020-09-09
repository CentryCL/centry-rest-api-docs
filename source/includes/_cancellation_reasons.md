# CancellationReasons

## Parámetros

Atributo      | Tipo    | Descripción                                                                            
------------- | ------- | -----------
`_id`         | string  | Identificador del motivo de la cancelación <i class="label label-info">sólo lectura</i>
`name`        | string  | Nombre del motivo de la cancelación en Centry <i class="label label-info">sólo lectura</i>
`description` | string  | Texto que describe con mayor detalle cada item <i class="label label-info">sólo lectura</i>

## Todos los motivos de cancelación

Este endpoint entrega todos los motivos de cancelación de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/cancellation_reasons.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5e4d26431a61bb54b678a145",
        "_restock": "not_allowed",
        "name": "Sin stock",
        "description": "El producto se encuentra agotado."
    },
    {
        "_id": "5e4d26431a61bb54b678a14c",
        "_restock": "optional",
        "name": "Solicitud del cliente",
        "description": "Es el compardor el que ha decidido anular la compra"
    },
    {
        "_id": "5e4d26431a61bb54b678a153",
        "_restock": "optional",
        "name": "Demora en la entrega",
        "description": "Se ha retrasado en forma excesiva el despacho del pedido"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/cancellation_reasons.json </h6>
  </div>
</div>

## Obtener un motivo de cancelación específico

Este endpoint entrega un motivo de cancelación específico.

```shell
curl "https://www.centry.cl/conexion/v1/cancellation_reasons/5e4d26431a61bb54b678a145.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
  "_id": "5e4d26431a61bb54b678a145",
  "_restock": "not_allowed",
  "name": "Sin stock",
  "description": "El producto se encuentra agotado."
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/cancellation_reasons/&lt;cancellation_reason_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro                | Descripción
------------------------ | -----------
`cancellation_reason_id` | El identificador del motivo de la cancelación a recuperar
