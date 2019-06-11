---
title: 'Lync Server 2013: informe actividad de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="44d7c-102">Informe de actividad de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44d7c-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44d7c-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="44d7c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="44d7c-104">El informe de actividad de conferencia le facilita que responda a preguntas como cuántas conferencias se están celebrando cada día y cuántas se celebran.</span><span class="sxs-lookup"><span data-stu-id="44d7c-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="44d7c-105">La información como esta no es solo útil por sí misma sino también como herramienta de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="44d7c-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="44d7c-106">Por ejemplo, supongamos que los usuarios se están quejando de que la red parece particularmente lenta a mitad del día.</span><span class="sxs-lookup"><span data-stu-id="44d7c-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="44d7c-107">Un vistazo rápido a los informes de actividad de conferencia puede sugerir una posible causa: muchas más conferencias se programan entre las horas de 10:00 AM y 2:00 PM, en cualquier otro momento.</span><span class="sxs-lookup"><span data-stu-id="44d7c-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="44d7c-108">Si la red lenta está causando problemas, puede animar a los usuarios a reprogramar algunas de sus conferencias durante las horas de menor tráfico del día.</span><span class="sxs-lookup"><span data-stu-id="44d7c-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="44d7c-109">Acceso al informe de actividad de conferencia</span><span class="sxs-lookup"><span data-stu-id="44d7c-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="44d7c-110">Para obtener acceso al informe de actividad de conferencia desde el [Informe de Resumen de conferencia en Lync Server 2013](lync-server-2013-conference-summary-report.md) , haga clic en una de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="44d7c-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="44d7c-111">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="44d7c-111">Total conferences</span></span>

  - <span data-ttu-id="44d7c-112">Total de participantes</span><span class="sxs-lookup"><span data-stu-id="44d7c-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="44d7c-113">Aprovechar al máximo el informe de actividad de conferencia</span><span class="sxs-lookup"><span data-stu-id="44d7c-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="44d7c-p102">De manera predeterminada, el informe de actividad de conferencia le muestra la cantidad total de conferencias para el período de tiempo especificado (por ejemplo, la cantidad total de conferencias por día o la cantidad total de conferencias por hora del día). Pero, puede elegir visualizar la cantidad total de participantes para ese período de tiempo o la cantidad total de minutos de participante. Para ello, haga clic en el botón Mostrar u ocultar parámetros para visualizar las opciones de filtrado y, luego, seleccione uno de los siguientes en la lista desplegable Informe por:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="44d7c-117">Recuento de participantes</span><span class="sxs-lookup"><span data-stu-id="44d7c-117">Participant count</span></span>

  - <span data-ttu-id="44d7c-118">Minutos de participantes</span><span class="sxs-lookup"><span data-stu-id="44d7c-118">Participant minutes</span></span>

  - <span data-ttu-id="44d7c-119">Recuento de conferencias</span><span class="sxs-lookup"><span data-stu-id="44d7c-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="44d7c-120">Filtros</span><span class="sxs-lookup"><span data-stu-id="44d7c-120">Filters</span></span>

<span data-ttu-id="44d7c-p103">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de actividad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="44d7c-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="44d7c-123">Filtros del informe de actividad de conferencia</span><span class="sxs-lookup"><span data-stu-id="44d7c-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44d7c-124">Nombre</span><span class="sxs-lookup"><span data-stu-id="44d7c-124">Name</span></span></th>
<th><span data-ttu-id="44d7c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="44d7c-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44d7c-126"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="44d7c-129">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="44d7c-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44d7c-p105">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44d7c-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44d7c-132">7/7/2012</span></span></p>
<p><span data-ttu-id="44d7c-133">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="44d7c-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44d7c-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44d7c-134">7/3/2012</span></span></p>
<p><span data-ttu-id="44d7c-135">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="44d7c-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44d7c-136"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="44d7c-139">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="44d7c-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44d7c-p107">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44d7c-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44d7c-142">7/7/2012</span></span></p>
<p><span data-ttu-id="44d7c-143">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="44d7c-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44d7c-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44d7c-144">7/3/2012</span></span></p>
<p><span data-ttu-id="44d7c-145">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="44d7c-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44d7c-146"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="44d7c-149">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="44d7c-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44d7c-150">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="44d7c-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44d7c-151">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="44d7c-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44d7c-152">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="44d7c-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="44d7c-153">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="44d7c-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="44d7c-154">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="44d7c-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44d7c-155"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-p110">Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="44d7c-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="44d7c-158">Recuento de participantes</span><span class="sxs-lookup"><span data-stu-id="44d7c-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="44d7c-159">Minutos de participantes</span><span class="sxs-lookup"><span data-stu-id="44d7c-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="44d7c-160">Recuento de conferencias</span><span class="sxs-lookup"><span data-stu-id="44d7c-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="44d7c-161">Métricas para conferencias por grupo</span><span class="sxs-lookup"><span data-stu-id="44d7c-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="44d7c-162">En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="44d7c-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="44d7c-163">Métricas para conferencias por grupo</span><span class="sxs-lookup"><span data-stu-id="44d7c-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44d7c-164">Nombre</span><span class="sxs-lookup"><span data-stu-id="44d7c-164">Name</span></span></th>
<th><span data-ttu-id="44d7c-165">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="44d7c-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="44d7c-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="44d7c-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44d7c-167"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-168">No</span><span class="sxs-lookup"><span data-stu-id="44d7c-168">No</span></span></p></td>
<td><p><span data-ttu-id="44d7c-169">Nombre del grupo de registradores o servidor perimetral utilizado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="44d7c-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44d7c-170"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-171">No</span><span class="sxs-lookup"><span data-stu-id="44d7c-171">No</span></span></p></td>
<td><p><span data-ttu-id="44d7c-172">Fecha y hora en que se desarrolló la conferencia.</span><span class="sxs-lookup"><span data-stu-id="44d7c-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44d7c-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-174">No</span><span class="sxs-lookup"><span data-stu-id="44d7c-174">No</span></span></p></td>
<td><p><span data-ttu-id="44d7c-175">Recuento total de participantes, minutos totales por participante o recuento total de conferencias.</span><span class="sxs-lookup"><span data-stu-id="44d7c-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="44d7c-176">Métricas para conferencias por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="44d7c-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="44d7c-177">En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="44d7c-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="44d7c-178">Métricas para conferencias por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="44d7c-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44d7c-179">Nombre</span><span class="sxs-lookup"><span data-stu-id="44d7c-179">Name</span></span></th>
<th><span data-ttu-id="44d7c-180">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="44d7c-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="44d7c-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="44d7c-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44d7c-182"><strong>Tipo de servidor de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-183">No</span><span class="sxs-lookup"><span data-stu-id="44d7c-183">No</span></span></p></td>
<td><p><span data-ttu-id="44d7c-184">Tipo de servidor usado en la conferencia, generalmente, uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="44d7c-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="44d7c-185">Servidor de conferencia web</span><span class="sxs-lookup"><span data-stu-id="44d7c-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="44d7c-186">Servidor de conferencia de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="44d7c-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="44d7c-187">Servidor de conferencia con telefonía</span><span class="sxs-lookup"><span data-stu-id="44d7c-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="44d7c-188">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="44d7c-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="44d7c-189">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="44d7c-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44d7c-190"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-191">No</span><span class="sxs-lookup"><span data-stu-id="44d7c-191">No</span></span></p></td>
<td><p><span data-ttu-id="44d7c-192">Fecha y hora en que se desarrolló la conferencia.</span><span class="sxs-lookup"><span data-stu-id="44d7c-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44d7c-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="44d7c-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="44d7c-194">No</span><span class="sxs-lookup"><span data-stu-id="44d7c-194">No</span></span></p></td>
<td><p><span data-ttu-id="44d7c-195">Recuento total de participantes, minutos totales por participante o recuento total de conferencias.</span><span class="sxs-lookup"><span data-stu-id="44d7c-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

