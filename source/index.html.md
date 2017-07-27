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
  - errors

search: true
---

# Introducción

Bienvenido a la API de Centry. Puedes usar nuestra API para acceder a los endpoints, los que entregan variada
información sobre los recursos registrados en nuestra base de datos.

Puedes ver los códigos de ejemplo en la región oscura de la derecha y seleccionar el lenguaje de programación
que más te acomode en las pestañas que se encuentran en la parte superior.

# Autenticación

Para poder interactuar desde tu aplicación con centry se debe solicitar las credenciales necesarias para que 
dicha conexión sea exitosa.
Dicho lo anterior se deben realizar los siguientes pasos.

## Obtener credenciales de acceso ##
Ingresaremos a nuestro panel de [aplicaciones externas desde centry](https://www.centry.cl/oauth/applications)
Y le damos click a Nueva Aplicación.




![Configuración de llaves Centry REST API](images/appCentry1.png)

Se rellena el formulario que aparecerá para obtener las llaves de acceso. 

![Configuración de llaves Centry REST API](images/appCentry2.png)

Finalizado este paso tendremos las llaves necesarias para la conexión 

![Configuración de llaves Centry REST API](images/appCentry3.png)

Procedemos a autorizar estas credenciales, para obtener la llave de autorización

![Configuración de llaves Centry REST API](images/appCentry4.png)


## Solicitar acceso desde Aplicación
> ### Para autorizar nuestra aplicación:
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


Configurar la conexión en nuestra app.

### URL parameters ###

|   Parameter    |  Type  | Description                                                      |
|----------------|--------|------------------------------------------------------------------|
| `client_id`    | string | Tu id de cliente visto en el paso anterior <i class="label label-info">mandatory</i>    |
| `client_secret`| string | Id Secreto visto en el paso anterior <i class="label label-info">mandatory</i>           |
| `redirect_uri` | string | Dirección de redirección luego de consulta <i class="label label-info">mandatory</i> |
| `grant_type`   | string | Valor a solicitar `authorization_code` inicialmente<i class="label label-info">mandatory</i>       |
| `code`         | string | Llave de autorización (authorization_code) <i class="label label-info">mandatory</i>   |

## Configurar Header 

```shell
#comando para obtener codigo de autorización 


curl -H "Authorization: Bearer fa56dff5a29c8..(access_token) " https://www.centry.cl/oauth/token


```

### Uso de Acces_token
Por cada nueva solicitud de acceso que quieras realizar, es importante configurar el Header de nuestro entorno.

Realizando este paso el acceso tu aplicación estará garantizada.





## Renovar Acceso

> ### Para renovar el acceso de nuestra aplicación:
Debe voler a realizar un Request POST a la url https://www.centry.cl/oauth/token

```shell
#comando para renovar autorización 


curl --data "client_id=<My_client_id>&client_secret=<My_client_secret>&redirect_uri=urn:<My_redirect_uri>&grant_type=refresh_token&refresh_token=<My_previus_refresh_token>" https://www.centry.cl/oauth/token
```
> Ejemplo de respuesta JSON luego de ejecutar el comando anterior

```
{
"access_token":"64ad4cf7...",
"token_type":"bearer",
"expires_in":7200,
"refresh_token":"ea14ff30...",
"created_at":1501080163
}
```
Renovar solicitudes de acceso 

### URL parameters ###

|   Parameter    |  Type  | Description                                                      |
|----------------|--------|------------------------------------------------------------------|
| `client_id`    | string | Tu id de cliente visto en el paso anterior <i class="label label-info">mandatory</i>            |
| `client_secret`| string | Id Secreto visto en el paso anterior <i class="label label-info">mandatory</i>s |
| `redirect_uri` | string | Dirección de redirección luego de consulta <i class="label label-info">mandatory</i> |
| `grant_type`   | string | **Este valor cambia** a `refresh_token` <i class="label label-info">mandatory</i>   |
| `refresh_token`| string | Se tenía guardado de la solicitud anterior <i class="label label-info">mandatory</i> |



