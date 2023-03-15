- [Introducción](#introducción)
- [Backend](#backend)
- [Ejecución y Reporte del experimento](#ejecución-y-reporte-del-experimento)

# Introducción
Este experimento tiene como objetivo validar el efecto de la implementación de un componente Autenticador asociado al microservicio de Ventas de la aplicación, permitiendo que mediante el uso de la librería JWT sea posible controlar los accesos a este componente y garantizar el cumplimiento del requisito de calidad estipulado, en este caso, la seguridad.

# Backend
```pip3 install -r requirements.txt```

# Ejecución y Reporte del experimento
Para la ejecución del experimento y posterior reporte es necesario instalar las librerias de npm *newman-reporter-html* y *newman-reporter-htmlextra*

```npm install -g  newman-reporter-html```

```npm install -g  newman-reporter-htmlextra```

Se creó una colección de peticiones en Postman en donde se incluyeron los siguientes escenarios:
-NO_TOKEM
-TOKEN_EXPIRADO
-TOKEN_INVALIDO
-TOKEN_VALIDO

Para cada una de estas peticiones se configuró un test a través del cual se validó el status code obtenido por la petición.

El archivo de la colección Seguridad.postman_collection.json fue cargado al repositorio y puede usarse para futuras pruebas teniendo en cuenta que el token utilizado en la petición de TOKEN_VALIDO debe actualizarse por un token valido.

La colección creada en Postman debe guardarse en la raiz del repositorio.

Desde el directorio raíz del repositorio, ejecutar el siguiente comando:

```newman run Seguridad.postman_collection.json -e environment.postman_environment.json -n 2 -r htmlextra```

Al terminar la ejecución se generará una carpeta llamada *newman* que contiene un archivo *html* con los resultados de la prueba.

Al abrir el archivo html es posible visualizar el número de las peticiones exitosas y el detalle de la información enviada y recibida 
