# Guía de Fairness

## Ejercicio 1

Tenemos un dataset de transacciones de tarjetas de crédito con un label que indica si fueron fraude o no y con eso entrenamos y ponemos a funcionar en tiempo real un modelo para detectarlas. Contamos con las siguientes afirmaciones:

* Las transacciones fraudulentas son el 0.01% de todas las transacciones
* El dataset de train tiene un 1% de transacciones fraudulentas
* El dataset de test tiene un 0.01% de transacciones fraudulentas ya que es una muestra fiel del universo real.
* El modelo indica que el 0.1% de las transacciones que le llegan son fraudulentas.

Indique cual/cuales de las siguientes afirmaciones son correctas:

`[ ]`  El dataset de train es sesgado respecto de la realidad

`[ ]`  El dataset de test es sesgado respecto de la realidad

`[ ]`  En test el modelo tendrá como mucho una precisión para la clase fraudulenta de 10%.

`[ ]`  El modelo tiene un sesgo respecto de la realidad

`[ ]`  El dataset de train es insesgado

`[ ]`  El dataset de test es insesgado

`[ ]`  El modelo es insesgado

## Ejercicio 2

Para un modelo se tiene en test las siguientes predicciones $$\hat{y}$$ y sus labels reales $$y$$:

| $$\hat{y}$$   	| $$y$$ 	|
|-----	|---	|
| 0.1 	| 0 	|
| 0.1 	| 0 	|
| 0.3 	| 1 	|
| 0.3 	| 0 	|
| 0.3 	| 0 	|
| 0.3 	| 0 	|
| 0.7 	| 1 	|
| 0.7 	| 1 	|
| 0.7 	| 0 	|
| 0.7 	| 1 	|
| 0.7 	| 1 	|
| 0.9 	| 1 	|
| 0.9 	| 1 	|

Dibuje la curva de calibración y la curva ideal que debería seguir si estuviera perfectamente calibrado.

## Ejercicio 3

¿Cuál de las siguientes afirmaciones sobre el caso de COMPAS son ciertas?

`[ ]`  El dataset está sesgado a la realidad

`[ ]`  No se sabe si el dataset está sesgado respecto de la realidad

`[ ]`  Según lo medido algunas razas tienden a reincidir más frecuentemente

`[ ]`  En el contexto de COMPAS no se pueden igualar la calibración y la tasa de falsos positivos

`[ ]`  Un modelo insesgado es también justo

`[ ]`  Un modelo calibrado es también justo

`[ ]`  Un modelo que trate a todos los grupos de igual forma es también justo

## Ejercicio 4

Imagine un ejemplo para cada uno de los casos siguientes que según su propia ética cumpla lo pedido. Explique cuál criterio ético está siguiendo en términos de métricas y lo que quiera explicar del universo real y los datos obtenidos:

* Un modelo que da resultados distintos según la orientación sexual, pero no es injusto.
* Un caso donde aplicar discriminación positiva disminuya las métricas de costo, pero que en el universo real las mejore.
* Un caso donde lo más justo sea tener un modelo bien calibrado
* Un caso donde lo más justo sea tener group fairness por tasa de verdaderos positivos
* Un caso donde crea que es importante la individual fairness

## Ejercicio 5

Se identifican 3 tipos de origen posibles de diferencias entre grupos: Sesgo en la medición, Prejuicio histórico y Diferencia intrínseca. Proporcione un ejemplo distinto a los vistos para cada uno. De un ejemplo de una diferencia entre grupos que no podamos saber en que categoría va.
