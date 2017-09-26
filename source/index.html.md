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
  - webhooks
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

## Obtener credenciales de acceso
Ingresar al panel de [aplicaciones externas desde centry](https://www.centry.cl/oauth/applications) y presionar
el botón "Nueva Aplicación".

![Configuración de llaves Centry REST API](images/appCentry1.png)

Se debe rellenar el formulario que aparecerá para obtener las llaves de acceso. 

![Configuración de llaves Centry REST API](images/appCentry2.png)

Finalizado este paso se obtienen las llaves necesarias para la conexión .

![Configuración de llaves Centry REST API](images/appCentry3.png)

El último paso es la autirización que consiste en obtener primer el "access token" y "refresh token" utilizando
el código aturización que genera Centry.

![Configuración de llaves Centry REST API](images/appCentry4.png)

## Solicitar acceso desde Aplicación

> Debe realizar un Request POST a la url https://www.centry.cl/oauth/token

```shell
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

### URL parameters

|   Parameter    |  Type  | Description                                                                                  |
|----------------|--------|----------------------------------------------------------------------------------------------|
| `client_id`    | string | Id de cliente visto en el paso anterior <i class="label label-info">mandatory</i>            |
| `client_secret`| string | Id Secreto visto en el paso anterior <i class="label label-info">mandatory</i>               |
| `redirect_uri` | string | Dirección de redirección luego de consulta <i class="label label-info">mandatory</i>         |
| `grant_type`   | string | Valor a solicitar `authorization_code` inicialmente<i class="label label-info">mandatory</i> |
| `code`         | string | Llave de autorización (authorization_code) <i class="label label-info">mandatory</i>         |

## Configurar Header 

```shell
curl -H "Authorization: Bearer fa56dff5a29c8..(access_token) " https://www.centry.cl/oauth/token
```

### Uso de acces_token

Por cada nueva solicitud de acceso que se quiera realizar, es importante configurar el Header del entorno.

## Renovar Acceso

>  Request POST a la url https://www.centry.cl/oauth/token

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

### URL parameters

|   Parameter    |  Type  | Description                                                                          |
|----------------|--------|--------------------------------------------------------------------------------------|
| `client_id`    | string | Id de cliente visto en el paso anterior <i class="label label-info">mandatory</i>    |
| `client_secret`| string | Id Secreto visto en el paso anterior <i class="label label-info">mandatory</i>s      |
| `redirect_uri` | string | Dirección de redirección luego de consulta <i class="label label-info">mandatory</i> |
| `grant_type`   | string | Volor fijo igual a `refresh_token` <i class="label label-info">mandatory</i>         |
| `refresh_token`| string | Se tenía guardado de la solicitud anterior <i class="label label-info">mandatory</i> |
