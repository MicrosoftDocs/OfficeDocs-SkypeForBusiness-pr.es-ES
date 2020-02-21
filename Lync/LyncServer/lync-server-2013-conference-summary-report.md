---
title: 'Lync Server 2013: informe de Resumen de conferencia'
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
ms.openlocfilehash: 772ece86803f9fc499b38299621ccd491221f84b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Informe de Resumen de conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-03_

El informe de resumen de conferencia ofrece una vista general de las sesiones de conferencia en línea. Una conferencia suele implicar a más de 2 usuarios y requiere el uso de los servicios de conferencia de Microsoft Lync Server 2013. Por su parte, una sesión punto a punto suele implicar a solo dos usuarios y no precisa del uso de los servicios de conferencia de Lync Server. Las actividades punto a punto se indican en el [Informe de Resumen de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

El informe de Resumen de conferencia no solo indica el número de conferencias que se realizaron durante un período de tiempo determinado (cada hora, diariamente, semanalmente, mensualmente), sino que también indica el número total de personas que participaron en esas conferencias y el número total de conferencias únicas organizadores.

Un organizador "único” es alguien que programa al menos una conferencia. Así, por ejemplo, si Pilar Ackerman programa una conferencia, se contabilizará como una organizadora única y, si Ken Myer programa 148 conferencias, también se considerará como organizador único. En la siguiente tabla se recogen ocho conferencias programadas, pero solo tres organizadores únicos (Ken Myer, Pilar Ackerman y David Ahs).


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
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>2/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>2/7/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


El informe de resumen de conferencia también indica el número de conferencias que incluyeron audio y/o vídeo.

<div>

## <a name="accessing-the-conference-summary-report"></a>Acceso al informe de resumen de conferencia

Puede acceder al informe de resumen de conferencia desde la página principal de informes de supervisión. Para llegar hasta dicho informe, deberá hacer clic en las siguientes métricas:

  - Total de conferencias

  - Total de participantes

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usar el informe de resumen de conferencia de la mejor forma posible

En la parte inferior del informe de resumen de conferencia se plasman los valores totales de la mayor parte de las métricas que se usan en este informe. Desplácese hacia abajo para conocer valores como el número total de conferencias celebrado durante el periodo de tiempo especificado y el número total de personas que participaron en ellas. Una métrica cuyo valor total no se recoge ahí es Total de organizadores de conferencia distintos. Esto responde a un motivo: imagine que está consultando los datos de un mes entero. En el día 1 hubo 34 organizadores distintos y en el día 2, 27. Esto no tiene por qué significar que hubo 61 organizadores distintos esos días, ya que las 27 personas que organizaron conferencias durante el día 2 podrían encontrarse entre las 34 que organizaron conferencias en el día 1. Vea en este sencillo informe cómo Ken Myer y Pilar Ackerman programaron conferencias en los días 7/7/2012 y 2/7/2012:


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
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>2/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>2/7/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Para componerse una mejor idea del número total de usuarios distintos que ha organizado conferencias, cambie el intervalo temporal (por ejemplo, consulte los datos por mes en lugar de por día).

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
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 pm</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre empiezan en domingo y terminan en sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>07.07.12 13:00</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo de</strong></p></td>
<td><p>Intervalo de tiempo. Seleccione una de las siguientes opciones:</p>
<ul>
<li><p>Cada hora (se puede ver un máximo de 25 horas)</p></li>
<li><p>Cada día (se puede ver un máximo de 31 días)</p></li>
<li><p>Cada semana (se puede ver un máximo de 12 semanas)</p></li>
<li><p>Cada mes (se puede ver un máximo de 12 meses)</p></li>
</ul>
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solamente se mostrará la cantidad máxima de valores (empezando por la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, los datos de un total de 31 días).</p></td>
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
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Cada hora</strong></p>
<p><strong>Diario</strong></p>
<p><strong>Semanal</strong></p>
<p><strong>Mensualmente</strong></p></td>
<td><p>No</p></td>
<td><p>Indica el intervalo temporal que ha seleccionado en la barra de herramientas de filtro. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada al respecto. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 7/7/2012, verá un desglose por horas de la actividad de registro del usuario correspondiente a esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de conferencias (independientemente del tipo de conferencia) celebradas. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de participantes</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de personas que participaron en las conferencias. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Media de participantes por conferencia</strong></p></td>
<td><p>No</p></td>
<td><p>Número medio de participantes que participaron en una conferencia en concreto. Se calcula dividiendo el número total de conferencias por el número total de participantes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Número total de conferencias A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de conferencias que incluían audio o vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>	Total de minutos de conferencia A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de minutos dedicados a conferencias de audio/vídeo.</p>
<p>La métrica total de minutos de conferencia A/V resume todos los tipos de conferencia de audio y vídeo, entre los que se incluyen: conferencias A/V; Conferencias de mensajería instantánea; conferencias de uso compartido de aplicaciones; conferencias de datos; y conferencias RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes en conferencia A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de minutos de los participantes dedicados a conferencias de audio/vídeo. Por ejemplo, supongamos que un usuario participa 5 minutos en una conferencia de audio/vídeo y un segundo usuario participa 3 minutos en la misma conferencia. Esto hace un total de 8 minutos de los participantes: 5 minutos más 3 minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Número medio de minutos en conferencias A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Número medio de minutos por conferencia de audio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Número total de organizadores únicos de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de usuarios que organizaron al menos una conferencia. Los usuarios que organizaron más de una conferencia se cuentan como un único organizador, al igual que ocurre con los usuarios que solo organizaron una única conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Número total de mensajes de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de mensajes instantáneos enviados durante las conferencias.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

