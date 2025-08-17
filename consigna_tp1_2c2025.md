# Ciencia de Datos — Trabajo Práctico N.º 1  
## Análisis Exploratorio con Pandas

Los trabajos prácticos de este cuatrimestre estarán organizados en **tres etapas**:

1. **Pandas y Visualizaciones**  
   Se realizará un análisis exploratorio del conjunto de datos provisto.  
   El objetivo es que el alumno adquiera las habilidades necesarias para **explorar**, **explicar** y **visualizar** la información de manera efectiva.

2. **Spark**  
   Se utilizará **Apache Spark** para ejemplificar cómo realizar un procesamiento distribuido de datos, así como los desafíos que implica pensar en un análisis distribuido.

3. **Machine Learning**  
   Se desarrollará un proceso básico de *Machine Learning*, implementando conceptos clave para la creación de modelos predictivos.

---

El conjunto de datos para la **primera parte** puede descargarse en el siguiente enlace:

- [Descargar datos](example.com)

---

## Pandas

Se busca que el alumno se lleve un entendimiento profundo del dataset, para eso, además de **realizar sus propias consultas**, se brindarán ejemplos de consultas iniciales que los alumnos deberán resolver:

1) Cuál es el estado que más descuentos tiene en total? y en promedio? Supongan que de una direccion del estilo: `3123 Alan Extension Port Andrea, MA 26926`, "MA" es el estado.

2) ¿Cuáles son los 5 códigos postales más comunes para las órdenes con estado 'Refunded'? ¿Y cuál es el nombre más frecuente entre los clientes de esas direcciones?

3) Para cada tipo de pago y segmento de cliente, devolver la suma y el promedio expresado como porcentaje, de clientes activos y de consentimiento de marketing. Se valora que el output de la consulta tenga nombres claros y en español.

4) Para los productos que contienen en su descripción la palabra "stuff" (sin importar mayúsculas o minúsculas), calcular el peso total de su inventario agrupado por marca, mostrar sólo la marca y el peso total de las 5 más pesadas.

---

## Visualizaciones

Realizar visualizaciones que contengan la comparacion de los siguientes tipos de variables:
1) Una continua con una línea de tiempo.
2) Una discreta con una continua.
3) Una discreta con una discreta.
4) Una continua con otra continua.

Además, sin repetir tipo de visualización con el punto anterior(ej si usaron barplot, no usar barplot otra vez), hacer:

5) Un heatmap.
6) Dos visualizaciones a elección.
7) Una visualización que use una de las siguientes:
- Treemap
- Sankey
- Una visu "joint" (ej JointGrid)
- Una visu hecha a mano con gráficas personalizadas.

---

## Metodología

- Cada alumno contará con un **ayudante asignado** al que podrá hacer consultas específicas sobre su trabajo.
- Existirá un **canal de consultas general en Slack** para dudas que puedan ser respondidas por cualquier miembro del equipo docente o incluso por otros alumnos.

---

## Importante

**Se dictará una clase específica de consultas, de carácter obligatorio**, en la cual cada alumno deberá **presentar el avance de su trabajo práctico** junto con su ayudante asignado.

---

## Formato de Evaluación y Entrega

La evaluación del trabajo práctico se basará en los siguientes puntos:

1. **Informe escrito**  
   - Debe incluir enlaces a los *notebooks* utilizados.  
   - Explicaciones de hallazgos y resultados.  
   - Hipótesis planteadas y su justificación.
   
2. **Evaluación en vivo**  
   - Elaboración de visualizaciones de los datos.  
   - Respuesta a consultas sobre el conjunto de datos.  
   - Preguntas conceptuales sobre el procesamiento realizado.

La entrega se realizará a través de la plataforma [Gradescope](https://www.gradescope.com).

---

## Formato de las Consultas Entregadas

Cada consulta debe incluir:

1. **Título de la consulta**  
2. **Hipótesis tomadas**  
3. **Código que resuelve la consulta**  
4. **Conclusión sobre los resultados**

---

## Evaluación del Informe y Código

La calificación será sobre **10 puntos**.  
Cada uno de los siguientes errores restará puntos:

- ❌ No se presentan más consultas que las dadas → **Desaprueba**  
- ❌ No se entrega informe escrito más allá del código → **Desaprueba**  
- ⚠️ Resolución ineficiente de las consultas → **-2 pts**  
- ⚠️ Falta de trabajo para que las visualizaciones sean eficientes → **-2 pts**  
- ⚠️ No se realizan visualizaciones extra → **-3 pts**  
- ⚠️ No se realiza limpieza de los datos → **-2 pts**  
- *(...)*  
