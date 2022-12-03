# Guía de Clustering

## Ejercicio 1

Dados los siguientes puntos: (1,2) (1,3) (1,5) (2,3) (2,8) (3,3) (4,1) (4,9) (7,8) (9,9) (12,2) (13,4)

Agrupar utilizando Clustering Jerárquico, indicando la cantidad de clusters resultantes y el criterio utilizado para definir dicho número.
Representar el dendrograma mostrando como se agrupan los distintos elementos en los clusters obtenido.

## Ejercicio 2

Se tienen los centroides $$(0,0)$$ y $$(100, 40)$$. Dados los siguientes puntos, indicar para cuál de ellos cambiaría el centroide al cual queda asignado según si se usa distancia Manhattan o Euclídea:
* $$(53, 15)$$
* $$(51, 15)$$
* $$(50, 18)$$
* $$(51, 13)$$

## Ejercicio 3

Dados los siguientes puntos en dos dimensiones:
$$(5,1)$$, $$(5, 3)$$, $$(4, 4)$$, $$(9, 4)$$, $$(10, 3)$$, $$(11, 6)$$

Aplicar K-Means con centroides iniciales en $$(8, 1)$$ y $$(7, 5)$$.

## Ejercicio 4

Sea los siguientes puntos en dos dimensiones:
* $$x_1=(0,0)$$
* $$x_2=(8,0)$$
* $$x_3=(16,0)$$
* $$x_4=(0,6)$$
* $$x_5=(8,6)$$
* $$x_6=(16,6)$$

Sobre estos puntos queremos usar K-Means, con la distancia euclídea, para encontrar 3 clusters. Sabemos que el resultado del algoritmo depende de la forma en la que elijamos los tres centroides iniciales. En base a esto responder:

* ¿Cuántas configuraciones iniciales posibles existen?
* ¿Cuántas clusterizaciones finales son posibles? (es decir aquellas clusterizaciones en las que K-Means ya ha convergido).

## Ejercicio 5

En cada uno de los siguientes casos sugiera que algoritmo de clustering usaría:

1. 1000 puntos, 3 clusters de diferentes densidades y formas complejas.
2. 1340 millones de puntos, 168 clusters de diferentes densidades y forma regular.
3. 20.000 millones de puntos, no sabemos la cantidad de clusters, densidad variable y formas complejas.
