# Autenticación

Para poder interactuar desde una aplicación con Centry se debe solicitar las credenciales necesarias para que
dicha conexión sea exitosa. Para lo anterior, se deben realizar los siguientes pasos.

## Crear una aplicación

Ingresar al panel de [aplicaciones externas de Centry](https://www.centry.cl/oauth/applications) y presionar
el botón "Nueva Aplicación".

![Configuración de llaves Centry REST API](images/appCentry1.png)

Se debe rellenar el formulario con los siguientes datos:

**Name:** <i class="label label-info">mandatory</i>

Nombre que se le quiera dar a la App. Es un campo de texto libre que pretende servir de ayuda al propietario
para recordar el uso que le está dando. Ej: "Mi App Android".

**Redirect uri:** <i class="label label-info">mandatory</i>

URI a la que se redireccionará cuando se solicite una autorización. En el capítulo **Autorización** se ve
en detalle el uso de esta URI, pero a modo de adelanto, tiene que ser una ruta que sea capaz de leer parámetros
que se le envíen vía GET y de ejecutar los pasos necesarios para completar el proceso de autorización. Es en ese
sentido que se recomienda habilitar una ruta dedicada a atender esta redirección.
Ej: `https://www.mi-website.com/centry/auth`.

Si se quiere probar localmente o correr en un ambiente en el que no se disponga de una URL fija, puede ingresar
`urn:ietf:wg:oauth:2.0:oob` como redirect URI. Esto va a requerir un par de pasos más por parte del usuario,
pero el efecto en el desempeño de la aplicación es exactamente el mismo.

**Scopes:**

No tiene utilidad por el momento. Se recomienda dejar en blanco.

![Configuración de llaves Centry REST API](images/appCentry2.png)

Una vez enviado el formulario, Centry generará un identificador y una clave secreta que serán las llaves
necesarias para las futuras conexiones.

![Configuración de llaves Centry REST API](images/appCentry3.png)

## Autorización

Hasta el minuto lo único que se tiene es una aplicación creada. Pero para que un cliente pueda usarla,
debe solicitar los primeros `access_token` y `refresh_token` en base a un código de que genera Centry
para cada ocasión. Este proceso se conoce como "Autorización".

Los pasos a seguir son los siguientes:

1. Ingresar al panel de [aplicaciones externas de Centry](https://www.centry.cl/oauth/applications).
2. Presionar el nombre de la aplicación.
3. Presionar el botón "Autorizar" que está bajo el título "Callback urls".
4. Confirmar la autorización presionando el botón "Autorizar".
5. Recuperar el código de actualización.
  * Si la app tiene la URI para hacer pruebas locales, entonces Centry mostrará en pantalla el código
    de autorización.
  * Si la app está configurada con una URL pública, entonces se redireccionará a la dirección informada
    en el campo `redirect_uri` y como un parámetro GET llamado `code`, se enviará el código de autorización.

![Configuración de llaves Centry REST API](images/appCentry4_2-4.png)
![Configuración de llaves Centry REST API](images/appCentry4_5.png)

> Request POST a la URL https://www.centry.cl/oauth/token

```shell
curl -X POST https://www.centry.cl/oauth/token \
  -H 'Content-Type: application/json' \
  -d '{
        "client_id" : "49fca0b1207097f29a21f12c96a1ce73b361ed354a40d1274d536ab7be4f921e",
        "client_secret" : "73b83c1b7d0257d500e203cb97767c5036c036b71be6b8ed07fa630579b3a3b2",
        "redirect_uri" : "urn:ietf:wg:oauth:2.0:oob",
        "grant_type" : "authorization_code",
        "code" : "770e0c559a2aacee72dd98d573fdeeda3615ef529011c6731fe4592ad327427f"
      }'
```

> Ejemplo de respuesta JSON luego de ejecutar el comando anterior

```json
{
  "access_token":"ae7a9cecd01b346cfb7e6f196b948d8a63cb37f7feae38c4f4a2a31eca27c985",
  "token_type":"bearer",
  "expires_in":7200,
  "refresh_token":"64ab90f5675b0230677a10db46f52f66989e860f534fe92f23329f0e91d76ff5",
  "created_at":1515418927
}
```

Luego, desde el cliente que hará uso de la API, se completa el proceso de autorización enviando vía
POST a la URL `https://www.centry.cl/oauth/token` los siguientes parámetros:.

|   Parámetro    |  Tipo  | Descripción                                                                           |
|----------------|--------|---------------------------------------------------------------------------------------|
| `client_id`    | string | Identificador de la aplicación <i class="label label-info">mandatory</i>              |
| `client_secret`| string | Llave secreta de la aplicación <i class="label label-info">mandatory</i>              |
| `redirect_uri` | string | Dirección de redirección <i class="label label-info">mandatory</i>                    |
| `grant_type`   | string | Valor fijo igual a `authorization_code` <i class="label label-info">mandatory</i>     |
| `code`         | string | Código de autorización (authorization_code) <i class="label label-info">mandatory</i> |

De la respuesta que entregue la API, es importante registrar el `access_token` y `refresh_token`. El primero servirá
para firmar todas las solicitudes que se hagan a la API, mientras que el segundo servirá para solicitar un nuevo
`access_token` cuando el actual caduque.

## Renovar los tokens

>  Request POST a la URL https://www.centry.cl/oauth/token

```shell
curl -X POST https://www.centry.cl/oauth/token \
  -H 'Content-Type: application/json' \
  -d '{
        "client_id" : "49fca0b1207097f29a21f12c96a1ce73b361ed354a40d1274d536ab7be4f921e",
        "client_secret" : "73b83c1b7d0257d500e203cb97767c5036c036b71be6b8ed07fa630579b3a3b2",
        "redirect_uri" : "urn:ietf:wg:oauth:2.0:oob",
        "grant_type" : "refresh_token",
        "refresh_token" : "64ab90f5675b0230677a10db46f52f66989e860f534fe92f23329f0e91d76ff5"
      }'
```

> Ejemplo de respuesta JSON luego de ejecutar el comando anterior

```json
{
  "access_token":"e0b40212ad1f062aafe375ca1a570302940f6e223f164b8aeae108669411c3ef",
  "token_type":"bearer",
  "expires_in":7200,
  "refresh_token":"ea4d55434305f4929ee4dd3080039022912ad14d9fe7751ec7aea233aaca6277",
  "created_at":1515421188
}
```
El `access_token` expira cada 7200 segundos (2 horas) por lo que pasado ese periodo cualquier solicitud que se intente
hacer con esas credenciales, la API responderá con un error 401.

Lo que se debe hacer es solicitar un nuevo `access_token` a partir del `refresh_token`, esto se hace enviando a la URL
`https://www.centry.cl/oauth/token` los siguientes datos vía POST:

|   Parámetro    |  Tipo  | Descripción                                                                         |
|----------------|--------|-------------------------------------------------------------------------------------|
| `client_id`    | string | Identificador de la aplicación <i class="label label-info">mandatory</i>            |
| `client_secret`| string | Llave secreta de la aplicación <i class="label label-info">mandatory</i>            |
| `redirect_uri` | string | Dirección de redirección <i class="label label-info">mandatory</i>                  |
| `grant_type`   | string | Valor fijo igual a `refresh_token` <i class="label label-info">mandatory</i>        |
| `refresh_token`| string | Último `refresh_token` enviado por la API <i class="label label-info">mandatory</i> |

De la respuesta que entregue la API, es importante registrar el `access_token` y `refresh_token`. El primero servirá
para firmar todas las solicitudes que se hagan a la API, mientras que el segundo servirá para solicitar un nuevo
`access_token` cuando el actual caduque.
