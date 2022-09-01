# Guía de Visualizaciones

## Repaso teórico

### Plots de distribución continua

Los plots de distribución continua muestran como se distribuye una variable continua, pudiendo mostrarla en función de alguna variable discreta. Estos plots son:

* Histograma: Soporte continuo en el eje x, frecuencia en el eje y.
* Density plot: Igual que el histograma pero suavizado.
* Box plot: Soporte continuo en un eje, con opción de variable discreta en el otro eje para comparar distribuciones condicionadas. Es una "caja" que muestra varios estadísticos: Q1, Q2, Q3 y máximos y mínimos atípicos.
* Violin plot: Similar al box plot en función pero permite ver la forma de la distribución de igual forma que un density plot.

### Plot de distribución discreta

Los plots de distribución discreta muestran como se distribuyen las variables discretas, pudiendo mostrarla en función de otra variable discreta condicionada.

* Pie plot
* Bar plot
* Stacked bar plot
* Treemap

### Plot de relación

Muestran la relación entre varias variables.

* Scatter plot: Gráfico de puntos con ejes continuos.
* Regression plot: Scatter plot con regresión y a veces coeficientes de Pearson R1 y R2.
* Heatmap: Dos ejes discretos y un cuadrado con un mapa de colores para cada intersección que muestra el valor de algún agregado para ese grupo.

### Plots de series de tiempo

* Line plot: Para series de tiempo continuas.
* Lollipop plot: Para series de tiempo discretas.

## Ejercicio 1

Dadas tres variables continuas x1, x2 y x3 queremos ver como se dsitribuyen entre sí. ¿Cúales de los siguientes plots puede ser útil?

* Scatter plot 3D
* Bar plot discretizando las 3 variables
* Heatmap discretizando dos de las variables
* Violin plot discretizando una variable

## Ejercicio 2

Tenemos un dataset que muestra estadísticas para personas que tuvieron y que no tuvieron un infarto en una encuesta. El dataset consiste de las columnas:

* Edad
* ¿Es fumador?
* Colesterol
* Sexo
* ¿Tuvo infarto?

Proponga dos visualizaciones que puedan resultar interesantes para explicar quienes tuvieron un infarto. Dibujelas.

# Respuestas

## Ejercicio 1

Scatter plot 3D: Sí, funciona.
Bar plot discretizando las 3 variables: No es posible.
Heatmap discretizando dos de las variables: Sí, si ponemos las variables discretizadas en los ejes x e y con agregados de la tercera en el medio, es una buena idea.
Violin plot discretizando una variable: Podemos hacerlo discretizando dos y poniendo una en el eje x y otra como `hue`, pero no se puede discretizando una sola.

## Ejercicio 2

Tiene múltiples soluciones, voy a dejar una:

1. Edad según infarto como violin plot

2. Probabilidad de tener un infarto por edad y si es fumador como heatmap

Intenten dibujarlas en papel.
