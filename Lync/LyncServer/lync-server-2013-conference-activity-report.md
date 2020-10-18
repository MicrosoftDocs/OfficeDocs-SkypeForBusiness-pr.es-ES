---
title: 'Lync Server 2013: informe de actividad de conferencia'
description: 'Lync Server 2013: informe de actividad de conferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a2b23a08970defaec62b98d075ad1167527fd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577656"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="1d98e-103">Informe de actividad de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d98e-103">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d98e-104">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1d98e-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1d98e-105">El informe de actividad de conferencia le facilita que responda a preguntas como cuántas conferencias se están celebrando cada día y cuántas se celebran.</span><span class="sxs-lookup"><span data-stu-id="1d98e-105">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="1d98e-106">La información como esta no es solo útil por sí misma sino también como herramienta de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="1d98e-106">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="1d98e-107">Por ejemplo, supongamos que los usuarios se están quejando de que la red parece particularmente lenta a mitad del día.</span><span class="sxs-lookup"><span data-stu-id="1d98e-107">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="1d98e-108">Un vistazo rápido a los informes de actividad de conferencia puede sugerir una posible razón: muchas más conferencias se están programando entre las horas 10:00 A.M. y 2:00 P.M. después, en cualquier otro momento.</span><span class="sxs-lookup"><span data-stu-id="1d98e-108">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="1d98e-109">Si la red lenta está causando problemas, puede animar a los usuarios a reprogramar algunas de sus conferencias durante las horas de menor tráfico del día.</span><span class="sxs-lookup"><span data-stu-id="1d98e-109">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="1d98e-110">Acceso al informe de actividad de conferencia</span><span class="sxs-lookup"><span data-stu-id="1d98e-110">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="1d98e-111">Para obtener acceso al informe de actividad de conferencia, vaya al [Informe de Resumen de conferencia en Lync Server 2013](lync-server-2013-conference-summary-report.md) haciendo clic en una de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="1d98e-111">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="1d98e-112">Total de conferencias</span><span class="sxs-lookup"><span data-stu-id="1d98e-112">Total conferences</span></span>

  - <span data-ttu-id="1d98e-113">Total de participantes</span><span class="sxs-lookup"><span data-stu-id="1d98e-113">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="1d98e-114">Aprovechar al máximo el informe de actividad de conferencia</span><span class="sxs-lookup"><span data-stu-id="1d98e-114">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="1d98e-p102">De manera predeterminada, el informe de actividad de conferencia le muestra el número total de conferencias para el período de tiempo especificado (por ejemplo, el número total de conferencias por día o el número total de conferencias por hora del día). Sin embargo, puede elegir visualizar el número total de participantes para ese período de tiempo o el número total de minutos de participante. Para ello, haga clic en el botón Mostrar u ocultar parámetros para visualizar las opciones de filtrado y, a continuación, seleccione uno de los siguientes en la lista desplegable Informe por:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="1d98e-118">Recuento de participantes</span><span class="sxs-lookup"><span data-stu-id="1d98e-118">Participant count</span></span>

  - <span data-ttu-id="1d98e-119">Minutos de participantes</span><span class="sxs-lookup"><span data-stu-id="1d98e-119">Participant minutes</span></span>

  - <span data-ttu-id="1d98e-120">Recuento de conferencias</span><span class="sxs-lookup"><span data-stu-id="1d98e-120">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1d98e-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="1d98e-121">Filters</span></span>

<span data-ttu-id="1d98e-p103">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de actividad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1d98e-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="1d98e-124">Filtros del informe de actividad de conferencia</span><span class="sxs-lookup"><span data-stu-id="1d98e-124">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d98e-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="1d98e-125">Name</span></span></th>
<th><span data-ttu-id="1d98e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d98e-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d98e-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1d98e-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1d98e-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1d98e-p105">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1d98e-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1d98e-133">7/7/2012</span></span></p>
<p><span data-ttu-id="1d98e-134">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="1d98e-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1d98e-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1d98e-135">7/3/2012</span></span></p>
<p><span data-ttu-id="1d98e-136">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="1d98e-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d98e-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1d98e-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1d98e-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1d98e-p107">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1d98e-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1d98e-143">7/7/2012</span></span></p>
<p><span data-ttu-id="1d98e-144">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="1d98e-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1d98e-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1d98e-145">7/3/2012</span></span></p>
<p><span data-ttu-id="1d98e-146">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="1d98e-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d98e-147"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d98e-150">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1d98e-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1d98e-151">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="1d98e-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1d98e-152">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1d98e-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1d98e-153">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1d98e-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1d98e-p109">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 7/7/2012 y una fecha de finalización 28/2/2012, se mostrarán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="1d98e-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d98e-156"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-156"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-p110">Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d98e-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d98e-159">Recuento de participantes</span><span class="sxs-lookup"><span data-stu-id="1d98e-159">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="1d98e-160">Minutos de participante</span><span class="sxs-lookup"><span data-stu-id="1d98e-160">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="1d98e-161">Recuento de conferencias</span><span class="sxs-lookup"><span data-stu-id="1d98e-161">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="1d98e-162">Métricas para conferencias por grupo</span><span class="sxs-lookup"><span data-stu-id="1d98e-162">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="1d98e-163">En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="1d98e-163">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="1d98e-164">Métricas para conferencias por grupo</span><span class="sxs-lookup"><span data-stu-id="1d98e-164">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d98e-165">Nombre</span><span class="sxs-lookup"><span data-stu-id="1d98e-165">Name</span></span></th>
<th><span data-ttu-id="1d98e-166">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="1d98e-166">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1d98e-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d98e-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d98e-168"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-169">No</span><span class="sxs-lookup"><span data-stu-id="1d98e-169">No</span></span></p></td>
<td><p><span data-ttu-id="1d98e-170">Nombre del grupo de registradores o servidor perimetral utilizado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="1d98e-170">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d98e-171"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-171"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-172">No</span><span class="sxs-lookup"><span data-stu-id="1d98e-172">No</span></span></p></td>
<td><p><span data-ttu-id="1d98e-173">Fecha y hora en que se desarrolló la conferencia.</span><span class="sxs-lookup"><span data-stu-id="1d98e-173">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d98e-174"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-174"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-175">No</span><span class="sxs-lookup"><span data-stu-id="1d98e-175">No</span></span></p></td>
<td><p><span data-ttu-id="1d98e-176">Recuento total de participantes, minutos totales por participante o recuento total de conferencias.</span><span class="sxs-lookup"><span data-stu-id="1d98e-176">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="1d98e-177">Métricas para conferencias por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="1d98e-177">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="1d98e-178">En la tabla siguiente, se muestra la información proporcionada en el informe de actividad de conferencia para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="1d98e-178">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="1d98e-179">Métricas para conferencias por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="1d98e-179">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d98e-180">Nombre</span><span class="sxs-lookup"><span data-stu-id="1d98e-180">Name</span></span></th>
<th><span data-ttu-id="1d98e-181">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="1d98e-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1d98e-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d98e-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d98e-183"><strong>Tipo de servidor de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-183"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-184">No</span><span class="sxs-lookup"><span data-stu-id="1d98e-184">No</span></span></p></td>
<td><p><span data-ttu-id="1d98e-185">Tipo de servidor usado en la conferencia, generalmente, uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d98e-185">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d98e-186">Servidor de conferencia web</span><span class="sxs-lookup"><span data-stu-id="1d98e-186">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1d98e-187">Servidor de conferencia de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="1d98e-187">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1d98e-188">Servidor de conferencia con telefonía</span><span class="sxs-lookup"><span data-stu-id="1d98e-188">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1d98e-189">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="1d98e-189">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1d98e-190">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1d98e-190">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d98e-191"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-191"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-192">No</span><span class="sxs-lookup"><span data-stu-id="1d98e-192">No</span></span></p></td>
<td><p><span data-ttu-id="1d98e-193">Fecha y hora en que se desarrolló la conferencia.</span><span class="sxs-lookup"><span data-stu-id="1d98e-193">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d98e-194"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1d98e-194"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1d98e-195">No</span><span class="sxs-lookup"><span data-stu-id="1d98e-195">No</span></span></p></td>
<td><p><span data-ttu-id="1d98e-196">Recuento total de participantes, minutos totales por participante o recuento total de conferencias.</span><span class="sxs-lookup"><span data-stu-id="1d98e-196">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

