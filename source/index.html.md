---
title: Centry REST Api

language_tabs:
  - shell: cURL

toc_footers:
  - <a href='https://www.centry.cl'>Iniciar sesión para obtener una API Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - products 
  - orders
  - categories
  - brands
  - colors
  - sizes
  - doorkeeperapps
  - webhooks
  - errors

search: true
---

# Introduction

Bienvenido a la API de Centry. Puedes usar nuestra API para acceder a los endpoints, los que entregan variada
información sobre los recursos registrados en nuestra base de datos.

Puedes ver los códigos de ejemplo en la región oscura de la derecha y seleccionar el lenguaje de programación
que más te acomode en las pestañas que se encuentran en la parte superior.

# Authentication

Para poder interactuar desde tu aplicación con centry se debe solicitar las credenciales necesarias para que 
dicha conexión sea exitosa.
Dicho lo anterior se deben realizar los siguientes pasos.

## Primer paso ##
Ingresaremos a nuestro panel de [aplicaciones externas desde centry](https://www.centry.cl/oauth/applications)
Y le damos click a Nueva Aplicación.




![Configuración de llaves Centry REST API](images/appCentry1.png)

Se rellena el formulario que aparecerá para obtener las llaves de acceso. 

![Configuración de llaves Centry REST API](images/appCentry2.png)

Finalizado este paso tendremos las llaves necesarias para la conexión 

![Configuración de llaves Centry REST API](images/appCentry3.png)

Procedemos a autorizar estas credenciales, para obtener la llave de autorización

![Configuración de llaves Centry REST API](images/appCentry4.png)

## Segundo paso

Configurar la conexión en nuestra app.

>Para autorizar nuestra aplicación:
Debe realizar un Request POST a la url https://www.centry.cl/oauth/token

```shell
#comando para obtener codigo de autorización 

curl --data "client_id=<My_client_id>&client_secret=<My_client_secret>&redirect_uri<My_redirect_uri>&grant_type=authorization_code&code=<My_authorization_code>" https://www.centry.cl/oauth/token

```
> Ejemplo de respuesta JSON luego de ejecutar el comando anterior

```
{
"access_token":"fa56dff5a29c8...",
"token_type":"bearer",
"expires_in":7200,
"refresh_token":"c38eabc8f00...",
"created_at":1501020167
}
```


#### URL parameters ####

|   Parameter    |  Type  | Description                                                      |
|----------------|--------|------------------------------------------------------------------|
| `client_id`    | string | Tu id de cliente visto en el paso anterior <i class="label label-info">mandatory</i>            |
| `client_secret`| string | Id Secreto visto en el paso anterior <i class="label label-info">mandatory</i>                                                                        |
| `redirect_uri` | string | Dirección de redirección luego de consulta <i class="label label-info">mandatory</i> |
| `grant_type`   | string | Llave de autorización (authorization_code)<i class="label label-info">mandatory</i>                                                                             |
| `code`         | string | Llave de autorización (authorization_code) <i class="label label-info">mandatory</i>                                                |




