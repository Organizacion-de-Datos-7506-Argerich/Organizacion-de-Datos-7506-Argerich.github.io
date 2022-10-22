# TP3 - Machine Learning I

## Dataset a usar

El dataset fue extraido por la cátedra para distintas canciones, y se encuentre [acá](https://drive.google.com/drive/folders/1-S0MrftIbCRalfL876-p2hyMkrX52TKM?usp=sharing).

El target a predecir es el género de la canción en la columna `genre`.

La métrica de validación es top-2 accuracy.

## Parte I - Análisis Exploratorio (6 <img src="imgs/1c2022/luisito64.jpg" />)

Deberán realizar 6 visualizaciones **interesantes** que **ayuden a explicar o entender el target**.

## Parte II - Machine Learning Baseline (4 <img src="imgs/1c2022/luisito64.jpg" />)

Vamos a construir un modelo muy sencillo para saber qué es lo peor que podemos hacer, en general esta es una tarea muy importante que queremos que repitan en sus proyectos de machine learning. ¿Por qué?

* [Navaja de Ockam](https://es.wikipedia.org/wiki/Navaja_de_Ockham): “Cuando se ofrecen dos o más explicaciones de un fenómeno, es preferible la explicación completa más simple; es decir, no deben multiplicarse las entidades sin necesidad.” ¿Para qué desarrollar un modelo super complejo si capaz es peor o casi igual que uno muy sencillo?
* Nos sirve para saber si estamos usando bien los modelos más complejos, si su score nos da peor al baseline probablemente se deba a un error de código.
* Nos sirve para rápidamente saber que tan complejo es un problema.
* Los modelos simples son fáciles de entender.

Utilice **todas las columnas del dataset** (exceptuando columnas que no tenga sentido usar para predecir) con algún encoding donde sea necesario para entrenar una regresión logística, utilizando búsqueda de hiperparametros y garantizando la reproducibilidad de los resultados cuando el notebook corriera varias veces. Conteste las preguntas:

* ¿Cuál es el mejor score de validación obtenido? (¿Cómo conviene obtener el dataset para validar?)
* Al predecir con este modelo para test, ¿Cúal es el score obtenido? (guardar el csv con predicciones para entregarlo después)
* ¿Qué features son los más importantes para predecir con el mejor modelo? Graficar.

## Parte III - Machine Learning (10 <img src="imgs/1c2022/luisito64.jpg" />)

Entrenar 2 (de tipos distintos, excluyendo regresiones logísticas) modelos (5 puntos cada uno) con búsqueda de hiperparametros (¿cómo conviene elegir los datos de validación respecto de los de train?).
Los modelos deben cumplir las siguientes condiciones:
* Deben utilizar top-2 accuracy como métrica de validación.
* Deben medirse solo en validación, **no contra test!!!**
* Deben ser reproducibles (correr el notebook varias veces no afecta al resultado).
* Deben tener un score en validación superior a 0,3.
* Para el feature engineering debe utilizarse imputación de nulos, mean encoding y one hot encoding al menos una vez cada uno.
* Deben utilizar al menos 40 features (contando cómo features columnas con números, pueden venir varios de la misma variable).
* Deben utilizar CountVectorizer o TfIdfVectorizer para algunos features.
* Deberán contestar la siguiente pregunta: Para **el mejor modelo de ambos**, ¿cuál es el score en test? (guardar el csv con predicciones para entregarlo después)

## Puntos extra (hasta 4 <img src="imgs/1c2022/luisito64.jpg" />)

Estas consignas suman puntos extra por fuera de los necesarios para aprobar el TP, mientras más consignas extra realicen más puntos consiguen y menos va a depender su aprobación de que los puntos de arriba estén bien:

* Entrenar un modelo basado en árboles que sea multi-label. ¿Qué tan bien dan las métricas en validación y test? (1 punto)
* Entrenar una red neuronal con Keras que sea reproducible, usando al menos 40 features y un score en validación superior a 0,3. Debe ser un modelo por separado a los propuestos, no necesita búsqueda de hiper parámetros ni cumplir otra condición. ¿Cúal es su score en validación y en test? (1 puntos)
* Graficar la importancia de features para algún modelo de la parte III. ¿Qué tanto se parece a los features importantes de la parte II? (1 punto)
* Ensamble ambos modelos de la parte III en uno solo. ¿Cúal es su score en validación y en test? (1 punto)

## Premio kahoot (un <img src="imgs/1c2022/luisito64.jpg" />)

Utilizamos el promedio del puntaje normalizado de cada kahoot/parcialito para armar un podio. El podio se modificara a medida participen en los Kahoots. Los 5 primeros reciben un <img src="imgs/1c2022/luisito.jpg" /> extra.

## Criterio de corrección

Se necesita un 60% (12/20) de los puntos para aprobar. Los puntos extra permiten sumar por dentro de los 20 (uno se puede sacar hasta 25 pero se sigue aprobando con 12 y el 20 representa un 10).

### Criterio de reentrega

Se podrá reentregar el TP si el puntaje es >=8 y están **todos los puntos desarrollados**.  La reentrega consiste en hacer un punto extra y corregir todos los puntos donde tuvieran menos de la mitad de los puntos.

Se aprueba la reentrega si todos los puntos tienen al menos la mitad de los puntos. En caso de luego aprobar la instancia de reentrega, la nota es siempre 4.

### Parte I

Cada visualización vale un <img src="imgs/1c2022/luisito.jpg" /> de los seis y debe cumplir con las siguientes condiciones:
  * Debe explicarse por si misma, sin necesidad de texto aclaratorio.
  * Debe tener rótulos en los ejes que corresponda y en el título.
  * Debe mostrar una relación o algo con la variable pedida que sea claro e interesante.
  * El uso de color debe ser intencional, elegido por ustedes, no por la librería.
  * La visualización debe ser legible (por ejemplo, un bar plot de 40 barras es ilegible)

### Parte II

Vamos a corregir los siguientes puntos (no pueden restar más de 4 en total):

* Utiliza mal los datos de validación ya sea para obtener el resultado o para buscar hiper parámetros (-4 puntos), ejemplos: calcular el score con otras labels, calcular el AUC-ROC usando la predicción binaria y no la probabilidad, el set de validación se usa para elegir los parámetros pero también está dentro del entrenamiento de cada modelo, el set de validación se usa filtrando información a los encodings, validación no está tomado de forma correcta, etc.
* El modelo no está bien hecho (-4 puntos), ejemplo: entrenan con las labels o datos cambiados para algunas filas
* No es capaz de predecir para test o no lo hace correctamente (-4 puntos)
* No es reproducible (-2 puntos)
* No obtiene bien los features más importantes (-2 puntos)
* La predicción en test da menos de 0,3 (-2 puntos)
* La predicción para test tiene errores (-1 punto)
* No utiliza todas las columnas del dataset (-1 punto)

### Parte III

Vamos a corregir los siguientes puntos en cada modelo de 5 puntos (a medida se acumulan estos pueden hacer que el modelo valga 0, pero nunca negativo):
* Para cada modelo cada condición no cumplida (o mal hecha) resta 1 punto.
* Feature engineering inapropiado para el modelo elegido (-2 puntos), ejemplos: features que no están normalizadas para una red neuronal, features sin ninguna consideración de escalas para un KNN, etc.
* No buscan para todos los hiperparametros importantes (-2 puntos).

Además si un modelo diera un resultado **menor a 0,3 en validación se invalida entero**.
Por sobre el puntaje total del ejercicio (ambos modelos) se restan 3 puntos si cualquiera de las siguientes cosas suceden (no acumulables): eligen mal el mejor modelo entre los dos o la predicción para test no está bien hecha o la predicción en test da menos de 0,3.

## Detalles y recomendaciones

* Para consultas conceptuales sobre machine learning o preguntas de consigna pueden consultar en el canal de slack #consultas-tp3.
* Para consultas de código con su corrector o algún ayudante por privado.
* No recomendamos usar de forma directa y sin modificaciones modelos entrenados por otros para usarlos, esto solo les puede jugar en contra porque es imposible que cumplan las condiciones pedidas. Es probable que esos modelos estén orientados a conseguir buenos resultados (cosa que encima no evaluamos) y que tengan algún error conceptual.
* Recomendamos trabajar durante todo el TP en solo 4 notebooks: Uno de visualizaciones, otro para la regresión logística y uno para cada modelo de la parte III. Les recomendamos desarrollarlos de forma prolija y mostrar de forma ordenada cada uno de los resultados y pasos, con títulos y comentarios donde corresponda.
* El TP pide solo 6 visus y 3 modelos con condiciones muy claras, tengan esa consideración a medida avanzan para chequear que cumplen todo.
* El TP **no pide ni evalúa más que lo que dice**, si bien ser original y tener un buen score suma en términos de trabajo y aprendizaje para ustedes, sean inteligentes respecto a los modelos y features que eligen para trabajar para garantizar que pueden terminar. Ya van a tener tiempo de ser originales en el TP4…
* Particularmente **este TP es muy difícil empezarlo al final**, en cuotas se vuelve mucho más sencillo, les recomendamos empezar por las visus que no necesitan teoría nueva. Sabemos que muchos de ustedes vienen haciendo algunos tps la última semana, pero la experiencia del cuatrimestre pasado nos dice que **con este no se puede hacer eso**, son demasiados conceptos a entender y muchas formas de hacerlo mal, no es solo una consigna a cumplir. No es que el TP sea más largo, sino que se vuelve más corto mientras más temprano lo empiecen.
* Todos los puntos deben estar desarrollados (exceptuando por supuesto los extra).

## Asignación de correctores

|   Padron | Nombre                             | Ayudante asignado                                   |
|---------:|:-----------------------------------|:----------------------------------------------------|
|   106870 | ADRIS, MARIO SANTIAGO              | Matias Fusco y Gabriel Semorile                     |
|   104498 | ALMADA, FRANCO MARTIN              | Gianmarco Cafferata                                 |
|   106892 | AMBOAGE, JUAN PATRICIO             | Esteban Djeordijan y Alejo Caliz Blanco             |
|   105190 | BARRETO, SEVERINO                  | Gianmarco Cafferata                                 |
|   108100 | BENITO, AGUSTÍN                    | Julieta Ponti y Martín Stefanelli                   |
|   108225 | BERENGUEL IBARRA, RAFAEL FRANCISCO | Natalia Golmar                                      |
|   105620 | BOUCHARD, JOSUE ALEJANDRO          | Gianmarco Cafferata                                 |
|    97640 | BRONDO, FACUNDO LUCIO              | Damian Martinelli                                   |
|   106691 | CAMPILLAY, EDGAR MATIAS            | Damian Martinelli                                   |
|   106359 | CAMURRI, FEDERICO ALFREDO          | Damian Martinelli                                   |
|   108298 | CHACON SALEMME, IGNACIO ALEJANDRO  | Esteban Djeordijan y Alejo Caliz Blanco             |
|   105907 | CHEN, NICOLAS                      | Matias Rotondo                                      |
|    99879 | CLAROS CASTRO, ELVIS               | Luis Argerich                                       |
|   102868 | CONTE GRAND, JOAQUIN               | Natalia Golmar                                      |
|   102104 | COSTA, LUCIANO                     | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   107963 | CUEVAS, JUAN FRANCISCO             | Natalia Golmar                                      |
|   104098 | CUPPARI, FRANCO                    | Luis Argerich                                       |
|   101830 | DE SANTIS, FEDERICO EZEQUIEL       | Gianmarco Cafferata                                 |
|   106368 | DELLA VECCHIA, TOMAS               | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   107835 | DEMARCHI, IGNACIO                  | Natalia Golmar                                      |
|   105122 | DIAZ CALIXTO, LUZ MILAGROS         | Luis Argerich                                       |
|   106308 | DUCA, FRANCISCO                    | Luis Argerich                                       |
|   106295 | ENCINOZA VILELA, NATHALIA LUCIA    | Ignacio Brusati y Juan Pablo Fresia                 |
|   105989 | ERLICH, IVAN                       | Esteban Djeordijan y Alejo Caliz Blanco             |
|   103992 | ESPERON, RAMIRO                    | Ignacio Brusati y Juan Pablo Fresia                 |
|   106160 | FABREGAS, ALEJO VALENTIN           | Ignacio Brusati y Juan Pablo Fresia                 |
|   103740 | FABREGAS, CAMILO EZEQUIEL          | Damian Martinelli                                   |
|    97261 | FARFAN LENCINA, NICOLAS RAFAEL     | Natalia Golmar                                      |
|    97897 | FERRERO, MANUEL                    | Lucas Waisten                                       |
|   104354 | GALIAN, TOMAS EZEQUIEL             | Esteban Djeordijan y Alejo Caliz Blanco             |
|   105043 | GARCIA PIZALES, IGNACIO            | Matias Rotondo                                      |
|   105552 | GENERAL, CAMILA                    | Luis Argerich                                       |
|   101185 | GOIJMAN, LAUTARO ENZO              | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   104503 | GORDYN BIELLO, GONZALO             | Matias Fusco y Gabriel Semorile                     |
|   104084 | GRZEGORCZYK, IVAN                  | Ignacio Brusati y Juan Pablo Fresia                 |
|   107404 | HURTADO VARGAS, DANIEL ALEJANDRO   | Natalia Golmar                                      |
|   107854 | HUTTIN, FACUNDO TOMÁS              | Damian Martinelli                                   |
|   104424 | Joel Isaac Fernandez Fox           | Luis Argerich                                       |
|   107188 | KIM, DANIEL TOMAS                  | Ignacio Brusati y Juan Pablo Fresia                 |
|   103346 | Lautaro Rodriguez                  | Esteban Djeordijan y Alejo Caliz Blanco             |
|   100589 | LEGUIZAMON, VERONICA BEATRIZ       | Luis Argerich                                       |
|   107825 | LIN, CRISTIAN MARTIN               | Ignacio Brusati y Juan Pablo Fresia                 |
|   105974 | MACKE, FRANCO                      | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   105645 | MARIÑO, ALEJO TOMÁS                | Esteban Djeordijan y Alejo Caliz Blanco             |
|   101186 | Mauro Giampietri                   | Matias Fusco y Gabriel Semorile                     |
|   108294 | MAURO, CAROLINA LUCIA              | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   101769 | MEDELA, MARIANO TOMAS              | Gianmarco Cafferata                                 |
|   103878 | MEDONE SABATINI, JUAN IGNACIO      | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   108485 | MENDAÑA, JOAQUÍN                   | Natalia Golmar                                      |
|   107164 | MORANDI, FABRIZZIO LEONARDO        | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   106016 | Nicolás Vagó                       | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|   104881 | OLANO SOLEY, NICOLÁS GUILLERMO     | Julieta Ponti y Martín Stefanelli                   |
|        0 | Pablo Serrati                      | Matias Fusco y Gabriel Semorile                     |
|   103851 | PANACCIO, GUIDO DANIEL             | Luis Argerich                                       |
|   108891 | PELLEGRINI, ANTONELLA JAZMÍ­N      | Gianmarco Cafferata                                 |
|    91076 | PORRAS CARHUAMACA, SHERLY KATERIN  | Natalia Golmar                                      |
|   108405 | PORRO, JOAQUIN                     | Damian Martinelli                                   |
|    91561 | PRIETO, PABLO ALEJANDRO            | Matias Rotondo                                      |
|   105167 | REGAZZOLI, IGNACIO                 | Gianmarco Cafferata                                 |
|   104677 | RIAL, TADEO EZEQUIEL               | Julieta Ponti y Martín Stefanelli                   |
|   108267 | RODRIGUEZ JUSTO, IGNACIO           | Gianmarco Cafferata                                 |
|   105318 | RODRIGUEZ, TOMAS GUSTAVO           | Luis Argerich                                       |
|   103439 | SAGMAN, EMANUEL NICOLAS            | Lucas Waisten                                       |
|   105637 | SANTANDER, VALENTIN                | Lucas Waisten                                       |
|   103967 | SCAZZOLA, LARA                     | Matias Fusco y Gabriel Semorile                     |
|   106403 | SCAZZOLA, MARTIN                   | Natalia Golmar                                      |
|   102110 | SCHEJTMAN, EZEQUIEL                | Gianmarco Cafferata                                 |
|    91979 | SEDEK, JORGE IGNACIO               | NIL: Nahuel Spieguelman, Ignacio Argel y Lucas Bilo |
|    98911 | TEJELO, FERNANDO MARTIN            | Damian Martinelli                                   |
|    97819 | TORRES, LUCAS GABRIEL              | Gianmarco Cafferata                                 |
|   103359 | TOSONI MARQUEZ, FRANCO             | Matias Fusco y Gabriel Semorile                     |
