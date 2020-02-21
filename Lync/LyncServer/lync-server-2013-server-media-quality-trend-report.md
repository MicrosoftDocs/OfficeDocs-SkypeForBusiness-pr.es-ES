---
title: 'Lync Server 2013: informe de tendencias de calidad de medios de servidor'
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
ms.openlocfilehash: 35e7e0f3cfe38a7a1c4802eca16c37a62013cecb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="a7adf-102">Informe de tendencias de calidad de medios de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7adf-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7adf-103">_**Última modificación del tema:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="a7adf-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="a7adf-p101">El Informe de tendencias de calidad de medios de servidores permite comparar de forma gráfica hasta 5 servidores según diversas métricas de Calidad de la experiencia, como volumen de llamadas, porcentaje de llamadas deficientes, pérdida de paquetes y vibración. De este modo, resulta fácil llevar a cabo ciertas tareas, como identificar los servidores cuyo funcionamiento es deficiente, los que no se aprovechan bastante o los que se utilizan demasiado.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="a7adf-106">Acceso al Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="a7adf-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="a7adf-107">Se puede obtener acceso al Informe de tendencias de calidad de medios de servidores desde uno de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="a7adf-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="a7adf-108">[Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en la métrica tendencia)</span><span class="sxs-lookup"><span data-stu-id="a7adf-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="a7adf-109">[Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) (haciendo clic en la métrica del servidor perimetral a/V.</span><span class="sxs-lookup"><span data-stu-id="a7adf-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="a7adf-110">Si el autor o el destinatario de la llamada es un servidor, también puede obtener acceso al Informe de tendencias de calidad de medios de servidores haciendo clic en el nombre del extremo.)</span><span class="sxs-lookup"><span data-stu-id="a7adf-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="a7adf-111">Uso óptimo del Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="a7adf-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="a7adf-112">Al hacer clic en la métrica tendencia del [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) para un servidor específico, se abrirá el informe de tendencias de calidad de medios del servidor.</span><span class="sxs-lookup"><span data-stu-id="a7adf-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="a7adf-113">Sin embargo, solamente verá una instancia vacía de ese informe; el servidor que seleccionó en el Informe de rendimiento del servidor no se mostrará en pantalla.</span><span class="sxs-lookup"><span data-stu-id="a7adf-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="a7adf-114">Por el contrario, tendrá que seleccionar ese servidor en la lista desplegable Servidores.</span><span class="sxs-lookup"><span data-stu-id="a7adf-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="a7adf-115">Observe, también, que la lista desplegable Servidores contiene la opción Seleccionar todo.</span><span class="sxs-lookup"><span data-stu-id="a7adf-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="a7adf-116">Esta opción no funciona si tiene más de 5 servidores; el Informe de tendencias de calidad de medios de servidores solo puede mostrar datos de 5 servidores al mismo tiempo, como máximo.</span><span class="sxs-lookup"><span data-stu-id="a7adf-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="a7adf-117">En los gráficos mostrados por el informe de tendencias de calidad de medios de servidor, los puntos con la etiqueta llamada volumen y porcentaje de llamada deficiente son hotlinks; al hacer clic en un punto del gráfico, se abrirá una instancia del [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) que muestra el total de llamadas (o llamadas deficientes) durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="a7adf-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a7adf-118">Filtros</span><span class="sxs-lookup"><span data-stu-id="a7adf-118">Filters</span></span>

<span data-ttu-id="a7adf-p104">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Informe de tendencias de calidad de medios de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="a7adf-121">Filtros del Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="a7adf-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7adf-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7adf-122">Name</span></span></th>
<th><span data-ttu-id="a7adf-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7adf-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p105">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a7adf-127">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="a7adf-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a7adf-p106">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a7adf-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a7adf-130">7/7/2012</span></span></p>
<p><span data-ttu-id="a7adf-131">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="a7adf-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a7adf-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a7adf-132">7/3/2012</span></span></p>
<p><span data-ttu-id="a7adf-133">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="a7adf-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p107">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a7adf-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a7adf-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a7adf-p108">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a7adf-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a7adf-140">7/7/2012</span></span></p>
<p><span data-ttu-id="a7adf-141">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="a7adf-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a7adf-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a7adf-142">7/3/2012</span></span></p>
<p><span data-ttu-id="a7adf-143">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="a7adf-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-144"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p109">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7adf-147">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="a7adf-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a7adf-148">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="a7adf-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a7adf-149">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="a7adf-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a7adf-p110">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando por la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, los datos de 31 días en total).</span><span class="sxs-lookup"><span data-stu-id="a7adf-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-152"><strong>Tipo de servidor</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p111">Tipo de servidor que se usa en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7adf-155">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="a7adf-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="a7adf-156">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="a7adf-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="a7adf-157">Servidor perimetral A/V</span><span class="sxs-lookup"><span data-stu-id="a7adf-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="a7adf-158">Puerta de enlace (servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="a7adf-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="a7adf-159">Puerta de enlace (desvío de servidor de mediación)</span><span class="sxs-lookup"><span data-stu-id="a7adf-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="a7adf-160">Servidor de conferencias AS</span><span class="sxs-lookup"><span data-stu-id="a7adf-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-161"><strong>Servidores</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p112">Nombre del servidor que se usa en la sesión; esta lista desplegable se rellena automáticamente según el valor del filtro Tipo de servidor. Puede seleccionar hasta 5 servidores diferentes al compilar un informe.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-164"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p113">Indica si el participante tenía la sesión iniciada en la red interna o en la red externa. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7adf-167">Todos</span><span class="sxs-lookup"><span data-stu-id="a7adf-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7adf-168">Interno</span><span class="sxs-lookup"><span data-stu-id="a7adf-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="a7adf-169">External</span><span class="sxs-lookup"><span data-stu-id="a7adf-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-170"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p114">Indica el tipo de red al que estaba conectado el participante. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7adf-173">Todos</span><span class="sxs-lookup"><span data-stu-id="a7adf-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7adf-174">Cableada</span><span class="sxs-lookup"><span data-stu-id="a7adf-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="a7adf-175">Wireless</span><span class="sxs-lookup"><span data-stu-id="a7adf-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-p115">Indica si un participante externo estaba usando una conexión de red privada virtual (VPN) durante la sesión. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="a7adf-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7adf-179">Todos</span><span class="sxs-lookup"><span data-stu-id="a7adf-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="a7adf-180">VPN</span><span class="sxs-lookup"><span data-stu-id="a7adf-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="a7adf-181">No VPN</span><span class="sxs-lookup"><span data-stu-id="a7adf-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a7adf-182">Métricas</span><span class="sxs-lookup"><span data-stu-id="a7adf-182">Metrics</span></span>

<span data-ttu-id="a7adf-183">En la tabla siguiente se muestra la información que recoge el Informe de tendencias de calidad de medios de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7adf-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="a7adf-184">Métricas del Informe de tendencias de calidad de medios de servidores</span><span class="sxs-lookup"><span data-stu-id="a7adf-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7adf-185">Nombre</span><span class="sxs-lookup"><span data-stu-id="a7adf-185">Name</span></span></th>
<th><span data-ttu-id="a7adf-186">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="a7adf-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a7adf-187">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7adf-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-188"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-189">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-189">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-190">Número total de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a7adf-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-191"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-192">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-192">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-193">Cantidad media de degradación de MOS (puntuación de opinión media) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7adf-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="a7adf-194">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0; un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="a7adf-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="a7adf-195">Anteriormente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="a7adf-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="a7adf-196">Lync Server usa un conjunto de algoritmos para predecir la forma en que los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="a7adf-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="a7adf-p117">Los valores altos de degradación pueden ser producto de la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o un extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-199"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-200">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-200">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-p118">El número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="a7adf-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-203"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-204">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-204">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-p119">Tiempo medio (en milisegundos) necesario para que un paquete de Protocolo de transporte en tiempo real (RTP) llegue a un extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="a7adf-p120">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales; a una configuración incorrecta del enrutamiento, o a una sobrecarga en el servidor de medios. Estos valores elevados causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-209"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-210">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-210">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-p121">Tasa media de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-214"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-215">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-215">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-216">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="a7adf-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a7adf-217">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="a7adf-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-218"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-219">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-219">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-p123">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7adf-222"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-223">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-223">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-p124">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7adf-226"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="a7adf-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a7adf-227">No</span><span class="sxs-lookup"><span data-stu-id="a7adf-227">No</span></span></p></td>
<td><p><span data-ttu-id="a7adf-p125">Tasa media de muestras de audio comprimidas respecto al número total de muestras. (El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red.) Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones, y esto da lugar a un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="a7adf-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

