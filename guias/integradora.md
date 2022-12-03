# Guía integradora

Estos ejercicios no tienen un tema definido, son generales de toda la materia. Puede que tengan múltiples soluciones.

## Ejercicio 1

Se entrena un algoritmo de clasificación para determinar a que categoría corresponde una noticia. El algoritmo funciona muy mal con el set de test, todas las noticias que contienen la palabra “Alemania” son clasificadas en la categoría “conflictos bélicos” lo cual evidentemente no tiene sentido. ¿Qué está pasando? ¿Cuál sería su recomendación para solucionar el problema?

## Ejercicio 2

En cada una de las siguientes situaciones completar con el nombre de algún/algunos algoritmo/s o técnica/s que le permitan resolver el problema planteado. Desarrolle todo lo necesario para entender como usaría esa técnica.

1. Tenemos un set de datos de 25.000 observaciones  en 145.000 dimensiones que corresponden a  parámetros de un motor, cada dato cuenta con un label que indica si el motor tuvo o no una falla. Queremos entrenar un modelo de Machine Learning que aprenda a clasificar automáticamente si un motor va a fallar o no en base a sus parámetros.
2. Contamos con imágenes en B&N que corresponden a capturas de cámaras de seguridad, a partir de una imagen nueva queremos encontrar las imágenes más similares que tenemos almacenadas en nuestra base de imágenes.
3. Un sitio de noticias tiene una gran cantidad de noticias a mostrar pero solo puede mostrar 10 noticias en su página principal (homepage). Queremos mostrar noticias que puedan ser interesantes para el usuario. El sitio almacena qué noticias leyó cada usuario históricamente.
4. Contamos con una base de reportes de accidentes aéreos, usamos TF-IDF para procesar los reportes obteniendo un vector que representa a cada reporte. Cada reporte está asociado a una línea aérea. Queremos saber qué tipo de accidentes diferentes tenemos para calcular a qué tipo de accidente es más propensa cada línea aérea.
5. Una empresa de seguros quiere evaluar el nivel de riesgo de una persona con respecto a accidentes de tránsito, la empresa cuenta con una base de datos de clientes con más de 180 datos de cada uno y para cada uno tiene un nivel de riesgo asociado que puede ser bajo, medio o alto. La empresa quiere construir un modelo que a partir de los datos de la persona pueda predecir su nivel de riesgo y que sea factible explicarle al agente de seguros por qué la persona fue clasificada de esa forma.
6. Duolingo es una plataforma para aprender idiomas. Cuando un estudiantes está aprendiendo un nuevo idioma Duolingo quiere recomendarle historias para leer que sean incrementales en dificultad. ¿Cómo medirías la dificultad de una historia?
7. Tenemos un dataset de transacciones de tarjetas de crédito con un label que indica si fueron fraude o no. Tener en cuenta que las transacciones fraudulentas son el 0.01% del dataset. Tenemos varios modelos propuestos pero no sabemos como medir su performance.
8. Cuando escribís una pregunta en Stack Overflow se te muestra una serie de preguntas similares para asegurarte que no estés preguntando algo que ya se preguntó.
9. Queremos predecir el idioma en el que está escrito un texto.
10. Un chat-bot que permita pedir envíos de supermercado. El chat-bot no funciona con opciones sino que reconoce qué es lo que quiere hacer el usuario escrito de distintas formas.

## Ejercicio 3

En cada punto marcar todas las opciones correctas (puede ser una, todas o ninguna).

¿En qué tipo de modelo de Machine Learning tiene sentido agregar una nueva columna que sea el logaritmo de una columna existente?
`[ ]`  Xgboost
`[ ]`  Random Forests
`[ ]`  Redes Neuronales
`[ ]`  KNN

¿En Apache Spark si queremos reusar un RDD en varios cómputos que tipo de instrucción deberíamos usar?
`[ ]`  collect
`[ ]`  persist
`[ ]`  broadcast
`[ ]`  cache
`[ ]`  reduceByKey

¿Qué tipo de visualización es adecuada para comparar un grupo pequeño de registros en 10 dimensiones?
`[ ]`  Scatter Plot
`[ ]`  Radar Chart
`[ ]`  Barplot
`[ ]`  Piechart
`[ ]`  ViolinPlot
`[ ]`  Histograma

En Pandas si queremos calcular la diferencia entre el precio de un producto y el precio promedio de los productos en la misma categoría. ¿Qué tipo de operación deberíamos usar?
`[ ]`  groupby y agg
`[ ]`  applymap
`[ ]`  apply
`[ ]`  groupby y transform
`[ ]`  groupby y ngreatest
`[ ]`  map

¿Cuáles de las siguientes opciones ayudaría a combatir un problema de overfitting en Machine Learning?
`[ ]`  Tener un set de datos con más registros
`[ ]`  Usar regularización
`[ ]`  Eliminar las variables categóricas
`[ ]`  Tener un set de test más grande
`[ ]`  Agregar más features
`[ ]`  Normalizar los features

Un modelo con buen score contra el set de validación y mal score contra el set de test podría ser síntoma de:
`[ ]`  Underfitting
`[ ]`  Overfitting
`[ ]`  Set de validación sesgado
`[ ]`  Set de test sesgado

Si tenemos 5000 registros en 200 dimensiones y desconocemos la cantidad de clusters. ¿Cuál sería un buen algoritmo de clustering para aplicar?
`[ ]`  Kmeans
`[ ]`  DBScan
`[ ]`  Clustering jerárquico
`[ ]`  Clustering espectral
`[ ]`  t-SNE

¿Cuáles de las siguientes afirmaciones son ciertas para el algoritmo de Random Forests en Machine Learning?
`[ ]`  Se aplica el concepto de bagging
`[ ]`  Se aplica el concepto de boosting
`[ ]`  No sirven para regresiones
`[ ]`  A mayor cantidad de árboles más probable es que generen overfitting
`[ ]`  Carece de fase de entrenamiento
`[ ]`  El único hiper-parametro es la cantidad de árboles a usar
`[ ]`  Es un caso de ensamble
