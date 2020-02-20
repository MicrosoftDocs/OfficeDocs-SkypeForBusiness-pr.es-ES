---
title: 'Lync Server 2013: informe de rendimiento del servidor'
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
ms.openlocfilehash: 05c1e366c797eb0c626d00744ef6f0088d28e465
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="66ca0-102">Informe de rendimiento del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66ca0-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66ca0-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="66ca0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="66ca0-104">El informe de rendimiento del servidor proporciona una lista de servidores de Microsoft Lync Server 2013 que han experimentado el mayor porcentaje de llamadas deficientes.</span><span class="sxs-lookup"><span data-stu-id="66ca0-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="66ca0-105">El informe desglosa los servidores por tipo de servidor y notifica diferentes estadísticas para los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="66ca0-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="66ca0-106">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="66ca0-106">Mediation Server</span></span>

  - <span data-ttu-id="66ca0-107">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="66ca0-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="66ca0-108">Servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="66ca0-108">A/V Edge Server</span></span>

  - <span data-ttu-id="66ca0-109">Puerta de enlace (servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="66ca0-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="66ca0-110">Puerta de enlace (desvío del servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="66ca0-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="66ca0-111">Vídeo (incluye métricas de vídeo para servidores de conferencia A/V y servidores perimetrales A/V)</span><span class="sxs-lookup"><span data-stu-id="66ca0-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="66ca0-112">Uso compartido de aplicaciones (incluye métricas de uso compartido de aplicaciones para servidores de conferencia A/V y servidores perimetrales A/V)</span><span class="sxs-lookup"><span data-stu-id="66ca0-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="66ca0-p102">Es importante recordar que la clasificación mostrada en este informe es una clasificación relativa. Por ejemplo, supongamos que el servidor con el peor rendimiento tuvo una llamada deficiente entre las 1.000 llamadas realizadas. Eso supone un porcentaje más que aceptable del 0,1%. Sin embargo, si es el servidor de peor rendimiento (es decir, todos los demás servidores tienen un porcentaje de llamadas deficientes incluso inferior al 0,1%), aparecerá en el informe de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="66ca0-117">Acceso al informe de rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="66ca0-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="66ca0-118">El informe de acceso del servidor es accesible desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="66ca0-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="66ca0-119">Puede explorar en profundidad el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="66ca0-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="66ca0-120">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="66ca0-120">Call volume</span></span>

  - <span data-ttu-id="66ca0-121">Porcentaje de llamadas deficientes</span><span class="sxs-lookup"><span data-stu-id="66ca0-121">Poor call percentage</span></span>

<span data-ttu-id="66ca0-122">Además, puede navegar hasta el informe de tendencias de calidad de medios del servidor haciendo clic en las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="66ca0-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="66ca0-123">Tendencia</span><span class="sxs-lookup"><span data-stu-id="66ca0-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="66ca0-124">Optimización del uso del informe de rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="66ca0-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="66ca0-p104">El informe de rendimiento del servidor ofrece varias maneras de filtrar los datos; por ejemplo, puede filtrar por tipo de red (llamadas realizadas desde una conexión cableada frente a las llamadas realizadas desde una conexión inalámbrica) y tipo de acceso (llamadas realizadas desde dentro del firewall frente a las llamadas realizadas desde fuera del firewall). Para ver el informe de rendimiento del servidor, es buena idea utilizar estos filtros. Por ejemplo, supongamos que tiene un servidor de mediación con un porcentaje de llamadas deficientes del 3,24%. Si solo consulta las llamadas inalámbricas, el mismo servidor podría tener un porcentaje de llamadas deficientes cercano al 20%. Eso significa que el servidor tenía dificultades con las llamadas inalámbricas, un problema que quedó oculto en parte por que el servidor no tenía problemas con las llamadas cableadas.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="66ca0-130">Filtros</span><span class="sxs-lookup"><span data-stu-id="66ca0-130">Filters</span></span>

<span data-ttu-id="66ca0-p105">Los filtros constituyen un modo de obtener un conjunto de datos más acorde con lo que se busca o para ver los datos devueltos de diversas formas. Por ejemplo, el informe de rendimiento del servidor permite realizar tareas como filtrar los datos devueltos por el tipo de servidor o por el tipo de red (con cable o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="66ca0-135">En la siguiente tabla se muestran los filtros que se pueden usar en el informe de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="66ca0-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="66ca0-136">Filtros del informe de rendimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="66ca0-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66ca0-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="66ca0-137">Name</span></span></th>
<th><span data-ttu-id="66ca0-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ca0-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p106">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="66ca0-142">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="66ca0-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="66ca0-p107">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="66ca0-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="66ca0-145">7/7/2012</span></span></p>
<p><span data-ttu-id="66ca0-146">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="66ca0-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="66ca0-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="66ca0-147">7/3/2012</span></span></p>
<p><span data-ttu-id="66ca0-148">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="66ca0-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p108">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="66ca0-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="66ca0-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="66ca0-p109">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="66ca0-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="66ca0-155">7/7/2012</span></span></p>
<p><span data-ttu-id="66ca0-156">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="66ca0-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="66ca0-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="66ca0-157">7/3/2012</span></span></p>
<p><span data-ttu-id="66ca0-158">El orden de las semanas siempre es de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="66ca0-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-159"><strong>Tipo de servidor</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p110">Indica el tipo de servidor cuyo rendimiento debe notificarse. Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="66ca0-162">Todos</span><span class="sxs-lookup"><span data-stu-id="66ca0-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="66ca0-163">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="66ca0-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="66ca0-164">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="66ca0-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="66ca0-165">Servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="66ca0-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-166"><strong>Superior N</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p111">Indica el número de servidores (en función de su escaso porcentaje de llamadas) que se va a mostrar en cada categoría. Por ejemplo, si selecciona <strong>5</strong>, aparecerán los cinco servidores con peor rendimiento. Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="66ca0-170">Todos</span><span class="sxs-lookup"><span data-stu-id="66ca0-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="66ca0-171">2,5</span><span class="sxs-lookup"><span data-stu-id="66ca0-171">5</span></span></p></li>
<li><p><span data-ttu-id="66ca0-172">10 </span><span class="sxs-lookup"><span data-stu-id="66ca0-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-173"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p112">Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="66ca0-176">Todos</span><span class="sxs-lookup"><span data-stu-id="66ca0-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="66ca0-177">Interno</span><span class="sxs-lookup"><span data-stu-id="66ca0-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="66ca0-178">External</span><span class="sxs-lookup"><span data-stu-id="66ca0-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-179"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p113">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="66ca0-182">Todos</span><span class="sxs-lookup"><span data-stu-id="66ca0-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="66ca0-183">Cableada</span><span class="sxs-lookup"><span data-stu-id="66ca0-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="66ca0-184">Wireless</span><span class="sxs-lookup"><span data-stu-id="66ca0-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-p114">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="66ca0-188">Todos</span><span class="sxs-lookup"><span data-stu-id="66ca0-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="66ca0-189">VPN</span><span class="sxs-lookup"><span data-stu-id="66ca0-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="66ca0-190">No VPN</span><span class="sxs-lookup"><span data-stu-id="66ca0-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="66ca0-191">Métricas</span><span class="sxs-lookup"><span data-stu-id="66ca0-191">Metrics</span></span>

<span data-ttu-id="66ca0-192">En la tabla siguiente se muestra la información que recoge el informe de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="66ca0-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="66ca0-193">Métricas del informe de rendimiento del servidor: resumen de llamadas de audio</span><span class="sxs-lookup"><span data-stu-id="66ca0-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66ca0-194">Nombre</span><span class="sxs-lookup"><span data-stu-id="66ca0-194">Name</span></span></th>
<th><span data-ttu-id="66ca0-195">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="66ca0-195">Can Sort On</span></span></th>
<th><span data-ttu-id="66ca0-196">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ca0-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-197"><strong>Servidor</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-198">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-198">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-199">Nombre/dirección IP del servidor.</span><span class="sxs-lookup"><span data-stu-id="66ca0-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-200"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-201">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-201">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-202">Número total de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="66ca0-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-203"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-204">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-204">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p115">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="66ca0-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-207"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-208">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p116">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y, después, vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="66ca0-p117">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-213"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-214">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-215">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66ca0-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="66ca0-216">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="66ca0-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="66ca0-217">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="66ca0-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="66ca0-218">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="66ca0-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="66ca0-219">En Lync Server, el servidor de supervisión usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="66ca0-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="66ca0-p119">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-222"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-223">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p120">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-227"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-228">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-229">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="66ca0-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="66ca0-230">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="66ca0-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-231"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-232">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p122">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-235"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-236">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p123">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-239"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-240">Sí</span><span class="sxs-lookup"><span data-stu-id="66ca0-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p124">Tasa media de muestras de audio comprimidas respecto al número total de muestras (el audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red). Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="66ca0-243">Métricas del informe de rendimiento del servidor: resumen de llamadas de vídeo</span><span class="sxs-lookup"><span data-stu-id="66ca0-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66ca0-244">Nombre</span><span class="sxs-lookup"><span data-stu-id="66ca0-244">Name</span></span></th>
<th><span data-ttu-id="66ca0-245">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="66ca0-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="66ca0-246">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ca0-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-247"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-248">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-248">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p125">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="66ca0-251">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="66ca0-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="66ca0-252">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="66ca0-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="66ca0-253">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="66ca0-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="66ca0-254">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="66ca0-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="66ca0-255">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="66ca0-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="66ca0-256">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="66ca0-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="66ca0-257">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="66ca0-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-258"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-259">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-259">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-260">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="66ca0-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-261"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-262">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-262">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p126">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="66ca0-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-265"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-266">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-266">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-267">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="66ca0-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-268"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-269">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-269">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-270">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="66ca0-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-271"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-272">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-272">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-273">Número de llamadas que han empleado una conexión externa (es decir, una conexión fuera de la red interna).</span><span class="sxs-lookup"><span data-stu-id="66ca0-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-274"><strong>Velocidad de bits media (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-275">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-275">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-276">Velocidad de bits de vídeo media (en kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="66ca0-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-277"><strong>Porcentaje de velocidad de bits baja</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-278">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-278">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-279">Porcentaje de la llamada durante el cual la velocidad de bits era baja.</span><span class="sxs-lookup"><span data-stu-id="66ca0-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-280"><strong>Pérdida de paquetes salientes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-281">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-281">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p127">Pérdida de paquetes de salida del Protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes de RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Las altas tasas de pérdidas suelen estar causadas por congestión, falta de ancho de banda, congestión inalámbrica o interferencias, o un servidor de medios sobrecargado. La pérdida de paquetes suele producir distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-285"><strong>$$$% fotogramas congelados</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-286">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-286">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p128">Porcentaje de fotogramas "inmovilizados". En un fotograma inmovilizado, el vídeo deja de avanzar mientras la parte de audio de la llamada continúa.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-289"><strong>Velocidad media de fotogramas salientes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-290">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-290">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-291">Velocidad media de los fotogramas en las transmisiones salientes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66ca0-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-292"><strong>Velocidad media de fotogramas entrantes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-293">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-293">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-294">Velocidad media de los fotogramas en las transmisiones entrantes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66ca0-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-295"><strong>Porcentaje de velocidad de fotogramas entrantes lenta</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-296">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-296">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-297">Porcentaje de la llamada durante el cual la velocidad de bits del vídeo entrante era baja.</span><span class="sxs-lookup"><span data-stu-id="66ca0-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-298"><strong>Porcentaje de estado del cliente</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66ca0-299">Indica el estado relativo del dispositivo cliente durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66ca0-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="66ca0-300">Métricas del informe de rendimiento del servidor: resumen de llamadas de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="66ca0-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66ca0-301">Nombre</span><span class="sxs-lookup"><span data-stu-id="66ca0-301">Name</span></span></th>
<th><span data-ttu-id="66ca0-302">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="66ca0-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="66ca0-303">Descripción</span><span class="sxs-lookup"><span data-stu-id="66ca0-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-304"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-305">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-305">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p129">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="66ca0-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="66ca0-308">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="66ca0-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="66ca0-309">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="66ca0-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="66ca0-310">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="66ca0-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="66ca0-311">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="66ca0-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="66ca0-312">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="66ca0-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="66ca0-313">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="66ca0-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="66ca0-314">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="66ca0-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-315"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-316">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-316">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-317">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="66ca0-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-318"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-319">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-319">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p130">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="66ca0-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-322"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-323">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-323">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-324">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="66ca0-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-325"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-326">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-326">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-327">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="66ca0-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-328"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-329">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-329">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-330">Número de llamadas que han empleado una conexión externa (es decir, una conexión fuera de la red interna).</span><span class="sxs-lookup"><span data-stu-id="66ca0-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-331"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-332">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-332">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-333">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="66ca0-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="66ca0-334">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="66ca0-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-335"><strong>Unidireccional relativo medio</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-336">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-336">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p132">Retraso unidireccional relativo medio entre dos extremos de medios. Se trata de una medida de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66ca0-339"><strong>Latencia media de procesamiento de mosaicos de RDP</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-340">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-340">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-p133">La latencia media de procesamiento de mosaicos de RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización. Esta métrica no incluye la latencia de red. Si la media es alta, refleja un retraso mayor en la visualización. Cuando el servidor de conferencias está sobrecargado, el retraso medio puede ser mayor.</span><span class="sxs-lookup"><span data-stu-id="66ca0-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66ca0-345"><strong>Porcentaje total de mosaicos estropeados</strong></span><span class="sxs-lookup"><span data-stu-id="66ca0-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="66ca0-346">No</span><span class="sxs-lookup"><span data-stu-id="66ca0-346">No</span></span></p></td>
<td><p><span data-ttu-id="66ca0-347">Porcentaje total de mosaicos de RDP estropeados.</span><span class="sxs-lookup"><span data-stu-id="66ca0-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

