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

Trabajaremos entonces en el análisis exploratorio de los datos presentados. Para esto, vamos a presentarles algunas consultas a resolver en Pandas. 
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

### Asignaciones de ayudantes
 
Cada alumno trabajará con un ayudante o grupo de ayudantes asignado y pueden ser consultadas en la siguiente tabla

| Padrón | Apellido         | Nombre           | Ayudante         |
| ------ | ---------------- | ---------------- | ---------------- |
| 81061  | Sanchez Negrette | Juan Pablo       | Lucas            |
| 96970  | Brandan          | Ricardo Ezequiel | Martín y Joaquín |
| 97529  | Batallan         | David Leonardo   | Nacho B          |
| 101284 | Jadur            | Luciano          | Julieta          |
| 104078 | Delgado          | Nahuel           | Martín y Joaquín |
| 104545 | Cano             | Ezequiel Martin  | Nacho B          |
| 104607 | Mendoza          | Elias            | Nacho B          |
| 105079 | Brizuela Lopez   | Mariano Jesus    | Matías           |
| 106194 | Galarza          | Adrian           | Natalia          |
| 106267 | Lozano           | Martina Victoria | Lucas            |
| 106828 | Peña             | Alejandro Daniel | Damián           |
| 106863 | Losada           | Tomas Facundo    | Nacho A          |
| 108090 | Fontana          | María Agustina   | Julieta          |
| 108932 | Zysman Bayetto   | Nicolás          | Matías           |
| 109065 | Moscoloni        | Maria Florencia  | Nacho A          |
| 109425 | Ruiz             | Karen Belén      | Natalia          |
| 109441 | Calvert de Bohun | Lucia            | Natalia          |
| 109669 | Fatala           | Siro             | Julieta          |
| 109883 | Manuel           | Herrera          | Damián           |
| 110147 | Barroero         | Ignacio          | JuanMa y Alejo   |
| 110198 | Perez Mendoza    | Salvador         | JuanMa y Alejo   |
| 110402 | Caserio Longoni  | Felipe           | Nacho A          |
| 111028 | Paniccia         | Delfina          | Lucas            |
