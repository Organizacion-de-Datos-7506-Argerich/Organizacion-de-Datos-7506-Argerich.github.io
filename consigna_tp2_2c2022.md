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

|   Padrón | Alumno          |   Spark I |   Spark II |   Spark III |   Spark especial |   Puntos |Premio |
|---------:|:----------------|----------:|-----------:|------------:|-----------------:|---------:|-------:|
|   103878 | MEDONE SABATINI |      0.81 |       0.91 |        0.82 |             0.62 | 0.792857 | <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />|
|   105620 | BOUCHARD        |      0.74 |       0.72 |        0.58 |             1    | 0.759831 | <img src="imgs/1c2022/luisito.jpg" />|
|   107854 | HUTTIN          |      0.63 |       0.75 |        1    |             0.5  | 0.720662 | <img src="imgs/1c2022/luisito.jpg" />|
|   105190 | BARRETO         |      1    |       0.77 |        0.66 |             0.4  | 0.704921 | <img src="imgs/1c2022/luisito.jpg" />|
|   106160 | FABREGAS        |      0.86 |       0.94 |        0.34 |             0.53 | 0.665439 | <img src="imgs/1c2022/luisito.jpg" />|
|    97897 | FERRERO         |      0.66 |       0.64 |        0.64 |             0.65 | 0.645755 |-|
|   104084 | GRZEGORCZYK     |      0.77 |       0.2  |        0.97 |             0.58 | 0.626133 |-|

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

Ciertos grupos de colaboradores son un equipo, y como tal, deben contactarlos a todos juntos y no por separado.

* Ignacio Brusati y Juan Pablo Fresia
* Esteban Djeordijan y Alejo Caliz Blanco
* Julieta Ponti y Martín Stefanelli
* NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo
* Matias Fusco y Gabriel Semorile

<img src="https://i.gifer.com/GAf7.gif" />

|   Padron | Nombre                             | 1 - <img src="imgs/1c2022/luisito.jpg" />   | 2 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 3 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 4 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 5 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | Ayudante asignado                                   |
|---------:|:-----------------------------------|:--------|:---------|:---------|:---------|:----------|:----------------------------------------------------|
|   106870 | ADRIS, MARIO SANTIAGO              | S3      | S16      | S17      | S18      | S39       | Ignacio Brusati y Juan Pablo Fresia                 |
|   104498 | ALMADA, FRANCO MARTIN              | S4      | S19      | S23      | S11      | S32       | Natalia Golmar                                      |
|   106892 | AMBOAGE, JUAN PATRICIO             | S5      | S14      | S28      | S17      | S36       | Lucas Waisten                                       |
|   105190 | BARRETO, SEVERINO                  | S5      | S28      | S31      | S27      | S35       | Luis Argerich                                       |
|   108100 | BENITO, AGUSTÍN                    | S9      | S12      | S29      | S31      | S38       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   108225 | BERENGUEL IBARRA, RAFAEL FRANCISCO | S2      | S30      | S10      | S13      | S36       | Lucas Waisten                                       |
|   105620 | BOUCHARD, JOSUE ALEJANDRO          | S7      | S14      | S21      | S10      | S35       | Natalia Golmar                                      |
|    97640 | BRONDO, FACUNDO LUCIO              | S9      | S15      | S11      | S20      | S38       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   106691 | CAMPILLAY, EDGAR MATIAS            | S2      | S23      | S11      | S20      | S37       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   106359 | CAMURRI, FEDERICO ALFREDO          | S9      | S27      | S19      | S29      | S36       | Julieta Ponti y Martín Stefanelli                   |
|   108298 | CHACON SALEMME, IGNACIO ALEJANDRO  | S7      | S23      | S25      | S11      | S34       | Natalia Golmar                                      |
|   105907 | CHEN, NICOLAS                      | S7      | S18      | S19      | S29      | S35       | Julieta Ponti y Martín Stefanelli                   |
|    99879 | CLAROS CASTRO, ELVIS               | S4      | S10      | S29      | S22      | S35       | Esteban Djeordijan y Alejo Blanco                   |
|   102868 | CONTE GRAND, JOAQUIN               | S1      | S20      | S16      | S17      | S37       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   102104 | COSTA, LUCIANO                     | S2      | S24      | S14      | S21      | S33       | Esteban Djeordijan y Alejo Blanco                   |
|   107963 | CUEVAS, JUAN FRANCISCO             | S9      | S18      | S16      | S23      | S35       | Ignacio Brusati y Juan Pablo Fresia                 |
|   104098 | CUPPARI, FRANCO                    | S3      | S31      | S15      | S16      | S38       | Matias Rotondo                                      |
|   101830 | DE SANTIS, FEDERICO EZEQUIEL       | S6      | S31      | S15      | S21      | S38       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   106368 | DELLA VECCHIA, TOMAS               | S3      | S19      | S18      | S21      | S39       | Julieta Ponti y Martín Stefanelli                   |
|   107835 | DEMARCHI, IGNACIO                  | S5      | S29      | S25      | S23      | S39       | Ignacio Brusati y Juan Pablo Fresia                 |
|   105122 | DIAZ CALIXTO, LUZ MILAGROS         | S9      | S24      | S20      | S15      | S36       | Matias Fusco y Gabriel Semorile                     |
|   106308 | DUCA, FRANCISCO                    | S8      | S13      | S18      | S25      | S37       | Damian Martinelli                                   |
|   106295 | ENCINOZA VILELA, NATHALIA LUCIA    | S8      | S19      | S26      | S14      | S32       | Julieta Ponti y Martín Stefanelli                   |
|   105989 | ERLICH, IVAN                       | S7      | S24      | S27      | S26      | S34       | Ignacio Brusati y Juan Pablo Fresia                 |
|   103992 | ESPERON, RAMIRO                    | S1      | S25      | S10      | S22      | S34       | Gianmarco Cafferata                                 |
|   106160 | FABREGAS, ALEJO VALENTIN           | S7      | S26      | S28      | S12      | S32       | Damian Martinelli                                   |
|   103740 | FABREGAS, CAMILO EZEQUIEL          | S6      | S30      | S22      | S13      | S36       | Natalia Golmar                                      |
|    97261 | FARFAN LENCINA, NICOLAS RAFAEL     | S2      | S11      | S20      | S25      | S39       | Esteban Djeordijan y Alejo Blanco                   |
|    97897 | FERRERO, MANUEL                    | S3      | S21      | S28      | S24      | S36       | Luis Argerich                                       |
|   104354 | GALIAN, TOMAS EZEQUIEL             | S6      | S18      | S21      | S12      | S39       | Natalia Golmar                                      |
|   105043 | GARCIA PIZALES, IGNACIO            | S7      | S12      | S27      | S19      | S33       | Matias Fusco y Gabriel Semorile                     |
|   105552 | GENERAL, CAMILA                    | S5      | S29      | S21      | S10      | S33       | Damian Martinelli                                   |
|   101185 | GOIJMAN, LAUTARO ENZO              | S6      | S28      | S23      | S18      | S33       | Damian Martinelli                                   |
|   104503 | GORDYN BIELLO, GONZALO             | S5      | S13      | S15      | S14      | S32       | Matias Rotondo                                      |
|   104084 | GRZEGORCZYK, IVAN                  | S8      | S22      | S13      | S27      | S35       | Luis Argerich                                       |
|   107404 | HURTADO VARGAS, DANIEL ALEJANDRO   | S4      | S10      | S30      | S15      | S37       | Matias Rotondo                                      |
|   107854 | HUTTIN, FACUNDO TOMÁS              | S2      | S17      | S18      | S24      | S33       | Lucas Waisten                                       |
|   104424 | Joel Isaac Fernandez Fox           | S9      | S10      | S17      | S12      | S33       | Gianmarco Cafferata                                 |
|   107188 | KIM, DANIEL TOMAS                  | S6      | S15      | S16      | S17      | S34       | Natalia Golmar                                      |
|   103346 | Lautaro Rodriguez                  | S1      | S11      | S30      | S10      | S32       | Julieta Ponti y Martín Stefanelli                   |
|   100589 | LEGUIZAMON, VERONICA BEATRIZ       | S6      | S25      | S10      | S22      | S38       | Damian Martinelli                                   |
|   107825 | LIN, CRISTIAN MARTIN               | S5      | S20      | S31      | S19      | S33       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   105974 | MACKE, FRANCO                      | S1      | S12      | S14      | S28      | S35       | Gianmarco Cafferata                                 |
|   105645 | MARIÑO, ALEJO TOMÁS                | S7      | S20      | S26      | S18      | S35       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   101186 | Mauro Giampietri                   | S1      | S29      | S13      | S19      | S33       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   108294 | MAURO, CAROLINA LUCIA              | S1      | S21      | S13      | S26      | S39       | Esteban Djeordijan y Alejo Blanco                   |
|   101769 | MEDELA, MARIANO TOMAS              | S1      | S27      | S19      | S29      | S36       | Esteban Djeordijan y Alejo Blanco                   |
|   103878 | MEDONE SABATINI, JUAN IGNACIO      | S8      | S23      | S17      | S26      | S35       | Luis Argerich                                       |
|   108485 | MENDAÑA, JOAQUÍN                   | S9      | S14      | S28      | S30      | S37       | Matias Fusco y Gabriel Semorile                     |
|   107164 | MORANDI, FABRIZZIO LEONARDO        | S6      | S11      | S30      | S31      | S37       | Gianmarco Cafferata                                 |
|   106016 | Nicolás Vagó                       | S4      | S16      | S25      | S23      | S34       | Natalia Golmar                                      |
|   104881 | OLANO SOLEY, NICOLÁS GUILLERMO     | S3      | S16      | S20      | S31      | S34       | Natalia Golmar                                      |
|        0 | Pablo Serrati                      | S8      | S15      | S16      | S19      | S37       | Luis Argerich                                       |
|   103851 | PANACCIO, GUIDO DANIEL             | S4      | S22      | S24      | S30      | S32       | Matias Fusco y Gabriel Semorile                     |
|   108891 | PELLEGRINI, ANTONELLA JAZMÍ­N      | S8      | S25      | S11      | S20      | S38       | Damian Martinelli                                   |
|    91076 | PORRAS CARHUAMACA, SHERLY KATERIN  | S3      | S17      | S25      | S29      | S34       | Luis Argerich                                       |
|   108405 | PORRO, JOAQUIN                     | S4      | S22      | S24      | S15      | S32       | Julieta Ponti y Martín Stefanelli                   |
|    91561 | PRIETO, PABLO ALEJANDRO            | S7      | S23      | S26      | S21      | S33       | Luis Argerich                                       |
|   105167 | REGAZZOLI, IGNACIO                 | S8      | S17      | S22      | S28      | S34       | Luis Argerich                                       |
|   104677 | RIAL, TADEO EZEQUIEL               | S8      | S27      | S31      | S25      | S38       | Matias Fusco y Gabriel Semorile                     |
|   108267 | RODRIGUEZ JUSTO, IGNACIO           | S1      | S26      | S12      | S14      | S36       | Esteban Djeordijan y Alejo Blanco                   |
|   105318 | RODRIGUEZ, TOMAS GUSTAVO           | S3      | S28      | S24      | S16      | S32       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   103439 | SAGMAN, EMANUEL NICOLAS            | S3      | S15      | S12      | S24      | S39       | Damian Martinelli                                   |
|   105637 | SANTANDER, VALENTIN                | S2      | S21      | S11      | S28      | S37       | Ignacio Brusati y Juan Pablo Fresia                 |
|   103967 | SCAZZOLA, LARA                     | S4      | S13      | S23      | S30      | S37       | Natalia Golmar                                      |
|   106403 | SCAZZOLA, MARTIN                   | S2      | S31      | S27      | S16      | S34       | Gianmarco Cafferata                                 |
|   102110 | SCHEJTMAN, EZEQUIEL                | S9      | S17      | S14      | S20      | S38       | Luis Argerich                                       |
|    91979 | SEDEK, JORGE IGNACIO               | S4      | S14      | S18      | S30      | S39       | Matias Fusco y Gabriel Semorile                     |
|    98911 | TEJELO, FERNANDO MARTIN            | S5      | S26      | S22      | S24      | S38       | Gianmarco Cafferata                                 |
|    97819 | TORRES, LUCAS GABRIEL              | S2      | S12      | S26      | S11      | S36       | Ignacio Brusati y Juan Pablo Fresia                 |
|   103359 | TOSONI MARQUEZ, FRANCO             | S5      | S30      | S29      | S13      | S39       | Gianmarco Cafferata                                 |
