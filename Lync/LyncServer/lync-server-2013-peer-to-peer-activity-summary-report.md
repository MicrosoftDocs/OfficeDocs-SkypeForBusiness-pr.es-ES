---
title: 'Lync Server 2013: informe de Resumen de actividad punto a punto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f96470163b1f258f59bb37128b45fbc5e15476e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Informe de Resumen de actividad punto a punto en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

El Informe de resumen de actividad punto a punto proporciona una vista general de las sesiones de comunicación punto a punto. Una sesión punto a punto suele implicar solo a dos usuarios y no requiere el uso de los servicios de conferencia de Lync Server. En comparación, una conferencia suele implicar a más de dos usuarios y requiere el uso de los servicios de conferencia de Microsoft Lync Server 2013. La actividad de la conferencia se notifica en el Informe de resumen de conferencia.

Con el Informe de resumen de actividad punto a punto le será más fácil responder a preguntas como la siguiente:

  - ¿Cuántos mensajes instantáneos de punto a punto envían habitualmente mis usuarios en un día normal?

  - ¿Alguno de mis usuarios aprovecha realmente las capacidades de transferencia de archivos y uso compartido de aplicaciones de Lync Server?

  - Los usuarios se han estado quejando de que en determinados momentos del día, parece que la red va más lenta. ¿Cuántos minutos se dedican a las sesiones de audio o vídeo en esos períodos de tiempo?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Acceder al Informe de resumen de actividad punto a punto

Acceda al Informe de resumen de actividad punto a punto desde la página inicial de los informes de supervisión. Para abrir el [Informe de mensajería instantánea punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , haga clic en cualquiera de las métricas siguientes:

  - Total de sesiones de MI punto a punto

  - Total de mensajes instantáneos punto a punto

Igualmente, puede abrir el informe de voz y vídeo punto a punto haciendo clic en una de estas métricas:

  - Total de sesiones de audio punto a punto

  - Total de minutos de sesiones de audio punto a punto

  - Total de sesiones de audio punto a punto

  - Total de minutos de sesiones de audio punto a punto

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Sacar el máximo provecho del Informe de resumen de actividad punto a punto

En la parte inferior del Informe de resumen de actividad punto a punto encontrará los totales de métricas como Sesiones de mensajería instantánea punto a punto o Total de mensajes de mensajería instantánea punto a punto. De esta forma obtiene un resumen rápido de la información detallada encontrada en el cuerpo del informe.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el resumen de actividad punto a punto le permite elegir cuántos datos agrupar. En este caso, la actividad se agrupa por hora, día, semana o mes.

En la siguiente tabla se enumeran los filtros que puede utilizar con el Informe de resumen de actividad punto a punto.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Filtros del Informe de resumen de actividad punto a punto

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
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como a continuación:</p>
<p>17/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/17/12012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/13/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como a continuación:</p>
<p>1/1/2011 13:00</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/17/12012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/13/2012</p>
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
<p>Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 1/1/2011 y una fecha de finalización 28/2/2011, se mostrarán los datos correspondientes a los días entre el 1/8/2011 a las 12:00 horas y el 1/9/2011 a las 12:00 horas (es decir, datos para un total de 31 días).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información que recoge el Informe de resumen de actividad punto a punto.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Métricas del Informe de resumen de actividad punto a punto

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
<td><p>Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 1/1/2011, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones punto a punto realizadas, independientemente del tipo de sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sesiones de MI punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones de mensajería instantánea punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de mensajes instantáneos punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de mensajes instantáneos enviados en sesiones punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sesiones de audio punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas de audio punto a punto. Cuando se hace clic en este campo, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de sesiones de audio punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de tiempo total transcurrida en sesiones de audio punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Promedio de minutos en sesiones de audio punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de tiempo promedio transcurrido en sesiones de audio punto a punto. Se calcula dividiendo el total del tiempo de sesiones de audio por el número total de sesiones de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones de vídeo punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de llamadas de vídeo punto a punto. Observe que las sesiones de vídeo también se cuentan como sesiones de audio: cada sesión de vídeo se cuenta como una sesión de vídeo y una sesión de audio. Cuando se hace clic en este elemento, el informe muestra el informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de sesiones de vídeo punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de tiempo transcurrido en sesiones de vídeo punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Promedio de minutos en sesiones de vídeo punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de tiempo promedio transcurrido en sesiones de vídeo punto a punto. Se calcula dividiendo el total del tiempo de sesiones de vídeo por el número total de sesiones de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sesiones de transferencia de archivos punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones punto a punto en las que se realizaron transferencias de archivos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones compartidas de aplicaciones punto a punto</strong></p></td>
<td><p>No</p></td>
<td><p>Número total de sesiones punto a punto en las que se compartieron aplicaciones</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

