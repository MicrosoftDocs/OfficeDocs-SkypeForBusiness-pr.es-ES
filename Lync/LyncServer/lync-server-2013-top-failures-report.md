---
title: 'Lync Server 2013: informe de errores principales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="f564e-102">Informe de errores principales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f564e-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f564e-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f564e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f564e-p101">El Informe de errores principales proporciona una presentación de los errores más frecuentes y las tendencias en el tiempo. Los errores se basan en una combinación de las dos métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f564e-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="f564e-p102">**Id. de diagnóstico**. Identificador único (en forma de un encabezado de ms-diagnostics) que se adjunta a un mensaje SIP. Los Id. de diagnóstico proporcionan información útil para la solución de problemas relacionados con la llamada.</span><span class="sxs-lookup"><span data-stu-id="f564e-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="f564e-109">**Código de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="f564e-109">**Response code**.</span></span> <span data-ttu-id="f564e-110">Los códigos de respuesta se usan en las sesiones de comunicación SIP para responder a solicitudes SIP.</span><span class="sxs-lookup"><span data-stu-id="f564e-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="f564e-111">Por ejemplo, supongamos que Ken envía la solicitud INVITE a Pilar Ackerman (es decir, supongamos que Ken Myer llama Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="f564e-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="f564e-112">Si Pilar responde, su teléfono le enviará el código de respuesta 200 (OK), indicando al teléfono de Ken que Pilar ha respondido.</span><span class="sxs-lookup"><span data-stu-id="f564e-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="f564e-113">El informe de errores principales solo incluye códigos de respuesta que se enviaron en respuesta a un error de llamada. Lync Server no realiza un seguimiento de todos los códigos de respuesta emitidos durante el transcurso de una llamada.</span><span class="sxs-lookup"><span data-stu-id="f564e-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="f564e-114">No solo se proporciona información de la cantidad total de sesiones donde se produjo un error, sino también de la cantidad total de usuarios a los que afectó el error.</span><span class="sxs-lookup"><span data-stu-id="f564e-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="f564e-115">Acceso al Informe de errores principales</span><span class="sxs-lookup"><span data-stu-id="f564e-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="f564e-116">Desde la página Informes supervisión se obtiene acceso al Informe de errores principales.</span><span class="sxs-lookup"><span data-stu-id="f564e-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f564e-117">Al hacer clic en la métrica de sesiones notificadas, se abrirá el [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="f564e-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="f564e-118">Hacer el mejor uso del Informe de errores principales</span><span class="sxs-lookup"><span data-stu-id="f564e-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="f564e-p105">El Informe de errores principales es inusual en un sentido: le permite filtrar a la vez hasta 5 Id. de diagnóstico. (Normalmente solo se filtra por un elemento cada vez, como una dirección SIP de usuario). Para filtrar por varios Id. de diagnóstico, simplemente introduzca cada Id. en el cuadro Id. de diagnóstico, separe los identificadores con comas. (Si desea, puede dejar un espacio en blanco después de cada coma). Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f564e-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="f564e-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="f564e-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="f564e-123">Haga eso y solo aparecerán las llamadas erróneas que notificaron al menos uno de esos cinco Id. de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="f564e-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="f564e-p106">Si coloca el mouse sobre un código de respuesta verá una información sobre herramientas que le indica el significado del código de respuesta en cuestión. Por ejemplo, si coloca el mouse sobre el código de respuesta 486 verá este mensaje:</span><span class="sxs-lookup"><span data-stu-id="f564e-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="f564e-126">No disponible aquí.</span><span class="sxs-lookup"><span data-stu-id="f564e-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f564e-127">Filtros</span><span class="sxs-lookup"><span data-stu-id="f564e-127">Filters</span></span>

<span data-ttu-id="f564e-p107">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de errores más comunes le permite filtrar los datos en función de aspectos tales como el tipo de actividad (sesión punto a punto o sesión de conferencia) o por el código de respuesta SIP que acompañó a la sesión fallida. Es posible también elegir la forma en la que los datos necesitan agruparse. En este caso, los usos se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="f564e-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f564e-132">La siguiente tabla muestra los filtros que puede utilizar con el informe de errores más comunes.</span><span class="sxs-lookup"><span data-stu-id="f564e-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="f564e-133">Filtros del informe de errores más comunes</span><span class="sxs-lookup"><span data-stu-id="f564e-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f564e-134">Nombre</span><span class="sxs-lookup"><span data-stu-id="f564e-134">Name</span></span></th>
<th><span data-ttu-id="f564e-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="f564e-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f564e-136"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p108">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f564e-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f564e-139">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="f564e-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f564e-p109">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="f564e-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f564e-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f564e-142">7/7/2012</span></span></p>
<p><span data-ttu-id="f564e-143">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="f564e-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f564e-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f564e-144">7/3/2012</span></span></p>
<p><span data-ttu-id="f564e-145">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="f564e-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f564e-146"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p110">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f564e-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f564e-149">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="f564e-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f564e-p111">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="f564e-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f564e-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f564e-152">7/7/2012</span></span></p>
<p><span data-ttu-id="f564e-153">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="f564e-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f564e-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f564e-154">7/3/2012</span></span></p>
<p><span data-ttu-id="f564e-155">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="f564e-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f564e-156"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p112">Tipo de actividad. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f564e-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f564e-159">[Todas]</span><span class="sxs-lookup"><span data-stu-id="f564e-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="f564e-160">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="f564e-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="f564e-161">Una conferencia</span><span class="sxs-lookup"><span data-stu-id="f564e-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f564e-162"><strong>Modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-163">En este momento, la única opción disponible es <strong>[Todos]</strong>.</span><span class="sxs-lookup"><span data-stu-id="f564e-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f564e-164"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p113">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f564e-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f564e-168"><strong>Categoría</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p114">Tipo de error. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f564e-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f564e-171">Error esperado e inesperado</span><span class="sxs-lookup"><span data-stu-id="f564e-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="f564e-172">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="f564e-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="f564e-173">Un &quot;error&quot; esperado es un error que se espera que suceda.</span><span class="sxs-lookup"><span data-stu-id="f564e-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="f564e-174">Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.</span><span class="sxs-lookup"><span data-stu-id="f564e-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="f564e-175">Un &quot;error&quot; inesperado es un error que se produce en lo que parecería ser un sistema saludable en otro caso.</span><span class="sxs-lookup"><span data-stu-id="f564e-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="f564e-176">Por ejemplo, una llamada no tendría que finalizarse si el autor de la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="f564e-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="f564e-177">De ser así, tal cosa se identificaría como un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="f564e-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f564e-178"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p116">Código de respuesta SIP enviado cuando la conferencia ha fallado. Escriba el código de respuesta en su totalidad, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f564e-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="f564e-181">400</span><span class="sxs-lookup"><span data-stu-id="f564e-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f564e-182"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-p117">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="f564e-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f564e-185">Métricas</span><span class="sxs-lookup"><span data-stu-id="f564e-185">Metrics</span></span>

<span data-ttu-id="f564e-186">En la tabla siguiente se muestra la información que recoge el informe de errores más comunes.</span><span class="sxs-lookup"><span data-stu-id="f564e-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="f564e-187">Métricas del informe de errores más comunes</span><span class="sxs-lookup"><span data-stu-id="f564e-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f564e-188">Nombre</span><span class="sxs-lookup"><span data-stu-id="f564e-188">Name</span></span></th>
<th><span data-ttu-id="f564e-189">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="f564e-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f564e-190">Descripción</span><span class="sxs-lookup"><span data-stu-id="f564e-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f564e-191"><strong>Clasificación</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-192">Sí</span><span class="sxs-lookup"><span data-stu-id="f564e-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="f564e-193">Clasificación relativa basada en la cantidad de sesiones de las que se informa.</span><span class="sxs-lookup"><span data-stu-id="f564e-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f564e-194"><strong>Sesiones notificadas</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-195">Sí</span><span class="sxs-lookup"><span data-stu-id="f564e-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="f564e-196">Cantidad total de sesiones con error basadas en el Id. de diagnóstico y en el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="f564e-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f564e-197"><strong>Usuarios afectados</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-198">Sí</span><span class="sxs-lookup"><span data-stu-id="f564e-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="f564e-199">Cantidad total de usuarios afectados por la sesión con error.</span><span class="sxs-lookup"><span data-stu-id="f564e-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f564e-200"><strong>Información del error</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-201">No</span><span class="sxs-lookup"><span data-stu-id="f564e-201">No</span></span></p></td>
<td><p><span data-ttu-id="f564e-202">Información detallada sobre el error, incluido el Id. de diagnóstico, el código de respuesta SIP y la descripción de los motivos por los que se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="f564e-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f564e-203"><strong>Tendencia en el pasado</strong></span><span class="sxs-lookup"><span data-stu-id="f564e-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="f564e-204">No</span><span class="sxs-lookup"><span data-stu-id="f564e-204">No</span></span></p></td>
<td><p><span data-ttu-id="f564e-205">Gráfico de sesiones con error a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="f564e-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

