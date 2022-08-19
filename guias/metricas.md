# Guía de Métricas y Errores

## Repaso teórico

Llamamos "métrica" a toda forma de medir que tan bien le va a un modelo. Un "error" o "pérdida" u "objetivo" es una métrica que se usa para entrenar los parámetros de un modelo.

Vimos 4 métricas de clasificación importantes:
* Accuracy
* Precisión
* Recall
* AUC-ROC

Además vimos 2 de regresión:
* MSE
* MAE

### Accuracy

$$\textit{accuracy} = \frac{\textit{#correctos}}{\textit{#total}}$$

### Precisión

La precisión para una clase es:
$$\textit{precision}_{\textit{clase}} = \frac{\textit{#predichos correctos de la clase}}{\textit{#predichos para la clase}}$$

### Recall

El recall para una clase es:
$$\textit{recall}_{\textit{clase}} = \frac{\textit{#recuperados de la clase}}{\textit{#miembros de la clase}}$$

### AUC-ROC

Es la probabilidad de que dados dos puntos de la clase 0 y 1 cualesquiera, sus probabilidad estén bien ordenadas.

### MAE

$$\sum_{i=1}^{N}\frac{|x_i-y_i|}{N}$$

### MSE

$$\sum_{i=1}^{N}\frac{(x_i-y_i)^2}{N}$$

El MSE es más sensible que el MAE a errores grandes.

## Ejercicio 1

Dadas las labels [0,1,0,1,1] y las predicciones [0.1, 0.3, 0.4, 0.99, 0.6]. ¿Con qué cortes la accuracy es $$\frac{4}{5}$$?
* 0.2
* 0.7
* 0.5
* 0.9

## Ejercicio 2

Dadas las labels [0,1,0,1,1] y las predicciones [$$x$$, 0.3, 0.6, $$x$$, 0.7]. ¿Para cúales de los siguientes valores de $$x$$ la precisión de la clase 1 es $$\frac{1}{2}$$ teniendo en cuenta que el corte es 0.5?
* $$x=0.99$$
* $$x=0.4$$
* $$x=0.55$$
* $$x=0.04$$

## Ejercicio 3

¿Cúal de las siguientes afirmaciones sobre AUC-ROC es correcta?

* El peor modelo posible tiene roc-auc 0.5
* El peor modelo posible tiene roc-auc 0
* En un problema de clasificación binaria, no importa el balanceo de las clases, tirar una moneda para predecir siempre va a dar AUC-ROC 0.5
* AUC-ROC es la mejor métrica para clasificación

## Ejercicio 4

Calcular el AUC-ROC para las labels [1,0,1,0,1] y las predicciones [0.3, 0.1, 0.7, 0.4, 0.9].

## Ejercicio 5

Calcular el MSE para el target [2000, 6000, 1000, 100] y predicciones [1700, 4000, 900, 0].

## Ejercicio 6

Tenemos un dataframe representando precios de pasajes de diferentes líneas aéreas. Las columnas del dataframe son:

* Línea (código de línea aérea)
* Fecha (fecha en que fue emitido el pasaje)
* Categoría (por ejemplo Economy, Economy Plus, First Class, etc.)
* Ciudad Origen
* Ciudad Destino
* Precio del pasaje

Queremos construir un modelo predictivo que nos permita predecir el precio en base a las otras variables. Se decide usar un algoritmo basado en Gradient-Boosting para la construcción del modelo. ¿Qué métrica usaria para evaluar el modelo?

# Respuestas

## Ejercicio 1

Si el corte es 0.2 las predicciones son [0, 1, 1, 1, 1] con accuracy 4/5.

Si el corte es 0.5 las predicciones son [0, 0, 0, 1, 1] con accuracy tambien 4/5.

Los otros dos cortes no logran accuracy 4/5.

## Ejercicio 2

Si elegimos $$x > 0.5$$ las predicciones quedan [1, 0, 1, 1, 1] lo que hace que la mitad de los puntos clasificados como 1s estén mal, por lo tanto dando precisión de $$\frac{1}{2}$$.

Por otro lado, si elegimos $$x < 0.5$$ las predicciones dan [0, 0, 1, 0, 1] donde de nuevo la precisión de la clase 1 es $$\frac{1}{2}$$.

Todas las respuestas son correctas.

## Ejercicio 3

Si el AUC-ROC es 0 entonces tus probabilidades están todas al revés, por lo que hacer 1 - tu predicción es un predictor perfecto. En terminos de valor predictivo este modelo es igual de bueno que uno con AUC-ROC de 1.

Por otro lado si el AUC-ROC es 0.5, todas tus probabilidades están ordendas de forma aleatoria y es lo mismo que tirar una moneda para decidir, no tiene ningún valor predictivo. Esto es cierto no importa el balance de clases en el dataset.

AUC-ROC es una métrica complementaria de otras, no es necesariamente la mejor y funciona mal en datasets fuertemente desbalanceados.

Resumiendo solo las 3 primeras opciones son correctas.

## Ejercicio 4

0.83333...

# Ejercicio 5

1027500

## Ejercicio 6

Se puede usar o bien MAE o MSE ya que son métricas de regresión. ¿Cuál es la más adecuada para el negocio?
