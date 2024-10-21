# Trabajo Práctico 
## Consigna General

El trabajo práctico de este cuatrimestre consta de cuatro entregas: 
* Pandas
* Visualizaciones
* Spark
* Machine Learning.

En todas ellas trabajaremos con este [dataset](https://drive.google.com/drive/folders/1XID89pM_mwJyFpxkdQow6rSJcyCseGix?usp=sharing).

Los datos presentados son transacciones electrónicas de pago, 
con información relacionada a la misma que va desde el importe, 
dispositivo en que fue realizada, 
hasta **si se trataba de un intento de fraude o no**. 
Esto podemos encontrarlo en el archivo transaction, indicado en la columna **target**.

_En un futuro trabajaremos para entrenar un modelo que nos permita predecir el valor de esa columna, pero por ahora vamos a dedicarle tiempo a analizar esos datos._

### Primera Entrega (Analisis exploratorio)

Trabajaremos en el análisis exploratorio de los datos presentados. Para esto, vamos a presentarles algunas consultas a resolver en Pandas. 
Si bien deben estar resueltas, **no son la totalidad de la entrega**. La idea es que sirvan de base para comenzar a entender los datos, investigarlos y sacar conclusiones.

* ¿Cuál es la proporción de transacciones fraudulentas?
* ¿Qué relación existe entre el tipo de producto y el monto de la transacción y la columna target? Calcular qué proporción de transacciones son fraudulentas para cada tipo de producto, y verificar si existe impacto.
* Al mismo tiempo, ¿los fraudulentos eligen algún tipo de producto en particular? Calcular para las transacciones fraudulentas, qué proporción corresponde a cada uno de los tipos de producto. ¿Se puede sacar alguna conclusión?
* ¿Cuál es el monto promedio de las transacciones fraudulentas? (discriminado por dispositivo) Calcularlo y comprobar si existe o no impacto.
* ¿Cuál es el impacto del tiempo en la probabilidad de fraude?¿Cómo se distribuyen los casos fraudulentos a lo largo del tiempo?
* Apoyarse del valor de timestamp para calcular la distribución de transacciones fraudulentas. Verificar el porcentaje de dichas transacciones a lo largo del tiempo. ¿Se puede llegar a alguna conclusión en base a esta información?
* ¿Hay alguna plataforma más utilizada que otras para cometer fraude?
* ¿Hay alguna tarjeta preferida por los fraudulentos?
* En los datos vemos gran cantidad de valores nulos, ¿cómo los manejarías?

Estas preguntas deben usarse como puntapié para desarrollar el análisis, intentando descubrir la relación que existe entre los distintos atributos y el target. 

### Segunda Entrega (Visualizaciones)

Tabajaremos en construir visualizaciones que nos permitan entender mejor los datos presentados y complementar nuestro análisis exploratorio. Para esto, vamos a proponerles algunos plots a realizar.

* **Stacked Barplot** Debe que permitir ver la relación que existe entre el **tipo de producto** y **las transacciones fraudulentas**.

* **Scatterplot** Debe que permitir ver la relación que existe entre el **monto de la transacción** y el **_target_**. Para elaborar este plot **necesitaran otra variable continua** (Podrían por ej tomar el tiempo).

* **Heatmap** Debe que permitir ver la cantidad de **transacciones fraudulentas** para los distintos **tipos de tarjeta y montos**. _**Sugerencia:** en este punto trabajar con rangos de montos de transacción_

* **Plot a elección** Debe que permitir ver como impacta el tipo de producto el target. **Importante**: no puede repetirse el tipo de plot con ninguno de los puntos anteriores.

* **Visualización a elección** Debe que permitir mostrar al menos 4 variables del set de datos. **Importante**: no puede repetirse el tipo de plot con ninguno de los puntos anteriores.

* (**OPCIONAL**) Elaborar una **visualización original** que muestre algún aspecto _interesante_ del set de datos. **Importante**: diferenciar una visualización original de un plot. En una visualización debe haber elementos gráficos que acompañen y refuercen el mensaje; debe ser atractiva para la vista, debe contar una historia, y permitir a quien la ve sacar sus conclusiones. Ante cualquier consulta pueden verlo con sus respectivos ayudantes. _Como referencia, pueden ver algunas [visualizaciónes de cuatrimestres anteriores](https://organizacion-de-datos-7506-argerich.github.io/visualizaciones.html)_.

#### Criterio de evaluacion

En todos los casos, evaluaremos la calidad de las visualizaciones presentadas. Algunos puntos a tener en cuenta son:
* ¿Tienen todos los ejes su rótulo?
* ¿Tiene cada visualización un título?
* ¿Es entendible la visualización sin tener que leer la explicación?
* ¿El tipo de plot elegido es adecuado para lo que se quiere visualizar?
* ¿Es una visualización interesante?
* ¿El uso del color es adecuado?
* ¿Hay un exceso o falta de elementos visuales en la visualización elegida?
* ¿La visualización es consistente con los datos?

### Tercera Entrega (Spark)

Trabajaremos resolviendo las consultas de la [primera entrega](https://organizacion-de-datos-7506-argerich.github.io/consigna_tp_2c2024.html#primera-entrega-analisis-exploratorio), pero esta vez utilizando **Spark**. Se debe utilizar la api de RDD (la vista en clase) y **NO** otra, ya sea la de SQL, Dataframe, etc.

Estas consultas deben estar resueltas, pero _**no son la totalidad de la entrega. Debe tomar lo aprendido sobre los datos en el TP de Pandas e intentar descubrir más información sobre el set de datos.**_

* ¿Cuál es la proporción de transacciones fraudulentas?
* ¿Qué relación existe entre el tipo de producto y el monto de la transacción y la columna target? Calcular qué proporción de transacciones son fraudulentas para cada tipo de producto, y verificar si existe impacto.
* ¿Cuál es el impacto del tiempo en la probabilidad de fraude?¿Cómo se distribuyen los casos fraudulentos a lo largo del tiempo?
* ¿Hay alguna plataforma más utilizada que otras para cometer fraude?
* ¿Hay alguna tarjeta preferida por los fraudulentos?
* En los datos vemos gran cantidad de valores nulos, ¿cómo los manejarías?

Importante: **Estas preguntas deben usarse como puntapié para desarrollar el análisis, intentando descubrir la relación que existe entre los distintos atributos y el target.**

### Cuarta Entrega (Machine Learning)

_El futuro es hoy_ y como cuarta entrega finalmente deberan desarrollar modelos de machine learning que nos permitan predecir el target de nuestro conjunto de datos dados.

#### Baseline

Deberan construir un modelo **muy sencillo** para saber qué es lo peor que podemos hacer. En general, esta es una tarea muy importante que queremos que repitan en sus proyectos de machine learning. ¿Por qué?
* Navaja de Ockam[ * ](https://es.wikipedia.org/wiki/Navaja_de_Ockham): “Cuando se ofrecen dos o más explicaciones de un fenómeno, es preferible la explicación completa más simple; es decir, no deben multiplicarse las entidades sin necesidad.” ¿Para qué desarrollar un modelo super complejo si capaz es peor o casi igual que uno muy sencillo?
* Nos sirve para saber si estamos usando bien los modelos más complejos, si su score nos da peor al baseline probablemente se deba a un error de código.
* Nos sirve para rápidamente saber que tan complejo es un problema.
* Los modelos simples son fáciles de entender.

##### Tareas a realizar
Utilizando **todos las columnas del dataset** (exceptuando ids únicos) con algún encoding donde sea necesario, entrenar una [regresión logística](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html), haciendo búsqueda de hiperparametros y garantizando su reproducibilidad (los resultados del notebook no deberan variar segun la corrida).

##### Responder
- ¿Cómo conviene obtener el dataset para validar?
- ¿Cuál es el mejor score de validación obtenido?
- ¿Qué features son los más importantes para predecir con el mejor modelo?
- Graficar el feature importance

#### Modelos para prediccion

##### Tareas a realizar
Para este punto debe diseñar y entrenar 2 modelos distintos a eleccion. Cada uno debe incluir su respectiva búsqueda de hiperparametros y feature engineering. 


##### Requerimientos

- Los modelos entre si deben ser de distintos tipos **excluyendo regresiones logísticas**. 
- Utilizar AUC-ROC como métrica de validación.
- Deben medirse en validación.
- Deben ser reproducibles (el resultado del notebook **siempre** debe ser el mismo).
- Tener un score en validación superior a 0,8.
- Para el feature engineering debe utilizarse al menos una vez:
  - Imputación de nulos
  - Mean encoding
  - One hot encoding
- Utilizar al menos 80 features (contando cómo features columnas con números, pueden venir varios de la misma variable).
- Utilizar las columnas: **id_31, id_33, DeviceType, DeviceInfo**.
- Utilizar _CountVectorizer_ o _TfIdfVectorizer_ para algún feature.
- **Ambos modelos deben cumplir TODOS los requerimientos**

##### Responder
- ¿Cómo conviene elegir los datos de validación respecto de los de train?.
- ¿Cuál de los dos modelos arroja mejores resultados?
- ¿Por que cree que se dio ese resultado?

### Asignaciones de ayudantes
 
Cada alumno trabajará con un ayudante o grupo de ayudantes asignado y pueden ser consultadas en la siguiente tabla

| Padrón | Apellido         | Nombre           | Ayudante         |
| ------ | ---------------- | ---------------- | ---------------- |
| 81061  | Sanchez Negrette | Juan Pablo       | Lucas            |
| 96970  | Brandan          | Ricardo Ezequiel | Martín y Joaquín |
| 97529  | Batallan         | David Leonardo   | Nacho B          |
| ~~101284~~ | ~~Jadur~~            | ~~Luciano~~          | ~~Julieta~~          |
| ~~104078~~ | ~~Delgado~~          | ~~Nahuel~~           | ~~Martín y Joaquín~~ |
| ~~104545~~ | ~~Cano~~             | ~~Ezequiel Martin~~  | ~~Nacho B~~          |
| ~~104607~~ | ~~Mendoza~~          | ~~Elias~~            | ~~Nacho B~~          |
| 105079 | Brizuela Lopez   | Mariano Jesus    | Matías           |
| ~~106194~~ | ~~Galarza~~          | ~~Adrian~~           | ~~Natalia~~          |
| 106267 | Lozano           | Martina Victoria | Lucas            |
| 106828 | Peña             | Alejandro Daniel | Damián           |
| 106863 | Losada           | Tomas Facundo    | Nacho A          |
| 108090 | Fontana          | María Agustina   | Julieta          |
| 108932 | Zysman Bayetto   | Nicolás          | Matías           |
| 109065 | Moscoloni        | Maria Florencia  | Nacho A          |
| ~~109425~~ | ~~Ruiz~~             | ~~Karen Belén~~      | ~~Natalia~~          |
| 109441 | Calvert de Bohun | Lucia            | Natalia          |
| 109669 | Fatala           | Siro             | Julieta          |
| ~~109883~~ | ~~Manuel~~           | ~~Herrera~~          | ~~Damián~~           |
| 110147 | Barroero         | Ignacio          | JuanMa y Alejo   |
| ~~110198~~ | ~~Perez Mendoza~~    | ~~Salvador~~         | ~~JuanMa y Alejo~~   |
| ~~110402~~ | ~~Caserio Longoni~~  | ~~Felipe~~           | ~~Nacho A~~          |
| 111028 | Paniccia         | Delfina          | Lucas            |
