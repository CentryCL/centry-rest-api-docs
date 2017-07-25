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





## Todos los Productos de la cuenta


```shell
curl "https://www.centry.cl/conexion/v1/products"
  -H "Authorization: tu_centry_api_key"
```