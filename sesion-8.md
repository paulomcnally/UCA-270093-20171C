# Unidad II - Conección a un API REST con Android

# Temas, subtemas

* Instalación de librerias.
* Creación de clases para la comunicación con el API.

# Actividades de Aprendizaje

* Conferencia.
* Taller práctico.

**Librería - (Retrofit)**

https://square.github.io/retrofit/

    compile 'com.squareup.retrofit2:retrofit:2.1.0'

**Api.java**

    public class Api {
        private final static String URL = "http://api.com";

        public static String getBase() {
            return URL + "/";
        }
    }

**ApiInterface.java**

    public interface ApiInterface {

        @GET("/resource")
        Call<MyModel> getData();
    }

**Main.java**

    Retrofit retrofit = new Retrofit.Builder().baseUrl(Api.getBase()).build();

    ApiInterface apiInterface = retrofit.create(ApiInterface.class);

**Implementación**

    Call<MyModel> call = apiInterface.getData();

    call.enqueue(new Callback<MyModel>() {
                @Override
                public void onResponse(Call<MyModel> call, Response<MyModel> response) {
                    //...
                }

                @Override
                public void onFailure(Call<PersonModel> call, Throwable t) {
                    Log.e("Error", t.getMessage());
                }
            });
