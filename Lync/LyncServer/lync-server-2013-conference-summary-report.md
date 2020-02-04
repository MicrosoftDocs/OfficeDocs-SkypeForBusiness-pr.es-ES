---
title: 'Lync Server 2013: informe Resumen de la Conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68858d56c47953a99928a59e5f83485ba9d305cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Informe de Resumen de conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-03_

El informe de resumen de conferencia ofrece una vista general de las sesiones de conferencia en línea. Una conferencia suele implicar a más de 2 usuarios y requiere el uso de los servicios de conferencia de Microsoft Lync Server 2013. Por comparación, una sesión de punto a punto normalmente implica solo 2 usuarios y no requiere el uso de los servicios de conferencia de Lync Server. Las actividades de punto a punto se notifican en el [Informe de Resumen de actividad punto a punto de Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

El informe Resumen de la Conferencia no solo le indica cuántas conferencias se han mantenido durante un período de tiempo determinado (cada hora, diariamente, semanalmente, mensualmente), pero también le indica el número total de personas que participaron en esas conferencias, así como el número total de conferencias únicas los organizadores reuniones.

Un organizador "único" es cualquier persona que programe al menos una conferencia. Por ejemplo, si Pilar Ackerman programa una conferencia, cuenta como un único organizador. Si Ken Myer programa conferencias de 148, también cuenta como un único organizador. Por ejemplo, la siguiente tabla muestra ocho conferencias programadas, pero solo tres organizadores únicos (Ken Myer, Pilar Ackerman y David AHS).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizador de la conferencia</th>
<th>Fecha de la conferencia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 A.M.</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 A.M.</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 A.M.</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 A.M.</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 P.M.</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 P.M.</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 A.M.</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 A.M.</p></td>
</tr>
</tbody>
</table>


El informe de resumen de conferencia también indica la cantidad de conferencias que incluyeron audio o vídeo.

<div>

## <a name="accessing-the-conference-summary-report"></a>Acceso al informe de resumen de conferencia

Puede obtener acceso al informe de resumen de conferencia desde la página principal de informes de supervisión. Para llegar hasta dicho informe, necesitará hacer clic en las siguientes métricas:

  - Total de conferencias

  - Total de participantes

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usar el informe de resumen de conferencia de la mejor forma posible

Los valores totales de la mayoría de las métricas que se usan en el informe de Resumen de conferencia se pueden encontrar en la parte inferior del informe; Desplácese hacia abajo para ver valores como el número total de conferencias mantenidas durante el período de tiempo especificado y el número total de personas que participaron en esas conferencias. Una métrica que no se totaliza en la parte inferior del informe es un total de organizadores únicos de conferencia. ¿Por qué no? He aquí una de las razones. Supongamos que está buscando un mes de datos. El día 1 tenía 34 organizadores únicos de conferencia; el día 2 tenía 27 organizadores únicos de conferencia. ¿Eso significa que tenía 61 organizadores únicos para esos dos días? No necesariamente. Después de todo, las 27 personas que organizaron las conferencias en el día 2 pueden ser entre las 34 personas que organizón las conferencias en el día 1. Por ejemplo, en este informe simple, tenga en cuenta que Ken Myer y Pilar Ackerman las conferencias programadas en 7/7/2012 y en 7/2/2012:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizador de la conferencia</th>
<th>Fecha de la conferencia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 A.M.</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 A.M.</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 A.M.</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 A.M.</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 P.M.</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 P.M.</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 A.M.</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 A.M.</p></td>
</tr>
</tbody>
</table>


Para componerse una mejor idea de la cantidad total de usuarios distintos que ha organizado conferencias, cambie el intervalo temporal (por ejemplo, consulte los datos por mes en lugar de por día).

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de conferencia le permite elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.

La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.

### <a name="conference-summary-report-filters"></a>Filtros del informe de resumen de conferencia

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
<li><p>Cada mes (se puede ver un máximo de 12 meses)</p></li>
</ul>
<p>Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

La siguiente tabla incluye la información que ofrece el informe de resumen de conferencia.

### <a name="conference-summary-report-metrics"></a>Métricas del informe de resumen de conferencia

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
<td><p><strong>Cada hora</strong></p>
<p><strong>Cada día</strong></p>
<p><strong>Cada semana</strong></p>
<p><strong>Cada mes</strong></p></td>
<td><p>No</p></td>
<td><p>Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo diario y hace clic en 7/7/2012, verá un desglose por hora de actividad de registro de usuario para esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de conferencias (independientemente del tipo de conferencia) celebradas. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de participantes</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de personas que participaron en las conferencias. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Media de participantes por conferencia</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad media de participantes que participaron en una conferencia en concreto. Se calcula dividiendo la cantidad total de conferencias por la cantidad total de participantes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cantidad total de conferencias A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de conferencias que incluían audio o vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de conferencia A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de minutos dedicados a conferencias de audio/vídeo.</p>
<p>La métrica total de minutos de conferencia A/V resume todos los tipos de conferencias de audio y vídeo, entre los que se incluyen: conferencias A/V; Conferencias de mensajería instantánea; conferencias de uso compartido de aplicaciones; conferencias de datos; y conferencias de RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes en conferencia A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de minutos de los participantes dedicados a conferencias de audio/vídeo. Por ejemplo, supongamos que un usuario participa 5 minutos en una conferencia de audio/vídeo y un segundo usuario participa 3 minutos en la misma conferencia. Esto hace un total de 8 minutos de los participantes: 5 minutos más 3 minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cantidad media de minutos en conferencias A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad media de minutos por conferencia de audio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cantidad total de organizadores únicos de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de usuarios que organizaron al menos una conferencia. Los usuarios que organizaron más de una conferencia se cuentan como un único organizador, al igual que ocurre con los usuarios que solo organizaron una única conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cantidad total de mensajes de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de mensajes instantáneos enviados durante las conferencias.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

