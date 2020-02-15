---
title: 'Lync Server 2013: informe de control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5b643adf6a8208285aeba66304ddd1657afdfa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="91032-102">Informe de control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91032-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91032-103">_**Última modificación del tema:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="91032-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="91032-104">El Informe de control de admisión de llamadas ofrece información sobre las sesiones de punto a punto y de conferencia que se han llevado a cabo con restricciones definidas por el Control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="91032-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="91032-105">El control de admisión de llamadas, que se incorporó en Microsoft Lync Server 2010, permite a los administradores permitir (o no permitir) sesiones de comunicación basadas en restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="91032-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="91032-106">Por ejemplo, los administradores pueden crear directivas que impongan un límite a la cantidad de ancho de banda disponible para las llamadas de voz y vídeo.</span><span class="sxs-lookup"><span data-stu-id="91032-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="91032-107">Si se alcanza ese límite de ancho de banda, no se podrán realizar nuevas llamadas de voz o vídeo hasta que finalice alguna de las llamadas en curso y se liberen los recursos de red necesarios.</span><span class="sxs-lookup"><span data-stu-id="91032-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="91032-108">Acceso al Informe de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="91032-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="91032-p102">Al Informe de control de admisión de llamadas se accede desde la página de inicio de Informes de supervisión. Desde el Informe de control de admisión de llamadas, puede acceder a cualquiera de los informes siguientes:</span><span class="sxs-lookup"><span data-stu-id="91032-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="91032-111">Informe de detalles de conferencia: Para acceder a este informe, hada clic en la métrica Detalles desde una sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="91032-112">Informe de detalles de sesiones punto a punto: Para acceder a este informe, haga clic en la métrica Detalles desde una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="91032-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="91032-113">Cómo hacer el mejor uso del Informe de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="91032-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="91032-p103">Para obtener una lista de las llamadas que no se han podido completar correctamente porque el ancho de banda no era suficiente, seleccione Llamadas rechazadas debido al control de admisión de llamadas en la lista desplegable Categoría de llamada. La mayoría de las llamadas devueltas presentarán seguramente el identificador de diagnóstico 5:</span><span class="sxs-lookup"><span data-stu-id="91032-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="91032-p104">Ancho de banda insuficiente para establecer la sesión. Intente volver a enrutar la llamada a través de RTC.</span><span class="sxs-lookup"><span data-stu-id="91032-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="91032-118">Este mensaje indica que las limitaciones del Control de admisión de llamadas impidió que la llamada se realizara en la red VoIP.</span><span class="sxs-lookup"><span data-stu-id="91032-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="91032-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="91032-119">Filters</span></span>

<span data-ttu-id="91032-p105">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el Informe de control de admisión de llamadas le permite filtrar llamadas por el usuario que inicia la llamada o por el usuario que recibe la llamada. También puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="91032-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="91032-124">En la tabla siguiente se muestran los filtros que se pueden utilizar con el Informe de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="91032-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="91032-125">Filtros del Informe de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="91032-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91032-126">Nombre</span><span class="sxs-lookup"><span data-stu-id="91032-126">Name</span></span></th>
<th><span data-ttu-id="91032-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="91032-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91032-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="91032-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-p106">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="91032-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="91032-131">17/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="91032-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="91032-p107">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="91032-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="91032-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="91032-134">7/17/12012</span></span></p>
<p><span data-ttu-id="91032-135">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="91032-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="91032-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="91032-136">7/13/2012</span></span></p>
<p><span data-ttu-id="91032-137">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="91032-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="91032-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-p108">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="91032-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="91032-141">17/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="91032-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="91032-p109">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="91032-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="91032-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="91032-144">7/17/12012</span></span></p>
<p><span data-ttu-id="91032-145">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="91032-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="91032-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="91032-146">7/13/2012</span></span></p>
<p><span data-ttu-id="91032-147">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="91032-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="91032-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-p110">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="91032-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-152"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="91032-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-p111">Tipo de actividad. Seleccione una de las siguientes actividades:</span><span class="sxs-lookup"><span data-stu-id="91032-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="91032-155">Todos</span><span class="sxs-lookup"><span data-stu-id="91032-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="91032-156">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="91032-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="91032-157">Conversación</span><span class="sxs-lookup"><span data-stu-id="91032-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-158"><strong>Categoría de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="91032-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-p112">Indica el motivo por el que se usó el control de admisión de llamadas para la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91032-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="91032-161">Todos</span><span class="sxs-lookup"><span data-stu-id="91032-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="91032-162">Llamada rechazada debido al control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="91032-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="91032-163">Llamadas que se han vuelto a enrutar a través de RTC debido al control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="91032-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="91032-164">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="91032-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="91032-165">En la siguiente tabla se muestra la información proporcionada por el Informe del control de admisión de llamadas para las sesiones punto a punto (es decir, sesiones entre solo dos participantes).</span><span class="sxs-lookup"><span data-stu-id="91032-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="91032-166">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="91032-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91032-167">Nombre</span><span class="sxs-lookup"><span data-stu-id="91032-167">Name</span></span></th>
<th><span data-ttu-id="91032-168">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="91032-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="91032-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="91032-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91032-170"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="91032-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-171">No</span><span class="sxs-lookup"><span data-stu-id="91032-171">No</span></span></p></td>
<td><p><span data-ttu-id="91032-172">Cuando se hace clic en este elemento, el informe muestra un informe detallado de sesión punto a punto de la sesión específica.</span><span class="sxs-lookup"><span data-stu-id="91032-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-173"><strong>Remitente</strong></span><span class="sxs-lookup"><span data-stu-id="91032-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-174">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-175">Dirección SIP del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="91032-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-176"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="91032-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-177">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-178">Dirección SIP del usuario al que se invitó a unirse a la sesión.</span><span class="sxs-lookup"><span data-stu-id="91032-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-179"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="91032-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-180">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-181">Modalidades de comunicación (como audio y vídeo) que se usaron durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="91032-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-182"><strong>Hora de invitación</strong></span><span class="sxs-lookup"><span data-stu-id="91032-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-183">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-184">Fecha y hora en que se envió al remitente la invitación a la sesión inicial.</span><span class="sxs-lookup"><span data-stu-id="91032-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-185"><strong>Tiempo de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="91032-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-186">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-187">Fecha y hora en que se recibió la aceptación de la invitación.</span><span class="sxs-lookup"><span data-stu-id="91032-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-188"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="91032-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-189">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-190">Fecha y hora en que finalizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="91032-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-191"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="91032-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-192">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-p113">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="91032-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="91032-195">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="91032-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="91032-196">En la siguiente tabla se muestra información proporcionada en el Informe de control de admisión de llamadas para las sesiones de conferencia (es decir, sesiones con tres o más participantes).</span><span class="sxs-lookup"><span data-stu-id="91032-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="91032-197">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="91032-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91032-198">Nombre</span><span class="sxs-lookup"><span data-stu-id="91032-198">Name</span></span></th>
<th><span data-ttu-id="91032-199">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="91032-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="91032-200">Descripción</span><span class="sxs-lookup"><span data-stu-id="91032-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91032-201"><strong>URI de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="91032-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-202">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-p114">Identificador único de la conferencia. Cuando se hace clic en este elemento, el informe muestra los participantes individuales de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-205"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="91032-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-206">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-207">Dirección SIP del usuario que organizó la conferencia</span><span class="sxs-lookup"><span data-stu-id="91032-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="91032-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-209">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-210">Servidor perimetral usado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-211"><strong>Fecha y hora de inicio</strong></span><span class="sxs-lookup"><span data-stu-id="91032-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-212">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-213">Fecha y hora en que comenzó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-214"><strong>Fecha y hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="91032-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-215">Sí</span><span class="sxs-lookup"><span data-stu-id="91032-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="91032-216">Fecha y hora en que finalizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="91032-217">Métricas de participantes en conferencias individuales</span><span class="sxs-lookup"><span data-stu-id="91032-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="91032-218">En la siguiente tabla se muestra la información proporcionada en el Informe de control de admisión de llamadas sobre participantes en conferencias individuales.</span><span class="sxs-lookup"><span data-stu-id="91032-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="91032-219">Métricas de participantes en conferencias individuales</span><span class="sxs-lookup"><span data-stu-id="91032-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91032-220">Nombre</span><span class="sxs-lookup"><span data-stu-id="91032-220">Name</span></span></th>
<th><span data-ttu-id="91032-221">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="91032-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="91032-222">Descripción</span><span class="sxs-lookup"><span data-stu-id="91032-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91032-223"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="91032-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-224">No</span><span class="sxs-lookup"><span data-stu-id="91032-224">No</span></span></p></td>
<td><p><span data-ttu-id="91032-225">Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-226"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="91032-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-227">No</span><span class="sxs-lookup"><span data-stu-id="91032-227">No</span></span></p></td>
<td><p><span data-ttu-id="91032-228">Dirección SIP del participante de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-229"><strong>Conectividad</strong></span><span class="sxs-lookup"><span data-stu-id="91032-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-230">No</span><span class="sxs-lookup"><span data-stu-id="91032-230">No</span></span></p></td>
<td><p><span data-ttu-id="91032-231">Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</span><span class="sxs-lookup"><span data-stu-id="91032-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-232"><strong>Modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="91032-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-233">No</span><span class="sxs-lookup"><span data-stu-id="91032-233">No</span></span></p></td>
<td><p><span data-ttu-id="91032-234">Tipo de conferencia (por ejemplo, conferencia A/V).</span><span class="sxs-lookup"><span data-stu-id="91032-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-235"><strong>Fecha y hora de conexión</strong></span><span class="sxs-lookup"><span data-stu-id="91032-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-236">No</span><span class="sxs-lookup"><span data-stu-id="91032-236">No</span></span></p></td>
<td><p><span data-ttu-id="91032-237">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91032-238"><strong>Hora de desconexión</strong></span><span class="sxs-lookup"><span data-stu-id="91032-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-239">No</span><span class="sxs-lookup"><span data-stu-id="91032-239">No</span></span></p></td>
<td><p><span data-ttu-id="91032-240">Fecha y hora en que el participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="91032-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91032-241"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="91032-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="91032-242">No</span><span class="sxs-lookup"><span data-stu-id="91032-242">No</span></span></p></td>
<td><p><span data-ttu-id="91032-p115">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="91032-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

