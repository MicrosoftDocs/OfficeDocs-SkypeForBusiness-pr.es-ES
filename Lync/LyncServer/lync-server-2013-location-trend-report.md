---
title: 'Lync Server 2013: informe de tendencias de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68c1eac461d65c2c0b023086422bb66505e9c929
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a>Informe de tendencias de ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

El informe de tendencias de ubicación proporciona información sobre la tendencia de calidad de las llamadas de las ubicaciones de red.

<div>

## <a name="filters"></a>Filtros

Los filtros son un modo de recuperar un conjunto de datos más específico o de ver los datos devueltos de diferentes formas. Por ejemplo, el informe de tendencias de ubicación permite filtrar los datos devueltos por tipo de acceso (acceso interno o externo) o por tipo de conexión de red (cableada o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día o semana.

En la siguiente tabla se muestran los filtros que se pueden usar con el informe de tendencias de ubicación.

### <a name="location-trend-report-filters"></a>Filtros del informe de tendencias de ubicación

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
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 01/01/2011 y una fecha de finalización del 28/02/2011, aparecerán los datos correspondientes a los días entre el 01/08/2011 a las 12:00 horas y el 01/09/2011 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acceso</strong></p></td>
<td><p>Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de red</strong></p></td>
<td><p>Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>Cableada</p></li>
<li><p>Inalámbrica</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>[Todas]</p></li>
<li><p>VPN</p></li>
<li><p>Distinto de VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

