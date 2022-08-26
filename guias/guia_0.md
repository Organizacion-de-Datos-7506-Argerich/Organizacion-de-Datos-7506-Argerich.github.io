# Guía 0: Fundamentos

Esta es una guía de fundamentos iniciales sobre probabilidad y estadística y repaso de análisis multivariado y álgebra.

## Ejercicio 1

Hallar la probabilidad de lanzar 3 monedas al aire y que salgan dos caras y una ceca.

## Ejercicio 2

En un mazo de 40 cartas españolas, calcular la probabilidad de que al elegir una carta, ésta sea:
1. Un ancho
2. Una carta de espada
3. El 4 de copas

## Ejercicio 3

Calcular la probabilidad de que al tirar un dado de 6 caras salga:
1. Un número par
2. Un número impar
3. Un múltiplo de dos

## Ejercicio 4

Calcular la probabilidad de que al tirar dos veces un dado de 6 caras, la suma de los resultados sea 6.

## Ejercicio 5

En una urna hay 4 bolas amarillas, 2 verdes, 3 azules y 1 violeta. Calcular la probabilidad de:

1. Sacar una amarilla
2. Sacar una verde
3. Sacar una azul
4. Sacar una violeta
5. Sacar una roja

## Ejercicio 6

Se lanzó un dado 10 veces y se obtuvieron los siguientes valores: 1, 2, 2, 4, 6, 6, 5, 6, 6, 3. Calcular la varianza.

## Ejercicio 7

Se realizó un experimento aleatorio y se obtuvieron los siguientes resultados: 10,5,4,20,9.

1. Calcular la varianza
2. Calcular el desvio estandar

## Ejercicio 8

Se lanzó un dado 4 veces y se obtuvieron los siguientes resultados: 4,2,6,5. Calcular el desvío estándar.

## Ejercicio 9

Dada la siguiente tabla con resultados de observaciones de dos variables x e y, calcular el coeficiente de correlación y determinar de qué tipo de correlación se trata:

| x | y | xy | x^2 | y^2 |
|---|---|----|-----|-----|
| 1 | 1 | 1  | 1   | 1   |
| 2 | 2 | 4  | 4   | 4   |
| 2 | 1 | 2  | 4   | 1   |
| 3 | 1 | 3  | 9   | 1   |
| 4 | 2 | 8  | 16  | 4   |

## Ejercicio 10

Dada la siguiente tabla con resultados de observaciones de dos variables x e y, calcular el coeficiente de correlación y determinar de qué tipo de correlación se trata:

| x | y   |
|---|-----|
| 2 | 0.5 |
| 3 | 0.4 |
| 4 | 0.3 |
| 5 | 0.1 |

## Ejercicio 11

Encontrar el mínimo y su posición en (x,y) de la función $$f(x,y) = 4x^2+2(x-2)+y^2-5$$.

## Ejercicio 12

Compruebe que en $$\mathbb{R}^2$$ la suma de los subespacios que comprenden dos rectas distintas $$S_1$$ y $$S_2$$ que pasan por el origen es todo $$\mathbb{R}^2$$.

# Respuestas

## Ejercicio 1

Definir los casos posibles y los favorables.
Denoto a los eventos:
* C: salió cara
* X: salió ceca
* Y: salieron dos caras y una ceca

Casos posibles = ccc,ccx,cxc,cxx,xxx, xcc,xcx,xxc.
Casos favorables = ccx,cxc,xcc

$$P(Y) = \frac{3}{8}$$

## Ejercicio 2

Definir los casos posibles y los favorables.
1. Denoto a los eventos:
  - Casos posibles = 40
  - Y: "La carta elegida es un ancho"
  - $$P(Y) = \frac{4}{40} = \frac{1}{10}$$
2. Y: "La carta elegida es de espada"
  - $$P(Y) = \frac{1}{4}$$
3. Y: "La carta elegida es el 4 de copas"
  - $$P(Y) = \frac{1}{40}$$

## Ejercicio 3

1. $$\frac{1}{2}$$
2. $$\frac{1}{2}$$
3. $$\frac{1}{2}$$

## Ejercicio 4

Casos favorables:

|   | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|
| 1 |   |   |   |   | x |   |
| 2 |   |   |   | x |   |   |
| 3 |   |   | x |   |   |   |
| 4 |   | x |   |   |   |   |
| 5 | x |   |   |   |   |   |
| 6 |   |   |   |   |   |   |

Respuesta: $$\frac{5}{36}$$

## Ejercicio 5

1. $$\frac{4}{10}$$
2. $$\frac{2}{10}$$
3. $$\frac{3}{10}$$
4. $$\frac{1}{10}$$
5. $$0$$

## Ejercicio 6

Calculamos el valor medio:

$$\bar{X} = 4,1$$

Luego la varianza:

<font size="2">$$\sigma^2 = \frac{(1-4,1)^2+(2-4,1)^2+(2-4,1)^2+(4-4,1)^2+(6-4,1)^2+(6-4,1)^2+(5-4,1)^2+(6-4,1)^2+(6-4,1)^2+(3-4,1)^2}{10}$$</font>

## Ejercicio 7

Varianza: $$32,88$$

Desviación: $$5,7341$$

## Ejercicio 8

$$\sigma^2 = \frac{(4−3,5)^2+(2−3,5)^2+(6−3,5)^2+(5−3,5)^2}{4}$$

$$\sigma = \sqrt{\sigma^2}$$

## Ejercicio 9

$$r = \frac{SS_{XY}}{\sqrt{SS_{XX}SS_{YY}}} = \frac{1,2}{\sqrt{5,2*1,2}} = 0,4803$$

## Ejercicio 10

Es una correlación negativa: $$-0.979$$

## Ejercicio 11

Planteamos el gradiente y lo igualamos a 0 para encontrar mínimos y máximos locales.

El mínimo es: $$\frac{-37}{4}$$ y está en $$x=-\frac{1}{4}, y=0$$
