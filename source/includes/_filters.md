# Filters

La siguiente tabla contiene parámetros URL útiles al momento de enviar un request GET list, el cual termina en una lista detallada de los datos que se quieren obtener. La utilización de valores previamente conocidos pueden ayudar a los procesos de búsqueda y recopilación de información.

 Filtro       | Descripción                                     | Ejemplo
 ------------ | ----------------------------------------------- | -------
 `created_at`        | Fecha de creación exactamente igual al valor indicado    | https://www.centry.cl/conexion/v1/products.json?created_at=2017-09-13T21:00:00.000-03:00 
`created_at_gte` | Fecha de creación mayor o igual al valor indicado | https://www.centry.cl/conexion/v1/products.json?created_at_gte=2017-09-13T21:00:00.000-03:00
`created_at_lte` | Fecha de creación menor o igual al valor indicado | https://www.centry.cl/conexion/v1/products.json?created_at_lte=2017-09-13T21:00:00.000-03:00
`created_at_gt` | Fecha de creación mayor al valor indicado | https://www.centry.cl/conexion/v1/products.json?created_at_gt=2017-09-13T21:00:00.000-03:00
`created_at_lt` | Fecha de creación menor al valor indicado | https://www.centry.cl/conexion/v1/products.json?created_at_lt=2017-09-13T21:00:00.000-03:00
`updated_at` | Fecha de actualización exactamente igual al valor indicado | https://www.centry.cl/conexion/v1/products.json?updated_at=2017-09-13T21:00:00.000-03:00
`updated_at_gte` | Fecha de actualización mayor o igual al valor indicado | https://www.centry.cl/conexion/v1/products.json?updated_at_gte=2017-09-13T21:00:00.000-03:00
`updated_at_lte` | Fecha de actualización menor o igual al valor indicado | https://www.centry.cl/conexion/v1/products.json?updated_at_lte=2017-09-13T21:00:00.000-03:00
`updated_at_gt` | Fecha de actualización mayor al valor indicado | https://www.centry.cl/conexion/v1/products.json?updated_at_gt=2017-09-13T21:00:00.000-03:00
`updated_at_lt` | Fecha de actualización menor al valor indicado | https://www.centry.cl/conexion/v1/products.json?updated_at_lt=2017-09-13T21:00:00.000-03:00
`offset` | Cantidad de resultados que debe saltarse | https://www.centry.cl/conexion/v1/products.json?offset=20
`limit` | Cantidad máxima de resultados que debe mostrar | https://www.centry.cl/conexion/v1/products.json?offset=20&limit=30 o https://www.centry.cl/conexion/v1/products.json?limit=20
