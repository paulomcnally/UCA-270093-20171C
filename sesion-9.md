# Unidad II - Conección a un API REST con Android

# Temas, subtemas

* Instalación de librería.
* Autenticación de usuario.
* Registro de usuario.

# Actividades de Aprendizaje

* Conferencia.
* Taller práctico.

**Librería - (Remember)**

https://github.com/tumblr/Remember

    compile (group: 'com.tumblr', name: 'remember', version: '1.0.0', ext: 'aar')

**MyApplication.java**

    @Override
    public void onCreate() {
        super.onCreate();
        Remember.init(getApplicationContext(), "com.foo.bar");
    }


**Ejemplo de Remember**

    Remember.putString("some key", "some value");
    String value = Remember.getString("some key", "");

**Recurso creación de usuario**

    Users

**Recurso de inicio de sesión de usuario**

    Users/login

**Campos modelo usuario**

    {
      "id": 1
      "email": "paulomcnallly@gmail.com",
      "password": "123456789",
      "ttl": 31449600
    }

**Campos modelo AccessToken**

    {
      "id": "1Yv96vnG7Ek02uwMATH1cFDVsjEPDkFhgwdREFOR89Du2BnHsf7LYLbeuN4e1xFk",
      "ttl": 31449600,
      "created": "2017-02-27T19:55:52.515Z",
      "userId": 1
    }
