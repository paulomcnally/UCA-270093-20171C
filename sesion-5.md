# Unidad I - Creación de un API REST

# Temas, subtemas

* ACL (Acceso a control de listas)
* Autenticación.
* Registro de usuario.
* Aspectos de seguridad.
* Deploy.

# Actividades de Aprendizaje

* Conferencia.
* Taller práctico.

### ACL ([Lista de control de acceso](https://es.wikipedia.org/wiki/Lista_de_control_de_acceso))

Denegar el acceso a todos los recursos del API par todos los usuarios. [Ver ejemplo](https://github.com/Informante/api/blob/master/common/models/post.json#L61)

    {
      "accessType": "*",
      "principalType": "ROLE",
      "principalId": "$everyone",
      "permission": "DENY"
    }

Permitir un acceso a un método especifico siempre y cuando sea un usuario duseño del registro.

> Para usar $owner debe existir un campo user_id y una relación con el modelo User.

    {
      "accessType": "READ",
      "principalType": "ROLE",
      "principalId": "$owner",
      "permission": "ALLOW",
      "property": "create"
    }

Permitir un acceso a un método especifico siempre y cuando sea un usuario autenticado.

> Para usar $authenticated debe enviar un accessToken a los métodos.

    {
      "accessType": "READ",
      "principalType": "ROLE",
      "principalId": "$authenticated",
      "permission": "ALLOW",
      "property": "create"
   }

### Aspectos de seguridad

https://loopback.io/doc/en/lb3/Security-considerations.html

### Deploy

Heroku Instalador | [Descargar](https://cli-assets.heroku.com/branches/stable/heroku-windows-amd64.exe)

Subir a heroku

    $ heroku git:remote -a api-...
    $ git add .
    $ git commit -m "mi api"
    $ git push heroku master

Heroku app

    Procfile

    web: npm start
