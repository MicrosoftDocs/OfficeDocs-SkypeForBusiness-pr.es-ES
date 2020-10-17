---
title: 'Lync Server 2013: informe de Resumen de conferencia'
description: 'Lync Server 2013: informe de Resumen de conferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d9c0b8ad7280d2c7336282c14f46e6b5d6a1aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550716"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="dfc1d-103">Informe de Resumen de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfc1d-103">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfc1d-104">_**Última modificación del tema:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="dfc1d-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="dfc1d-105">El informe de resumen de conferencia ofrece una vista general de las sesiones de conferencia en línea.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-105">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="dfc1d-106">Una conferencia suele implicar a más de 2 usuarios y requiere el uso de los servicios de conferencia de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-106">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="dfc1d-107">Por su parte, una sesión punto a punto suele implicar a solo dos usuarios y no precisa del uso de los servicios de conferencia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-107">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="dfc1d-108">Las actividades punto a punto se indican en el [Informe de Resumen de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="dfc1d-108">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="dfc1d-109">El informe de Resumen de conferencia no solo indica el número de conferencias que se realizaron durante un período de tiempo determinado (cada hora, diariamente, semanalmente, mensualmente), sino que también indica el número total de personas que participaron en esas conferencias y el número total de organizadores de conferencia únicos.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-109">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="dfc1d-p102">Un organizador "único” es alguien que programa al menos una conferencia. Así, por ejemplo, si Pilar Ackerman programa una conferencia, se contabilizará como una organizadora única y, si Ken Myer programa 148 conferencias, también se considerará como organizador único. En la siguiente tabla se recogen ocho conferencias programadas, pero solo tres organizadores únicos (Ken Myer, Pilar Ackerman y David Ahs).</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfc1d-114">Organizador de la conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-114">Conference Organizer</span></span></th>
<th><span data-ttu-id="dfc1d-115">Fecha de la conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-115">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-116">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-116">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-117">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-117">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-118">David Ahs</span><span class="sxs-lookup"><span data-stu-id="dfc1d-118">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-119">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-119">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-120">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-120">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-121">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-121">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-122">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dfc1d-122">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-123">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-123">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-124">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-124">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-125">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-126">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dfc1d-126">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-127">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-127">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-128">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-128">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-129">2/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-129">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-130">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dfc1d-130">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-131">2/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-131">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfc1d-132">El informe de resumen de conferencia también indica el número de conferencias que incluyeron audio y/o vídeo.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-132">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="dfc1d-133">Acceso al informe de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-133">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="dfc1d-p103">Puede acceder al informe de resumen de conferencia desde la página principal de informes de supervisión. Para llegar hasta dicho informe, deberá hacer clic en las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="dfc1d-136">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="dfc1d-136">Total conferences</span></span>

  - <span data-ttu-id="dfc1d-137">Total de participantes</span><span class="sxs-lookup"><span data-stu-id="dfc1d-137">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="dfc1d-138">Usar el informe de resumen de conferencia de la mejor forma posible</span><span class="sxs-lookup"><span data-stu-id="dfc1d-138">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="dfc1d-p104">En la parte inferior del informe de resumen de conferencia se plasman los valores totales de la mayor parte de las métricas que se usan en este informe. Desplácese hacia abajo para conocer valores como el número total de conferencias celebrado durante el periodo de tiempo especificado y el número total de personas que participaron en ellas. Una métrica cuyo valor total no se recoge ahí es Total de organizadores de conferencia distintos. Esto responde a un motivo: imagine que está consultando los datos de un mes entero. En el día 1 hubo 34 organizadores distintos y en el día 2, 27. Esto no tiene por qué significar que hubo 61 organizadores distintos esos días, ya que las 27 personas que organizaron conferencias durante el día 2 podrían encontrarse entre las 34 que organizaron conferencias en el día 1. Vea en este sencillo informe cómo Ken Myer y Pilar Ackerman programaron conferencias en los días 7/7/2012 y 2/7/2012:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfc1d-149">Organizador de la conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-149">Conference Organizer</span></span></th>
<th><span data-ttu-id="dfc1d-150">Fecha de la conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-150">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-151">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-151">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-152">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-152">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-153">David Ahs</span><span class="sxs-lookup"><span data-stu-id="dfc1d-153">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-154">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-154">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-155">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-155">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-156">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-156">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-157">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dfc1d-157">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-158">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-158">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-159">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-159">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-160">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-161">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dfc1d-161">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-162">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-162">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-163">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dfc1d-163">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-164">2/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-164">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-165">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dfc1d-165">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-166">2/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-166">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfc1d-167">Para componerse una mejor idea del número total de usuarios distintos que ha organizado conferencias, cambie el intervalo temporal (por ejemplo, consulte los datos por mes en lugar de por día).</span><span class="sxs-lookup"><span data-stu-id="dfc1d-167">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dfc1d-168">Filtros</span><span class="sxs-lookup"><span data-stu-id="dfc1d-168">Filters</span></span>

<span data-ttu-id="dfc1d-p105">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de conferencia le permite elegir cómo agrupar los datos. En este caso, las conferencias se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="dfc1d-172">La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-172">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="dfc1d-173">Filtros del informe de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-173">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfc1d-174">Nombre</span><span class="sxs-lookup"><span data-stu-id="dfc1d-174">Name</span></span></th>
<th><span data-ttu-id="dfc1d-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfc1d-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-176"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-176"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p106">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dfc1d-179">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-179">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dfc1d-p107">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dfc1d-182">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dfc1d-182">7/7/2012</span></span></p>
<p><span data-ttu-id="dfc1d-183">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="dfc1d-183">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dfc1d-184">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dfc1d-184">7/3/2012</span></span></p>
<p><span data-ttu-id="dfc1d-185">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-185">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-186"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-186"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p108">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dfc1d-189">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dfc1d-189">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dfc1d-p109">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dfc1d-192">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dfc1d-192">7/7/2012</span></span></p>
<p><span data-ttu-id="dfc1d-193">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="dfc1d-193">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dfc1d-194">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dfc1d-194">7/3/2012</span></span></p>
<p><span data-ttu-id="dfc1d-195">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-195">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-196"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-196"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p110">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dfc1d-199">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="dfc1d-199">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dfc1d-200">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="dfc1d-200">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dfc1d-201">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="dfc1d-201">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dfc1d-202">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="dfc1d-202">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="dfc1d-p111">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solamente se mostrará la cantidad máxima de valores (empezando por la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, los datos de un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="dfc1d-205">Métricas</span><span class="sxs-lookup"><span data-stu-id="dfc1d-205">Metrics</span></span>

<span data-ttu-id="dfc1d-206">La siguiente tabla incluye la información que ofrece el informe de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-206">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="dfc1d-207">Métricas del informe de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="dfc1d-207">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfc1d-208">Nombre</span><span class="sxs-lookup"><span data-stu-id="dfc1d-208">Name</span></span></th>
<th><span data-ttu-id="dfc1d-209">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="dfc1d-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dfc1d-210">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfc1d-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-211"><strong>Cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="dfc1d-212"><strong>Diario</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="dfc1d-213"><strong>Semanal</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="dfc1d-214"><strong>Mensualmente</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-215">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-215">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p112">Indica el intervalo temporal que ha seleccionado en la barra de herramientas de filtro. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada al respecto. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 7/7/2012, verá un desglose por horas de la actividad de registro del usuario correspondiente a esa fecha.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-219"><strong>Total de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-219"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-220">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-220">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p113">Número total de conferencias (independientemente del tipo de conferencia) celebradas. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-223"><strong>Total de participantes</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-223"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-224">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-224">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p114">Número total de personas que participaron en las conferencias. Al hacer clic en este elemento, el informe le muestra el informe de actividad de conferencia del periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-227"><strong>Media de participantes por conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-227"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-228">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-228">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p115">Número medio de participantes que participaron en una conferencia en concreto. Se calcula dividiendo el número total de conferencias por el número total de participantes.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-231"><strong>Número total de conferencias A/V</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-231"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-232">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-232">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-233">Número total de conferencias que incluían audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-233">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-234"><strong>	Total de minutos de conferencia A/V</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-234"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-235">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-235">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-236">Número total de minutos dedicados a conferencias de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-236">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="dfc1d-237">La métrica total de minutos de conferencia A/V resume todos los tipos de conferencia de audio y vídeo, entre los que se incluyen: conferencias A/V; Conferencias de mensajería instantánea; conferencias de uso compartido de aplicaciones; conferencias de datos; y conferencias RTC.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-237">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-238"><strong>Total de minutos de participantes en conferencia A/V</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-238"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-239">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-239">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p116">Número total de minutos de los participantes dedicados a conferencias de audio/vídeo. Por ejemplo, supongamos que un usuario participa 5 minutos en una conferencia de audio/vídeo y un segundo usuario participa 3 minutos en la misma conferencia. Esto hace un total de 8 minutos de los participantes: 5 minutos más 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-243"><strong>Número medio de minutos en conferencias A/V</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-243"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-244">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-244">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-245">Número medio de minutos por conferencia de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-245">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfc1d-246"><strong>Número total de organizadores únicos de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-246"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-247">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-247">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-p117">Número total de usuarios que organizaron al menos una conferencia. Los usuarios que organizaron más de una conferencia se cuentan como un único organizador, al igual que ocurre con los usuarios que solo organizaron una única conferencia.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfc1d-250"><strong>Número total de mensajes de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="dfc1d-250"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="dfc1d-251">No</span><span class="sxs-lookup"><span data-stu-id="dfc1d-251">No</span></span></p></td>
<td><p><span data-ttu-id="dfc1d-252">Número total de mensajes instantáneos enviados durante las conferencias.</span><span class="sxs-lookup"><span data-stu-id="dfc1d-252">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

