# TP2 - Spark

## Spark sobre Yelp (8 <img src="imgs/1c2022/luisito64.jpg" />)

Vamos a utilizar como dataset los csvs de [esta carpeta](https://drive.google.com/drive/folders/1aluo8daHgFMn40ndeBkpRMzE4hN00cEj) correspondientes a un recorte de los datos de Yelp.

Yelp es un sitio donde se pueden dejar reseñas y tips sobre negocios de todo tipo, muy utilizado en Estados Unidos. Los csvs son:

* businesses.csv
  * business_id
  * name
  * address
  * city
  * state
  * postal_code
  * latitude
  * longitude
  * stars: float, star rating, rounded to half-stars
  * review_count
  * is_open
  * attributes: un json con atributos variados
  * categories: lista de categorías en json a las que pertenece el negocio
  * hours: diccionario json con horarios día por día en los que abre
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
* user.csv
  * user_id
  * name
  * review_count
  * yelping_since: fecha de registro
  * friends: lista en json de user ids que son amigos
  * useful: cantidad de votos “useful” que recibió el usuario
  * funny: cantidad de votos “funny” que recibió el usuario
  * cool: cantidad de votos “cool” que recibió el usuario
  * fans: cantidad de fans que tiene el usuario
  * elite: lista json con los años que el usuario fue élite
  * average_stars: promedio de rating de todas sus reviews
  * compliment_*: la cantidad de cumplidos de tipo * que recibió el usuario
* checkins.csv: Las visitas que los usuarios registran a los lugares
  * business_id
  * date: lista de fechas separadas por coma de los chekins que recibió el negocio
* tip.csv: tips que los usuarios dan sobre lugares
  * text
  * date
  * compliment_count: cumplidos que recibió el tip
  * business_id
  * user_id

### Consignas a realizar

❗⚠️ Debajo están las consignas del TP entero, deberá realizar **las que le toquen según la tabla que se encuentra al final**. ⚠️❗

Tienen asignados **1 ejercicio que vale un** <img src="imgs/1c2022/luisito.jpg" />, **2 que valen dos** <img src="imgs/1c2022/luisito.jpg" /> y **1 que vale tres** <img src="imgs/1c2022/luisito.jpg" />.

#### Ejercicios

* **S1** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el estado con mejor rating promedio en sus negocios? ¿Por qué?
* **S2** (<img src="imgs/1c2022/luisito.jpg" />). Para el promedio de stars por cada ciudad, ¿cuáles son los 5 promedios más comunes?
* **S3** (<img src="imgs/1c2022/luisito.jpg" />). Muestre el nombre del usuario que ha hecho una review al mismo lugar mas veces, y también el nombre del lugar.
* **S4** (<img src="imgs/1c2022/luisito.jpg" />). De los 3 estados con más ciudades, indique la cantidad de ciudades y el promedio de stars de las ciudades por cada uno de los 3 estados
* **S5** (<img src="imgs/1c2022/luisito.jpg" />). Para los negocios que indican su horario, calcule la probabilidad de que un negocio esté abierto a las 21 horas del domingo. Si el domingo no apareciera en el diccionario asuma que no abre.
* **S6** (<img src="imgs/1c2022/luisito.jpg" />). Teniendo en cuenta las reviews que reciben los locales, devolver una del local que haya recibido más votos del tipo divertido en sus reviews.
* **S7** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el nombre del segundo usuario que hizo reviews a más referencias geográficas?
* **S8** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cual es el nombre del usuario que hizo más reviews en el estado de California?
* **S9** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el código postal del local cuyas reviews suman más votos obtenidos de ‘cool’, ‘funny’ y ‘useful’?
* **S10** (<img src="imgs/1c2022/luisito.jpg" />). ¿Quién es el usuario con al menos un fan con mayor ratio amigos/fans?
* **S11** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es el top 10 palabras más comunes para los textos de los tips? Puede usar split como tokenizer, considere las palabras en minúscula sin contar stopwords.
* **S12** (<img src="imgs/1c2022/luisito.jpg" />). Calcule la entropía de Shannon (base 2) del campo stars de reviews
* **S13** (<img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el restaurante mexicano más cercano a FIUBA?  Datos ubicación FIUBA: Latitud:-34.61748 – Longitud:-58.36824.
* **S14** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Nos vamos a quedar dos días en New Orleans por una meetup de data science. Queremos visitar la ciudad pero no tenemos mucho tiempo así que visitaremos sus mejores lugares. Vamos a calcular el score de review promedio para cada lugar, pero para tener en cuenta la varianza vamos a restarle a cada promedio su desviación estándar y solo usar lugares con más de 10 reviews.
  * Nos han dicho que la ciudad tiene un barrio francés con muy buena gastronomía. ¿Cúal es el mejor lugar para comer con la categoría “French”?
  * Después de comer queremos ir a un bar a tomar tragos, ¿cuál es el mejor de la categoría “Bars”?
  * ¿Cuál es el mejor museo (categoría “Museums”)? ¿De qué trata?
* **S15** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Ginebra planea mudarse a la ciudad de Santa Bárbara. Con ella llevará a su perro "Gin". Es por esto, que quiere saber cuales son las reviews del local más cercano a la ubicación donde ha logrado alquilar un departamento de venta de artículos para mascotas, dado que es una compradora compulsiva de juguetes para él. También devolver la distancia euclídea. El departamento se encuentra en las coordenadas: 34.424137, -119.690012.
* **S16** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el usuario más quejumbroso por estado? Consideramos quejumbroso a un usuario que tiene más de 5 reviews y son todas de 2 estrellas o menos.
* **S17** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). La antigüedad promedio de los usuarios y el nombre del usuario más antiguo cuyas última review contenga la palabra 'pizza'
* **S18** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos saber cuáles son los negocios más sexys, para esto vamos a ver cuáles son los nombres de los 3 negocios con más tips que contengan el texto "sexy"
* **S19** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Fernando quiere festejar su cumpleaños, que cae jueves, al salir de la oficina a las 19 hs. Sus amigos viven distribuidos en la ciudad de Philadelphia, por lo que es indiferente la ubicación del lugar, siempre y cuando esté en la ciudad. Quiere que le ofrezcamos el top 3 de lugares de comida italiana, generando el ranking según la cantidad de reviews de 5 estrellas que hayan recibido. Devolver algunas referencias (al azar) de cada uno de ellos, para ayudarlo a  decidir en cual realizar la reserva.
* **S20** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Buscar la distancia mínima que existe entre dos locales de McDonald 's en el estado de LA (que no comparten dirección). ¿Cuál es la distancia?¿A qué ciudad/es pertenecen? ¿Cuáles son las direcciones de los locales?
* **S21** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Yelp quiere reconocer qué usuarios están progresando en el sitio de manera excepcional respecto a la mayoría para darles una medallita. El problema es que todos los usuarios tienen distintas edades en el sitio y eso dificulta medir progreso. Calcule la velocidad con que cada usuario consiguió fans e hizo reviews en el sitio. ¿Cuántos usuarios superan ambas velocidades promedio?
* **S22** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Verifique si el valor de stars en business.csv es válido y consistente. ¿Qué porcentaje del campo es válido?
* **S23** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). De los negocios que tienen acceso para silla de ruedas (si no dice nada asuma que no tiene) y tienen más de 10 reviews, ¿cuál es el mejor? ¿y el peor?
* **S24** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). La 3-upla de palabras (no letras) más común en los comentarios de los tips. De ser necesario, se puede utilizar un sample y no la totalidad de datos.
* **S25** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es el la review con menor ratio de stopwords en función de su longitud para aquellas que tienen por lo menos 100 caracteres?
* **S26** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuantos triangulos hay en la red de amigos?
* **S27** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Quién es el usuario más antiguo en el sitio que tiene exactamente 250 fans?
* **S28** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Calcule la mediana del campo stars de reviews de forma distribuida.
* **S29** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Calcule el percentil 95 de la cantidad de fans de los usuarios de forma distribuida.
* **S30** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cuál es la pendiente y ordenada al origen de la recta de cuadrados mínimos de amigos en función de fanes? Calcule de forma distribuida.
* **S31** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para los usuarios que tengan más de 100 reviews registradas, ¿cuál es el user_id cuya mediana del tiempo entre reviews es menor?
* **S32** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Yelp tiene la teoría de que quienes hacen las reviews más útiles en la plataforma son aquellos usuarios con más antigüedad. Para probar está hipótesis para cada review consiga la suma total de sus votos (funny + cool + useful) y correlacionela con la antigüedad del usuario *al momento de hacer la review*.
* **S33** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la correlación entre el score que deja un usuario en una review, y el score que dejó en la anterior? Tenemos la teoría de que un usuario tiende a dejar reviews similares. Puede tomar un sample para calcularla.
* **S34** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). ¿Cúal es la correlación entre el score que dejaron los usuarios en cada review después de 2017, y el score promedio que dejaron en todas las reviews del 2017? Calcule sin usar samples.
* **S35** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos saber donde vive alguno de nuestros usuarios, para los usuarios que tiene más de 50 registros a negocios distintos en la tabla reviews obtenga el promedio y desviación estándar de la latitud y longitud de los negocios que calificaron (contando cada negocio una sola vez). Para el usuario que menos desviación estándar sumada tenga de ambas coordenadas muestre ese promedio y dónde está eso ([https://www.gps-coordinates.net/](https://www.gps-coordinates.net/)) y cómo se llama el usuario para después irlo a buscar a la casa.
* **S36** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para los usuarios que hicieran más de 10 reviews, decimos que la ubicación de un usuario es el promedio de la ubicación de los lugares a los que hicieron reviews. ¿Cuáles son los dos usuarios más cercanos?
* **S37** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Según la [paradoja de la amistad](https://www.youtube.com/watch?v=httLvVufAYs), en redes sociales, tus amigos suelen tener en promedio más amigos que vos :(. Calcule el promedio de amigos que tiene cada usuario y el promedio de amigos que tienen los amigos de cada usuario.
* **S38** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Según la teoría de los 6 grados de separación, en redes sociales, las personas tienen 6 amigos de separación entre sí. Esto es, si queres llegar a contactar a cualquier persona en el mundo, estás a una cadena de 6 amigos para llegar a esa persona. ¿Qué proporción de usuarios están a distancia menor o igual a 1 y menor o igual a 2 entre sí? Utilice una muestra (muestra de que?)
* **S39** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Estime la centralidad de cada usuario por medio de random walks sobre sus amigos. ¿Quién es el usuario más popular?
* **S40** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Para las reviews y tips que contienen la palabra “fuck”:
  * Para las reviews, ¿cuál es el promedio del score?
  * ¿Cuál es el usuario que más veces usó la palabra en ambas tablas?
  * ¿Cuál es el negocio que más veces recibió la palabra en ambas tablas?
  * ¿Cuál es el negocio de más de 3 reviews con mayor ratio de textos que contienen “fuck”?
  * Para los negocios con textos que tienen “fuck” correlacione el rating promedio del negocio con su ratio de “fuck” en textos.
* **S41** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Utilizando los textos de las reviews y las técnicas de NLP(TF-IDF), de modo que la query sea 'high quality', devolver el nombre de la pizzería, la review y la ciudad, que haya sido reconocida por la calidad de sus productos.
* **S42** (<img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" /><img src="imgs/1c2022/luisito.jpg" />). Queremos crear nuestro propio clasificador de reviews según sean positivas o negativas usando los datos de yelp, para hacer esto vamos a hacer una cosa muy sencilla: asignarle a cada palabra de las 500 más comunes sin contar stopwords el promedio de las stars para las reviews en las que aparece, luego, cuando aparezca un nuevo texto para las palabras que conozcamos del mismo promediamos sus scores. Por ejemplo, si tenemos las palabras “buena” con polaridad 3.4 y “rica” con polaridad 4.3 y tenemos el texto “buena y rica” su predicción será 3.85. Puede usar una muestra para entrenar. ¿Cuál es la salida del predictor para “I loved this place, the food was amazing!”?

## Puntos extra (un <img src="imgs/1c2022/luisito64.jpg" />)

Utilizamos el promedio del puntaje normalizado de cada kahoot/parcialito para armar un podio. El podio se modificara a medida participen en los Kahoots. Los 5 primeros recibiran un <img src="imgs/1c2022/luisito.jpg" /> extra.

## Criterio de aprobación

El criterio general es que la totalidad del tp tiene que sumar 4.8 puntos de los 8, es un 60%. Además todas las consignas deben estar desarrolladas, entregando algo en cada una.

Cada une va a tener algún ayudante asignado, pueden hacer consultas por slack a su ayudante o en el canal.

### Spark sobre Yelp

Todos los ejercicios valen lo mismo que los <img src="imgs/1c2022/luisito.jpg" /> que tienen asignados.

* Cada ejercicio se considera 100% correcto si:
  * Resuelve lo pedido (¡cuidado con casos bordes! ¡revisen todo lo que pueda ser NULL!): Si el ejercicio no resuelve al 100% lo pedido, se considera que vale como máximo la mitad.
    * Cada ejercicio deberá funcionar si los datos cambian, esto significa, por ejemplo, que no podemos buscar un valor en una tabla y copiar y pegar ese literal para buscar en otra. El código debe soportar que la respuesta cambie.
  * Lo hace de la forma más eficiente posible: Si el ejercicio no está resuelto de la forma más óptima, pierde la mitad de su valor.
* La idea es que no lo hagan solos! Las consignas son complejas de entender en una sola lectura y necesitan pensarse lento, por esto es que es crucial consultar. Para esto hacemos lo siguiente según el tipo de duda:
  * Dudas de consigna:
    * Van a poder consultar en el canal de slack #consultas-tp1, es MUY importante que antes de consultar vean si su duda no fue resuelta allí.
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

El equipo NIL (Nahuel Spiguelman, Ignacio Argel y Lucas Bilo) se fusiono en uno y van a responder consultas todos juntos, por lo que por favor si les tocaron escribanles a los 3 juntos.

<img src="https://i.gifer.com/GAf7.gif" />

en construcción.
