# Unidad I

# Temas, subtemas

* Protocolo de comunicación.
* Creación de un API cos LoopbackJS. | [Ver sesión 3](session-3.md)
* Creación de modelos. | [Ver sesión 3](session-3.md)

# Actividades de Aprendizaje

* Conferencia.
* Taller práctico.

Métodos HTTP

| HTTP Verb     | CRUD                  |
| ------------- |:---------------------:|
| POST          | Crear                 |
| GET           | Leer                  |
| PUT           | Actualizar/reemplazar |
| PATCH         | Actualizar/modificar  |
| DELETE        | Eliminar              |

Códigos de estado HTTP

https://es.wikipedia.org/wiki/Anexo:C%C3%B3digos_de_estado_HTTP


Método con lógica de negocio



datasources.production.js

    module.exports = {
      database: {
        url: process.env.DATABASE_URL,
        connector: 'postgresql'
      }
    }

Agregar connector

    $ npm install loopback-connector-postgresql --save

Loopback auto

   https://github.com/nodenica/grunt-loopback-auto

Gruntfile.js

    module.exports = function(grunt) {
      grunt.initConfig({
        'loopback_auto': {
          'db_autoupdate': {
            options: {
              dataSource: 'database',
              app: './server/server',
              config: './server/model-config',
              method: 'autoupdate'
            }
          },
          'db_automigrate': {
            options: {
              dataSource: 'database',
              app: './server/server',
              config: './server/model-config',
              method: 'automigrate'
            }
          }
        }
      });
      // Load the plugin
      grunt.loadNpmTasks('grunt-loopback-auto');
      grunt.registerTask('default', ['loopback_auto']);
    };

Instalar grunt

    $ npm install grunt --save-dev

Instalar grunt cli

    $ npm install grunt-cli -g

Instalar conector postgresql

    $ npm install loopback-connector-postgresql --save
