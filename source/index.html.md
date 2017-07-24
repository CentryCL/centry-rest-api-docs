---
title: API de Centry

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

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: tu_centry_api_key"

> Asegúrate de reemplazar `tu_centry_api_key` con tu API key.

Centry usa llaves para permitir el acceso a la API. Puedes registrar una nueva API key en nuestro 
[portal de desarrolladores](https://www.centry.cl/oauth/applications).

Centry espera que una API key sea incluída en todas las llamadas a la API en la cabecera de cada request tal como
lo muestra el ejemplo siguiente:

`Authorization: tu_centry_api_key`

<aside class="notice">
Debes reemplazar <code>tu_centry_api_key</code> con tu API key personal.
</aside>

