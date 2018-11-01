---
title: 'Lync Server 2013: Informe de lista de llamadas'
TOCTitle: Informe de lista de llamadas
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48276087
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Informe de lista de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

El informe de lista de llamadas proporciona métricas relativas a la calidad de la experiencia para las llamadas individuales realizadas y recibidas en su organización. Tenga en cuenta que las métricas reales que se incluyan dependerán de cómo acceda al informe de lista de llamadas. Por ejemplo, si abre el informe desde el [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md), verá métricas como las siguientes, que también se incluyen en el informe de dispositivos:

  - Micrófono del autor de la llamada

  - Altavoz del autor de la llamada

  - Micrófono del destinatario de la llamada

  - Altavoz del destinatario de la llamada

  - Relación de tiempo de conmutación de voz

Sin embargo, si abre el informe de lista de llamadas desde el [Informe de ubicaciones en Lync Server 2013](lync-server-2013-location-report.md), no verá ninguna de estas métricas y, en cambio, verá las siguientes:

  - Recorrido de ida y vuelta (ms)

  - Degradación (MOS)

  - Pérdida de paquetes

  - Vibración (ms)

Esas son las métricas incluidas en el informe de ubicaciones. No obstante, siempre puede hacer clic en la métrica Detalles, en el informe de lista de llamadas, para obtener información completa sobre la calidad de la experiencia de cualquier llamada.

## Acceso al informe de lista de llamadas

El informe de lista de llamadas es accesible desde cualquiera de los siguientes informes:

  - El [Informe de ubicaciones en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en las métricas Volumen de llamadas o Porcentaje de llamadas deficientes)

  - El [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md) (haciendo clic en las métricas Volumen de llamadas o Porcentaje de llamadas deficientes)

  - El [Informe del resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en las métricas Volumen de llamadas o Porcentaje de llamadas deficientes)

  - El [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en las métricas Volumen de llamadas o Porcentaje de llamadas deficientes)

Desde el informe de lista de llamadas, puede acceder al [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) haciendo clic en la métrica Detalles.

## Optimización del uso del informe de lista de llamadas

Si no recuerda qué miden algunas de las métricas del informe de lista de llamadas (por ejemplo, Relación de tiempo de conmutación de voz), mantenga el mouse sobre la etiqueta de la métrica y aparecerá una información sobre la herramienta con una breve descripción de la métrica.

## Filtros

Ninguno. No se puede filtrar el informe de lista de llamadas.

## Métricas

En la siguiente tabla se detalla la información facilitada en el informe de lista de llamadas para cada llamada.

### Métricas del informe de lista de llamadas

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
<td><p><strong>Detalles</strong></p></td>
<td><p>N.º</p></td>
<td><p>Al hacer clic en este elemento, el informe muestra información adicional sobre la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Autor de llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP de la persona que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP de la persona que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de inicio</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que se inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de finalización</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que finalizó la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente de usuario de autor de la llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Software utilizado por el extremo de la persona que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario de destinatario de la llamada</strong></p></td>
<td><p>Sí</p></td>
<td><p>Software utilizado por el extremo de la persona que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Lync Server, Lync Server usa un conjunto de algoritmos para predecir la puntuación que los usuarios van a dar a una llamada.</p>
<p>Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Vibración</strong></p></td>
<td><p>Sí</p></td>
<td><p>Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la &quot;inestabilidad&quot; de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras ocultas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras extendidas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras comprimidas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividad</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tipo de vínculo de comunicación inalámbrica. Normalmente es uno de los siguientes:</p>
<ul>
<li><p>Retransmisión</p></li>
<li><p>Directo</p></li>
</ul></td>
</tr>
</tbody>
</table>

