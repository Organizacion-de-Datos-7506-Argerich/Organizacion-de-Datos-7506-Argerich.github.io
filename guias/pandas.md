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

_Los datos pueden ser de cualquier tipo, entonces no puede inferir como unirlos_
  - **Verdadero**: Si bien algunos metodos tienen cosas por defecto, `groupby` afecta a todo el DataFrame, entonces no es posible definir una funcion de agregacion que funcione para todo o la mayoria de los casos.


_Al no tener una función de agregación, no sabría cómo unir los datos_
  - **Verdadero**: Es un tanto redundante, pero si agrupa los datos y no tiene como unirlos, mucho no puede hacer. Aclaracion al margen, si la idea es 'no hacer nada', `set_index` ya deja implicitamente agrupar las filas bajo un mismo indice.  

_Es una decisión de diseño arbitraria de Pandas_
 - **Falso**: Seria arbitrario si no tuviese un por que, o mejor dicho si diera lo mismo hacerlo de una forma u otra.

_La serie de cada columna no tiene un tipo definido_
 - **Falso**: Las columnas tienen un tipo definido. Incluso cuando no se sabe que tienen, tienen un tipo definido `object`.

</details>

## EJ 2
Realizar los siguientes items en orden:
- Generar un dataset de los números de n a m con su correspondiente raíz cuadrada
- Obtener del dataset la cantidad de raíces enteras para los números pares
- Dado un número k, obtener el promedio de los números cuyas raíces son enteras en los intervalos de largo k  entre n y m.

**Aclaración**: _Entre **n**=2 y **n**=7, con **k**=3 hay 2 intervalos o segmentos no superpuestos de de largo **k**:_ `[2:4]` _y_ `[5:7]`.

<details>
  <summary>Respuesta</summary>

``` python

df = pd.DataFrame( [ [x,x**(1/2)] for x in range(n,m+1) ] , columns=["numero","raiz"])

df["es_entera"] = df.raiz.map(lambda x: (x-int(x)) == 0)
pares = df[df.numero.map(lambda x: x%2==0)]
print("Raices enteras para los numeros pares ",pares.es_entera.sum())

df["intervalo"] = df.numero.map( lambda x: (x-n) // k )
agrupado = df.groupby("intervalo").sum()
print("Promedio de raices enteras en intervalos de largo k",agrupado.es_entera.mean())

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

_Los dtype de las columnas de df3 son todas `int` por haber utilizado el `fillna(0)`_
  - **Falso**: Si alguna de las columnas no estaba en el otro, la columna quedo con tipo (al menos) `float`. De todas formas, si habia columnas con otro tipo, el `fillna` no les va a cambiar el tipo.

_Los dtype de las columnas de df3 son todas `float` por haber tenido antes `NaN`_

- **Falso**: Es solo verdadero si la columna era originalmente un dato numerico. Si era otra cosa la columna va a generalizarse como `object`.

_len(df3.columns) < len(df1.columns) + len(df2.columns)_

- **Falso**: Si df1 y df2 no comparten columnas df3 va a tener las columnas de ambos DataFrames.

_len(df3) = len(df1) + len(df2)_

- **Verdadero**: Las filas se agregan, no se agrega nada mas ni se elimina nada.

_El índice de df3 está ordenado_

- **Falso**: Los indices (por fila) se pegan. Si uno es [0-10] y el otro [0-10], el indice de df3 va a ir de 0 a 10 y nuevamente de 0 a 10.

</details>

## EJ 4
Se tiene un DataFrame con las columnas `año , actor , prenda , marca`. Se dice que un conjunto (prenda + marca) está ‘quemado’ si lo usa mucha gente. Agregar al dataframe una columna que indique si el actor usó un conjunto ‘quemado’, considerando que para que esté quemado, se tiene que haber utilizado más veces que el 2% del número de los actores que aparecen todos los años en el dataset.

**Aclaración**: _Un actor puede aparecer múltiples veces por año, incluso utilizando el mismo conjunto, y cada uso cuenta por separado_

<details>
  <summary>Respuesta</summary>

``` python

df["años_aparece"] = df.groupby(["actor"]).año.transform("nunique")
cantidad_actores = df.loc[df.años_aparece == 4].actor.nunique()
usos_maximos = cantidad_actores * .02
df["conjunto"] = df.prenda + "+" + df.marca
df["usos_conjunto"] = df.groupby(["conjunto"]).actor.transform("count")
df["esta_quemada"] = df.usos_conjunto > usos_maximos
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

_`df.stack().unstack()` no tiene valores `NaN`_
- **Falso**: Aplicar de forma encadenada `stack` y `unstack` puede hacer desaparecer algunas filas completas con `NaN`, pero no es algo que aplique a cualquier DataFrame. No hay que confundir el hecho de que stack nos pueda dejar un DataFrame sin `NaN`  

_`df.unstack().stack()` devuelve un df sin valores `NaN`_
- **Falso**: Uno puede creer que es falso por lo mismo que el anterior, pero este es falso por algo distinto. Al aplicar `stack` o `unstack` a un DataFrame sin multiindice siempre va a terminar degenerando a una serie. Una serie tiene indice, pero siempre es un **indice por fila**. `unstack` funciona sobre los indices de fila, pero `stack` sobre los de columna. Entonces, al aplicar primero `unstack` y terminar con una serie, `stack` fallaria porque las series no tienen ese metodo.

_Siempre puedo hacer `df.stack()`_
- **Verdadero**: Cualquier DataFrame tiene un indice por columna, asi que siempre es posible

_Siempre puedo hacer `df.unstack()`_
- **Verdadero**: Cualquier DataFrame tiene un indice por fila, asi que siempre es posible


```python3

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

_El DataFrame mantiene o aumenta el uso de memoria_
 - **Verdadero**: Como una de las columnas es object van a pasar a ser todos object que ocupan mas que un `int8`. Por mas que los datos puedan ser convertidos de object a `int8`, Pandas generaliza al tipo que incluya a los tipos que ya tienen, no intenta optimizar la memoria.

_El DataFrame mantiene o reduce el uso de memoria_
 - **Falso**: Necesariamente el uso de memoria va a aumentar porque el tipo de una de las columnas es `int8` y va a pasar a object.

_Le puedo aplicar `.T` para volver al mismo df original_
 - **Falso**: Al volver a aplicar `.T` la primera vez los datos van a cambiar de tipo. Al volver a aplicar `.T` ese cambio no se va a revertir

_Van a aparecer nuevos valores `NaN`_
 - **Falso**: Las columnas pasan a filas y las filas a columnas, no se agregan datos.

</details>
