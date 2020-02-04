---
title: 'Lync Server 2013: informe Resumen de actividad punto a punto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55c3d84fe48158490473c31e9782dc63e298310
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="69554-102">Informe de Resumen de actividad de punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69554-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69554-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="69554-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="69554-104">El Informe de resumen de actividad punto a punto proporciona una vista general de las sesiones de comunicación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="69554-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="69554-105">Una sesión de punto a punto normalmente implica solo dos usuarios y no requiere el uso de los servicios de conferencia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69554-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="69554-106">En comparación, una conferencia suele implicar a más de dos usuarios y requiere el uso de los servicios de conferencia de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69554-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="69554-107">La actividad de la conferencia se notifica en el Informe de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="69554-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="69554-108">Con el Informe de resumen de actividad punto a punto le será más fácil responder a preguntas como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="69554-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="69554-109">¿Cuántos mensajes instantáneos de punto a punto envían habitualmente mis usuarios en un día normal?</span><span class="sxs-lookup"><span data-stu-id="69554-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="69554-110">¿Todos los usuarios aprovechan realmente las capacidades de uso compartido de aplicaciones y transferencia de archivos de Lync Server?</span><span class="sxs-lookup"><span data-stu-id="69554-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="69554-p102">Los usuarios se han estado quejando de que en determinados momentos del día, parece que la red va más lenta. ¿Cuántos minutos se dedican a las sesiones de audio o vídeo en esos períodos de tiempo?</span><span class="sxs-lookup"><span data-stu-id="69554-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="69554-113">Obtener acceso al Informe de resumen de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="69554-114">Obtenga acceso al Informe de resumen de actividad punto a punto desde la página inicial de los informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="69554-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="69554-115">Para abrir el [Informe de mensajería instantánea de punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , haga clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="69554-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="69554-116">Total de sesiones de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="69554-117">Total de mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="69554-118">Igualmente, puede abrir el informe de voz y vídeo punto a punto haciendo clic en una de estas métricas:</span><span class="sxs-lookup"><span data-stu-id="69554-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="69554-119">Total de sesiones de audio de punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="69554-120">Total de minutos de sesiones de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="69554-121">Total de sesiones de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="69554-122">Total de minutos de sesiones de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="69554-123">Sacar el máximo provecho del Informe de resumen de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="69554-p104">En la parte inferior del Informe de resumen de actividad punto a punto encontrará los totales de métricas como Sesiones de mensajería instantánea punto a punto o Total de mensajes de mensajería instantánea punto a punto. De esta forma obtiene un resumen rápido de la información detallada encontrada en el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="69554-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="69554-126">Filtros</span><span class="sxs-lookup"><span data-stu-id="69554-126">Filters</span></span>

<span data-ttu-id="69554-p105">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el resumen de actividad punto a punto le permite elegir cuántos datos agrupar. En este caso, la actividad se agrupa por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="69554-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="69554-130">En la siguiente tabla se enumeran los filtros que puede utilizar con el Informe de resumen de actividad punto a punto.</span><span class="sxs-lookup"><span data-stu-id="69554-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="69554-131">Filtros del Informe de resumen de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69554-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="69554-132">Name</span></span></th>
<th><span data-ttu-id="69554-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="69554-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69554-134"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="69554-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-p106">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="69554-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="69554-137">7/17/12012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="69554-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="69554-p107">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="69554-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="69554-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="69554-140">7/17/12012</span></span></p>
<p><span data-ttu-id="69554-141">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="69554-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="69554-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="69554-142">7/13/2012</span></span></p>
<p><span data-ttu-id="69554-143">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="69554-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-144"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="69554-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-p108">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="69554-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="69554-147">7/17/12012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="69554-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="69554-p109">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="69554-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="69554-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="69554-150">7/17/12012</span></span></p>
<p><span data-ttu-id="69554-151">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="69554-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="69554-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="69554-152">7/13/2012</span></span></p>
<p><span data-ttu-id="69554-153">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="69554-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69554-154"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="69554-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-p110">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="69554-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69554-157">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="69554-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="69554-158">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="69554-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="69554-159">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="69554-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="69554-160">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="69554-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="69554-161">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="69554-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="69554-162">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/17/12012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/12012 12:00 A.M. a 9/7/12012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="69554-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="69554-163">Métricas</span><span class="sxs-lookup"><span data-stu-id="69554-163">Metrics</span></span>

<span data-ttu-id="69554-164">En la tabla siguiente se muestra la información que recoge el Informe de resumen de actividad punto a punto.</span><span class="sxs-lookup"><span data-stu-id="69554-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="69554-165">Métricas del Informe de resumen de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="69554-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69554-166">Nombre</span><span class="sxs-lookup"><span data-stu-id="69554-166">Name</span></span></th>
<th><span data-ttu-id="69554-167">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="69554-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="69554-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="69554-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69554-169"><strong>Cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="69554-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="69554-170"><strong>Cada día</strong></span><span class="sxs-lookup"><span data-stu-id="69554-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="69554-171"><strong>Cada semana</strong></span><span class="sxs-lookup"><span data-stu-id="69554-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="69554-172"><strong>Cada mes</strong></span><span class="sxs-lookup"><span data-stu-id="69554-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-173">No</span><span class="sxs-lookup"><span data-stu-id="69554-173">No</span></span></p></td>
<td><p><span data-ttu-id="69554-174">Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros.</span><span class="sxs-lookup"><span data-stu-id="69554-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="69554-175">Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo.</span><span class="sxs-lookup"><span data-stu-id="69554-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="69554-176">Por ejemplo, si está usando el intervalo diario y hace clic en 7/17/12012, verá un desglose por hora de actividad de registro de usuario para esa fecha.</span><span class="sxs-lookup"><span data-stu-id="69554-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-177"><strong>Total de sesiones punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-178">No</span><span class="sxs-lookup"><span data-stu-id="69554-178">No</span></span></p></td>
<td><p><span data-ttu-id="69554-179">Cantidad total de sesiones punto a punto realizadas, independientemente del tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="69554-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69554-180"><strong>Total de sesiones de mensajería instantánea de punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-181">No</span><span class="sxs-lookup"><span data-stu-id="69554-181">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p113">Cantidad total de sesiones de mensajería instantánea punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69554-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-184"><strong>Total de mensajes instantáneos de punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-185">No</span><span class="sxs-lookup"><span data-stu-id="69554-185">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p114">Cantidad total de mensajes instantáneos enviados en sesiones punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de MI punto a punto para el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69554-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69554-188"><strong>Total de sesiones de audio punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-189">No</span><span class="sxs-lookup"><span data-stu-id="69554-189">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p115">Cantidad total de llamadas de audio punto a punto. Cuando se hace clic en este campo, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69554-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-192"><strong>Total de minutos de sesiones de audio punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-193">No</span><span class="sxs-lookup"><span data-stu-id="69554-193">No</span></span></p></td>
<td><p><span data-ttu-id="69554-194">Cantidad de tiempo total transcurrida en sesiones de audio punto a punto.</span><span class="sxs-lookup"><span data-stu-id="69554-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="69554-195">Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69554-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69554-196"><strong>Promedio de minutos en sesiones de audio punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-197">No</span><span class="sxs-lookup"><span data-stu-id="69554-197">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p117">Cantidad de tiempo promedio transcurrido en sesiones de audio punto a punto. Se calcula dividiendo el total del tiempo de sesiones de audio por el número total de sesiones de audio.</span><span class="sxs-lookup"><span data-stu-id="69554-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-200"><strong>Total de sesiones de vídeo punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-201">No</span><span class="sxs-lookup"><span data-stu-id="69554-201">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p118">Cantidad total de llamadas de vídeo punto a punto. Observe que las sesiones de vídeo también se cuentan como sesiones de audio: cada sesión de vídeo se cuenta como una sesión de vídeo y una sesión de audio. Cuando se hace clic en este elemento, el informe muestra el informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69554-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69554-205"><strong>Total de minutos de sesiones de vídeo punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-206">No</span><span class="sxs-lookup"><span data-stu-id="69554-206">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p119">Cantidad total de tiempo transcurrido en sesiones de vídeo punto a punto. Cuando se hace clic en este elemento, el informe muestra el Informe de voz y vídeo punto a punto para el período de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69554-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-209"><strong>Promedio de minutos en sesiones de vídeo punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-210">No</span><span class="sxs-lookup"><span data-stu-id="69554-210">No</span></span></p></td>
<td><p><span data-ttu-id="69554-p120">Cantidad de tiempo promedio transcurrido en sesiones de vídeo punto a punto. Se calcula dividiendo el total del tiempo de sesiones de vídeo por el número total de sesiones de vídeo.</span><span class="sxs-lookup"><span data-stu-id="69554-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69554-213"><strong>Total de sesiones de transferencia de archivos punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-214">No</span><span class="sxs-lookup"><span data-stu-id="69554-214">No</span></span></p></td>
<td><p><span data-ttu-id="69554-215">Cantidad total de sesiones punto a punto en las que se realizaron transferencias de archivos.</span><span class="sxs-lookup"><span data-stu-id="69554-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69554-216"><strong>Total de sesiones compartidas de aplicaciones punto a punto</strong></span><span class="sxs-lookup"><span data-stu-id="69554-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="69554-217">No</span><span class="sxs-lookup"><span data-stu-id="69554-217">No</span></span></p></td>
<td><p><span data-ttu-id="69554-218">Cantidad total de sesiones punto a punto en las que se compartieron aplicaciones</span><span class="sxs-lookup"><span data-stu-id="69554-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

