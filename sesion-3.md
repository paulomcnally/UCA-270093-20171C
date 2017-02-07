# Unidad I

# Temas, subtemas

* ¿Qué es un API y para qué sirve?
* ¿Qué es Node.js y para qué sirve?
* Framework Strongloop  Loopback
* La terminal

# Actividades de Aprendizaje

* Conferencia.
* Taller práctico.

# Materiales (físicos, digitales, audiovisuales) y recursos, guías de aprendizaje

* LoopbackJS | [Ver sitio web](http://loopback.io/)
* LoopbackJS v3 Documentación | [Ver sitio web](http://loopback.io/doc/en/lb3/)
* NodeJS | [Ver sitio web](https://nodejs.org/es/)
* NodeJS Instalador v7.4.0 |  [Descargar](https://nodejs.org/dist/v7.4.0/node-v7.4.0-x64.msi)
* Atom Instalador | [Descargar](https://atom.io/)

**Instalar LoopbackJS - CLI**

    $ npm install -g loopback-cli

**Crear un API**

    $ lb

**Crear un modelo**

    $ lb model

**Crear una relación entre modelos**

    $ lb relation

**Correr/ejecutar el API**

    $ npm start

**Parámetros para crear un usuario e iniciar sesión**

    {
      "email": "paulomcnallly@gmail.com",
      "password": "123456789"
    }

### Hangout sobre LoopbackJS

https://www.youtube.com/watch?v=uVMX_zk0LzQ


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
      "principalId": "$owner",
      "permission": "ALLOW",
      "property": "create"
    }
