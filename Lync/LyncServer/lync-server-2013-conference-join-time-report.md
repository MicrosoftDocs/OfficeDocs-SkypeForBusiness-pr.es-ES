---
title: 'Lync Server 2013: informe de tiempo de unirse a la Conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76388655fc8ed893e09b192ae24c7807b46f9f6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Informe de tiempo de incorporación a la Conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-23_

El Resumen del tiempo de incorporación a la conferencia permite determinar cuánto tardan los usuarios en unirse a una conferencia. El informe muestra el tiempo de unión promedio (en milisegundos), así como un desglose que permite saber cuántos usuarios pudieron unirse a una conferencia en 2 o menos segundos, cuántos usuarios necesitaron entre 2 y 5 segundos para unirse a la conferencia, etc.

<div>

## <a name="accessing-the-conference-join-time-report"></a>Acceder al informe de tiempo de incorporación a la conferencia

Para obtener acceso al informe del tiempo de incorporación a la conferencia tiene que ir a la página principal de los informes de supervisión.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de tiempo de incorporación a la conferencia.

### <a name="conference-join-time-report-filters"></a>Filtros del informe de tiempo de incorporación a la conferencia

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
<p>7/7/2012 1:00 PM</p>
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
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones de conferencia</strong></p></td>
<td><p>Tipo de sesión. Los valores permitidos son:</p>
<ul>
<li><p>Todos</p></li>
<li><p>Sesiones de foco (el enfoque es el administrador de directivas y estado central para las reuniones en línea y coordina todos los aspectos de una conferencia</p></li>
<li><p>Uso compartido de aplicaciones</p></li>
<li><p>Conferencia A/V</p></li>
</ul>
<p>Si selecciona [Todo], aparecerá el tiempo de incorporación a la conferencia total en la parte superior del informe. Recuerde que estos totales son solo para conferencias programada con Microsoft Exchange o Microsoft Outlook.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de tiempo de incorporación a la conferencia.

### <a name="conference-join-time-report-metrics"></a>Métricas del informe de tiempo de incorporación a la conferencia

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
<td><p><strong>Fecha</strong></p>
<p>El título real de esta métrica variará en función del intervalo seleccionado.</p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en las que tuvo lugar la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Promedio (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Promedio del tiempo (en milisegundos) que tardaron los participantes en unirse a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones &lt; 2 segundos, volumen</strong></p></td>
<td><p>No</p></td>
<td><p>Número de participantes que pudieron unirse a la conferencia en menos de 2 segundos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones &lt; 2 segundos, porcentaje</strong></p></td>
<td><p>No</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones 2-5 segundos, Volumen</strong></p></td>
<td><p>No</p></td>
<td><p>Número de participantes que tardaron entre 2 y 5 segundos en unirse a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones 2-5 segundos, Porcentaje</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje del número total de participantes que llamaron que tardaron entre 2 y 5 segundos en unirse a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones 5-10 segundos, Volumen</strong></p></td>
<td><p>No</p></td>
<td><p>Número de participantes que tardaron entre 5 y 10 segundos en unirse a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones 5-10 segundos, Porcentaje</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje del número total de participantes que llamaron que tardaron entre 5 y 10 segundos en unirse a la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones &gt; 10 segundos, volumen</strong></p></td>
<td><p>No</p></td>
<td><p>Número de participantes que necesitaron más de 10 segundos en unirse a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sesiones &gt; 10 segundos, porcentaje</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje del número total de participantes que necesitaron más de 10 segundos en unirse a la conferencia.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

