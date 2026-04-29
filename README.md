# Proyecto Final - Curso Data Engineer UTN

Este repositorio contiene el Trabajo Práctico Final del curso de Data Engineer de la UTN (Agosto - Septiembre 2024).

## Descripción del Proyecto

El objetivo principal es construir un pipeline de datos (ETL) que extrae, procesa y analiza información sobre los artistas más populares y sus temas destacados, combinando datos de múltiples fuentes.

El sistema realiza una **extracción incremental particionada por fecha** para monitorear el Top 100 de artistas y sus mejores canciones.

### Fuentes de Datos
* **[Last.fm API](https://www.last.fm/api):** Se utiliza para obtener el ranking de los 100 artistas más escuchados y sus temas principales.
* **[Spotify API](https://developer.spotify.com/documentation/web-api/):** Se utiliza para enriquecer la información con datos de popularidad de los tracks y fechas de lanzamiento de los álbumes.

## Arquitectura y Flujo de Datos

El proyecto sigue una arquitectura de datos moderna utilizando **Delta Lake**:

1.  **Extracción (Bronze):** Los datos crudos se extraen de las APIs y se almacenan en formato Delta, particionados por la fecha de extracción.
2.  **Transformación (Silver/Gold):** 
    * Se identifica la entrada y salida de artistas del Top 100.
    * Se calculan métricas de popularidad, como la distancia media al promedio total.
    * Se limpia y normaliza la información para su posterior análisis.

## Tecnologías Utilizadas

* **Lenguaje:** Python
* **Procesamiento de Datos:** Pandas, PyArrow
* **Almacenamiento:** Delta Lake (deltalake library)
* **APIs:** Requests (Last.fm), Spotipy (Spotify)
* **Gestión de Entorno:** Python-dotenv

## Estructura del Proyecto

* `TP FINAL/`: Carpeta principal del proyecto integrador.
    * `ValentinKebat_extracciones.ipynb`: Notebook con la lógica de ingesta y carga a la capa Bronze.
    * `ValentinKebat_transformaciones.ipynb`: Notebook con la lógica de limpieza y cálculo de métricas.
    * `utils.py`: Funciones auxiliares para interactuar con las APIs y Delta Lake.
    * `datalake/`: Directorio donde se almacenan las tablas Delta.
    * `requirements.txt`: Dependencias del proyecto.
* `ValentinKebat_TP1.ipynb`: Trabajo Práctico inicial del curso.

## Requisitos y Configuración

Para ejecutar este proyecto, necesitarás:

1.  Clonar el repositorio.
2.  Instalar las dependencias: `pip install -r "TP FINAL/requirements.txt"`.
3.  Configurar un archivo `.env` en la carpeta `TP FINAL/` con las siguientes credenciales:
    ```env
    clientID=tu_spotify_client_id
    apiKEY=tu_spotify_client_secret
    FM_API_KEY=tu_lastfm_api_key
    ```

---
**Autor:** Valentín Kebat
