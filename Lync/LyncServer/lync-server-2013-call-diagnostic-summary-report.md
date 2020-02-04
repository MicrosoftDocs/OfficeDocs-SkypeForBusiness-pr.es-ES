---
title: 'Lync Server 2013: informe de Resumen de diagnóstico de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Informe de Resumen de diagnóstico de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

El informe de resumen de diagnósticos de llamadas proporciona un resumen general de las sesiones de punto a punto y las sesiones de conferencia con errores. El informe muestra el porcentaje general de errores para ambos tipos de sesiones y desglosa la información sobre los errores por tipo de modalidad de sesión:

  - Mensajería instantánea

  - Uso compartido de aplicaciones

  - Transferencia de archivos

  - Audio

  - Vídeo

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>Acceso al informe de resumen de diagnósticos de llamadas

El informe de resumen de diagnósticos de llamadas es accesible desde la página principal de informes de supervisión. En el informe Resumen de diagnóstico de llamadas, puede obtener acceso al [Informe de diagnóstico de actividad de punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) haciendo clic en la métrica de la tasa de errores de la sección de la sesión de punto a punto del informe. También puede acceder al [Informe de diagnóstico de conferencia en Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) haciendo clic en cualquiera de las siguientes métricas de la Conferencia:

  - Porcentaje de errores de sesión generales

  - Porcentaje de errores de foco

  - Porcentaje de errores de MCU

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Optimización del uso del informe de resumen de diagnósticos de llamadas

El informe Resumen de diagnóstico de llamadas incluye gráficos que comparan las tasas de errores para las distintas modalidades usadas en Microsoft Lync Server 2013. Las columnas de estos gráficos son realmente hotlinks. por ejemplo, si hace clic en la columna mensajes instantáneos en sesiones de punto a punto, se desplazará en profundidad a una instancia del [Informe de diagnóstico de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un informe que proporciona detalles adicionales sobre todas las sesiones de mensajería instantánea incluidas en el informe de Resumen de diagnósticos de llamadas.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de diagnósticos de llamadas permite filtrar por elementos como el grupo de registradores o el servidor perimetral empleado en la sesión. También puede elegir el modo en que los datos necesitan agruparse (en este caso, las llamadas se agrupan por hora, día, semana o mes).

En la siguiente tabla se muestran los filtros que se pueden usar en el informe de resumen de diagnósticos de llamadas.

### <a name="call-diagnostic-summary-report-filters"></a>Filtros del informe de resumen de diagnósticos de llamadas

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
<tr class="even">
<td><p><strong>Grupo de servidores</strong></p></td>
<td><p>Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones punto a punto (esto es, sesiones en las que solo participan dos usuarios).

### <a name="metrics-for-peer-to-peer-sessions"></a>Métricas de las sesiones punto a punto

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
<td><p><strong>Total de sesiones</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones punto a punto que ha tenido lugar.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentaje de errores</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de las sesiones punto a punto con errores. Al hacer clic en este elemento, el informe muestra el informe de diagnósticos de actividad punto a punto, que contiene información más detallada sobre las sesiones punto a punto con errores.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones de conferencia (esto es, sesiones en las que participan tres o más usuarios).

### <a name="metrics-for-conferencing-sessions"></a>Métricas de las sesiones de conferencia

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
<td><p><strong>Total de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de conferencias que ha tenido lugar.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sesiones de conferencias</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de sesiones de conferencia que ha tenido lugar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de sesión generales</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje del total de sesiones de conferencia con errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones de foco</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de las sesiones de conferencia basadas en foco con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de foco</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de las sesiones de conferencia basadas en foco con errores.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sesiones MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad total de conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentaje de errores de MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Porcentaje de las conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

