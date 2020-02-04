---
title: 'Lync Server 2013: informe de tendencias de calidad de Media Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4efb7e2f29c1da75a81f4df4ec586c396d77d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="78eac-102">Informe de tendencias de calidad de Media Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78eac-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78eac-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="78eac-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="78eac-104">El informe de tendencias de calidad de Media Server proporciona una forma de comparar de forma gráfica hasta 5 servidores en métricas de la calidad de la experiencia, como el volumen de las llamadas, el porcentaje de llamada deficiente, la pérdida de paquetes y la vibración.</span><span class="sxs-lookup"><span data-stu-id="78eac-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="78eac-105">De este modo, resulta fácil llevar a cabo ciertas tareas, como identificar los servidores cuyo funcionamiento es deficiente, los que no se aprovechan bastante o los que se utilizan demasiado.</span><span class="sxs-lookup"><span data-stu-id="78eac-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="78eac-106">Acceso al Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="78eac-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="78eac-107">Se puede obtener acceso al Informe de tendencias de calidad de medios de servidores desde uno de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="78eac-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="78eac-108">[Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (al hacer clic en la métrica de tendencia)</span><span class="sxs-lookup"><span data-stu-id="78eac-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="78eac-109">[Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) (haciendo clic en la métrica del servidor perimetral a/V).</span><span class="sxs-lookup"><span data-stu-id="78eac-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="78eac-110">Si el autor o el destinatario de la llamada es un servidor, también puede obtener acceso al Informe de tendencias de calidad de medios de servidores haciendo clic en el nombre del extremo).</span><span class="sxs-lookup"><span data-stu-id="78eac-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="78eac-111">Uso óptimo del Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="78eac-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="78eac-112">Al hacer clic en la métrica de tendencia en el [Informe rendimiento del servidor de Lync server 2013](lync-server-2013-server-performance-report.md) para un servidor específico, se abrirá el informe tendencia de calidad multimedia de servidor.</span><span class="sxs-lookup"><span data-stu-id="78eac-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="78eac-113">Pero, solamente verá una instancia vacía de ese informe; el servidor que seleccionó en el Informe de rendimiento del servidor no se mostrará en pantalla.</span><span class="sxs-lookup"><span data-stu-id="78eac-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="78eac-114">Por el contrario, tendrá que seleccionar ese servidor en la lista desplegable Servidores.</span><span class="sxs-lookup"><span data-stu-id="78eac-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="78eac-115">Observe, también, que la lista desplegable Servidores contiene la opción Seleccionar todo.</span><span class="sxs-lookup"><span data-stu-id="78eac-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="78eac-116">Esta opción no funciona si tiene más de 5 servidores; el Informe de tendencias de calidad de medios de servidores solo puede mostrar datos de 5 servidores al mismo tiempo, como máximo.</span><span class="sxs-lookup"><span data-stu-id="78eac-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="78eac-117">En los gráficos que muestra el informe de tendencias de calidad de Media Server, se hotlinksn los puntos con la etiqueta llamada de volumen y bajo porcentaje de llamada. al hacer clic en un punto del gráfico, se abrirá una instancia del informe de la [lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) , que muestra las llamadas totales (o llamadas deficientes) durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="78eac-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="78eac-118">Filtros</span><span class="sxs-lookup"><span data-stu-id="78eac-118">Filters</span></span>

<span data-ttu-id="78eac-p104">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Informe de tendencias de calidad de medios de servidores.</span><span class="sxs-lookup"><span data-stu-id="78eac-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="78eac-121">Filtros del Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="78eac-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78eac-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="78eac-122">Name</span></span></th>
<th><span data-ttu-id="78eac-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="78eac-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78eac-124"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p105">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="78eac-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="78eac-127">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="78eac-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="78eac-p106">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="78eac-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="78eac-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="78eac-130">7/7/2012</span></span></p>
<p><span data-ttu-id="78eac-131">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="78eac-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="78eac-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="78eac-132">7/3/2012</span></span></p>
<p><span data-ttu-id="78eac-133">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="78eac-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-134"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p107">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="78eac-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="78eac-137">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="78eac-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="78eac-p108">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="78eac-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="78eac-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="78eac-140">7/7/2012</span></span></p>
<p><span data-ttu-id="78eac-141">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="78eac-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="78eac-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="78eac-142">7/3/2012</span></span></p>
<p><span data-ttu-id="78eac-143">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="78eac-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-144"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p109">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="78eac-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="78eac-147">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="78eac-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="78eac-148">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="78eac-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="78eac-149">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="78eac-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="78eac-150">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="78eac-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="78eac-151">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 8/7/2012 y una fecha de finalización de 9/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="78eac-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-152"><strong>Tipo de servidor</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p111">Tipo de servidor que se usa en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="78eac-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="78eac-155">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="78eac-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="78eac-156">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="78eac-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="78eac-157">Servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="78eac-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="78eac-158">Puerta de enlace (servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="78eac-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="78eac-159">Puerta de enlace (desvío del servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="78eac-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="78eac-160">Servidor de conferencias AS</span><span class="sxs-lookup"><span data-stu-id="78eac-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-161"><strong>Servidores</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p112">Nombre del servidor que se usa en la sesión; esta lista desplegable se rellena automáticamente según el valor del filtro Tipo de servidor. Puede seleccionar hasta 5 servidores diferentes al compilar un informe.</span><span class="sxs-lookup"><span data-stu-id="78eac-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-164"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p113">Indica si el participante tenía la sesión iniciada en la red interna o en la red externa. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="78eac-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="78eac-167">[Todas]</span><span class="sxs-lookup"><span data-stu-id="78eac-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="78eac-168">Interno</span><span class="sxs-lookup"><span data-stu-id="78eac-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="78eac-169">Externo</span><span class="sxs-lookup"><span data-stu-id="78eac-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-170"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p114">Indica el tipo de red al que estaba conectado el participante. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="78eac-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="78eac-173">[Todas]</span><span class="sxs-lookup"><span data-stu-id="78eac-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="78eac-174">Cableada</span><span class="sxs-lookup"><span data-stu-id="78eac-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="78eac-175">Inalámbrica</span><span class="sxs-lookup"><span data-stu-id="78eac-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-p115">Indica si un participante externo estaba usando una conexión de red privada virtual (VPN) durante la sesión. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="78eac-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="78eac-179">[Todas]</span><span class="sxs-lookup"><span data-stu-id="78eac-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="78eac-180">VPN</span><span class="sxs-lookup"><span data-stu-id="78eac-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="78eac-181">Distinto de VPN</span><span class="sxs-lookup"><span data-stu-id="78eac-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="78eac-182">Métricas</span><span class="sxs-lookup"><span data-stu-id="78eac-182">Metrics</span></span>

<span data-ttu-id="78eac-183">En la tabla siguiente se muestra la información que recoge el Informe de tendencias de calidad de medios de servidores.</span><span class="sxs-lookup"><span data-stu-id="78eac-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="78eac-184">Métricas del Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="78eac-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78eac-185">Nombre</span><span class="sxs-lookup"><span data-stu-id="78eac-185">Name</span></span></th>
<th><span data-ttu-id="78eac-186">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="78eac-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="78eac-187">Descripción</span><span class="sxs-lookup"><span data-stu-id="78eac-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78eac-188"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-189">No</span><span class="sxs-lookup"><span data-stu-id="78eac-189">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-190">Cantidad total de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78eac-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-191"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-192">No</span><span class="sxs-lookup"><span data-stu-id="78eac-192">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-193">Cantidad promedio de la degradación de OP (puntuación de opción media) experimentada durante una llamada.</span><span class="sxs-lookup"><span data-stu-id="78eac-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="78eac-194">Los valores de degradación pueden oscilar entre un mínimo de 0,0 y un alto de 5,0. un valor de 0,5 o menos representa una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="78eac-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="78eac-195">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="78eac-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="78eac-196">Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</span><span class="sxs-lookup"><span data-stu-id="78eac-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="78eac-p117">Los valores elevados de degradación pueden ser producto de la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un extremo o servidor multimedia. Una degradación elevada causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="78eac-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-199"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-200">No</span><span class="sxs-lookup"><span data-stu-id="78eac-200">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-p118">Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="78eac-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-203"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-204">No</span><span class="sxs-lookup"><span data-stu-id="78eac-204">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-p119">Tiempo medio (en milisegundos) necesario para que un paquete de Protocolo de transporte en tiempo real (RTP) llegue a un extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="78eac-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="78eac-p120">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="78eac-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-209"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-210">No</span><span class="sxs-lookup"><span data-stu-id="78eac-210">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-p121">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="78eac-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-214"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-215">No</span><span class="sxs-lookup"><span data-stu-id="78eac-215">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-216">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="78eac-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="78eac-217">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="78eac-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-218"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-219">No</span><span class="sxs-lookup"><span data-stu-id="78eac-219">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-p123">Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="78eac-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78eac-222"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-223">No</span><span class="sxs-lookup"><span data-stu-id="78eac-223">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-p124">Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="78eac-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78eac-226"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="78eac-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="78eac-227">No</span><span class="sxs-lookup"><span data-stu-id="78eac-227">No</span></span></p></td>
<td><p><span data-ttu-id="78eac-p125">Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="78eac-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

