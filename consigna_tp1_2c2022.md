# TP1 - Pandas y Visualización de datos

## Primera parte - Pandas (15 <img src="imgs/1c2022/luisito64.jpg" />)

Vamos a utilizar como dataset los csvs de [esta carpeta](https://drive.google.com/drive/folders/1fOBnuxITZSsbChHfmrvw8rQt_D_SyJ18). Es una mezcla del dataset de “the movie database” para 45mil películas y datos de imdb.

Los csvs son:

* Movies.csv
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
* review.csv
  * review_id
  * user_id
  * business_id
  * stars: entero entre 1 y 5
  * date
  * text: texto de la review
  * useful: cantidad de gente que la voto útil
  * funny: cantidad de gente que la voto divertida
  * cool: cantidad de gente que la votó como cool
* cast.csv
  * id: id de película en la que participó
  * cast_id: id de la persona
  * character: personaje que hizo
  * name: nombre
* crew.csv
  * id: id de la película en la que participó
  * crew_id: id de la persona
  * department: departamento en el que trabajo
  * job: título de su trabajo
  * name: nombre
* companies.csv
  * id: id de la compañía
  * name: nombre
* keywords.csv
  * id: id de la película
  * keywords: palabras clave separadas por coma
* ratings.csv
  * userId: user que dejó el rating
  * movieId: película donde lo dejó
  * rating: el rating que dejó, del 1 al 5
  * timestamp: timestamp de cuando dejó el rating
* imdb_actors.csv: Es un csv extra que sale de imdb que contiene información de muchos actores y actrices
  * nconst: id de la persona
  * primaryName: nombre
  * birthYear: año de nacimiento
  * deathYear: año de muerte
  * primaryProfession: profesiones principales separadas por comas
  * knownForTitles: ids de imdb por los cuales se lo conoce, separado por comas
* links.csv
  * movieId: un ID único para cada película
  * imdbId: el id de imdb de esa película
  * tmdbId: el ID de “the movie database” que aparece en la mayoría de las otras tablas

### Consignas a realizar

❗⚠️ Debajo están las consignas del TP entero, deberá realizar **las que le toquen según la tabla que se encuentra al final**. ⚠️❗

Tienen asignados **1 ejercicio que vale un** <img src="imgs/1c2022/luisito.jpg" />, **4 que valen dos** <img src="imgs/1c2022/luisito.jpg" /> y **2 que valen tres** <img src="imgs/1c2022/luisito.jpg" />. Además tienen almenos un ejercicio de compresión, visualizaciones y NLP.

#### Pandas y Python

* **P1** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuáles son las 5 lenguas en las que más ganancia neta genera la industria aproximado por los datos propuestos? y las 5 que menos? (ganancia neta = ganancia - inversión)
* **P2** (<img src="imgs/1c2022/luisito.jpg" />). De las 10 películas más populares, ¿cuál es el título de la película que tiene más géneros asociados? ¿Cuáles son esos géneros?
* **P3** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es la película con el mayor ratio ingreso por minuto? ¿Y el cortometraje? Dar nombres y ratios. Criterio: Película > 30min>= Cortometraje >= 5min.
* **P4** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre del actor o actriz que participó en más películas en un rol que no sea de voz (‘voice’)? ¿En cuántas películas trabajó? ¿De quién se trata y por qué es conocida?
* **P5** (<img src="imgs/1c2022/luisito.jpg" />). Para las películas que duran más de tres horas, ¿cuál es la película con más ROI?
* **P6** (<img src="imgs/1c2022/luisito.jpg" />). Para las películas que contienen el género de acción, si las separamos entre películas antes del 2000 y después del 2000, ¿cuál es el promedio de cantidad de votos para cada etapa?
* **P7** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es el porcentaje de películas que contienen a su título en la descripción?
* **P8** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre de la película con mayor cantidad de empleados contratados para trabajar en Efectos Visuales?
* **P9** (<img src="imgs/1c2022/luisito.jpg" />). De las películas que están siendo rumoreadas, ¿cuál es el título de la que presenta el presupuesto más alto?
* **P10** (<img src="imgs/1c2022/luisito.jpg" />). Calcular la probabilidad de que al seleccionar un actor del registro aún esté vivo/no se haya documentado su muerte.
* **P11** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cúal fue el año más mortal para los actores y actrices?
* **P12** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Se desea encontrar a los 10 usuarios menos objetivos. Se considera a un usuario poco objetivo cuando sus calificaciones a las películas están muy alejadas de la media.
* **P12** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Nombre de la película, cuyo género es solo comedia, que obtuvo el mayor rating puntuado por usuarios.
* **P13** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Según los cinéfilos, ¿cuál es el rating promedio de las 5 películas más populares? Un usuario es cinéfilo cuando puntuó más de 50 películas y todas las puntuaciones son de más de 2.5 estrellas. Indicar id, título, popularidad y rating promedio de la película.
* **P14** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Top 10 películas Argentinas según vote_average que contengan el género drama con más de 100 reviews en ratings (dar géneros, cantidad de reviews en ratings, título, y vote_average).
* **P15** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Si decimos que un usuario es adyacente a otro cuando le dieron un rating a una misma película. ¿Cuántos usuarios son adyacentes al 179792? ¿Cuántos son adyacentes a sus adyacentes?
* **P16** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es el usuario cuya velocidad promedio para hacer ratings es mayor?
* **P17** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Si consideramos la antigüedad de un usuario como la diferencia entre el tiempo en el que hizo el primer rating y la última. ¿Cúal es el usuario más antiguo? ¿Cúal es la correlación entre la antigüedad de cada usuario y la cantidad de reviews que hizo?
* **P18** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos saber quién de los 2 actores le gusta más a la gente, si Guillermo Francella o Ricardo Darin, para eso queremos saber quien tiene en promedio mejor vote_average en movies.csv.
* **P19** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre del mejor actor o actriz de todos los que participaron en más de 10 películas? Se considera un actor mejor que otro cuando el promedio de las calificaciones promedio de las películas en las que participó es mayor que el de otro actor o actriz.
* **P20** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es la probabilidad de que una película de un género en particular tenga una calificación promedio mayor a 7? Obtenga las probabilidades de cada género posible.
* **P21** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para las mil keywords más comunes, obtenga la matriz de correlación entre keywords.
* **P22** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). En las películas a veces se habla en otros idiomas distintos al original, ya sea de forma continua como en Inglorius Basterds o de forma aislada como el francés en el [fín de la película Jumanji](https://youtube.com/clip/Ugkx0O8Cm976gvWM0SOy08eHU_rwos0worDK). Para los 15 idiomas más comunes hablados en las películas muestre con un heatmap sencillo la matriz de correlación entre ellos.
* **P23** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la correlación entre la última review que recibió una película y la siguiente?
* **P24** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Qué película contiene más actores y actrices que murieron a los dos o menos años siguientes al estreno? ¿Tan mala fue la película?
* **P25** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el género y la homepage de la película que tiene mayor cantidad de palabras claves?
* **P26** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Uno tendería a pensar que mientras más personas participan de una película, más cara es. Realice un regression plot entre la cantidad de crew que trabajó en cada película y el presupuesto, removiendo todo lo que supere el percentil 96 para ambos números para evitar outliers. ¿Cuál es la correlación entre estos números?
* **P27** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). En todo el mundo el estado financia parcialmente al cine de las productoras locales. Una preocupación creciente es la existencia de ***ñoquis*** en las crew de las películas que son amigos o conocidos de la producción de las mismas a expensas de fondos del estado. La consultora “Espumadera” es una startup Argentina se dedica a encontrar posibles ***ñoquis*** para auditar en distintos contextos y tiene como clientes a organismos estatales de todo el mundo. Deseamos buscar anomalías para auditar en la crew de las películas, ¿Quienes superan el percentil 95 de producciones en las que participaron en roles distintos de directores, productores o escritores en el mismo año de estreno?
* **P28** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuáles son los actores o actrices que hicieron más películas en una misma década según la década en la que más hicieron? ¿En qué posición del top está Nicolas Cage?
* **P29** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Construya la matriz que dadas dos productoras la posición i,j contenga la cantidad de veces que la productora i trabajo con la productora j. Considere solo productoras con más de 5 películas. Obtenga con esa matriz la matriz de correlación. Responda:
  * ¿Cuáles son las 5 productoras que trabajaron con más productoras distintas?
  * ¿Cuáles son las productoras que siempre trabajan juntas?
* **P30** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el género con más películas cada década? ¿Y la keyword para cada década?
* **P31** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para las películas con ROI (Return of Investment) entre -10 y 10 consiga una serie que tenga como índice cada país donde se produjeron películas y como valores el promedio del ROI. ¿Cuáles son los 5 países más rentables para producir una película?
* **P32** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Al parecer hay personas que además de actuar en una película también trabajaron en ella desde algún otro rol. ¿Cuál de estas personas es la que más trabajos tuvo en una misma película? Indicar el nombre de la película, el nombre de la persona y la cantidad de trabajos que tuvo.
* **P33** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Estime la probabilidad de que, al seleccionar un rating al azar con y sin reposición, este usuario comparta alguna película vista con el 179792 que sea del mismo género que la película a la que le dejó rating.
* **P34** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Consideremos que una persona ingresa a la población de actores y actrices cuando nace y la abandona cuando muere. Grafique la serie de tiempo de población en función del año. Definimos la tasa de natalidad y mortalidad de actores y actrices como la proporción de nacimientos y muertes sobre la población del período en el cual nacieron o murieron. Grafique las tasas de mortalidad y natalidad en función del año.
* **P35** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos hacer una película que incluya al mejor empleado para cada categoría de la tabla crews como líder de equipo. Para los empleados que participaron en más de 5 películas considerando el promedio de ratings de las películas en las que participaron, ¿Cúal es el mejor de cada tupla (department, job)? Con este mismo criterio, consiga un top 5 de actores y top 5 de actrices para el elenco de la misma. Con este mismo criterio queremos también el tema de la película, ¿cuáles son las 4 mejores keywords?
* **P36** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Consiga una matriz cuyas columnas sean los cast id y crew ids (diferenciados para no colisionar), que tenga una fila por cada película y que los valores sean la cantidad de roles para los que esa persona participa en la película. Estime cuánto ocuparía en RAM teniendo en cuenta que cada número pesa 4 bytes, y en caso de no entrar construyala como matriz dispersa.
* **P37** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos estimar el patrón de ratings de usuarios nuevos usando un MRUV. La ecuación a estimar cantidad de ratings en función del tiempo Q(t) = 1 + v*t + (½)*a^2*t. ¿Qué correlación hay entre la aceleración y velocidad individual de cada usuario? Haga un scatter plot de aceleración y velocidad. ¿Qué valores de v y de a resultan de tomar las velocidades y aceleraciones promedio de todos los usuarios que dieran más de 10 ratings? Grafique la Q resultante en función de t. Grafique en otro plot las series de tiempo de 100 usuarios random para comparar que tan bueno es nuestro modelo.

#### NLP

* **N1** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la descripción con mayor ratio de stopwords?
* **N2** (<img src="imgs/1c2022/luisito.jpg" />). Removiendo stopwords, ¿Cúal es el top 10 stems más comunes?
* **N3** (<img src="imgs/1c2022/luisito.jpg" />). Removiendo stopwords, ¿Cúal es el top 10 lemmas más comunes?
* **N4** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es el top 10 adjetivos más comunes en las descripciones de las películas?
* **N4** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es el top 10 palabras con mayor popularidad promedio, sin contar stopwords?
* **N5** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es el top 10 palabras con mayor popularidad promedio, sin contar stopwords?
* **N6** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos predecir el género de la película según su descripción. Para esto vamos a buscar para una descripción nueva los 10 vecinos más cercanos y asignar el género que más se repita entre ellos. Pruebe este algoritmo para 5 películas al azar y para una descripción inventada que se le ocurra para una película nueva de Disney (su corrector valorará si logra hacerlo reír (? ).
* **N7** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Dado el ROI de las películas, para aquellas cuyo ROI (Return of Investment) esté entre -10 y 10. ¿Cúal es el top 10 palabras que aparecen más de 5 veces y no son stopwords que generan mayor ROI promedio según su aparición en las descripciones?
* **N8** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Encuentre, para cada película, cuál es la más cercana en términos de distancia coseno respecto de las keywords. Muestre 5 pares aleatorios con sus descripciones.
* **N9** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos analizar qué tan fácil sería hacer un slogan para las películas en base a su descripción con machine learning. La primera pregunta consiste en entender: ¿Qué porcentaje de las palabras que no son stopwords de las que aparecen en los slogans aparecen también en la descripción? ¿Y qué porcentaje de las tuplas de dos palabras cumplen eso? ¿Y tuplas de tres? A mayores los porcentajes, más fácil será generar el slogan con la descripción.
* **N10** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). La primera regla del club del cine es que no se habla del club del cine: queremos utilizar las reviews de las películas para emparejar personas cinéfilas. Dadas las descripciones de las películas que le gustaron (calificación >3) a un usuario y las que no le gustaron (calificación <3) construya dos vectores con tf-idf. Busque para cada usuario, utilizando la concatenación de estos vectores, al usuario más similar. No utilice los usuarios que tienen menos de 30 reviews, ya que no son verdaderos fans del cine. ¿De qué tamaño es el conjunto conexo y poligámico más grande? ¿Quién es el usuario con más parejas?

#### Compresión

* **C1** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la entropía base 2 de la distribución del rating que dan los usuarios?
* **C2** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Sin contar el género “Foreign” considerando la probabilidad de hacer una película en cada género para cada productora con más de 100 películas, ¿Cuáles son las 5 productoras con más entropía de Shannon en base 2?
* **C3** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para variables continuas existe la entropía diferencial, un análogo al caso discreto. Para las productoras con más de 50 películas, ¿Cúal es la productora con más y menos entropía diferencial para su ROI (Return of Investment)? ¿Qué interpretación puede hacer de esto?
* **C4** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la productora con entropía base 2 más alta para la distribución de los idiomas originales de sus producciones?
* **C5** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la película cuya entropía de las ratings que recibe es más alta? Esta será la película con opiniones más variadas. Considere sólo películas con más de 30 ratings.
* **C6** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Comprima todos los textos de las descripciones de las películas obteniendo un ratio de compresión mejor que 2.
  * ¿De cuanto es el ratio de compresión?
  * ¿Cuánto tarda en comprimir y descomprimir (por separado)? (use el magic %%timeit)
  * ¿Cuánto ocupa cada carácter en promedio una vez comprimido?
  * Si tomamos la entropía base dos para los caracteres ¿cuánto da? ¿cuantos bytes por caracter son esos?
  * Si utilizaramos un compresor aritmético por caracter, aproximadamente ¿cuál sería el ratio de compresión en el caso más optimista?
  * ¿Cúal algoritmo de compresión de los dos sería mejor?
* **C7** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para todas las productoras obtenga una matriz cuadrada en donde la posición i,j sea la divergencia de kullback leibler entre la distribución de idiomas originales de la productora i respecto de la productora j. Grafique con `plt.imshow`.
* **C8** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Tenemos la teoría de que a más películas variadas ve un usuario, más snob es, y que en consecuencia da puntajes más bajos en los ratings. Para cada usuario que hizo más de 100 reviews calcule el ratio de compresión de las descripciones de las películas que vió. ¿Cúal es la correlación entre ese ratio y el promedio del rating que deja el usuario?
* **C9** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para cada usuario que hizo más de 100 reviews, ¿cuáles son los dos usuarios con mayor distancia normalizada de compresión entre la concatenación de la descripción de 100 películas al azar que vieron? ¿Y con menor? Muestrelos intentando justificar por qué resultan así.

#### Visualizaciones
* **V1** (<img src="imgs/1c2022/luisito.jpg" />). Calcule el ROI (Return of Investment) de cada película. Filtre aquellos entre -10 y 10 y consiga la siguiente visualización.
<img src="imgs/2c2022/ROI.png" />
* **V2** (<img src="imgs/1c2022/luisito.jpg" />). Reproduzca exactamente esta visualización
<img src="imgs/2c2022/longitud_dist.png" />
* **V3** (<img src="imgs/1c2022/luisito.jpg" />). Reproduzca exactamente esta visualización
<img src="imgs/2c2022/log_vote_dist.png" />
* **V4** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Reproduzca exactamente esta visualización
<img src="imgs/2c2022/correlacion.png" />
* **V5** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Utilizando la tabla de imdb_actors para estimar los géneros, realice la siguiente visualización. La misma debe tener el mismo estilo y rangos pero puede variar ligeramente debido a supuestos al aproximar valores.
<img src="imgs/2c2022/gender_year.png" />
* **V6** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Consiga la probabilidad de que una productora haga una película según el género para cada uno de los géneros. Para las productoras con participación total mayor a 100 en géneros, ¿cuáles son las dos productoras con más distancia coseno respecto de sus probabilidades? Realice este plot reemplazando los nombres de las productoras por los que corresponden
<img src="imgs/2c2022/companies.png" />
* **V7** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Utilizando la tabla de imdb_actors para estimar los géneros, realice la siguiente visualización. La misma debe tener el mismo estilo y rangos pero puede variar ligeramente debido a supuestos al aproximar valores.
<img src="imgs/2c2022/gender_genre.png" />
* **V8** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Utilizando la tabla de imdb_actors para estimar los géneros, realice la siguiente visualización. La misma debe tener el mismo estilo y rangos pero puede variar ligeramente debido a supuestos al aproximar valores.
<img src="imgs/2c2022/gender_genre_age.png" />

## Segunda parte - Visualización de datos (10 <img src="imgs/1c2022/luisito64.jpg" />)

1) (6 <img src="imgs/1c2022/luisito.jpg" />) Realizar dos visualizaciones para cada uno de los tres datasets que elija de los que le brindamos. Las visualizaciones deben incluir o ayudar a explicar la variable indicada encontrando alguna relación **interesante** con ella (esto es excluyente). Además se debe realizar almenos un plot de cada uno de los siguientes tipos:
  * Bar plot (o sus variaciones)
  * Histograma o Density plot
  * Violin plot
  * Box plot
  * Heatmap

Debe elegir tres de los siguientes datasets:

2) (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />) Utilice alguna herramienta para realizar diagramas (por ejemplo Google Draw, draw.io, Google Slides, HTML, Illustrator, Photoshop, alguna lib de Python novedosa, etc.) para crear una visualización **ORIGINAL** que no pueda realizarse de forma directa con las librerías más comunes de Python, puede utilizar las librerías de Python como paso intermedio. Puede realizar este punto sobre los datos de: cualquier dataset, estadística oficial, paper, estadística no oficial, encuesta, números sin ninguna fuente en un blog, etc. El objetivo es elegir un tema de su interés y comunicarlo de forma efectiva y agradable.

## Puntos extra (hasta tres <img src="imgs/1c2022/luisito64.jpg" />)

Utilizamos el promedio del puntaje normalizado de cada kahoot/parcialito para armar un podio. El podio se modificara a medida participen en los Kahoots.
Quien esté primero recibira tres <img src="imgs/1c2022/luisito.jpg" />, quienes estén segundos o terceros recibiran dos <img src="imgs/1c2022/luisito.jpg" /> extra. Quienes estén en cuarto y quinto puesto un <img src="imgs/1c2022/luisito.jpg" /> extra.

### Podio final

|   Padrón | Alumno       |   Pandas 1 |   Pandas 2 |   Pandas 3 |   NLP I | Compresión |   Promedio | Premio |
|---------:|:-------------|----------:|----------:|----------:|-------:|---------:|---------:|---------:|
|   105798 | GRÜNER       |      1    |      0.67 |      0.96 |   0.98 |     0.712657 | 0.865023 | <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />       |
|   100972 | PEREZ LEIRAS |      0.99 |      0.91 |      0.63 |   1    |     0.738722 | 0.854771 | <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />|
|    99642 | CAPRA        |      0.87 |      0.87 |      0.89 |   0.51 |     1        | 0.827812 | <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />|
|   105771 | MANGIATERRA  |      0.9  |      0.87 |      0.51 |   1    |     0.705846 | 0.79516  | <img src="imgs/1c2022/luisito.jpg" />|
|    86125 | FONZALIDA    |      0.88 |      0.66 |      0.88 |   0.61 |     0.669354 | 0.739782 | <img src="imgs/1c2022/luisito.jpg" />|
|   105637 | SANTANDER    |      0.56 |      0.62 |      0.7  |   0.87 |     0.660805 | 0.684344 |-|
|   102649 | PAGURA       |      0.65 |      1    |      0.55 |   0.43 |     0.594356 | 0.644391 |-|

## Criterio de aprobación

El criterio general es que la totalidad del tp tiene que sumar 15 puntos de los 25, es un 60%. Además todas las consignas deben estar desarrolladas, entregando algo en cada una.

Cada une va a tener algún ayudante asignado, pueden hacer consultas por slack a su ayudante o en el canal.

### Primera parte - Pandas

Todos los ejercicios valen lo mismo que los <img src="imgs/1c2022/luisito.jpg" /> que tienen asignados.

* Cada ejercicio se considera 100% correcto si:
  * Resuelve lo pedido (¡cuidado con casos bordes! ¡revisen todo lo que pueda ser NULL!): Si el ejercicio no resuelve al 100% lo pedido, se considera que vale como máximo la mitad.
    * Cada ejercicio deberá funcionar si los datos cambian, esto significa, por ejemplo, que no podemos buscar un valor en una tabla y copiar y pegar ese literal para buscar en otra. El código debe soportar que la respuesta cambie.
  * Lo hace de la forma más eficiente posible: Si el ejercicio no está resuelto de la forma más óptima, pierde la mitad de su valor.
* La idea es que no lo hagan solos! Las consignas son complejas de entender en una sola lectura y necesitan pensarse lento, por esto es que es crucial consultar. Para esto hacemos lo siguiente según el tipo de duda:
  * Dudas de consigna:
    * Van a poder consultar en el canal de slack #consultas-tp1, es MUY importante que antes de consultar vean si su duda no fue resuelta allí.
    * En caso de no haber sido resuelta previamente para organizarnos sigan el siguiente formato: "**codigo de consigna** - Su consulta...". De esta forma es más facil para todos buscar consultas del pasado, por ejemplo: "C7 - No entiendo como calcular el largo en bytes que ocuparía con un árbol de Huffman.". **NO** se debe incluir código de resolución ni en la consulta ni interactuando con otres compañeres.
  * Dudas para saber si se puede usar alguna librería:
    * Se hacen en el mismo formato que las dudas de consigna.
  * Dudas de código y optimización:
    * Si son dudas generales de "cómo se hace <algo> en pandas" se puede consultar en el canal de consultas o en las clases de consulta.
    * El resto de las dudas deben consultarse con su ayudante asignado.

### Segunda parte - Visualización de datos

1. Cada visualización vale un <img src="imgs/1c2022/luisito.jpg" /> de los seis y debe cumplir con las siguientes condiciones:
  * Debe explicarse por si misma, sin necesidad de texto aclaratorio.
  * Debe tener rótulos en los ejes que corresponda y en el título.
  * Debe mostrar una relación o algo con la variable pedida que sea claro e interesante.
  * El uso de color debe ser intencional, elegido por ustedes, no por la librería.
  * La visualización debe ser legible (por ejemplo, un bar plot de 40 barras es ilegible)
2. Debe cumplir con el objetivo propuesto: Les recomendamos preguntar en clases de consultas o por slack, vamos a estar guiandolos en este punto. Dado que la elección de este dataset es personal pueden ir compartiendo sus ideas/bocetos o consultar lo que quiera sobre este punto de forma pública en #consultas-tp1 o si lo prefieren en privado con su ayudante.

Valoramos que se ayuden entre ustedes, debatan y compartan ideas y tips en el canal de slack!

## Formato de Entrega

La entrega es en Gradescope en formato PDF.

En el PDF deben indicar cada uno de los puntos de la primer parte que les tocó, colocando el enunciado de la consulta a resolver y el link al notebook donde está resuelta.

Para la segunda parte, incluír las visualizaciones en el PDF, con el link al notebook que genera cada una de ellas.

## Asignaciones

El equipo NIL (Nahuel Spiguelman, Ignacio Argel y Lucas Bilo) se fusiono en uno y van a responder consultas todos juntos, por lo que por favor si les tocaron escribanles a los 3 juntos.

<img src="https://i.gifer.com/GAf7.gif" />

|   Padron | Nombre                              | 1 - <img src="imgs/1c2022/luisito.jpg" />   | 2 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 3 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 4 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 5 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 6 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | 7 - <img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />   | Ayudante asignado                                   |
|---------:|:------------------------------------|:--------|:---------|:---------|:---------|:---------|:----------|:----------|:----------------------------------------------------|
|   107143 | CALDERON, GONZALO MANUEL            | N1      | P21      | N5       | V3       | C2       | V10       | N7        | Ignacio Brusati                                     |
|   101830 | DE SANTIS, FEDERICO EZEQUIEL        | P4      | V4       | V7       | N3       | C2       | V9        | P33       | Gianmarco Cafferata                                 |
|   108183 | DIAZ, JUAN MANUEL                   | P1      | P8       | N6       | V6       | C2       | C6        | P31       | Lucas Waisten                                       |
|   104424 | FERNANDEZ FOX, JOEL ISAAC           | V1      | V8       | P21      | N2       | C3       | P31       | P33       | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   105027 | GOMEZ, THIAGO EZEQUIEL              | V1      | P15      | P10      | C2       | N4       | P32       | N7        | Matias Rotondo                                      |
|   105906 | GRUSS, OLIVIER ANTOINE              | P4      | P10      | P23      | N6       | V8       | C5        | N8        | Ignacio Brusati                                     |
|   101933 | KARAGOZ, FILYAN                     | P2      | P20      | V2       | N5       | C3       | P28       | P32       | Damian Martinelli                                   |
|   106148 | METZ, MIGUEL GABRIEL                | P2      | C2       | V5       | N6       | P17      | C8        | C4        | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   108221 | PAVON, MARIA DOLORES                | P2      | P17      | P14      | V2       | N5       | C4        | P29       | Damian Martinelli                                   |
|   101946 | PUQUIO ROJAS, GIANCARLO JOSE        | P6      | C2       | P26      | N5       | V8       | N8        | P28       | Gianmarco Cafferata                                 |
|   106016 | VAGÓ, NICOLÁS ESTEBAN               | C1      | P25      | P23      | V2       | N5       | C4        | N8        | Manuel Battan                                       |
|    97023 | YBARRA ESCALANTE, DIEGO EMANUEL     | P1      | P26      | P20      | C2       | V7       | N8        | V9        | Esteban Djeordjian                                  |
|   105829 | AGAMA  AVILA, ANNALI ARELY          | P5      | P12      | P20      | V6       | N6       | C5        | P31       | Julieta Ponti                                       |
|   104221 | AGUILAR, PEDRO                      | P6      | N6       | P16      | V6       | C3       | V9        | P32       | Damian Martinelli                                   |
|   100199 | AGUIRRE, ARIEL LEANDRO              | P5      | N3       | P25      | V8       | C3       | P28       | C4        | Matias Fusco                                        |
|    79558 | ALBORNOZ, ROMINA CARLA              | C1      | P21      | P19      | V7       | N2       | P31       | P28       | Lucas Waisten                                       |
|   101589 | ALVAREZ, JUAN MANUEL                | P3      | V6       | N3       | C3       | P17      | C4        | P28       | Matias Fusco                                        |
|   105081 | AVENDAÑO PADILLA, FRANZ JULIO       | P1      | P22      | C2       | V3       | N3       | N7        | V10       | Damian Martinelli                                   |
|   104482 | AVILA CABRERA, GASTON               | P2      | V2       | P13      | N3       | C3       | P30       | P33       | Lucas Waisten                                       |
|    98592 | BLOISE, JULIETA                     | P4      | N6       | P22      | V6       | C3       | C8        | P32       | Manuel Battan                                       |
|   104733 | BRASBURG, AGUSTIN                   | P6      | P27      | P18      | V4       | N5       | C8        | C6        | Gianmarco Cafferata |
|   106211 | BULNES, MATEO                       | P6      | V5       | P19      | N2       | C3       | P29       | N7        | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   102842 | CALIZ BLANCO, ALEJO MARTIN EZEQUIEL | P5      | P11      | P17      | V2       | N3       | C7        | P29       | Damian Martinelli                                   |
|    99676 | CANTERO, ALAN EZEQUIEL              | P1      | P15      | V3       | N5       | C2       | P33       | P29       | Esteban Djeordjian                                  |
|    99642 | CAPRA, FRANCO DANIEL                | P5      | P16      | N2       | V3       | C2       | P32       | C4        | Ignacio Brusati                                     |
|   106551 | CASTRO, NAHUEL ELIAS                | C1      | N3       | N4       | P18      | V7       | P30       | V10       | Gianmarco Cafferata                                 |
|    99879 | CLAROS CASTRO, ELVIS                | N1      | N2       | P8       | V7       | C3       | P28       | C8        | Damian Martinelli                                   |
|   102104 | COSTA, LUCIANO                      | P3      | V2       | V5       | N4       | C2       | C7        | C5        | Damian Martinelli                                   |
|   104098 | CUPPARI, FRANCO                     | P6      | V7       | P9       | N4       | C3       | V9        | C8        | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   106855 | DAHAB, MOISES TOMAS                 | P7      | P16      | N2       | V6       | C2       | C7        | N8        | Gianmarco Cafferata                                 |
|   106368 | DELLA VECCHIA, TOMAS                | P4      | P20      | P14      | V6       | N3       | C8        | C5        | Esteban Djeordjian                                  |
|   104525 | DEMARCHI, LUCAS                     | P4      | P17      | P11      | V2       | N6       | C7        | P30       | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   105122 | DIAZ CALIXTO, LUZ MILAGROS          | N1      | P11      | P24      | V4       | C3       | V10       | P32       | Ignacio Brusati                                     |
|   104581 | DUZAC, JUAN MARTIN                  | P7      | P14      | N6       | V5       | C3       | P30       | P33       | Gianmarco Cafferata                                 |
|   106295 | ENCINOZA VILELA, NATHALIA LUCIA     | P1      | V3       | V2       | N4       | C2       | C7        | V10       | Gianmarco Cafferata                                 |
|   103992 | ESPERON, RAMIRO                     | P3      | P22      | P15      | C2       | V8       | N7        | V9        | Matias Rotondo                                      |
|   103512 | FERNANDEZ BOCH, VALERIA ALEJANDRA   | P7      | P12      | P11      | V5       | N2       | C5        | V9        | Gianmarco Cafferata                                 |
|    81006 | FERNANDEZ, OMAR ALFREDO             | N1      | N3       | V8       | P19      | C3       | P31       | N8        | Gianmarco Cafferata                                 |
|    86125 | FONZALIDA, MIGUEL ANGEL             | V1      | V6       | P9       | C3       | N6       | P32       | P30       | Manuel Battan                                       |
|   102396 | FRESIA, JUAN PABLO                  | N1      | N5       | P16      | V4       | C2       | P30       | C6        | Gianmarco Cafferata                                 |
|   102184 | FUENTES, AZUL LUCILA                | P7      | P27      | P12      | N5       | V7       | C6        | P29       | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo                                 |
|    97490 | GALLO, ROCIO MARIANA                | P1      | P25      | P21      | V5       | N3       | C7        | C6        | Gianmarco Cafferata                                 |
|   105552 | GENERAL, CAMILA                     | C1      | P19      | P17      | V8       | N5       | C6        | P32       | Damian Martinelli                                   |
|   106514 | GOMEZ, NAHUEL NICOLAS               | P2      | P18      | C3       | V3       | N2       | P33       | C5        | Ignacio Brusati                                     |
|    88060 | GORDILLO, LUIS ALEJANDRO            | C1      | P12      | N5       | V3       | P18      | P29       | V10       | Matias Rotondo                                      |
|   104623 | GRAZIOSI, GERMAN                    | N1      | P24      | V7       | C3       | P21      | V10       | P29       | Gianmarco Cafferata                                 |
|   105798 | GRÜNER, TOMÁS                       | N1      | P23      | P27      | V6       | C2       | P33       | C5        | Gianmarco Cafferata                                 |
|   105553 | JALEH, FEDERICO EZEQUIEL            | P5      | N2       | C3       | V4       | P19      | P31       | V9        | Damian Martinelli                                   |
|    99093 | JAMILIS, NETANEL DAVID              | P6      | P13      | N3       | V4       | C3       | P33       | P28       | Damian Martinelli                                   |
|    94727 | JARMOLINSKI, ARIAN LUCAS            | P7      | C2       | V8       | N4       | P21      | P29       | C7        | Damian Martinelli                                   |
|    87796 | LA TORRE, GABRIEL                   | P7      | P15      | P20      | V8       | N6       | C5        | P30       | Gianmarco Cafferata                                 |
|   105931 | LAZZARO, MELINA                     | P3      | P25      | C3       | N4       | V7       | N8        | C8        | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   100589 | LEGUIZAMON, VERONICA BEATRIZ        | P3      | P23      | P25      | V8       | N5       | C6        | C5        | Matias Rotondo                                      |
|   106223 | LITTERI, IVAN                       | V1      | N4       | P13      | C2       | P19      | N7        | P29       | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   104002 | LOSCOCCO, IGNACIO ARIEL             | P5      | P24      | N4       | V8       | C3       | P33       | P30       | Gianmarco Cafferata                                 |
|   105771 | MANGIATERRA, FEDERICO CARLOS        | C1      | P8       | P19      | V8       | N5       | P28       | C6        | Gianmarco Cafferata                                 |
|   105994 | MARCHESINI, SOFIA                   | N1      | P26      | V8       | C3       | P9       | P30       | C7        | Julieta Ponti                                       |
|   105554 | ORQUERA LORDA, FRANCISCO            | V1      | V4       | P10      | C3       | N3       | C4        | C7        | Julieta Ponti                                       |
|   102256 | OSCO CABRERA, ALEJANDRO ABRAHAM     | V1      | P9       | P27      | N6       | C2       | C4        | V10       | Esteban Djeordjian                                  |
|   102649 | PAGURA, SEBASTIAN MARTIN            | P5      | V8       | C2       | N3       | P21      | P28       | P31       | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   102679 | PALAZON, MARTIN                     | V1      | P21      | P13      | N3       | C2       | V9        | P31       | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|   100972 | PEREZ LEIRAS, AGUSTIN TOMAS         | P3      | P26      | N2       | V7       | C3       | P29       | C8        | Damian Martinelli                                   |
|    98230 | PERRONE, PATRICIO NAHUEL            | P7      | P16      | P27      | V5       | N2       | C8        | C7        | Gianmarco Cafferata                                 |
|   104229 | PONT TOVAR, MARIA FERNANDA          | C1      | P13      | P9       | V8       | N6       | C6        | P30       | Esteban Djeordjian                                  |
|    91076 | PORRAS CARHUAMACA, SHERLY KATERIN   | P3      | V4       | P22      | N5       | C2       | V9        | P30       | Damian Martinelli                                   |
|    91561 | PRIETO, PABLO ALEJANDRO             | P5      | N5       | V4       | C3       | P17      | P28       | N8        | Gianmarco Cafferata                                 |
|   105703 | RONDAN, MARCELO ARIEL               | N1      | N5       | V7       | P21      | C2       | V10       | P28       | Matias Fusco                                        |
|   106280 | RUEDA, NAZARENA                     | P1      | V6       | N6       | C2       | P17      | P33       | P28       | Lucas Waisten                                       |
|   105558 | SALESE D'ASSARO, ARIANA MAGALÍ      | P2      | V3       | V2       | N2       | C3       | C7        | N7        | Matias Rotondo                                      |
|   105637 | SANTANDER, VALENTIN                 | C1      | P9       | P15      | N5       | V8       | N8        | P31       | Damian Martinelli                                   |
|    99131 | SECCHI, ANA MARIA                   | P7      | P19      | V4       | N3       | C2       | C6        | N8        | Julieta Ponti                                       |
|   106422 | SILVA, PATRICIO TOMAS               | V1      | P18      | P8       | N2       | C3       | C4        | C8        | Gianmarco Cafferata                                 |
|    93735 | SOSA AQUINO, RICARDO ARIEL          | P6      | N4       | V5       | C2       | P19      | C6        | P31       | Esteban Djeordjian                                  |
|    98741 | SOSA, CRISTIAN MARTIN               | P4      | C3       | P24      | V4       | N3       | C8        | C5        | Julieta Ponti                                       |
|   104909 | TAIBO, NAZARENO GABRIEL             | P1      | C3       | P24      | V7       | N6       | P31       | V10       | Esteban Djeordjian                                  |
|    97617 | YAVICOLI, TOMAS                     | P2      | P18      | P14      | C2       | V8       | N7        | C6        | NIL: Nahuel Spiguelman, Ignacio Argel y Lucas Bilo |
|    96995 | Matías Priano                       | P2      | V3       | V6       | N6       | C2       | V9        | C4        | Matias Fusco                                        |
|    93751 | José Israel Ramírez                 | P4      | P8       | P12      | V5       | N4       | C5        | N7        | Damian Martinelli                                   |
|    87039 | Zoraida Flores Sosa                 | P7      | P17      | P18      | V2       | N6       | C5        | C7        | Gianmarco Cafferata                                 |
|   100488 | Carlos Martín Stefanelli D'elias    | P3      | P10      | P23      | N5       | V8       | C5        | C4        | Damian Martinelli                                   |
|    97640 | Facundo Brondo                      | V1      | P14      | P10      | N3       | C3       | C4        | P32       | Gianmarco Cafferata                                 |
|    98559 | Nicolas Allende                     | P4      | V5       | P22      | N4       | C2       | V9        | P33       | Gianmarco Cafferata                                 |
|    96467 | José Eduardo Chávez Cabanillas      | P1      | P11      | V6       | N3       | C2       | P33       | P30       | Lucas Waisten                                       |
|   101186 | Mauro Giampietri                    | C1      | N4       | P26      | V4       | P19      | C8        | V9        | Esteban Djeordjian                                  |
