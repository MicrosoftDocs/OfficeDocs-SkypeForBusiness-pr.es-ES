---
title: "Rapport de tend. gén. de la qualité des médias serveur dans Lync Server 2013"
TOCTitle: "Rapport de tend. gén. de la qualité des médias serveur dans Lync Server 2013"
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48275937
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de tendencias de calidad de medios en el servidor en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El Informe de tendencias de calidad de medios de servidores permite comparar de forma gráfica hasta 5 servidores según diversas métricas de Calidad de la experiencia, como volumen de llamadas, porcentaje de llamadas deficientes, pérdida de paquetes y vibración. De este modo, resulta fácil llevar a cabo ciertas tareas, como identificar los servidores cuyo funcionamiento es deficiente, los que no se aprovechan bastante o los que se utilizan demasiado.

## Acceso al Informe de tendencias de calidad de medios de servidores

Se puede obtener acceso al Informe de tendencias de calidad de medios de servidores desde uno de los siguientes informes:

  - [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en la métrica Tendencia)

  - [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) (haciendo clic en la métrica Servidor perimetral A/V. Si el autor o el destinatario de la llamada es un servidor, también puede obtener acceso al Informe de tendencias de calidad de medios de servidores haciendo clic en el nombre del extremo.)

## Uso óptimo del Informe de tendencias de calidad de medios de servidores

Al hacer clic en la métrica Tendencia del [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) de un servidor determinado, se abrirá el Informe de tendencias de calidad de medios de servidores. Sin embargo, solamente verá una instancia vacía de ese informe; el servidor que seleccionó en el Informe de rendimiento del servidor no se mostrará en pantalla. Por el contrario, tendrá que seleccionar ese servidor en la lista desplegable Servidores. Observe, también, que la lista desplegable Servidores contiene la opción Seleccionar todo. Esta opción no funciona si tiene más de 5 servidores; el Informe de tendencias de calidad de medios de servidores solo puede mostrar datos de 5 servidores al mismo tiempo, como máximo.

En los gráficos que muestra el Informe de tendencias de calidad de medios de servidores, los puntos denominados Volumen de llamadas y Porcentaje de llamadas deficientes son vínculos activos; al hacer clic en un punto del gráfico, se abrirá una instancia del [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) con las llamadas totales (o las llamadas deficientes) del período de tiempo especificado.

## Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Informe de tendencias de calidad de medios de servidores.

### Filtros del Informe de tendencias de calidad de medios de servidores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Desde</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>07.07.12 13:00</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 AM del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>07.07.12</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>03.07.12</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>07.07.12 13:00</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 AM del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>07.07.12</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>03.07.12</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
</ul>
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando por la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, los datos de 31 días en total).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de servidor</strong></p></td>
<td><p>Tipo de servidor que se usa en la llamada. Los valores permitidos son:</p>
<ul>
<li><p>Servidor de mediación</p></li>
<li><p>Servidor de conferencia A/V</p></li>
<li><p>Servidor perimetral A/V</p></li>
<li><p>Puerta de enlace (servidor de mediación)</p></li>
<li><p>Puerta de enlace (desvío de servidor de mediación)</p></li>
<li><p>Servidor de conferencias AS</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Servidores</p></td>
<td><p>Nombre del servidor que se usa en la sesión; esta lista desplegable se rellena automáticamente según el valor del filtro Tipo de servidor. Puede seleccionar hasta 5 servidores diferentes al compilar un informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acceso</strong></p></td>
<td><p>Indica si el participante tenía la sesión iniciada en la red interna o en la red externa. Los valores permitidos son:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el participante. Los valores permitidos son:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un participante externo estaba usando una conexión de red privada virtual (VPN) durante la sesión. Los valores permitidos son:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Métricas

En la tabla siguiente se muestra la información que recoge el Informe de tendencias de calidad de medios de servidores.

### Métricas del Informe de tendencias de calidad de medios de servidores

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos por este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad media de degradación de MOS (puntuación de opinión media) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0; un valor de 0,5 o menos constituye una degradación aceptable. Anteriormente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. Lync Server usa un conjunto de algoritmos para predecir la puntuación que los usuarios habrían asignado a una llamada.</p>
<p>Los valores altos de degradación pueden ser producto de la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o un extremo. Una degradación alta causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>El número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</p></td>
</tr>
<tr class="even">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de Protocolo de transporte en tiempo real (RTP) llegue a un extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales; a una configuración incorrecta del enrutamiento, o a una sobrecarga en el servidor de medios. Estos valores elevados causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Vibración (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP. (La vibración es una forma de medir la &quot;inestabilidad&quot; de una llamada.) Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia, y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras ocultas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio ocultas respecto al número total de muestras. (Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que, normalmente, supondría la pérdida de paquetes de red.) Los valores altos indican niveles elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y da lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras extendidas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio extendidas respecto al número total de muestras. (El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red.) Los valores altos indican un elevado grado de extensión de las muestras a causa de las vibraciones, y esto hace que el audio resulte robótico o distorsionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras comprimidas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio comprimidas respecto al número total de muestras. (El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red.) Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones, y esto da lugar a un audio acelerado o distorsionado.</p></td>
</tr>
</tbody>
</table>

