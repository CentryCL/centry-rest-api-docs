# ConfirmationReasons

## Parámetros

Atributo      | Tipo    | Descripción                                                                            
------------- | ------- | -----------
`_id`         | string  | Identificador del motivo de la confirmación/división de pedido <i class="label label-info">sólo lectura</i>
`name`        | string  | Nombre del motivo de la confirmación/división en Centry <i class="label label-info">sólo lectura</i>
`description` | string  | Texto que describe con mayor detalle cada item <i class="label label-info">sólo lectura</i>

## Todos los motivos de confirmación/división

Este endpoint entrega todos los motivos de confirmación/división de Centry.

```shell
curl "https://www.centry.cl/conexion/v1/confirmation_reasons.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5e4d26431a61bb54b678a145",
        "name": "Frágil",
        "description": "Productos frágiles."
    },
    {
        "_id": "5e4d26431a61bb54b678a14c",
        "name": "Otro centro de distribución",
        "description": "Los productos tienen que ser despachados desde distintos orígenes."
    },
    {
        "_id": "5e4d26431a61bb54b678a153",
        "name": "Forma irregular",
        "description": "La forma de los productos impide enviarlos en un mismo paquete."
    },
    {
        "_id": "5e4d26431a61bb54b678a154",
        "name": "Dimensiones excedidas",
        "description": "Los productos no caben todos en un mismo bulto."
    },
    {
        "_id": "5e4d26431a61bb54b678a155",
        "name": "Otro motivo",
        "description": "Existen otros motivos por los cuales no todos los productos pueden ir en un mismo bulto."
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/confirmation_reasons.json </h6>
  </div>
</div>

## Obtener un motivo de confirmación/división específico

Este endpoint entrega un motivo de confirmación/división específico.

```shell
curl "https://www.centry.cl/conexion/v1/confirmation_reasons/5e4d26431a61bb54b678a145.json"/
 -H "Authorization: Bearer <access_token>"
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5e4d26431a61bb54b678a145",
    "name": "Frágil",
    "description": "Productos frágiles."
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/confirmation_reasons/&lt;confirmation_reason_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro                | Descripción
------------------------ | -----------
`confirmation_reason_id` | El identificador del motivo de la confirmación/división a recuperar
