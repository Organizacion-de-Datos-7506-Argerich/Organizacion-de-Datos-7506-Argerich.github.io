# Guía de Feature Engineering

## Repaso teórico

El feature engineering es el proceso de **creación o transformación de features**.

### One Hot Encoding
Consiste en **agregar una columna nueva por cada valor posible** que pueda tomar el feature en cuestión. Tenemos un problema cuando el feature puede tomar muchos valores posibles ya que agrega al dataset muchísimas columnas.

Por ejemplo, imaginemos que tenemos el siguiente dataset:

| País	      | Label		|
| ----------- | ----------- |
| Argentina   | 1           |
| Brasil	  | 1           |
| Argentina   | 0           |
| NaN	      | 1           |
| Brasil	  | 1           |

El dataset con la columna 'País' encodeada mediante One Hot Encoding quedaría así:

| Argentina   | Brasil	    | NaN		  | Label	    |
| ----------- | ----------- | ----------- | ----------- |
| 1		      | 0		    | 0		      | 1           |
| 0		      | 1		    | 0		      | 1           |
| 1		      | 0		    | 0		      | 0           |
| 0		      | 0		    | 1		      | 1           |
| 0		      | 1		    | 0		      | 1           |

### Binary Encoding
Consiste en **asignarle a los valores posibles de una columna un número distinto en binario**. En lugar de tener una sola columna para este valor, **agregamos tantas columnas como bits necesitemos** para representar el valor máximo que puede tomar el feature.

Por ejemplo, imaginemos que tenemos el siguiente dataset:

| País	      | Label		|
| ----------- | ----------- |
| Argentina   | 1           |
| Brasil	  | 1           |
| Argentina   | 0           |
| NaN	      | 1           |
| Brasil	  | 1           |

El dataset con la columna 'País' encodeada mediante Binary Encoding quedaría así:

| bit_2	      | bit_1	    | Label	      |
| ----------- | ----------- | ----------- |
| 0		      | 0		    | 1           |
| 0		      | 1		    | 1           |
| 0		      | 0		    | 0           |
| 1		      | 0		    | 1           |
| 0		      | 1		    | 1           |

### Mean Encoding
Consiste en **asignarle a los valores posibles de una columna el promedio de los labels de ese valor**. Esto tiene el problema de que se filtra información de los labels en los features del dataset. La ventaja de Mean Encoding es que no importa la cantidad de valores posibles que pueda tomar una columna, siempre la vamos a reemplazar por una única columna nueva.

Por ejemplo, imaginemos que tenemos el siguiente dataset:

| País	      | Label		|
| ----------- | ----------- |
| Argentina   | 1           |
| Brasil	  | 1           |
| Argentina   | 0           |
| NaN	      | 1           |
| Brasil	  | 1           |

El dataset con la columna 'País' encodeada mediante Mean Encoding quedaría así:

| País	      | Label		|
| ----------- | ----------- |
| 0.5	      | 1           |
| 1			  | 1           |
| 0.5	      | 0           |
| NaN	      | 1           |
| 1			  | 1           |

### Label Encoding
Consiste en **asignarle a los valores posibles de una columna un número entero distinto**. **Se agrega solamente una columna** en la que cada valor categórico es reemplazado por el número que le corresponde.

Por ejemplo, imaginemos que tenemos el siguiente dataset:

| País	      | Label		|
| ----------- | ----------- |
| Argentina   | 1           |
| Brasil	  | 1           |
| Argentina   | 0           |
| NaN	      | 1           |
| Brasil	  | 1           |

El dataset con la columna 'País' encodeada mediante Label Encoding quedaría así:

| País	      | Label		|
| ----------- | ----------- |
| 0 	      | 1           |
| 1			  | 1           |
| 0 	      | 0           |
| 2 	      | 1           |
| 1			  | 1           |

### Usando NLP Para Encodear
En algunos casos, puede pasar que tengamos una columna categórica pero que tenga mucho texto. Esto podría suceder si se tuviera una columna que fuera la descripción de un producto o una review de un negocio por ejemplo. De esta forma, las técnicas antes mencionadas pierden su utilidad. Es por eso que se pueden utilizar **técnicas de NLP tales como TF-IDF o Bag Of Words (BOW) para encontrar las *n* palabras más importantes y luego crear una columna para cada una de esas palabras**. Entonces, una fila tendrá un 1 si su texto contiene esa palabra, o tendrá un 0 en otro caso.

## Ejercicio 1

Dado el campo Padrón en un dataset de notas de estudiantes, ¿Cuál de las siguientes es la mejor forma de encodearlo?
* One hot encoding
* Mean encoding
* Lo dejo como está
* No lo puedo usar, debo sacarlo

## Ejercicio 2

Dado el campo categórico "nivel de inglés" (A1, A2, etc.) en un dataset de postulantes para trabajos, ¿Cuál es la mejor forma de encodearlo?

* One hot encoding
* Mean encoding
* Label encoding
* Binary encoding

## Ejercicio 3

Dados dos features $$f_1$$ y $$f_2$$ y un problema de clasificación. ¿Cúal de los siguientes modelos se beneficiaria menos de usar combinaciones de ambos (por ejemplo $$f_1*f_2$$ ó $$f_1+f_2$$)?

* XGboost
* Regresión logística
* Red neuronal
* KNN

## Ejercicio 4

Es necesario normalizar los datos para trabajar con cuales de estos modelos:

* Regresión Logística
* Xgboost
* Redes neuronales
* Random forest

## Ejercicio 5 (a desarrollar)

Tenemos un dataframe representando precios de pasajes de diferentes líneas aéreas. Las columnas del dataframe son:

* Línea (código de línea aérea)
* Fecha (fecha en que fue emitido el pasaje)
* Categoría (por ejemplo Economy, Economy Plus, First Class, etc.)
* Ciudad Origen
* Ciudad Destino
* Precio del pasaje

Queremos construir un modelo predictivo que nos permita predecir el precio en base a las otras variables. Se decide usar un algoritmo basado en Gradient-Boosting para la construcción del modelo. Responda:

1. Explique de qué forma transformaría el dataset para que sea aceptado por XGboost
2. Indique qué features agregaría además de los que ya existen y por qué considera que podrían ser importantes para predecir el precio del pasaje.

# Respuestas

## Ejercicio 1

Existe la posibilidad de que no resulte útil usarlo, pero no podemos asegurarlo, asique primero descartamos la última opción. De las otras la opción correcta es mean encoding ya que podemos encodear el padrón como el promedio del target o algún otro feature (por ejemplo promedio de la nota por estudiante).

## Ejercicio 2

Dado que la variable tiene un orden intrínseco la mejor opción es label encoding ya que lo conserva, dejando números mayores a medida el nivel es mayor.

## Ejercicio 3

La red neuronal ya que es la que tiene más capacidad de ver interacciones entre features y por lo tanto la que menos necesita este tipo de feature engineering.

## Ejercicio 4

Ya que el aprendizaje está basado en un gradiente es útil normalizar solo en regresión logística y redes neuronales.

## Ejercicio 5

Tiene múltiples respuestas correctas posibles.
