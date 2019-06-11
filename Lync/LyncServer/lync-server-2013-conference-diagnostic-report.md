---
title: 'Lync Server 2013: informe de diagnóstico de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="345cc-102">Informe de diagnóstico de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="345cc-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="345cc-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="345cc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="345cc-104">El Informe de diagnósticos de conferencia facilita información sobre las sesiones de conferencia que se han completado correctamente y las que han presentado algún error.</span><span class="sxs-lookup"><span data-stu-id="345cc-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="345cc-105">Tenga en cuenta que Microsoft Lync Server distingue entre diferentes tipos de errores:</span><span class="sxs-lookup"><span data-stu-id="345cc-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="345cc-p102">**Error esperado**. Un error esperado es, generalmente, un error en el sentido más técnico. Por ejemplo, supongamos que alguien inicia una conferencia, pero la comunicación se cuelga antes de que otros usuarios puedan unirse a ella. Técnicamente, eso es un error: la conferencia se ha iniciado, pero no se ha completado. Pero, es un error que cabe esperar que ocurra, porque si el organizador cancela la conferencia antes de que otros usuarios se unan a ella, no podemos esperar que la conferencia se complete.</span><span class="sxs-lookup"><span data-stu-id="345cc-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="345cc-p103">**Error inesperado**. Un error inesperado es exactamente lo que su nombre sugiere: un error que, en las circunstancias actuales, no se espera que ocurra. Por ejemplo, una conferencia que no se puede llevar a cabo porque no se ha podido recuperar la directiva de reunión del organizador. Ese es un error inesperado ya que siempre se tendrían que poder recuperar las directivas de reunión de un usuario.</span><span class="sxs-lookup"><span data-stu-id="345cc-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="345cc-p104">Observe que las métricas Correcta, Error esperado y Error inesperado podrían no incluirse en la métrica Total de sesiones. Por ejemplo, podría ver los siguientes valores en el informe:</span><span class="sxs-lookup"><span data-stu-id="345cc-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="345cc-117">Correctas</span><span class="sxs-lookup"><span data-stu-id="345cc-117">Successes</span></span></th>
<th><span data-ttu-id="345cc-118">Errores esperados</span><span class="sxs-lookup"><span data-stu-id="345cc-118">Expected failures</span></span></th>
<th><span data-ttu-id="345cc-119">Errores inesperados</span><span class="sxs-lookup"><span data-stu-id="345cc-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="345cc-120">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="345cc-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="345cc-121">2024</span><span class="sxs-lookup"><span data-stu-id="345cc-121">2024</span></span></p></td>
<td><p><span data-ttu-id="345cc-122">469</span><span class="sxs-lookup"><span data-stu-id="345cc-122">469</span></span></p></td>
<td><p><span data-ttu-id="345cc-123">apartado</span><span class="sxs-lookup"><span data-stu-id="345cc-123">16</span></span></p></td>
<td><p><span data-ttu-id="345cc-124">2521</span><span class="sxs-lookup"><span data-stu-id="345cc-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="345cc-125">Si sumamos 2024 + 469 + 16, obtenemos un total de 2509 sesiones y, en cambio, la columna Total de sesiones muestra 2521 sesiones.</span><span class="sxs-lookup"><span data-stu-id="345cc-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="345cc-126">Las 12 sesiones "que faltan" son las sesiones que el sistema no ha podido clasificar como correctas ni con error.</span><span class="sxs-lookup"><span data-stu-id="345cc-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="345cc-127">Esto se producirá en ocasiones cuando un producto de terceros presenta un nuevo código de diagnóstico que no está familiarizado con la supervisión de servidor.</span><span class="sxs-lookup"><span data-stu-id="345cc-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="345cc-128">Cuando esto ocurre, las llamadas realizadas por medio de este producto que ocasionen ese código de diagnóstico no siempre se clasificarán como Correcta, Error esperado o Error inesperado.</span><span class="sxs-lookup"><span data-stu-id="345cc-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="345cc-129">Acceso al Informe de diagnósticos de conferencia</span><span class="sxs-lookup"><span data-stu-id="345cc-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="345cc-130">Al Informe de diagnósticos de conferencia, se puede obtener acceso desde la página de inicio de Informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="345cc-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="345cc-131">Puede obtener acceso al [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md) haciendo clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="345cc-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="345cc-132">Volumen de errores inesperados</span><span class="sxs-lookup"><span data-stu-id="345cc-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="345cc-133">Volumen de errores esperados</span><span class="sxs-lookup"><span data-stu-id="345cc-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="345cc-134">Cómo hacer el mejor uso del Informe de diagnósticos de conferencia</span><span class="sxs-lookup"><span data-stu-id="345cc-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="345cc-135">El Informe de diagnósticos de conferencia incluye una serie de gráficos.</span><span class="sxs-lookup"><span data-stu-id="345cc-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="345cc-136">Cada una de las columnas mostradas en el gráfico es, en realidad, un hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="345cc-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="345cc-137">Si hace clic en una columna, profundizará en el [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md) para ese período de tiempo y ese tipo de conferencia.</span><span class="sxs-lookup"><span data-stu-id="345cc-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="345cc-138">Filtros</span><span class="sxs-lookup"><span data-stu-id="345cc-138">Filters</span></span>

<span data-ttu-id="345cc-p108">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el Informe de diagnósticos de conferencia le permite filtrar elementos tales como el tipo de conferencia que se realiza (por ejemplo, una conferencia basada en un tema) o por el servidor perimetral que se usa en la conferencia. También puede elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="345cc-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="345cc-143">En la tabla siguiente se muestran los filtros que se pueden utilizar con el Informe de diagnósticos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="345cc-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="345cc-144">Filtros del Informe de diagnósticos de conferencia</span><span class="sxs-lookup"><span data-stu-id="345cc-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="345cc-145">Nombre</span><span class="sxs-lookup"><span data-stu-id="345cc-145">Name</span></span></th>
<th><span data-ttu-id="345cc-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="345cc-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="345cc-147"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-p109">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="345cc-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="345cc-150">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="345cc-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="345cc-p110">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="345cc-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="345cc-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="345cc-153">7/7/2012</span></span></p>
<p><span data-ttu-id="345cc-154">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="345cc-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="345cc-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="345cc-155">7/3/2012</span></span></p>
<p><span data-ttu-id="345cc-156">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="345cc-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="345cc-157"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-p111">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="345cc-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="345cc-160">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="345cc-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="345cc-p112">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="345cc-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="345cc-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="345cc-163">7/7/2012</span></span></p>
<p><span data-ttu-id="345cc-164">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="345cc-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="345cc-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="345cc-165">7/3/2012</span></span></p>
<p><span data-ttu-id="345cc-166">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="345cc-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="345cc-167"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-p113">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="345cc-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="345cc-170">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="345cc-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="345cc-171">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="345cc-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="345cc-172">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="345cc-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="345cc-173">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="345cc-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="345cc-174">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="345cc-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="345cc-175">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="345cc-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="345cc-176"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-p115">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="345cc-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="345cc-180"><strong>Sesiones de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-p116">Indica el tipo de sesión de conferencia. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="345cc-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="345cc-183">[Todas]</span><span class="sxs-lookup"><span data-stu-id="345cc-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="345cc-184">Sesiones de foco</span><span class="sxs-lookup"><span data-stu-id="345cc-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="345cc-185">Todas las sesiones de MCU</span><span class="sxs-lookup"><span data-stu-id="345cc-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="345cc-186">Conferencia de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="345cc-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="345cc-187">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="345cc-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="345cc-188">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="345cc-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="345cc-189">Métricas</span><span class="sxs-lookup"><span data-stu-id="345cc-189">Metrics</span></span>

<span data-ttu-id="345cc-190">En la siguiente tabla se enumera la información proporcionada en el Informe de diagnósticos de conferencia para cada tipo de sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="345cc-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="345cc-191">Métricas del Informe de diagnósticos de conferencia</span><span class="sxs-lookup"><span data-stu-id="345cc-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="345cc-192">Nombre</span><span class="sxs-lookup"><span data-stu-id="345cc-192">Name</span></span></th>
<th><span data-ttu-id="345cc-193">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="345cc-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="345cc-194">Descripción</span><span class="sxs-lookup"><span data-stu-id="345cc-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="345cc-195"><strong>Volumen de corrección</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-196">No</span><span class="sxs-lookup"><span data-stu-id="345cc-196">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-197">Cantidad total de conferencias correctas</span><span class="sxs-lookup"><span data-stu-id="345cc-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="345cc-198"><strong>Porcentaje de corrección</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-199">No</span><span class="sxs-lookup"><span data-stu-id="345cc-199">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-p117">Porcentaje de conferencias que se realizaron con problemas considerables. Se calcula dividiendo el volumen de sesiones correctas por el total de sesiones.</span><span class="sxs-lookup"><span data-stu-id="345cc-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="345cc-202"><strong>Volumen de errores esperados</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-203">No</span><span class="sxs-lookup"><span data-stu-id="345cc-203">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-204">Número total de conferencias en las &quot;que se&quot; ha producido un error esperado.</span><span class="sxs-lookup"><span data-stu-id="345cc-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="345cc-p118">Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.</span><span class="sxs-lookup"><span data-stu-id="345cc-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="345cc-207"><strong>Porcentaje de errores esperados</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-208">No</span><span class="sxs-lookup"><span data-stu-id="345cc-208">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-p119">Porcentaje de conferencias en las que se produjo un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.</span><span class="sxs-lookup"><span data-stu-id="345cc-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="345cc-211"><strong>Volumen de errores inesperados</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-212">No</span><span class="sxs-lookup"><span data-stu-id="345cc-212">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-213">Número total de conferencias en las &quot;que se&quot; produjo un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="345cc-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="345cc-p120">Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no tendría que finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="345cc-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="345cc-217"><strong>Porcentaje de errores inesperados</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-218">No</span><span class="sxs-lookup"><span data-stu-id="345cc-218">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-p121">Porcentaje de conferencias en las que se produjo un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.</span><span class="sxs-lookup"><span data-stu-id="345cc-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="345cc-221"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="345cc-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="345cc-222">No</span><span class="sxs-lookup"><span data-stu-id="345cc-222">No</span></span></p></td>
<td><p><span data-ttu-id="345cc-223">Cantidad total de conferencias, incluyendo conferencias correctas, conferencias con errores (tanto errores esperados como inesperados) y conferencias no categorizadas.</span><span class="sxs-lookup"><span data-stu-id="345cc-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

