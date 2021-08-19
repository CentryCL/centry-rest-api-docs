# Warehouse Priority

Las [configuraciones de integraciones](#integration-configs) usan este recurso
para determina de cuáles [bodegas](#warehouses) se tomará el stock a la hora de
sincronizar las cantidades disponibles de productos y variantes. Por otro lado,
cuando se registra una venta de ésta integración, se útiliza este recurso para
determinar de cuáles bodegas se debe hacer el descuento de stock.

En definitiva los Warehouse Priorities son un listado ordenado de bodegas con
los cuales se trabajara con una integración en particular.

Opcionalmente, los Warehouse Priorities pueden tener una referencia a una
sucursal o bodega si la integración de permite. Esto tiene dos útilidades:

1. Permite actualizar stock de productos y variantes directo a una bodega
específica de la integración.
2. Si desde el origen viene un pedido asociado a una bodega, por ejemplo en una
compra con retiro en tienda, entonces Centry respeta esa relación y usa ese
criterio a la hora de hacer el descuento de stock y no usa el criterio de
prioridades explicados en los párrafos anteriores

## Parámetros

Atributo                | Tipo    | Descripción                                                                            
----------------------- | ------- | ---------------------------------------------------------------------------------------
`_id`                   | string  | Identificador del recurso <i class="label label-info">sólo lectura</i>
`priority`              | integer | Prioridad de la bodega en la integración, donde `0` es la prioridad más alta y va decayendo en la medida que este número crece <i class="label label-info">sólo lectura</i>              
`location_id`           | string  | Identificador de la sucursal o bodega de destino en caso de que la integración lo permita <i class="label label-info">sólo lectura</i>
`integration_config_id` | string  | Identificado de IntegrationConfig al que está asociado <i class="label label-info">sólo lectura</i>
`warehouse_id`          | string  | Identificado de Warehouse al que está asociado <i class="label label-info">sólo lectura</i>
`c_at`                  | string  | Registro de creación en Centry <i class="label label-info">sólo lectura</i>
`u_at`                  | string  | Registro de última actualización <i class="label label-info">sólo lectura</i>          

## Todos los Warehouse Priorities

Este endpoint entrega todos los Warehouse Priorities de un Integration Config

```shell
curl "https://www.centry.cl/conexion/v1/integration_configs/5b042c94f82f45124d0681bd/warehouse_priorities.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
[
    {
        "_id": "5daf12011a61bb3434b4ddfb",
        "c_at": "2019-10-22T11:28:17.180-03:00",
        "deleted_at": null,
        "integration_config_id": "5b042c94f82f45124d0681bd",
        "location_id": null,
        "priority": 0,
        "u_at": "2019-10-22T11:28:17.180-03:00",
        "warehouse_id": "577eb7b8f82f456ef4000001"
    },
    {
        "_id": "611e8dc0b291750ba5654110",
        "c_at": "2021-08-19T12:58:40.234-04:00",
        "deleted_at": null,
        "integration_config_id": "5b042c94f82f45124d0681bd",
        "location_id": null,
        "priority": 1,
        "u_at": "2021-08-19T12:58:40.234-04:00",
        "warehouse_id": "5db064b421b3eb70da09551d"
    },
    {
        "_id": "611e8dc0b291750ba5654111",
        "c_at": "2021-08-19T12:58:40.248-04:00",
        "deleted_at": null,
        "integration_config_id": "5b042c94f82f45124d0681bd",
        "location_id": null,
        "priority": 2,
        "u_at": "2021-08-19T12:58:40.248-04:00",
        "warehouse_id": "5db064fabc46c0578f83ae4e"
    }
]
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/integration_configs/&lt;integration_config_id&gt;/warehouse_priorities.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro               | Descripción
----------------------- | ---------------------------------------------------
`integration_config_id` | El identificador de la configuración de integración

### Filtros comunes

Si se desean obtener resultados más específicos para este endpoint, se puede precisar la request agregando parámetros a la URL de la forma https://www.centry.cl/conexion/v1/integration_config/&lt;integration_config_id&gt;/warehouse_priorities.json?&lt;filter&gt;=&lt;valor&gt; como se muestra en el capítulo **Filters** al final de la documentación. Además, de ser necesario algunos filtros pueden ser concatenados de la forma https://www.centry.cl/conexion/v1/integration_config/&lt;integration_config_id&gt;/warehouse_priorities.json?&lt;filter&gt;=&lt;valor&gt;&&lt;filter&gt;=&lt;valor&gt;&...

## Obtener un Warehouse Priority específico

Este endpoint entrega un Warehouse Priority específico

```shell
curl "https://www.centry.cl/conexion/v1/integration_configs/5b042c94f82f45124d0681bd/warehouse_priorities/5daf12011a61bb3434b4ddfb.json"/
 -H "Authorization: Bearer  <access_token> "
```

> Lo anterior retorna un JSON estructurado de la siguiente manera:

```json
{
    "_id": "5daf12011a61bb3434b4ddfb",
    "c_at": "2019-10-22T11:28:17.180-03:00",
    "deleted_at": null,
    "integration_config_id": "5b042c94f82f45124d0681bd",
    "location_id": null,
    "priority": 0,
    "u_at": "2019-10-22T11:28:17.180-03:00",
    "warehouse_id": "577eb7b8f82f456ef4000001"
}
```

### HTTP Request

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6> https://www.centry.cl/conexion/v1/integration_configs/&lt;integration_config_id&gt;/warehouse_priorities/&lt;warehouse_priority_id&gt;.json </h6>
  </div>
</div>

### Parámetros URL

Parámetro               | Descripción
----------------------- | ---------------------------------------------------
`integration_config_id` | El identificador de la configuración de integración
`warehouse_priority_id` | El identificador del WarehousePriority
