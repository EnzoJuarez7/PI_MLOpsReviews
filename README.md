#                                                              PI_MLOpsReviews

## Introducción

Proyecto de Machine Learning Operations (MLOps) en Soy Henry. En este proyecto, tendremos acceso a fuentes de información asociadas a las principales plataformas de streaming, incluyendo Amazon Prime Video, Disney Plus, Hulu y Netflix. Además, contaremos con ocho conjuntos de datos de ratings que contienen las puntuaciones que los usuarios han otorgado a ciertas películas.

## Rol a desarrollar
Soy un Data Scientist que acaba de unirse a una start-up que ofrece servicios de agregación de plataformas de streaming. Me he enfrentado a mi primera tarea: crear un sistema de recomendación que aún no ha sido implementado en la empresa. Pero al revisar los datos disponibles, me he dado cuenta de que la madurez de los mismos es nula. Los datos están sin procesar y no hay procesos automatizados para actualizar nuevos contenidos.

En este README, te guiaré en todo el proceso desde cero. Comenzaremos por limpiar los datos, explorar los datos y prepararlos para su uso en el modelo de aprendizaje automático en la API.


## Pasos realizados en el proyecto:

- ##### Se realiza un breve EDA (Analisis Exploratorio de Datos).

- #### Una vez analizados los datos se procede con un ETL (Extracción, Transformación y Carga) de dichos datos.
https://github.com/EnzoJuarez7/PI_MLOpsReviews/blob/main/ETL.ipynb

#### Realizar las siguientes transformaciones:

- Generar campo id: Cada id se compondrá de la primera letra del nombre de la plataforma, seguido del show_id ya presente en los datasets (ejemplo para títulos de Amazon = as123)

- Los valores nulos del campo rating deberán reemplazarse por el string “G” (corresponde al maturity rating: “general for all audiences”

- De haber fechas, deberán tener el formato AAAA-mm-dd

- Los campos de texto deberán estar en minúsculas, sin excepciones

- El campo duration debe convertirse en dos campos: duration_int y duration_type. El primero será un integer y el segundo un string indicando la unidad de medición de duración: min (minutos) o season (temporadas)


#### Se realiza un EDA máas completo  y extenso con los datos ya limpios.

#### Realizar las siguientes consultas a consumir en la API:

- Película (sólo película, no serie, etc) con mayor duración según año, plataforma y tipo de duración. La función debe llamarse get_max_duration(year, platform, duration_type) y debe devolver sólo el string del nombre de la película.

- Cantidad de películas (sólo películas, no series, etc) según plataforma, con un puntaje mayor a XX en determinado año. La función debe llamarse get_score_count(platform, scored, year) y debe devolver un int, con el total de películas que cumplen lo solicitado.

- Cantidad de películas (sólo películas, no series, etc) según plataforma. La función debe llamarse get_count_platform(platform) y debe devolver un int, con el número total de películas de esa plataforma. Las plataformas deben llamarse amazon, netflix, hulu, disney.

- Actor que más se repite según plataforma y año. La función debe llamarse get_actor(platform, year) y debe devolver sólo el string con el nombre del actor que más se repite según la plataforma y el año dado.

- La cantidad de contenidos/productos (todo lo disponible en streaming) que se publicó por país y año. La función debe llamarse prod_per_county(tipo,pais,anio) deberia devolver la cantidada de contenidos/productos segun el tipo de contenido (pelicula,serie) por pais y año en un diccionario con las variables llamadas 'pais' (nombre del pais), 'anio' (año), 'pelicula' (cantidad de contenidos/productos).

- La cantidad total de contenidos/productos (todo lo disponible en streaming, series, peliculas, etc) según el rating de audiencia dado (para que publico fue clasificada la pelicula). La función debe llamarse get_contents(rating) y debe devolver el numero total de contenido con ese rating de audiencias.

https://github.com/EnzoJuarez7/PI_MLOpsReviews/blob/main/main.py

#### Testeo de funcionamiento de las consultas y el modelo de Machine Learning.
https://github.com/EnzoJuarez7/PI_MLOpsReviews/blob/main/Consultas_recomendacion_prueba.ipynb

#### Se procede a generar el deploy de la API en Render
https://mlopsreviews-deploy.onrender.com/docs#/
