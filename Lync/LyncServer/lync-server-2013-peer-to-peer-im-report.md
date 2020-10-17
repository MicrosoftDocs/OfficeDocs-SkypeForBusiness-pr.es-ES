---
title: 'Lync Server 2013: informe de mensajería instantánea punto a punto'
description: 'Lync Server 2013: informe de mensajería instantánea punto a punto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac6291d0f099af8269ed15f7dc8c654ac944ed0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557296"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="3d887-103">Informe de mensajería instantánea punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d887-103">Peer-to-Peer IM Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d887-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3d887-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3d887-p101">El informe de mensajería instantánea punto a punto ofrece información de tendencias acerca de las sesiones de mensajería instantánea (MI) punto a punto, desglosadas por grupo de servidores y por tipo de autenticación. El informe puede mostrar el número total de sesiones mantenidas durante el período de tiempo especificado (por ejemplo, día a día u hora a hora) o bien, puede mostrar el número total de mensajes instantáneos enviados durante ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3d887-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="3d887-107">Obtener acceso al informe de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="3d887-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="3d887-108">Solo puede obtener acceso al informe de mensajería instantánea punto a punto abriendo el [Informe de Resumen de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) y, a continuación, haciendo clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="3d887-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3d887-109">Total de sesiones de MI punto a punto</span><span class="sxs-lookup"><span data-stu-id="3d887-109">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="3d887-110">Total de mensajes instantáneos punto a punto</span><span class="sxs-lookup"><span data-stu-id="3d887-110">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="3d887-111">Aprovechar al máximo el informe de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="3d887-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="3d887-p102">De manera predeterminada, el informe de mensajería instantánea de punto a punto le muestra el recuento de mensajes por hora (o día, en función de su configuración). Sin embargo, también puede elegir ver el día por sesiones por hora. Para ello, haga clic en **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana informes y, a continuación, haga clic en **Recuento de sesiones** en la lista **Informe por**.</span><span class="sxs-lookup"><span data-stu-id="3d887-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3d887-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="3d887-115">Filters</span></span>

<span data-ttu-id="3d887-p103">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de mensajería instantánea punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3d887-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="3d887-118">Filtros del informe de mensajería instantánea punto a punto</span><span class="sxs-lookup"><span data-stu-id="3d887-118">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d887-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d887-119">Name</span></span></th>
<th><span data-ttu-id="3d887-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d887-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d887-121"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3d887-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3d887-124">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="3d887-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3d887-p105">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="3d887-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3d887-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3d887-127">7/7/2012</span></span></p>
<p><span data-ttu-id="3d887-128">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="3d887-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3d887-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3d887-129">7/3/2012</span></span></p>
<p><span data-ttu-id="3d887-130">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="3d887-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d887-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3d887-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3d887-134">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="3d887-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3d887-p107">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="3d887-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3d887-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3d887-137">7/7/2012</span></span></p>
<p><span data-ttu-id="3d887-138">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="3d887-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3d887-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3d887-139">7/3/2012</span></span></p>
<p><span data-ttu-id="3d887-140">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="3d887-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d887-141"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-141"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3d887-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3d887-144">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="3d887-144">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3d887-145">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="3d887-145">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3d887-146">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="3d887-146">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3d887-147">Cada mes (se puede ver un máximo de  12 meses)</span><span class="sxs-lookup"><span data-stu-id="3d887-147">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="3d887-p109">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 7/7/2012 y una fecha de finalización 28/2/2012, se mostrarán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="3d887-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d887-150"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-150"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-151">Indica los valores a utilizar en el informe.</span><span class="sxs-lookup"><span data-stu-id="3d887-151">Indicates the values to be used in the report.</span></span> <span data-ttu-id="3d887-152">Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d887-152">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3d887-153">Recuento de sesiones</span><span class="sxs-lookup"><span data-stu-id="3d887-153">Session count</span></span></p></li>
<li><p><span data-ttu-id="3d887-154">Recuento de mensajes</span><span class="sxs-lookup"><span data-stu-id="3d887-154">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="3d887-155">Métricas para la mensajería instantánea punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="3d887-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="3d887-156">En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3d887-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="3d887-157">Métricas para la mensajería instantánea punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="3d887-157">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d887-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d887-158">Name</span></span></th>
<th><span data-ttu-id="3d887-159">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="3d887-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3d887-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d887-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d887-161"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-161"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-162">No</span><span class="sxs-lookup"><span data-stu-id="3d887-162">No</span></span></p></td>
<td><p><span data-ttu-id="3d887-163">Nombre del grupo de registrador o servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="3d887-163">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d887-164"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-164"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-165">No</span><span class="sxs-lookup"><span data-stu-id="3d887-165">No</span></span></p></td>
<td><p><span data-ttu-id="3d887-166">Fecha y hora en las que tuvo lugar la sesión.</span><span class="sxs-lookup"><span data-stu-id="3d887-166">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d887-167"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-167"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-168">No</span><span class="sxs-lookup"><span data-stu-id="3d887-168">No</span></span></p></td>
<td><p><span data-ttu-id="3d887-169">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3d887-169">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="3d887-170">Métricas para la mensajería instantánea punto a punto por tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="3d887-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="3d887-171">En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto para cada tipo de autenticación utilizado por los participantes de una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="3d887-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="3d887-172">Métricas para la mensajería instantánea punto a punto por tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="3d887-172">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d887-173">Nombre</span><span class="sxs-lookup"><span data-stu-id="3d887-173">Name</span></span></th>
<th><span data-ttu-id="3d887-174">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="3d887-174">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3d887-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d887-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d887-176"><strong>Tipo de autenticación</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-176"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-177">No</span><span class="sxs-lookup"><span data-stu-id="3d887-177">No</span></span></p></td>
<td><p><span data-ttu-id="3d887-p111">Tipo de autenticación utilizado por los participantes de la sesión. Los valores suelen ser los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d887-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3d887-180">Enterprise</span><span class="sxs-lookup"><span data-stu-id="3d887-180">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="3d887-181">Federadas</span><span class="sxs-lookup"><span data-stu-id="3d887-181">Federated</span></span></p></li>
<li><p><span data-ttu-id="3d887-182">IMG</span><span class="sxs-lookup"><span data-stu-id="3d887-182">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d887-183"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-184">No</span><span class="sxs-lookup"><span data-stu-id="3d887-184">No</span></span></p></td>
<td><p><span data-ttu-id="3d887-185">Fecha y hora en las que tuvo lugar la sesión.</span><span class="sxs-lookup"><span data-stu-id="3d887-185">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d887-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="3d887-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="3d887-187">No</span><span class="sxs-lookup"><span data-stu-id="3d887-187">No</span></span></p></td>
<td><p><span data-ttu-id="3d887-188">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3d887-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

