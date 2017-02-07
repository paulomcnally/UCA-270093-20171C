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

**Instalar LoopbackJS**

    $ npm install -g loopback-cli

**Crear un API**

    $ lb

Usuario loopback

    {
      "email": "paulomcnallly@gmail.com",
      "password": "123456789"
    }

### video

https://www.youtube.com/watch?v=uVMX_zk0LzQ


### ACL

    {
      "accessType": "*",
      "principalType": "ROLE",
      "principalId": "$everyone",
      "permission": "DENY"
    }
