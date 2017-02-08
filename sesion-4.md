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

   Método con lógica de negocio
