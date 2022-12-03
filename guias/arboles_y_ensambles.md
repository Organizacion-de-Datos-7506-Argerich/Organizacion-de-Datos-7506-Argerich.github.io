# Guía de Árboles y Ensambles

## Ejercicio 1

Proponer dataset de train y un árbol de decisión entrenado sobre el mismo que cumpla las siguientes condiciones:
* La variable de entrada del arbol es el mean encoding de una variable categórica de almenos 3 clases
* El modelo tiene accuracy de 0.75 en train

Muestra claramente tanto el arbol como el dataset.

## Ejercicio 2

Hay un dataset de train de clasificación binaria y dos modelos de los cuales se conoce solo las probabilidades que predice ($$\hat{y}$$) para ese dataset. Para un modelo la accuracy de su $$\hat{y}$$ en train es 0.5, para el otro la accuracy es 0.6, pero ensamblados con averaging de su probabilidad la accuracy es 0.7 en train.

Indique cuales son las salidas de ambos modelos $$\hat{y}_1$$ y $$\hat{y}_2$$.

## Ejercicio 3

¿Cuáles de las siguientes técnicas sirve para reducir el overfitting en XGBoost? Justificar.

* Aumentar el número de estimadores
* Reducir el valor del hiperparámetro `max-depth`.
* Reducir el valor de `subsample`.
* Aumentar el valor de `colsample_by_tree`.
* Reducir el learning rate.

## Ejercicio 4

Tenemos un dataframe representando precios de pasajes de diferentes líneas aéreas. Las columnas del dataframe son:
* Linea
* Fecha
* Categoría
* Ciudad Origen
* Ciudad Destino
* Precio del pasaje

Queremos construir un modelo predictivo que nos permita predecir el precio en base a las otras variables. Se decide usar un algoritmo basado en Gradient-Boosting para la construcción del modelo. Responda paso a paso cada una de las siguientes preguntas:

1. Explique de qué forma transformaría el dataset para que sea aceptado por Xgboost
2. Indique qué features agregaría además de los que ya existen y por qué considera que podrían ser importantes para predecir el precio de pasajes.
3. Indique de qué forma dividiría el dataset en train, validation y test.
4. ¿Con qué métrica evaluaría la performance del modelo?
5. ¿Cuáles son los hiper-parámetros más importantes? ¿Cómo haría la búsqueda de hiper-parámetros?
6. Indique una o más visualizaciones que utilizaría para comunicar a la gerencia la utilidad del modelo.
7. Explique que diferencias existirían en su proceso si en lugar de usar Xgboost quisiera usar redes neuronales
