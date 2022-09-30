# TP2 - Spark

## Spark (10 <img src="imgs/1c2022/luisito64.jpg" />)

Vamos a utilizar como dataset los csvs de [esta carpeta](https://drive.google.com/drive/folders/1Bj3Zv5KWzNOgJW9fDM2QWGn1HIelvwov?usp=sharing). Es una mezcla del dataset de “the movie database” para 45mil películas y datos de imdb.

Los parquets son:

* movies
  * adult: 😏🥵
  * belongs_to_collection: Nombre de la colección a la que pertenece la película
  * budget: presupuesto
  * genres: géneros separados por coma
  * homepage: web de la peli
  * id: id de la peli
  * imdb_id: id de la película en imdb
  * original_language: idioma original
  * original_title: título en el idioma original
  * overview: descripción de la película
  * popularity: popularidad
  * poster_path: ruta a la imagen del poster
  * production_companies: id de las empresas que produjeron la película, separadas por comas
  * production_countries: países donde se produjeron las películas
  * release_date: fecha de estreno
  * revenue: ingresos que generó
  * runtime: largo total en minutos
  * spoken_languages: idiomas que se hablan en la película
  * status: estado de la película
  * tagline: eslogan
  * title: título en inglés
  * video
  * vote_average: promedio de calificaciones
  * vote_count: cantidad de votos
* cast
  * id: id de película en la que participó
  * cast_id: id de la persona
  * character: personaje que hizo
  * name: nombre
* crew
  * id: id de la película en la que participó
  * crew_id: id de la persona
  * department: departamento en el que trabajo
  * job: título de su trabajo
  * name: nombre
* companies
  * id: id de la compañía
  * name: nombre
* keywords
  * id: id de la película
  * keywords: palabras clave separadas por coma
* ratings
  * userId: user que dejó el rating
  * movieId: película donde lo dejó
  * rating: el rating que dejó, del 1 al 5
  * timestamp: timestamp de cuando dejó el rating
* imdb_actors: Es un csv extra que sale de imdb que contiene información de muchos actores y actrices
  * nconst: id de la persona
  * primaryName: nombre
  * birthYear: año de nacimiento
  * deathYear: año de muerte
  * primaryProfession: profesiones principales separadas por comas
  * knownForTitles: ids de imdb por los cuales se lo conoce, separado por comas
* links
  * movieId: un ID único para cada película
  * imdbId: el id de imdb de esa película
  * tmdbId: el ID de “the movie database” que aparece en la mayoría de las otras tablas


### Consignas a realizar

❗⚠️ Debajo están las consignas del TP entero, deberá realizar **las que le toquen según la tabla que se encuentra al final**. ⚠️❗

Tienen asignados **1 ejercicio que vale un** <img src="imgs/1c2022/luisito.jpg" />, **3 que valen dos** <img src="imgs/1c2022/luisito.jpg" /> y **1 que vale tres** <img src="imgs/1c2022/luisito.jpg" />.

#### Ejercicios

* **S1** (<img src="imgs/1c2022/luisito.jpg" />). De las 10 películas más populares, ¿cuál es el título de la película que tiene más géneros asociados? ¿Cuáles son esos géneros?
* **S2** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre del actor o actriz que participó en más películas en un rol que no sea de voz (‘voice’)? ¿En cuántas películas trabajó? ¿De quién se trata y por qué es conocida?
* **S3** (<img src="imgs/1c2022/luisito.jpg" />). Para las películas que duran más de tres horas, ¿cuál es la película con más ROI?
* **S4** (<img src="imgs/1c2022/luisito.jpg" />). Para las películas que contienen el género de acción, si las separamos entre películas antes del 2000 y después del 2000, ¿cuál es el promedio de cantidad de votos para cada etapa?
* **S5** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre de la película con mayor cantidad de empleados contratados para trabajar en Efectos Visuales?
* **S6** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre de la película con mayor cantidad de empleados contratados para trabajar en Efectos Visuales?
* **S7** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál fue el año más mortal para los actores y actrices?
* **S8** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es la descripción con mayor ratio de stopwords?
* **S9** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es la entropía base 2 de la distribución del rating que dan los usuarios?
* **S10** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Se desea encontrar a los 10 usuarios menos objetivos. Se considera a un usuario poco objetivo cuando sus calificaciones a las películas están muy alejadas de la media.
* **S11** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Según los cinéfilos, ¿cuál es el rating promedio de las 5 películas más populares? Un usuario es cinéfilo cuando puntuó más de 50 películas y todas las puntuaciones son de más de 2.5 estrellas. Indicar id, título, popularidad y rating promedio de la película.
* **S12** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Top 10 películas Argentinas según vote_average que contengan el género drama con más de 100 reviews en ratings.csv (dar géneros, cantidad de ratings, título, y vote_average).
* **S13** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Si decimos que un usuario es adyacente a otro cuando le dieron un rating a una misma película. ¿Cuántos usuarios son adyacentes al 179792? ¿Cuántos son adyacentes a sus adyacentes?
* **S14** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el usuario cuya velocidad promedio para hacer ratings es mayor?
* **S15** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre del mejor actor o actriz de todos los que participaron en más de 10 películas? Se considera un actor mejor que otro cuando el promedio de las calificaciones promedio de las películas en las que participó es mayor que el de otro actor o actriz.
* **S16** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el género y la homepage de la película que tiene mayor cantidad de palabras claves?
* **S17** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuáles son los actores o actrices que hicieron más películas en una misma década según la década en la que más hicieron? ¿En qué posición del top está Nicolas Cage?
* **S18** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el género con más películas cada década? ¿Y la keyword para cada década?
* **S19** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Top 10 3-uplas de palabras más populares en las descripciones de las películas removiendo stopwords.
* **S20** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para las películas con exactamente 7 keywords, ¿cuál es la más popular?
* **S21** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para las películas que tengan en su descripción “in a world”(sin importar las mayúsculas) cuales son las 10 tuplas de palabras en sus descripciones más populares?
* **S22** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Nombre de la productora, película, popularidad, y id de productora, de la película más popular.
* **S23** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el usuario más pesimista (menor rating promedio) para cada género de películas? Considere solo usuarios con más de 20 reviews
* **S24** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Quién es el usuario con más y menos entropía base 2 de la distribución de ratings que hicieron? ¿Y el de menos? ¿Cuáles son esas distribuciones?
* **S25** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el percentil 95 de la popularidad?
* **S26** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Quién es el crew que trabajó en más tuplas (departamento, película) distintas?
* **S27** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuáles son las 10 keywords con mayor y menor distancia coseno respecto de las pelis en las que aparecen? Ignore las distancias que son 1 o 0.
* **S28** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos saber cual es el mayor fan de Brad Pitt. ¿Quién es la persona que mejor puntúa en las películas en las que aparece? Considerar las películas no puntuadas como con score 0.
* **S29** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Tenemos la teoría de que hay actores importantes que se odian pero no se sabe. Para los actores aún vivos o que murieron después del año 2000, hallar el par de actores que más compañías compartieron sin compartir películas.
* **S30** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Estimamos el sueldo de un actor como la inversión dividida entre la cantidad de actores. En base a esta estimación, ¿cuál es el actor con el patrimonio más grande?
* **S31** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Asesoramos a un inversionista de la industria cinematográfica y este necesita bajar el riesgo en sus actividades. Cual es el top 3 de compañías con el mayor ROI por película?
* **S32** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es la mediana de cantidad de crew para las películas? Calcular de forma distribuida.
* **S33** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Encuentre, para cada película, cuál es la más cercana en términos de distancia coseno respecto de las keywords. Muestre 5 pares aleatorios con sus descripciones.
* **S34** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) ¿Cuál es la probabilidad de que una película de un género en particular tenga una calificación promedio mayor a 3 (utilizando la tabla de ratings)? Obtenga las probabilidades de cada género posible.
* **S35** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Si consideramos la antigüedad de un usuario como la diferencia entre el tiempo en el que hizo el primer rating y la última. ¿Cúal es el usuario más antiguo? ¿Cúal es la correlación entre la antigüedad de cada usuario y la cantidad de reviews que hizo? Calcule la correlación de forma distribuida.
* **S36** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Uno tendería a pensar que mientras más personas participan de una película, más cara es. ¿Cuál es la correlación de Spearman entre estos números? Calcule de forma distribuida.
* **S37** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Dos películas se conectan si un usuario les hizo una rating a ambas. Considerando solo los usuarios que superen el percentil 90 de cantidad de ratings, ¿cuántos triángulos tiene el grafo de películas?
* **S38** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Dos películas se conectan si un usuario les hizo una rating a ambas. Considerando solo los usuarios que superen el percentil 90 de cantidad de ratings, ¿Cuál es la película con mayor centralidad en el grafo? Estime usando random walks.
* **S39** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Obtenga un vector que indique si una compañía trabajo/no trabajo en una película, para cada película. Para cada compañía utilice estos vectores para buscar cuál es la compañía más similar, utilizando la distancia coseno. Imprima toda la lista de tuplas (compañía, similar).

## Podio (hasta dos <img src="imgs/1c2022/luisito64.jpg" /><img src="imgs/1c2022/luisito64.jpg" />)

Utilizamos el promedio del puntaje normalizado de cada kahoot/parcialito para armar un podio. El podio se modificara a medida participen en los Kahoots. El primero recibe dos <img src="imgs/1c2022/luisito.jpg" /> extra y los próximos 4 primeros reciben un <img src="imgs/1c2022/luisito.jpg" /> extra.

## Criterio de aprobación

El criterio general es que la totalidad del tp tiene que sumar 6 puntos de los 10, es un 60%. Además todas las consignas deben estar desarrolladas, entregando algo en cada una.

Cada uno va a tener algún ayudante asignado, pueden hacer consultas por slack a su ayudante o en el canal.

### Criterio de reentrega

Se podrá reentregar el TP si el puntaje es >=4 y están **todos los puntos desarrollados**.  La reentrega consiste en hacer un punto extra y corregir todos los puntos donde tuvieran menos de la mitad de los puntos.

Se aprueba la reentrega si todos los puntos tienen al menos la mitad de los puntos. En caso de luego aprobar la instancia de reentrega, la nota es siempre 4.

### Spark

Todos los ejercicios valen lo mismo que los <img src="imgs/1c2022/luisito.jpg" /> que tienen asignados.

* Cada ejercicio se considera 100% correcto si:
  * Resuelve lo pedido (¡cuidado con casos bordes! ¡revisen todo lo que pueda ser NULL!): Si el ejercicio no resuelve al 100% lo pedido, se considera que vale como máximo la mitad.
    * Cada ejercicio deberá funcionar si los datos cambian, esto significa, por ejemplo, que no podemos buscar un valor en una tabla y copiar y pegar ese literal para buscar en otra. El código debe soportar que la respuesta cambie.
  * Lo hace de la forma más eficiente posible: Si el ejercicio no está resuelto de la forma más óptima, pierde la mitad de su valor.
* La idea es que no lo hagan solos! Las consignas son complejas de entender en una sola lectura y necesitan pensarse lento, por esto es que es crucial consultar. Para esto hacemos lo siguiente según el tipo de duda:
  * Dudas de consigna:
    * Van a poder consultar en el canal de slack #consultas-tp2, es MUY importante que antes de consultar vean si su duda no fue resuelta allí.
    * En caso de no haber sido resuelta previamente para organizarnos sigan el siguiente formato: "**codigo de consigna** - Su consulta...". De esta forma es más facil para todos buscar consultas del pasado, por ejemplo: "S7 - ¿Si un usuario hace dos veces review al mismo lugar, lo cuento una o dos veces?". **NO** se debe incluir código de resolución ni en la consulta ni interactuando con otres compañeres.
  * Dudas para saber si se puede usar alguna librería:
    * Se hacen en el mismo formato que las dudas de consigna.
  * Dudas de código y optimización:
    * Si son dudas generales de "cómo se hace algo en spark" se puede consultar en el canal de consultas o en las clases de consulta.
    * El resto de las dudas deben consultarse con su ayudante asignado.

## Formato de Entrega

La entrega es en Gradescope en formato PDF.

En el PDF deben indicar cada uno de los puntos que les tocó, colocando el enunciado de la consulta a resolver y el link al notebook donde está resuelta, como en el TP1.

## Asignaciones

Pendientes
