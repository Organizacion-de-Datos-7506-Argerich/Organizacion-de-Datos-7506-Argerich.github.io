# Ciencia de Datos — Trabajo Práctico N.º 2  
## Resolución de Consultas con Spark

Los trabajos prácticos de este cuatrimestre estarán organizados en **tres etapas**:

1. **Pandas y Visualizaciones**  
   Se realizará un análisis exploratorio del conjunto de datos provisto.  
   El objetivo es que el alumno adquiera las habilidades necesarias para **explorar**, **explicar** y **visualizar** la información de manera efectiva.

2. **Spark**  
   Se utilizará **Apache Spark** para ejemplificar cómo realizar un procesamiento distribuido de datos, así como los desafíos que implica pensar en un análisis distribuido.

3. **Machine Learning**  
   Se desarrollará un proceso básico de *Machine Learning*, implementando conceptos clave para la creación de modelos predictivos.

---

El conjunto de datos para la **segunda parte** puede descargarse en el drive de alumnos:

- [Descargar datos](https://drive.google.com/file/d/17MwEwXP8ICDWLbcJnC1o7dwHV6OT9gVt/view?usp=drive_link)

---

## Spark

Ahora que tuvieron la oportunidad de familiarizarse con el dataset, vamos a pedirles que, además de realizar sus propias consultas, resuelvan las consultas dadas a continuación utilizando Spark:

1) Cuál es el estado que más descuentos tiene en total? y en promedio? Supongan que de una direccion del estilo: `3123 Alan Extension Port Andrea, MA 26926`, "MA" es el estado.

2) ¿Cuáles son los 5 códigos postales más comunes para las órdenes con estado 'Refunded'? ¿Y cuál es el nombre más frecuente entre los clientes de esas direcciones?

3) Para cada tipo de pago y segmento de cliente, devolver la suma y el promedio expresado como porcentaje, de clientes activos y de consentimiento de marketing. Se valora que el output de la consulta tenga nombres claros y en español.

4) Para los productos que contienen en su descripción la palabra "stuff" (sin importar mayúsculas o minúsculas), calcular el peso total de su inventario agrupado por marca, mostrar sólo la marca y el peso total de las 5 más pesadas.

5) Calculen el porcentaje de productos cuyo stock es al menos 20% más alto que el stock promedio de su marca. Por ejemplo, si el stock promedio de la marca Adidas fuera 100, para los productos de dicha marca la condición será que tengan un stock mayor a 120, y luego se deberá calcular qué porcentaje del total de productos cumple con esta condición.
  
6) Obtener la cantidad de órdenes que no hayan comprado ninguno de los 10 productos más vendidos.

---

## Metodología

- Cada alumno contará con un **ayudante asignado** al que podrá hacer consultas específicas sobre su trabajo.
- Para cualquier duda de la solución que estan pensando, pueden pedir ayuda por Slack (sin publicar su idea), y el primer ayudante disponible intentará responderles.
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
   - Respuesta a consultas sobre el conjunto de datos.  
   - Preguntas conceptuales sobre el procesamiento realizado.

La entrega se realizará a través de la plataforma [Gradescope](https://www.gradescope.com). Donde se deberá entregar el notebook exportado a PDF (con el output de las celdas), el link al drive donde tengan el notebook, y también el informe escrito.

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

- ❌ No se alguna de las consultas solicitadas → **Desaprueba**  
- ❌ No se entrega informe escrito más allá del código → **Desaprueba**  
- ⚠️ Resolución ineficiente de las consultas → **-2 pts**  
- ⚠️ No se realiza una limpieza de los datos. → **-2 pts**
- ⚠️ Análisis de datos incompleto. → **-2 pts**
