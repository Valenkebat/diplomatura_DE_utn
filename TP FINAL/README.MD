# Trabajo integrador final. Curso data engineer UTN. Agosto - Septiembre 2024
## Proyecto
El objetivo de este proyecto es realizar una extracción de datos de temas musicales a partir
de la api de FM combinandola con la api de Spotify.
Se realiza una extraccion incremental particionada por fecha para llevar
el registro del mejor tema de los artistas que entran y salen del top 100 artistas. 
En las transformaciones se va a chequear si entró o no 100.
De la api de spotify se van a extraer datos del track, como la popularidad y la fecha del lanzamiento del album.
Adicionalmente se calcula la distancia media del promedio total de la popularidad.
## Fuentes de datos
* [API de FM](https://www.last.fm/api)
* [API de Spotify](https://spotipy.readthedocs.io/en/2.24.0/)
Para consumir la api de spotify se 
## Librerías
* [requests]
* [deltalake]
* [pyarrow]
* [spotipy]
* [python-dotenv]

