- [Introducción](#introducción)
- [Ejecución y Reporte del experimento](#ejecución-y-reporte-del-experimento)

# Introducción

# Ejecución y Reporte del experimento
Para la ejecución del experimento y posterior reporte es necesario instalar las librerias de npm *newman-reporter-html* y *newman-reporter-htmlextra*

```npm install -g  newman-reporter-html```

```npm install -g  newman-reporter-htmlextra```

Una vez instalados, desde el directorio raíz del repositorio, ejecutar el siguiente comando:

```newman run Seguridad.postman_collection.json -e environment.postman_environment.json -n 2 -r htmlextra```

Al terminar la ejecución se generará una carpeta llamada *newman* que contiene un archivo *html* con los resultados de la prueba.