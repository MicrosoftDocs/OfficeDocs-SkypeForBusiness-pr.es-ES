---
title: 'Lync Server 2013: informe de rendimiento del servidor'
description: 'Lync Server 2013: informe de rendimiento del servidor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed9b3b9eeec4487dce4d401df0d70ffba89677b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543346"
---
# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="03f3d-103">Informe de rendimiento del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03f3d-103">Server Performance Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f3d-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="03f3d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="03f3d-105">El informe de rendimiento del servidor proporciona una lista de servidores de Microsoft Lync Server 2013 que han experimentado el mayor porcentaje de llamadas deficientes.</span><span class="sxs-lookup"><span data-stu-id="03f3d-105">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="03f3d-106">El informe desglosa los servidores por tipo de servidor y notifica diferentes estadísticas para los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="03f3d-106">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="03f3d-107">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="03f3d-107">Mediation Server</span></span>

  - <span data-ttu-id="03f3d-108">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="03f3d-108">A/V Conferencing Server</span></span>

  - <span data-ttu-id="03f3d-109">Servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="03f3d-109">A/V Edge Server</span></span>

  - <span data-ttu-id="03f3d-110">Puerta de enlace (servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="03f3d-110">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="03f3d-111">Puerta de enlace (desvío del servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="03f3d-111">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="03f3d-112">Vídeo (incluye métricas de vídeo para servidores de conferencia A/V y servidores perimetrales A/V)</span><span class="sxs-lookup"><span data-stu-id="03f3d-112">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="03f3d-113">Uso compartido de aplicaciones (incluye métricas de uso compartido de aplicaciones para servidores de conferencia A/V y servidores perimetrales A/V)</span><span class="sxs-lookup"><span data-stu-id="03f3d-113">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="03f3d-p102">Es importante recordar que la clasificación mostrada en este informe es una clasificación relativa. Por ejemplo, supongamos que el servidor con el peor rendimiento tuvo una llamada deficiente entre las 1.000 llamadas realizadas. Eso supone un porcentaje más que aceptable del 0,1%. Sin embargo, si es el servidor de peor rendimiento (es decir, todos los demás servidores tienen un porcentaje de llamadas deficientes incluso inferior al 0,1%), aparecerá en el informe de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="03f3d-118">Acceso al informe de rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="03f3d-118">Accessing the Server Performance Report</span></span>

<span data-ttu-id="03f3d-119">El informe de acceso del servidor es accesible desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="03f3d-119">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="03f3d-120">Puede explorar en profundidad el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="03f3d-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="03f3d-121">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="03f3d-121">Call volume</span></span>

  - <span data-ttu-id="03f3d-122">Porcentaje de llamadas deficientes</span><span class="sxs-lookup"><span data-stu-id="03f3d-122">Poor call percentage</span></span>

<span data-ttu-id="03f3d-123">Además, puede navegar hasta el informe de tendencias de calidad de medios del servidor haciendo clic en las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="03f3d-123">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="03f3d-124">Tendencia</span><span class="sxs-lookup"><span data-stu-id="03f3d-124">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="03f3d-125">Optimización del uso del informe de rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="03f3d-125">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="03f3d-p104">El informe de rendimiento del servidor ofrece varias maneras de filtrar los datos; por ejemplo, puede filtrar por tipo de red (llamadas realizadas desde una conexión cableada frente a las llamadas realizadas desde una conexión inalámbrica) y tipo de acceso (llamadas realizadas desde dentro del firewall frente a las llamadas realizadas desde fuera del firewall). Para ver el informe de rendimiento del servidor, es buena idea utilizar estos filtros. Por ejemplo, supongamos que tiene un servidor de mediación con un porcentaje de llamadas deficientes del 3,24%. Si solo consulta las llamadas inalámbricas, el mismo servidor podría tener un porcentaje de llamadas deficientes cercano al 20%. Eso significa que el servidor tenía dificultades con las llamadas inalámbricas, un problema que quedó oculto en parte por que el servidor no tenía problemas con las llamadas cableadas.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="03f3d-131">Filtros</span><span class="sxs-lookup"><span data-stu-id="03f3d-131">Filters</span></span>

<span data-ttu-id="03f3d-p105">Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o para ver los datos devueltos de diversas formas. Por ejemplo, el informe de rendimiento del servidor permite realizar tareas como filtrar los datos devueltos por el tipo de servidor o por el tipo de red (con cable o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="03f3d-136">En la siguiente tabla se muestran los filtros que se pueden usar en el informe de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="03f3d-136">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="03f3d-137">Filtros del informe de rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="03f3d-137">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f3d-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="03f3d-138">Name</span></span></th>
<th><span data-ttu-id="03f3d-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f3d-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p106">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="03f3d-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="03f3d-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03f3d-p107">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03f3d-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="03f3d-146">7/7/2012</span></span></p>
<p><span data-ttu-id="03f3d-147">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="03f3d-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03f3d-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="03f3d-148">7/3/2012</span></span></p>
<p><span data-ttu-id="03f3d-149">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="03f3d-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p108">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="03f3d-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="03f3d-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03f3d-p109">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03f3d-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="03f3d-156">7/7/2012</span></span></p>
<p><span data-ttu-id="03f3d-157">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="03f3d-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03f3d-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="03f3d-158">7/3/2012</span></span></p>
<p><span data-ttu-id="03f3d-159">El orden de las semanas siempre es de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="03f3d-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-160"><strong>Tipo de servidor</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-160"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p110">Indica el tipo de servidor cuyo rendimiento debe notificarse. Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="03f3d-163">Todos</span><span class="sxs-lookup"><span data-stu-id="03f3d-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="03f3d-164">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="03f3d-164">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="03f3d-165">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="03f3d-165">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="03f3d-166">Servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="03f3d-166">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-167"><strong>Superior N</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-167"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p111">Indica el número de servidores (en función de su escaso porcentaje de llamadas) que se va a mostrar en cada categoría. Por ejemplo, si selecciona <strong>5</strong>, aparecerán los cinco servidores con peor rendimiento. Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="03f3d-171">Todos</span><span class="sxs-lookup"><span data-stu-id="03f3d-171">[All]</span></span></p></li>
<li><p><span data-ttu-id="03f3d-172">5 </span><span class="sxs-lookup"><span data-stu-id="03f3d-172">5</span></span></p></li>
<li><p><span data-ttu-id="03f3d-173">10  </span><span class="sxs-lookup"><span data-stu-id="03f3d-173">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-174"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-174"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p112">Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="03f3d-177">Todos</span><span class="sxs-lookup"><span data-stu-id="03f3d-177">[All]</span></span></p></li>
<li><p><span data-ttu-id="03f3d-178">Interno</span><span class="sxs-lookup"><span data-stu-id="03f3d-178">Internal</span></span></p></li>
<li><p><span data-ttu-id="03f3d-179">Externo</span><span class="sxs-lookup"><span data-stu-id="03f3d-179">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-180"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-180"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p113">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="03f3d-183">Todos</span><span class="sxs-lookup"><span data-stu-id="03f3d-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="03f3d-184">Cableada</span><span class="sxs-lookup"><span data-stu-id="03f3d-184">Wired</span></span></p></li>
<li><p><span data-ttu-id="03f3d-185">Wireless</span><span class="sxs-lookup"><span data-stu-id="03f3d-185">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-186"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-186"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-p114">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="03f3d-189">Todos</span><span class="sxs-lookup"><span data-stu-id="03f3d-189">[All]</span></span></p></li>
<li><p><span data-ttu-id="03f3d-190">VPN</span><span class="sxs-lookup"><span data-stu-id="03f3d-190">VPN</span></span></p></li>
<li><p><span data-ttu-id="03f3d-191">No VPN</span><span class="sxs-lookup"><span data-stu-id="03f3d-191">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="03f3d-192">Métricas</span><span class="sxs-lookup"><span data-stu-id="03f3d-192">Metrics</span></span>

<span data-ttu-id="03f3d-193">En la tabla siguiente se muestra la información que recoge el informe de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="03f3d-193">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="03f3d-194">Métricas del informe de rendimiento del servidor: resumen de llamadas de audio</span><span class="sxs-lookup"><span data-stu-id="03f3d-194">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f3d-195">Nombre</span><span class="sxs-lookup"><span data-stu-id="03f3d-195">Name</span></span></th>
<th><span data-ttu-id="03f3d-196">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="03f3d-196">Can Sort On</span></span></th>
<th><span data-ttu-id="03f3d-197">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f3d-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-198"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-198"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-199">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-199">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-200">Nombre/dirección IP del servidor.</span><span class="sxs-lookup"><span data-stu-id="03f3d-200">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-201"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-201"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-202">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-202">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-203">Número total de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="03f3d-203">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-204"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-204"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-205">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-205">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p115">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la que al menos uno de los valores medidos supera el valor permitido, por ejemplo, una llamada con un exceso de vibraciones.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-208"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-208"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-209">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p116">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y, después, vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="03f3d-p117">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-214"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-214"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-215">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-216">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="03f3d-216">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="03f3d-217">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="03f3d-217">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="03f3d-218">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="03f3d-218">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="03f3d-219">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="03f3d-219">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="03f3d-220">En Lync Server, el servidor de supervisión usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="03f3d-220">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="03f3d-p119">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-223"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-223"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-224">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p120">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-228"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-228"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-229">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-230">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="03f3d-230">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="03f3d-231">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="03f3d-231">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-232"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-232"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-233">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p122">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-236"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-236"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-237">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p123">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-240"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-240"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-241">Sí</span><span class="sxs-lookup"><span data-stu-id="03f3d-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p124">Tasa media de muestras de audio comprimidas respecto al número total de muestras (el audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red). Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="03f3d-244">Métricas del informe de rendimiento del servidor: resumen de llamadas de vídeo</span><span class="sxs-lookup"><span data-stu-id="03f3d-244">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f3d-245">Nombre</span><span class="sxs-lookup"><span data-stu-id="03f3d-245">Name</span></span></th>
<th><span data-ttu-id="03f3d-246">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="03f3d-246">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03f3d-247">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f3d-247">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-248"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-248"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-249">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-249">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p125">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="03f3d-252">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="03f3d-252">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="03f3d-253">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="03f3d-253">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03f3d-254">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="03f3d-254">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03f3d-255">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="03f3d-255">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="03f3d-256">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="03f3d-256">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="03f3d-257">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="03f3d-257">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="03f3d-258">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="03f3d-258">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-259"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-259"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-260">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-260">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-261">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="03f3d-261">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-262"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-262"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-263">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-263">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p126">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="03f3d-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-266"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-266"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-267">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-267">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-268">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="03f3d-268">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-269"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-269"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-270">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-270">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-271">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="03f3d-271">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-272"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-272"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-273">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-273">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-274">Número de llamadas que han empleado una conexión externa (es decir, una conexión fuera de la red interna).</span><span class="sxs-lookup"><span data-stu-id="03f3d-274">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-275"><strong>Velocidad de bits media (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-275"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-276">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-276">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-277">Velocidad de bits de vídeo media (en kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="03f3d-277">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-278"><strong>Porcentaje de velocidad de bits baja</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-278"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-279">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-279">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-280">Porcentaje de la llamada durante el cual la velocidad de bits era baja.</span><span class="sxs-lookup"><span data-stu-id="03f3d-280">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-281"><strong>Pérdida de paquetes salientes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-281"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-282">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-282">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p127">Pérdida de paquetes de salida del Protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes de RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Las altas tasas de pérdidas suelen estar causadas por congestión, falta de ancho de banda, congestión inalámbrica o interferencias, o un servidor de medios sobrecargado. La pérdida de paquetes suele producir distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-286"><strong>$$$% fotogramas congelados</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-286"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-287">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-287">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p128">Porcentaje de fotogramas "inmovilizados". En un fotograma inmovilizado, el vídeo deja de avanzar mientras la parte de audio de la llamada continúa.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-290"><strong>Velocidad media de fotogramas salientes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-290"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-291">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-291">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-292">Velocidad media de los fotogramas en las transmisiones salientes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="03f3d-292">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-293"><strong>Velocidad media de fotogramas entrantes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-293"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-294">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-294">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-295">Velocidad media de los fotogramas en las transmisiones entrantes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="03f3d-295">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-296"><strong>Porcentaje de velocidad de fotogramas entrantes lenta</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-296"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-297">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-297">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-298">Porcentaje de la llamada durante el cual la velocidad de bits del vídeo entrante era baja.</span><span class="sxs-lookup"><span data-stu-id="03f3d-298">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-299"><strong>Porcentaje de estado del cliente</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-299"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03f3d-300">Indica el estado relativo del dispositivo cliente durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="03f3d-300">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="03f3d-301">Métricas del informe de rendimiento del servidor: resumen de llamadas de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="03f3d-301">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f3d-302">Nombre</span><span class="sxs-lookup"><span data-stu-id="03f3d-302">Name</span></span></th>
<th><span data-ttu-id="03f3d-303">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="03f3d-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03f3d-304">Descripción</span><span class="sxs-lookup"><span data-stu-id="03f3d-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-305"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-305"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-306">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-306">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p129">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="03f3d-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="03f3d-309">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="03f3d-309">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="03f3d-310">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="03f3d-310">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03f3d-311">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="03f3d-311">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03f3d-312">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="03f3d-312">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="03f3d-313">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="03f3d-313">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="03f3d-314">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="03f3d-314">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="03f3d-315">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="03f3d-315">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-316"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-316"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-317">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-317">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-318">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="03f3d-318">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-319"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-319"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-320">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-320">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p130">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="03f3d-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-323"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-323"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-324">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-324">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-325">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="03f3d-325">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-326"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-326"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-327">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-327">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-328">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="03f3d-328">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-329"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-329"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-330">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-330">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-331">Número de llamadas que han empleado una conexión externa (es decir, una conexión fuera de la red interna).</span><span class="sxs-lookup"><span data-stu-id="03f3d-331">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-332"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-332"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-333">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-333">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-334">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="03f3d-334">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="03f3d-335">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="03f3d-335">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-336"><strong>Unidireccional relativo medio</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-336"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-337">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-337">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p132">Retraso unidireccional relativo medio entre dos extremos de medios. Se trata de una medida de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f3d-340"><strong>Latencia media de procesamiento de mosaicos de RDP</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-340"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-341">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-341">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-p133">La latencia media de procesamiento de mosaicos de RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización. Esta métrica no incluye la latencia de red. Si la media es alta, refleja un retraso mayor en la visualización. Cuando el servidor de conferencias está sobrecargado, el retraso medio puede ser mayor.</span><span class="sxs-lookup"><span data-stu-id="03f3d-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f3d-346"><strong>Porcentaje total de mosaicos estropeados</strong></span><span class="sxs-lookup"><span data-stu-id="03f3d-346"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="03f3d-347">No</span><span class="sxs-lookup"><span data-stu-id="03f3d-347">No</span></span></p></td>
<td><p><span data-ttu-id="03f3d-348">Porcentaje total de mosaicos de RDP estropeados.</span><span class="sxs-lookup"><span data-stu-id="03f3d-348">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

