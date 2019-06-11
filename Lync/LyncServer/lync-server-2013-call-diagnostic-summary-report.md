---
title: 'Lync Server 2013: informe de Resumen de diagnóstico de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e747d257e7c88973790e8fd0c9ba828949248598
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="626f9-102">Informe de Resumen de diagnóstico de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="626f9-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="626f9-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="626f9-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="626f9-p101">El informe de resumen de diagnósticos de llamadas proporciona un resumen general de las sesiones de punto a punto y las sesiones de conferencia con errores. El informe muestra el porcentaje general de errores para ambos tipos de sesiones y desglosa la información sobre los errores por tipo de modalidad de sesión:</span><span class="sxs-lookup"><span data-stu-id="626f9-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="626f9-106">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="626f9-106">Instant messaging</span></span>

  - <span data-ttu-id="626f9-107">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="626f9-107">Application sharing</span></span>

  - <span data-ttu-id="626f9-108">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="626f9-108">File transfer</span></span>

  - <span data-ttu-id="626f9-109">Audio</span><span class="sxs-lookup"><span data-stu-id="626f9-109">Audio</span></span>

  - <span data-ttu-id="626f9-110">Vídeo</span><span class="sxs-lookup"><span data-stu-id="626f9-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="626f9-111">Acceso al informe de resumen de diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="626f9-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="626f9-112">El informe de resumen de diagnósticos de llamadas es accesible desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="626f9-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="626f9-113">En el informe Resumen de diagnóstico de llamadas, puede obtener acceso al [Informe de diagnóstico de actividad de punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) haciendo clic en la métrica de la tasa de errores de la sección de la sesión de punto a punto del informe.</span><span class="sxs-lookup"><span data-stu-id="626f9-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="626f9-114">También puede acceder al [Informe de diagnóstico de conferencia en Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) haciendo clic en cualquiera de las siguientes métricas de la Conferencia:</span><span class="sxs-lookup"><span data-stu-id="626f9-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="626f9-115">Porcentaje de errores de sesión generales</span><span class="sxs-lookup"><span data-stu-id="626f9-115">Overall session failure rate</span></span>

  - <span data-ttu-id="626f9-116">Porcentaje de errores de foco</span><span class="sxs-lookup"><span data-stu-id="626f9-116">Focus failure rate</span></span>

  - <span data-ttu-id="626f9-117">Porcentaje de errores de MCU</span><span class="sxs-lookup"><span data-stu-id="626f9-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="626f9-118">Optimización del uso del informe de resumen de diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="626f9-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="626f9-119">El informe Resumen de diagnóstico de llamadas incluye gráficos que comparan las tasas de errores para las distintas modalidades usadas en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="626f9-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="626f9-120">Las columnas de estos gráficos son realmente hotlinks. por ejemplo, si hace clic en la columna de mensajes instantáneos en sesiones de punto a punto, profundizará en una instancia del [Informe de diagnóstico de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un informe que proporciona detalles adicionales sobre todo el instante sesiones de mensajería incluidas en el informe Resumen de diagnóstico de llamadas.</span><span class="sxs-lookup"><span data-stu-id="626f9-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="626f9-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="626f9-121">Filters</span></span>

<span data-ttu-id="626f9-p104">Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o de ver los datos devueltos de diversas formas. Por ejemplo, el informe de resumen de diagnósticos de llamadas permite filtrar por elementos como el grupo de registradores o el servidor perimetral empleado en la sesión. También puede elegir el modo en que los datos necesitan agruparse (en este caso, las llamadas se agrupan por hora, día, semana o mes).</span><span class="sxs-lookup"><span data-stu-id="626f9-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="626f9-126">En la siguiente tabla se muestran los filtros que se pueden usar en el informe de resumen de diagnósticos de llamadas.</span><span class="sxs-lookup"><span data-stu-id="626f9-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="626f9-127">Filtros del informe de resumen de diagnósticos de llamadas</span><span class="sxs-lookup"><span data-stu-id="626f9-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="626f9-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="626f9-128">Name</span></span></th>
<th><span data-ttu-id="626f9-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="626f9-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="626f9-130"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-p105">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="626f9-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="626f9-133">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="626f9-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="626f9-p106">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="626f9-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="626f9-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="626f9-136">7/7/2012</span></span></p>
<p><span data-ttu-id="626f9-137">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="626f9-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="626f9-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="626f9-138">7/3/2012</span></span></p>
<p><span data-ttu-id="626f9-139">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="626f9-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="626f9-140"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-p107">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="626f9-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="626f9-143">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="626f9-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="626f9-p108">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="626f9-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="626f9-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="626f9-146">7/7/2012</span></span></p>
<p><span data-ttu-id="626f9-147">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="626f9-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="626f9-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="626f9-148">7/3/2012</span></span></p>
<p><span data-ttu-id="626f9-149">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="626f9-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="626f9-150"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-p109">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="626f9-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="626f9-153">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="626f9-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="626f9-154">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="626f9-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="626f9-155">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="626f9-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="626f9-156">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="626f9-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="626f9-157">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="626f9-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="626f9-158">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="626f9-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="626f9-159"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-p111">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="626f9-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="626f9-163">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="626f9-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="626f9-164">En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones punto a punto (esto es, sesiones en las que solo participan dos usuarios).</span><span class="sxs-lookup"><span data-stu-id="626f9-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="626f9-165">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="626f9-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="626f9-166">Nombre</span><span class="sxs-lookup"><span data-stu-id="626f9-166">Name</span></span></th>
<th><span data-ttu-id="626f9-167">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="626f9-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="626f9-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="626f9-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="626f9-169"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-170">No</span><span class="sxs-lookup"><span data-stu-id="626f9-170">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-171">Cantidad total de sesiones punto a punto que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="626f9-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="626f9-172"><strong>Porcentaje de errores</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-173">No</span><span class="sxs-lookup"><span data-stu-id="626f9-173">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-p112">Porcentaje de las sesiones punto a punto con errores. Al hacer clic en este elemento, el informe muestra el informe de diagnósticos de actividad punto a punto, que contiene información más detallada sobre las sesiones punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="626f9-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="626f9-176">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="626f9-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="626f9-177">En la siguiente tabla se muestra la información recogida el informe de resumen de diagnósticos de llamadas de las sesiones de conferencia (esto es, sesiones en las que participan tres o más usuarios).</span><span class="sxs-lookup"><span data-stu-id="626f9-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="626f9-178">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="626f9-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="626f9-179">Nombre</span><span class="sxs-lookup"><span data-stu-id="626f9-179">Name</span></span></th>
<th><span data-ttu-id="626f9-180">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="626f9-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="626f9-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="626f9-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="626f9-182"><strong>Total de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-183">No</span><span class="sxs-lookup"><span data-stu-id="626f9-183">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-184">Cantidad total de conferencias que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="626f9-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="626f9-185"><strong>Total de sesiones de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-186">No</span><span class="sxs-lookup"><span data-stu-id="626f9-186">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-187">Cantidad total de sesiones de conferencia que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="626f9-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="626f9-188"><strong>Porcentaje de errores de sesión generales</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-189">No</span><span class="sxs-lookup"><span data-stu-id="626f9-189">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-190">Porcentaje del total de sesiones de conferencia con errores.</span><span class="sxs-lookup"><span data-stu-id="626f9-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="626f9-191"><strong>Sesiones de foco</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-192">No</span><span class="sxs-lookup"><span data-stu-id="626f9-192">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-193">Cantidad total de las sesiones de conferencia basadas en foco con errores.</span><span class="sxs-lookup"><span data-stu-id="626f9-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="626f9-194"><strong>Porcentaje de errores de foco</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-195">No</span><span class="sxs-lookup"><span data-stu-id="626f9-195">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-196">Porcentaje de las sesiones de conferencia basadas en foco con errores.</span><span class="sxs-lookup"><span data-stu-id="626f9-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="626f9-197"><strong>Sesiones MCU</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-198">No</span><span class="sxs-lookup"><span data-stu-id="626f9-198">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-199">Cantidad total de conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</span><span class="sxs-lookup"><span data-stu-id="626f9-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="626f9-200"><strong>Porcentaje de errores de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="626f9-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="626f9-201">No</span><span class="sxs-lookup"><span data-stu-id="626f9-201">No</span></span></p></td>
<td><p><span data-ttu-id="626f9-202">Porcentaje de las conferencias basadas en servidor de conferencia (antes denominadas unidades de control multipunto o MCU) con errores.</span><span class="sxs-lookup"><span data-stu-id="626f9-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

