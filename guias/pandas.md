# Guia Pandas

Los ejercicos estan separados segun la clase teorico/practica a la que corresponden para que sepan con que herramientas estan pensados que se resuelvan. De todas formas
para practicar mas adelante pueden volver e intentar los ejercicios practicos utilizando otras herramientas y comparando. Los ejercicios de eleccion multiple pueden tener una
o varias respuestas correctas.

# Pandas I
## EJ 1

Al hacer groupby, pandas nos devuelve un nuevo objeto distinto a un DataFrame porque:


`[ ]`  Los datos pueden ser de cualquier tipo, entonces no puede inferir como unirlos
    
    
`[ ]`  Al no tener una función de agregación, no sabría cómo unir los datos
    
    
`[ ]`  Es una decisión de diseño arbitraria de Pandas
    
    
`[ ]`  La serie de cada columna no tiene un tipo definido

<details>
  <summary>Respuesta</summary>
  
```
    TBA
```  
</details>

## EJ 2
Realizar los siguientes items en orden:
- Generar un dataset de los números de n a m con su correspondiente raíz cuadrada
- Obtener del dataset la cantidad de raíces enteras para los números pares
- Dado un número k, obtener el promedio de los números cuyas raíces son enteras en los intervalos de largo k  entre n y m.

**Aclaración**: _Entre **n**=2 y **n**=7, con **k**=3 hay 2 intervalos o segmentos no superpuestos de de largo **k**:_ `[2:4]` _y_ `[5:7]`. 

<details>
  <summary>Respuesta</summary>
  
```
    TBA
```  
</details>

# Pandas II
## EJ 3
Se tienen dos DataFrames df1 df2 y se les aplica `pd.concat([df2,df1]).fillna(0)` que se guarda en df3, cuales de las siguientes afirmaciones son correctas

`[ ]`  Los dtype de las columnas de df3 son todas `int` por haber utilizado el `fillna(0)`

`[ ]`  Los dtype de las columnas de df3 son todas `float` por haber tenido antes nans

`[ ]`  len(df3.columns) < len(df1.columns) + len(df2.columns)

`[ ]`  len(df3) = len(df1) + len(df2)

`[ ]`  El índice de df3 está ordenado

<details>
  <summary>Respuesta</summary>
  
```
    TBA
```  
</details>

## EJ 4
Se tiene un DataFrame con las columnas `año , actor , prenda , marca`. Se dice que un conjunto (prenda + marca) está ‘quemado’ si lo usa mucha gente. Agregar al dataframe una columna que indique si el actor usó un conjunto ‘quemado’, considerando que para que esté quemado, se tiene que haber utilizado más veces que el 2% del número de los actores que aparecen todos los años en el dataset.

**Aclaración**: _Un actor puede aparecer múltiples veces por año, incluso utilizando el mismo conjunto, y cada uso cuenta por separado_

<details>
  <summary>Respuesta</summary>
  
```
    TBA
```  
</details>

# Pandas III
## EJ 5
Para un DataFrame df cualquiera

`[ ]`  `df.stack().unstack()` no tiene valores `NaN`

`[ ]`  `df.unstack().stack()` devuelve un df sin valores `NaN`

`[ ]`  Siempre puedo hacer `df.stack()`

`[ ]`  Siempre puedo hacer `df.unstack()`

<details>
  <summary>Respuesta</summary>
  
```
    TBA
```  
</details>

## EJ 6
Tengo un df cuya columna A tiene un `dtype` `int8` y una columna B con `dtype` `float`. Al hacer `df.T`

`[ ]`  El DataFrame mantiene o aumenta el uso de memoria

`[ ]`  El DataFrame mantiene o reduce el uso de memoria

`[ ]`  Le puedo aplicar `.T` para volver al mismo df original

`[ ]`  Van a aparecer nuevos valores `NaN`

<details>
  <summary>Respuesta</summary>
  
```
    TBA
```  
</details>
