---
title: 'Lync Server 2013: informe de tiempo de combinación de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce80d3c61e94752423c70de9827d41243da7119
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="09558-102">Informe de tiempo de combinación en conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09558-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09558-103">_**Última modificación del tema:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="09558-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="09558-p101">El Resumen del tiempo de incorporación a la conferencia permite determinar cuánto tardan los usuarios en unirse a una conferencia. El informe muestra el tiempo de unión promedio (en milisegundos), así como un desglose que permite saber cuántos usuarios pudieron unirse a una conferencia en 2 o menos segundos, cuántos usuarios necesitaron entre 2 y 5 segundos para unirse a la conferencia, etc.</span><span class="sxs-lookup"><span data-stu-id="09558-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="09558-106">Obtener acceso al informe de tiempo de incorporación a la conferencia</span><span class="sxs-lookup"><span data-stu-id="09558-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="09558-107">Para obtener acceso al informe del tiempo de incorporación a la conferencia tiene que ir a la página principal de los informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="09558-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="09558-108">Filtros</span><span class="sxs-lookup"><span data-stu-id="09558-108">Filters</span></span>

<span data-ttu-id="09558-p102">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de tiempo de incorporación a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="09558-111">Filtros del informe de tiempo de incorporación a la conferencia</span><span class="sxs-lookup"><span data-stu-id="09558-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09558-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="09558-112">Name</span></span></th>
<th><span data-ttu-id="09558-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="09558-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09558-114"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="09558-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-p103">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="09558-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="09558-117">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="09558-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="09558-p104">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="09558-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="09558-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="09558-120">7/7/2012</span></span></p>
<p><span data-ttu-id="09558-121">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="09558-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="09558-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="09558-122">7/3/2012</span></span></p>
<p><span data-ttu-id="09558-123">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="09558-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-124"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="09558-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-p105">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="09558-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="09558-127">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="09558-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="09558-p106">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="09558-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="09558-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="09558-130">7/7/2012</span></span></p>
<p><span data-ttu-id="09558-131">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="09558-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="09558-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="09558-132">7/3/2012</span></span></p>
<p><span data-ttu-id="09558-133">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="09558-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-134"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="09558-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-p107">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="09558-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="09558-137">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="09558-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="09558-138">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="09558-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="09558-139">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="09558-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="09558-140">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="09558-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="09558-141">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="09558-141">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="09558-142">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="09558-142">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-143"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="09558-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-p109">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="09558-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-147"><strong>Sesiones de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="09558-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-p110">Tipo de sesión. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="09558-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="09558-150">[Todas]</span><span class="sxs-lookup"><span data-stu-id="09558-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="09558-151">Sesiones de foco (el foco es la directiva central y el administrador de estados para las reuniones en línea; coordina todos los aspectos de una conferencia)</span><span class="sxs-lookup"><span data-stu-id="09558-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="09558-152">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="09558-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="09558-153">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="09558-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="09558-p111">Si selecciona [Todo], aparecerá el tiempo de incorporación a la conferencia total en la parte superior del informe. Recuerde que estos totales son solo para conferencias programada con Microsoft Exchange o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="09558-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="09558-156">Métricas</span><span class="sxs-lookup"><span data-stu-id="09558-156">Metrics</span></span>

<span data-ttu-id="09558-157">En la tabla siguiente, se muestra la información proporcionada en el informe de tiempo de incorporación a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="09558-158">Métricas del informe de tiempo de incorporación a la conferencia</span><span class="sxs-lookup"><span data-stu-id="09558-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09558-159">Nombre</span><span class="sxs-lookup"><span data-stu-id="09558-159">Name</span></span></th>
<th><span data-ttu-id="09558-160">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="09558-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="09558-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="09558-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09558-162"><strong>Fecha</strong></span><span class="sxs-lookup"><span data-stu-id="09558-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="09558-163">El título real de esta métrica variará en función del intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="09558-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="09558-164">No</span><span class="sxs-lookup"><span data-stu-id="09558-164">No</span></span></p></td>
<td><p><span data-ttu-id="09558-165">Fecha y hora en las que tuvo lugar la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-166"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="09558-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-167">No</span><span class="sxs-lookup"><span data-stu-id="09558-167">No</span></span></p></td>
<td><p><span data-ttu-id="09558-168">Cantidad total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.</span><span class="sxs-lookup"><span data-stu-id="09558-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-169"><strong>Promedio (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="09558-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-170">No</span><span class="sxs-lookup"><span data-stu-id="09558-170">No</span></span></p></td>
<td><p><span data-ttu-id="09558-171">Promedio del tiempo (en milisegundos) que tardaron los participantes en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-172"><strong>Sesiones &lt; 2 segundos, volumen</strong></span><span class="sxs-lookup"><span data-stu-id="09558-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-173">No</span><span class="sxs-lookup"><span data-stu-id="09558-173">No</span></span></p></td>
<td><p><span data-ttu-id="09558-174">Número de participantes que pudieron unirse a la conferencia en menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="09558-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-175"><strong>Sesiones &lt; 2 segundos, porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="09558-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-176">No</span><span class="sxs-lookup"><span data-stu-id="09558-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-177"><strong>Sesiones 2-5 segundos, Volumen</strong></span><span class="sxs-lookup"><span data-stu-id="09558-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-178">No</span><span class="sxs-lookup"><span data-stu-id="09558-178">No</span></span></p></td>
<td><p><span data-ttu-id="09558-179">Número de participantes que tardaron entre 2 y 5 segundos en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-180"><strong>Sesiones 2-5 segundos, Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="09558-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-181">No</span><span class="sxs-lookup"><span data-stu-id="09558-181">No</span></span></p></td>
<td><p><span data-ttu-id="09558-182">Porcentaje del número total de participantes que llamaron que tardaron entre 2 y 5 segundos en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-183"><strong>Sesiones 5-10 segundos, Volumen</strong></span><span class="sxs-lookup"><span data-stu-id="09558-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-184">No</span><span class="sxs-lookup"><span data-stu-id="09558-184">No</span></span></p></td>
<td><p><span data-ttu-id="09558-185">Cantidad de participantes que tardaron entre 5 y 10 segundos en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-186"><strong>Sesiones 5-10 segundos, Porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="09558-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-187">No</span><span class="sxs-lookup"><span data-stu-id="09558-187">No</span></span></p></td>
<td><p><span data-ttu-id="09558-188">Porcentaje del número total de participantes que llamaron que tardaron entre 5 y 10 segundos en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09558-189"><strong>Sesiones &gt; 10 segundos, volumen</strong></span><span class="sxs-lookup"><span data-stu-id="09558-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-190">No</span><span class="sxs-lookup"><span data-stu-id="09558-190">No</span></span></p></td>
<td><p><span data-ttu-id="09558-191">Número de participantes que necesitaron más de 10 segundos en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09558-192"><strong>Sesiones &gt; 10 segundos, porcentaje</strong></span><span class="sxs-lookup"><span data-stu-id="09558-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="09558-193">No</span><span class="sxs-lookup"><span data-stu-id="09558-193">No</span></span></p></td>
<td><p><span data-ttu-id="09558-194">Porcentaje del número total de participantes que necesitaron más de 10 segundos en unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="09558-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

