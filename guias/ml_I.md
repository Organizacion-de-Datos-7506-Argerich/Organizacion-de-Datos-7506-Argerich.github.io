# Guía de Machine Learning I

## Ejercicio 1

Proponer datasets de train y de test y un modelo de regresión (entrenado sobre train) tal que el MSE en test sea 0.5 pero en train sea 0.

## Ejercicio 2

Proponer datasets de train y de test tal que un KNN (entrenado sobre train) con k=3 clasifique mal más de la mitad de los puntos de test.

## Ejercicio 3

Considerar los siguientes puntos en una dimensión y la clase a la que pertenece cada punto:

5-b, 10-b, 2-b, 6-a, 7-b, 8-b, 0-a, 13-b, 16-b, 1-a, 3-a, 17-b (el número es el valor de x, la letra es la clase a la que pertenece)

Se quiere usar KNN para clasificar los puntos con la distancia Manhattan. A fin de encontrar el valor óptimo de k (cantidad de vecinos) se decide usar cross-validation con folds de 4 registros, considerar los folds en el orden en que fueron presentados los puntos, es decir que el primer fold tiene (5-b,10-b,2-b,6-a).

Determinar el valor óptimo de "k" realizando grid-search para tres valores posiblesde k: 1,3 y 5. Usar precisión (accuracy) como métrica.
