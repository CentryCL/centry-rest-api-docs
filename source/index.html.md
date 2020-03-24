---
title: Centry REST Api

language_tabs:
  - shell: cURL

toc_footers:
  - <a href='https://www.centry.cl'>Iniciar sesión para obtener una API Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - authentication
  - products
  - variants
  - warehouses
  - variant_warehouses
  - location_countries
  - location_regions
  - location_cities
  - location_communes
  - orders
  - categories
  - brands
  - colors
  - sizes
  - integration_configs
  - company
  - user
  - webhooks
  - errors
  - filters

search: true
---

# Introducción

Bienvenido a la API de Centry. Puedes usar nuestra API para acceder a los endpoints, los que entregan variada
información sobre los recursos registrados en nuestra base de datos.

Puedes ver los códigos de ejemplo en la región oscura de la derecha y seleccionar el lenguaje de programación
que más te acomode en las pestañas que se encuentran en la parte superior.

Para descargar esta documentación y probarla vía postman descárgala en el siguiente link 

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/49f16248109c2795d7a0#?env%5BCentry%20Enviroment%20%5D=W3sia2V5IjoiQXBwX0lEIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlfSx7ImtleSI6IlNlY3JldF9LZXkiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWV9LHsia2V5IjoiQ2FsbGJhY2tfVVJMIiwidmFsdWUiOiJ1cm46aWV0Zjp3ZzpvYXV0aDoyLjA6b29iIiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJBdXRob3JpemF0aW9uX0NvZGUiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWV9LHsia2V5IjoiQWNjZXNzX1Rva2VuIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlfSx7ImtleSI6IlJlZnJlc2hfVG9rZW4iLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWV9LHsia2V5IjoiVVJMX0Jhc2UiLCJ2YWx1ZSI6Imh0dHBzOi8vd3d3LmNlbnRyeS5jbCIsImVuYWJsZWQiOnRydWV9XQ==)