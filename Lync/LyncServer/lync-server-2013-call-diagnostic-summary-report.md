---
title: 'Lync Server 2013: informe de Resumen de diagnósticos de llamadas'
description: 'Lync Server 2013: informe de Resumen de diagnósticos de llamadas.'
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
ms.openlocfilehash: b444a176c06974a9eb9827006e078c17b54047a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561706"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="e5af4-103">Informe de Resumen de diagnósticos de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5af4-103">Call Diagnostic Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5af4-104">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e5af4-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e5af4-p101">El informe de resumen de diagnósticos de llamadas proporciona un resumen general de las sesiones de punto a punto y las sesiones de conferencia con errores. El informe muestra el porcentaje general de errores para ambos tipos de sesiones y desglosa la información sobre los errores por tipo de modalidad de sesión:</span><span class="sxs-lookup"><span data-stu-id="e5af4-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="e5af4-107">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="e5af4-107">Instant messaging</span></span>

  - <span data-ttu-id="e5af4-108">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e5af4-108">Application sharing</span></span>

  - <span data-ttu-id="e5af4-109">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="e5af4-109">File transfer</span></span>

  - <span data-ttu-id="e5af4-110">Audio</span><span class="sxs-lookup"><span data-stu-id="e5af4-110">Audio</span></span>

  - <span data-ttu-id="e5af4-111">Vídeo</span><span class="sxs-lookup"><span data-stu-id="e5af4-111">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="e5af4-112">Acceso al informe de resumen de diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="e5af4-112">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="e5af4-113">El informe de resumen de diagnósticos de llamadas es accesible desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="e5af4-113">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="e5af4-114">Desde el informe de Resumen de diagnósticos de llamadas puede obtener acceso al [Informe de diagnósticos de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) haciendo clic en la métrica tasa de errores en la sección Resumen de sesiones punto a punto del informe.</span><span class="sxs-lookup"><span data-stu-id="e5af4-114">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="e5af4-115">También puede tener acceso al [Informe de diagnósticos de conferencia en Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) haciendo clic en cualquiera de las siguientes métricas de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="e5af4-115">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="e5af4-116">Porcentaje de errores de sesión generales</span><span class="sxs-lookup"><span data-stu-id="e5af4-116">Overall session failure rate</span></span>

  - <span data-ttu-id="e5af4-117">Porcentaje de errores de foco</span><span class="sxs-lookup"><span data-stu-id="e5af4-117">Focus failure rate</span></span>

  - <span data-ttu-id="e5af4-118">Porcentaje de errores de MCU</span><span class="sxs-lookup"><span data-stu-id="e5af4-118">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="e5af4-119">Optimización del uso del informe de resumen de diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="e5af4-119">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="e5af4-120">El informe de Resumen de diagnósticos de llamadas incluye gráficos que comparan las tasas de errores para las distintas modalidades usadas en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5af4-120">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e5af4-121">Las columnas de estos gráficos son realmente hotlinks; por ejemplo, si hace clic en la columna mensajería instantánea para sesiones punto a punto, profundizará en una instancia del [Informe de diagnósticos de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un informe que proporciona detalles adicionales sobre todas las sesiones de mensajería instantánea incluidas en el informe de Resumen de diagnósticos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e5af4-121">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e5af4-122">Filtros</span><span class="sxs-lookup"><span data-stu-id="e5af4-122">Filters</span></span>

<span data-ttu-id="e5af4-p104">Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de diagnósticos de llamadas permite filtrar por elementos como el grupo de registradores o el servidor perimetral empleado en la sesión. También puede elegir el modo en que los datos deben agruparse (en este caso, las llamadas se agrupan por hora, día, semana o mes).</span><span class="sxs-lookup"><span data-stu-id="e5af4-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e5af4-127">En la siguiente tabla se muestran los filtros que se pueden usar en el informe de resumen de diagnósticos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e5af4-127">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="e5af4-128">Filtros del informe de resumen de diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="e5af4-128">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5af4-129">Nombre</span><span class="sxs-lookup"><span data-stu-id="e5af4-129">Name</span></span></th>
<th><span data-ttu-id="e5af4-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5af4-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-131"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-131"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-p105">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e5af4-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e5af4-134">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e5af4-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5af4-p106">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="e5af4-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5af4-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5af4-137">7/7/2012</span></span></p>
<p><span data-ttu-id="e5af4-138">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="e5af4-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5af4-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5af4-139">7/3/2012</span></span></p>
<p><span data-ttu-id="e5af4-140">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="e5af4-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5af4-141"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-141"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-p107">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e5af4-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e5af4-144">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e5af4-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5af4-p108">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="e5af4-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5af4-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5af4-147">7/7/2012</span></span></p>
<p><span data-ttu-id="e5af4-148">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="e5af4-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5af4-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5af4-149">7/3/2012</span></span></p>
<p><span data-ttu-id="e5af4-150">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="e5af4-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-151"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-151"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-p109">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e5af4-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5af4-154">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="e5af4-154">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e5af4-155">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="e5af4-155">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e5af4-156">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="e5af4-156">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e5af4-157">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="e5af4-157">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e5af4-p110">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="e5af4-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5af4-160"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-p111">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5af4-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e5af4-164">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="e5af4-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="e5af4-165">En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones punto a punto (esto es, sesiones en las que solo participan dos usuarios).</span><span class="sxs-lookup"><span data-stu-id="e5af4-165">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e5af4-166">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="e5af4-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5af4-167">Nombre</span><span class="sxs-lookup"><span data-stu-id="e5af4-167">Name</span></span></th>
<th><span data-ttu-id="e5af4-168">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="e5af4-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5af4-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5af4-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-170"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-170"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-171">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-171">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-172">Número total de sesiones punto a punto que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="e5af4-172">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5af4-173"><strong>Porcentaje de errores</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-173"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-174">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-174">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-p112">Porcentaje de las sesiones punto a punto con errores. Al hacer clic en este elemento, el informe muestra el informe de diagnósticos de actividad punto a punto, que contiene información más detallada sobre las sesiones punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="e5af4-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e5af4-177">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="e5af4-177">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="e5af4-178">En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones de conferencia (esto es, sesiones en las que participan tres o más usuarios).</span><span class="sxs-lookup"><span data-stu-id="e5af4-178">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e5af4-179">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="e5af4-179">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5af4-180">Nombre</span><span class="sxs-lookup"><span data-stu-id="e5af4-180">Name</span></span></th>
<th><span data-ttu-id="e5af4-181">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="e5af4-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5af4-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5af4-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-183"><strong>Total de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-183"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-184">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-184">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-185">Número total de conferencias que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="e5af4-185">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5af4-186"><strong>Total de sesiones de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-186"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-187">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-187">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-188">Número total de sesiones de conferencia que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="e5af4-188">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-189"><strong>Porcentaje de errores de sesión generales</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-189"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-190">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-190">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-191">Porcentaje del total de sesiones de conferencia con errores.</span><span class="sxs-lookup"><span data-stu-id="e5af4-191">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5af4-192"><strong>Sesiones de foco</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-192"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-193">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-193">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-194">Número total de las sesiones de conferencia basadas en foco con errores.</span><span class="sxs-lookup"><span data-stu-id="e5af4-194">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-195"><strong>Porcentaje de errores de foco</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-195"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-196">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-196">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-197">Porcentaje de las sesiones de conferencia basadas en foco con errores.</span><span class="sxs-lookup"><span data-stu-id="e5af4-197">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5af4-198"><strong>Sesiones MCU</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-198"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-199">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-199">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-200">Número total de conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</span><span class="sxs-lookup"><span data-stu-id="e5af4-200">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5af4-201"><strong>Porcentaje de errores de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="e5af4-201"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5af4-202">No</span><span class="sxs-lookup"><span data-stu-id="e5af4-202">No</span></span></p></td>
<td><p><span data-ttu-id="e5af4-203">Porcentaje de las conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</span><span class="sxs-lookup"><span data-stu-id="e5af4-203">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

