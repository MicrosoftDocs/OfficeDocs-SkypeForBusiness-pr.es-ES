---
title: 'Lync Server 2013: informe de tendencias de calidad de Media Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc60cd4c0d8d00fa67a5fe77ca70e61058191baa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Informe de tendencias de calidad de Media Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

El informe de tendencias de calidad de Media Server proporciona una forma de comparar de forma gráfica hasta 5 servidores en métricas de la calidad de la experiencia, como el volumen de las llamadas, el porcentaje de llamada deficiente, la pérdida de paquetes y la vibración. De este modo, resulta fácil llevar a cabo ciertas tareas, como identificar los servidores cuyo funcionamiento es deficiente, los que no se aprovechan bastante o los que se utilizan demasiado.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Acceso al Informe de tendencias de calidad de medios de servidores

Se puede obtener acceso al Informe de tendencias de calidad de medios de servidores desde uno de los siguientes informes:

  - [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (al hacer clic en la métrica de tendencia)

  - [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) (haciendo clic en la métrica del servidor perimetral A/V. Si el autor o el destinatario de la llamada es un servidor, también puede obtener acceso al Informe de tendencias de calidad de medios de servidores haciendo clic en el nombre del extremo).

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Uso óptimo del Informe de tendencias de calidad de medios de servidores

Al hacer clic en la métrica de tendencia en el [Informe rendimiento del servidor de Lync server 2013](lync-server-2013-server-performance-report.md) para un servidor específico, se abrirá el informe tendencia de calidad multimedia de servidor. Pero, solamente verá una instancia vacía de ese informe; el servidor que seleccionó en el Informe de rendimiento del servidor no se mostrará en pantalla. Por el contrario, tendrá que seleccionar ese servidor en la lista desplegable Servidores. Observe, también, que la lista desplegable Servidores contiene la opción Seleccionar todo. Esta opción no funciona si tiene más de 5 servidores; el Informe de tendencias de calidad de medios de servidores solo puede mostrar datos de 5 servidores al mismo tiempo, como máximo.

En los gráficos que muestra el informe de tendencias de calidad de Media Server, se hotlinksn los puntos con la etiqueta llamada de volumen y bajo porcentaje de llamada. al hacer clic en un punto del gráfico, se abrirá una instancia del informe de la [lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) , que muestra las llamadas totales (o llamadas deficientes) durante el período de tiempo especificado.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Informe de tendencias de calidad de medios de servidores.

### <a name="server-media-quality-trend-report-filters"></a>Filtros del Informe de tendencias de calidad de medios de servidores

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
<td><p><strong>De</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</p>
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hasta</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</p>
<p>7/7/2012 1:00 P.M.</p>
<p>Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
</ul>
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 8/7/2012 y una fecha de finalización de 9/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de servidor</strong></p></td>
<td><p>Tipo de servidor que se usa en la llamada. Los valores permitidos son:</p>
<ul>
<li><p>Servidor de mediación</p></li>
<li><p>Servidor de conferencia A/V</p></li>
<li><p>Servidor perimetral A/V</p></li>
<li><p>Puerta de enlace (servidor de mediación)</p></li>
<li><p>Puerta de enlace (desvío del servidor de mediación)</p></li>
<li><p>Servidor de conferencias AS</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Servidores</strong></p></td>
<td><p>Nombre del servidor que se usa en la sesión; esta lista desplegable se rellena automáticamente según el valor del filtro Tipo de servidor. Puede seleccionar hasta 5 servidores diferentes al compilar un informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acceso</strong></p></td>
<td><p>Indica si el participante tenía la sesión iniciada en la red interna o en la red externa. Los valores permitidos son:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el participante. Los valores permitidos son:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un participante externo estaba usando una conexión de red privada virtual (VPN) durante la sesión. Los valores permitidos son:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el Informe de tendencias de calidad de medios de servidores.

### <a name="server-media-quality-trend-report-metrics"></a>Métricas del Informe de tendencias de calidad de medios de servidores

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
<td><p>Cantidad total de llamadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad promedio de la degradación de OP (puntuación de opción media) experimentada durante una llamada. Los valores de degradación pueden oscilar entre un mínimo de 0,0 y un alto de 5,0. un valor de 0,5 o menos representa una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</p>
<p>Los valores elevados de degradación pueden ser producto de la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un extremo o servidor multimedia. Una degradación elevada causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</p></td>
</tr>
<tr class="even">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de Protocolo de transporte en tiempo real (RTP) llegue a un extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Vibración (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras ocultas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras extendidas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras comprimidas</strong></p></td>
<td><p>No</p></td>
<td><p>Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

