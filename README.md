
# Conversor de Divisas en Java

Este proyecto es parte de una tarea para la materia de **Lenguajes de Programación** en el **Técnico Superior Universitario (TSU) en Servicios en la Nube**, ciclo 3. La aplicación permite convertir cantidades entre dos monedas utilizando la API de [ExchangeRate-API](https://www.exchangerate-api.com/).

## Descripción

La aplicación solicita al usuario ingresar:

1. La moneda de origen (por ejemplo, USD).
2. La moneda de destino (por ejemplo, EUR).
3. La cantidad a convertir.

Luego, realiza una solicitud HTTP a la API de ExchangeRate para obtener la tasa de cambio actual entre las dos monedas, y calcula la cantidad convertida. Los datos de respuesta de la API se procesan usando la librería Gson, que convierte el JSON a un objeto Java.

## Funcionalidades

- Conversión de divisas en tiempo real.
- Uso de la API REST para obtener los tipos de cambio.
- Procesamiento de JSON con la librería Gson.

## Requisitos

- **Java 8** o superior
- Conexión a Internet
- Clave API de [ExchangeRate-API](https://www.exchangerate-api.com/) (requiere registro gratuito)

## Librerías Utilizadas

El proyecto utiliza la librería **Gson** para convertir las respuestas JSON de la API en objetos Java.

### Agregar Gson al proyecto

Si usas Maven, agrega esta dependencia a tu archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.8.8</version>
</dependency>
```

Si usas Gradle, agrega la siguiente línea a `build.gradle`:
```groovy
implementation 'com.google.code.gson:gson:2.8.8'
```

Si no usas un gestor de dependencias, puedes descargar la librería desde [aquí](https://mvnrepository.com/artifact/com.google.code.gson/gson).

## Ejecución del Proyecto

1. Clona o descarga este repositorio en tu máquina local.
2. Abre el proyecto en tu IDE de Java favorito (por ejemplo, IntelliJ IDEA o Eclipse).
3. Reemplaza la clave API en el archivo `App.java` con tu propia clave obtenida de [ExchangeRate-API](https://www.exchangerate-api.com/):
    ```java
    String apiKey = "TU_CLAVE_API";
    ```
4. Ejecuta el archivo `App.java`.

### Desde la Línea de Comandos:

Si prefieres compilar y ejecutar desde la terminal:

1. Compila el código:
   ```bash
   javac -cp gson-2.8.8.jar App.java
   ```
2. Ejecuta el programa:
   ```bash
   java -cp .:gson-2.8.8.jar App
   ```

## Uso

Al ejecutar el programa, se te pedirá ingresar la moneda de origen, la moneda de destino, y la cantidad a convertir. El programa devolverá la cantidad convertida con base en el tipo de cambio actual.

### Ejemplo de Ejecución:

```
Conversor de Divisas
====================
Introduce la moneda de origen (por ejemplo, USD): USD
Introduce la moneda de destino (por ejemplo, EUR): EUR
Introduce la cantidad a convertir: 100
La URL queda así: https://v6.exchangerate-api.com/v6/tu_clave_api/pair/USD/EUR
Cantidad convertida: 91.23 EUR
```

## Estructura del Código

- `App.java`: Contiene toda la lógica del programa, desde la interacción con el usuario hasta la solicitud a la API y el procesamiento de la respuesta.

## Errores Comunes

- **Clave API inválida**: Si tu clave API es incorrecta o ha expirado, recibirás un mensaje de error.
- **Conexión fallida**: Asegúrate de estar conectado a Internet para poder obtener los datos de la API.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT.
