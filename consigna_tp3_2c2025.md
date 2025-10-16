# Ciencia de Datos — Trabajo Práctico N.º 3  
## Machine Learning

El tercer TP es una competencia de Machine Learning en donde cada alumno debe intentar determinar, para cada tweet brindado, si el mismo está basado en un hecho real o no.

La competencia se desarrolla en la plataforma de Kaggle  https://www.kaggle.com/c/nlp-getting-started.  

El dataset consta de una serie de tweets, para los cuales se informa:

- id - identificador único para cada  tweet

- text - el texto del tweet

- location - ubicación desde donde fue enviado (podría no estar)

- keyword - un keyword para el tweet  (podría faltar)

- target - en train.csv, indica si se trata de un desastre real  (1) o no (0)



Los submits con el resultado deben tener el formato:


- Id: Un id numérico para identificar el tweet

target: 1 / 0 según se crea que el tweet se trata sobre un desastre real, o no.


Los alumnos deberán probar distintos algoritmos de Machine Learning para intentar predecir si el tweet está basado en hechos reales o no. A medida que realicen pruebas deben realizar el correspondiente submit en Kaggle para evaluar el resultado de los mismos.

---

## Parte I: Análisis exploratorio (2 puntos)

Realizar 6 visualizaciones interesantes que ayuden a explicar el target.

---

## Parte II: Machine Learning Baseline (2 puntos)

Vamos a construir un modelo muy sencillo para saber qué es lo peor que podemos hacer, en general esta es una tarea muy importante que queremos que repitan en sus proyectos de machine learning. ¿Por qué?

- Navaja de Ockham: “Cuando se ofrecen dos o más explicaciones de un fenómeno, es preferible la explicación completa más simple; es decir, no deben multiplicarse las entidades sin necesidad.” ¿Para qué desarrollar un modelo super complejo si capaz es peor o casi igual que uno muy sencillo?

- Nos sirve para saber si estamos usando bien los modelos más complejos, si su score nos da peor al baseline probablemente se deba a un error de código.
  
- Nos sirve para rápidamente saber que tan complejo es un problema.
  
- Los modelos simples son fáciles de entender.


Se deben crear al menos dos features numéricas y dos features categóricas para entrenar una regresión logística, utilizando búsqueda de hiperparametros, realizando los encodings correspondientes y garantizando la reproducibilidad de los resultados cuando el notebook corriera varias veces. A su vez, usar un embedding para el campo text.


Conteste las preguntas:

- ¿Cuál es el mejor score de validación obtenido? (¿Cómo conviene obtener el dataset para validar?)
  
- Al predecir con este modelo para la competencia, ¿Cúal es el score obtenido? (guardar el csv con predicciones para entregarlo después)
  
- ¿Qué features son los más importantes para predecir con el mejor modelo? Graficar.
  

---

## Parte III: Machine Learning (4 puntos)


Entrenar 2 (de tipos distintos, excluyendo regresiones logísticas) modelos (2 puntos cada uno) con búsqueda de hiperparametros (¿cómo conviene elegir los datos de validación respecto de los de train?).

Los modelos deben cumplir las siguientes condiciones:

- Deben utilizar F1 score como métrica de validación.
- Deben medirse solo en validación, no contra la competencia.
- Deben ser reproducibles (correr el notebook varias veces no afecta al resultado).
- Deben tener un score en validación superior a 0,8.
- Para el feature engineering debe utilizarse mean encoding y one hot encoding al menos una vez cada uno.
- Se recomienda no limitarse a las features utilizadas previamente.

Deberán contestar la siguiente pregunta:
- Para el mejor modelo de ambos, ¿cuál es el score en la competencia? (guardar el csv con predicciones para entregarlo después)


---

## Parte IV: Consignas adicionales (2 puntos)


Sumar al menos 2 puntos adicionales, realizando las consignas a continuación que sean necesarias:

- Conseguir un modelo que con 4 features supere 0.80 de F1 (1 punto)
- Entrenar una red neuronal con una layer LSTM (Long Short-Term Memory) o GRU con un score mayor a 0.80 (No se incluye en los dos modelos previos) (2 puntos)
- Resolver el problema realizando un embedding para el campo text y KNN (No se incluye en los dos modelos previos) (1 puntos)
- Realizar un embedding para el campo text y visualizarlo con alguna técnica de reducción de visualizaciones distinta a PCA. En base a la visualización, ¿Sería posible predecir el target con este embedding? (2 punto)
- Graficar y analizar, para alguno de los modelos de la parte III, los siguientes resultados (1 punto): 
   - Curva ROC, explicando la selección de corte.
   - Feature importance.
   - Matriz de confusión.

---

## Criterio de corrección


Se necesita un 60% (6/10) de los puntos para aprobar.  


### Parte I

Cada visualización vale un punto, y debe cumplir con las siguientes condiciones:
- Debe explicarse por sí misma, sin necesidad de texto aclaratorio.
- Debe tener rótulos en los ejes que corresponda y en el título (incluyendo unidades si corresponde).
- Debe mostrar una relación con el target que sea clara.
- El uso del color debe ser intencional, elegido por ustedes, no por la librería.
- La visualización debe ser legible (Un bar chart de 40 barras por ejemplo es ilegible)
- Debe cumplir el objetivo propuesto

### Parte II

Vamos a corregir los siguientes puntos (no pueden restar más de 2 en total):
- Utiliza mal los datos de validación ya sea para obtener el resultado o para buscar hiper parámetros (-2 puntos), ejemplos: calcular el score con otras labels, calcular el score usando la predicción binaria y no la probabilidad, el set de validación se usa para elegir los parámetros pero también está dentro del entrenamiento de cada modelo, el set de validación se usa filtrando información a los encodings, etc.
- El modelo no está bien hecho (-2 puntos), ejemplo: entrenan con las labels o datos cambiados para algunas filas
- No es capaz de predecir para la competencia o no lo hace correctamente (-2 puntos)
- No es reproducible (-1 puntos)
- No obtiene bien los features más importantes (-1 puntos)
- La predicción en la competencia da menos de 0.5 (-1 puntos)
- La predicción para la competencia tiene errores (-0.5 punto)
- No utiliza todos los features (-0.5 punto)

### Parte III

Vamos a corregir los siguientes puntos en cada modelo de 2 puntos (a medida se acumulan estos pueden hacer que el modelo valga 0, pero nunca negativo):
- Para cada modelo cada condición no cumplida (o mal hecha) resta 0.5 puntos.
- Feature engineering inapropiado para el modelo elegido (-1 puntos), ejemplos: features que no están normalizadas para una red neuronal, features sin ninguna consideración de escalas para un KNN, etc.
- No buscan para todos los hiperparametros importantes (-1 puntos).

Además si un modelo diera un resultado menor a 0,6 en validación se invalida entero.
Por sobre el puntaje total del ejercicio (ambos modelos) se restan 2 puntos si cualquiera de las siguientes cosas suceden (no acumulables): eligen mal el mejor modelo entre los dos o la predicción para la competencia no está bien hecha o la predicción en la competencia da menos de 0.5.

### Detalles y recomendaciones

- Para consultas conceptuales sobre machine learning o preguntas de consigna pueden consultar en el canal de slack #consultas-tp3.
- Para consultas de código con su corrector o algún ayudante por privado.
- No deben buscar modelos entrenados por otros para usarlos, esto solo les puede jugar en contra porque es probable que no cumplan las condiciones pedidas, que no estén prolijos, que estén orientados a conseguir buenos resultados en la competencia (cosa que encima no evaluamos) y que tengan algún error conceptual.
- Recomendamos trabajar durante todo el TP en solo 4 notebooks: Uno de visualizaciones, otro para la regresión logística y uno para cada modelo de la parte III. Les recomendamos desarrollarlos de forma prolija y mostrar de forma ordenada cada uno de los resultados y pasos, con títulos y comentarios donde corresponda.
- El TP pide solo 6 visus y 3 modelos con condiciones muy claras, tengan esa consideración a medida avanzan para chequear que cumplen todo.
- El TP no pide ni evalúa más que lo que dice, si bien ser original y tener un buen score suma en términos de trabajo y aprendizaje para ustedes, sean inteligentes respecto a los modelos y features que eligen para trabajar para garantizar que pueden terminar. Ya van a tener tiempo de ser originales en el TP4…
- Particularmente este TP es muy difícil empezarlo al final, en cuotas se vuelve mucho más sencillo, les recomendamos empezar por las visus que no necesitan teoría nueva.
- Todos los puntos deben estar desarrollados.


