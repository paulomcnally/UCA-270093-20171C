# Unidad II - Conección a un API REST con Android

# Temas, subtemas

* Almacenar AccessToken de comunicación.
* Obtener una lista de registros.

# Actividades de Aprendizaje

* Conferencia.
* Taller práctico.

SessionUtil.java

      public class SessionUtil {

          public interface OnOpenActivity {
              void onOpen(boolean session);
          }

          public static final String ACCESS_TOKEN = "api_access_token";
          public static final String ACCESS_TOKEN_HEADER = "Authorization";

          private static OnOpenActivity listener;

          public void setListener(OnOpenActivity onOpenActivity) {
              listener = onOpenActivity;
          }

          public static String getAccessToken() {
              return Remember.getString(ACCESS_TOKEN, "");
          }

          public static boolean isActive() {
              return !getAccessToken().isEmpty();
          }

          public static void openActivity(Context context) {
              if (isActive()) {
                  listener.onOpen(false);
              } else {
                  Intent intent = new Intent(context, LoginActivity.class);
                  context.startActivity(intent);
              }
          }

          public static void close(Remember.Callback callback) {
              if (isActive()) {
                  Remember.remove(ACCESS_TOKEN, callback);
              }
          }
      }
