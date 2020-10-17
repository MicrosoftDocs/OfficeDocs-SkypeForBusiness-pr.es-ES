---
title: 'Lync Server 2013: informe de ubicación'
description: 'Lync Server 2013: informe de ubicaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b819bcffeee0795cd39d3dde3e38fbd9e4a1b7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569476"
---
# <a name="location-report-in-lync-server-2013"></a>Informe de ubicaciones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

El informe de ubicaciones proporciona información sobre las métricas de calidad de las llamadas agrupadas por ubicación de red (es decir, por subred de red). Si los usuarios tienen problemas con las llamadas, este informe puede ayudarle a determinar si estos problemas se han extendido o se limitan a un segmento de red determinado.

<div>

## <a name="accessing-the-location-report"></a>Acceso al informe de ubicaciones

Se obtiene acceso al informe de ubicaciones desde la página principal de informes de supervisión. Para profundizar hasta el informe de lista de llamadas, haga clic en cualquiera de las siguientes métricas:

  - Volumen de llamadas

  - Porcentaje de llamadas deficientes

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. Por ejemplo, el informe de ubicaciones le permite filtrar elementos tales como la ubicación del origen de una llamada o si la llamada se realizó desde una conexión inalámbrica o por cable. También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.

En la tabla siguiente se muestran los filtros que se pueden usar con el informe de ubicaciones

### <a name="location-report-filters"></a>Filtros del informe de ubicaciones

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
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre empiezan en domingo y terminan en sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ubicación del autor de la llamada</strong></p></td>
<td><p>Subred de IP del usuario que realizó la llamada. Solo puede seleccionar <strong>[Todos]</strong> para indicar todas las subredes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ubicación del destinatario de la llamada</strong></p></td>
<td><p>Subred de IP del usuario que recibió la llamada. Solo puede seleccionar <strong>[Todos]</strong> para indicar todas las subredes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ol>
<li><p>Todos</p></li>
<li><p>Cableada</p></li>
<li><p>Wireless</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ol>
<li><p>Todos</p></li>
<li><p>VPN</p></li>
<li><p>No VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el informe de ubicaciones.

### <a name="location-report-metrics"></a>Métricas del informe de ubicaciones

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Subred del autor de la llamada</strong></p></td>
<td><p>No</p></td>
<td><p>Subred de IP del usuario que realizó la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Subred del destinatario de la llamada</strong></p></td>
<td><p>No</p></td>
<td><p>Subred de IP del usuario que recibió la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volumen de llamadas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Número total de llamadas realizadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de llamadas deficientes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Porcentaje de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recorrido de ida y vuelta (ms)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradación (MOS)</strong></p></td>
<td><p>Sí</p></td>
<td><p>Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada. Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0. Un valor de 0,5 o menos constituye una degradación aceptable. Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5. En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</p>
<p>Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pérdida de paquetes</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>JIT</strong></p></td>
<td><p>Sí</p></td>
<td><p>Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP. (La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras ocultas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasa de recuperación de muestras extendidas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasa de recuperación de muestras comprimidas</strong></p></td>
<td><p>Sí</p></td>
<td><p>Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

