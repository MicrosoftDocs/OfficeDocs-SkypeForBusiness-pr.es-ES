---
title: 'Lync Server 2013: informe de mensajería instantánea de punto a punto'
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
ms.openlocfilehash: 359c3fad7f41d990ffdba3aa533d0d5f10456665
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="1738f-102">Informe de mensajería instantánea de punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1738f-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1738f-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1738f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1738f-p101">El informe de mensajería instantánea punto a punto ofrece información de tendencias sobre las sesiones de mensajería instantánea (MI) punto a punto, desglosadas por grupo de servidores y por tipo de autenticación. El informe puede mostrar la cantidad total de sesiones mantenidas durante el período de tiempo especificado (por ejemplo, día a día u hora a hora) o bien, puede mostrar la cantidad total de mensajes instantáneos enviados durante ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="1738f-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="1738f-106">Obtener acceso al informe de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="1738f-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="1738f-107">Puede obtener acceso al informe de mensajería instantánea de punto a punto solo si abre el [Informe de Resumen de actividad punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) y, a continuación, hace clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="1738f-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="1738f-108">Total de sesiones de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="1738f-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="1738f-109">Total de mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="1738f-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="1738f-110">Aprovechar al máximo el informe de mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="1738f-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="1738f-p102">De manera predeterminada, el informe de mensajería instantánea de punto a punto le muestra el recuento de mensajes por hora (o día, en función de su configuración). Pero, también puede elegir ver el día por sesiones por hora. Para ello, haga clic en **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana Informes y, luego, haga clic en **Recuento de sesiones** en la lista **Informe por**.</span><span class="sxs-lookup"><span data-stu-id="1738f-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1738f-114">Filtros</span><span class="sxs-lookup"><span data-stu-id="1738f-114">Filters</span></span>

<span data-ttu-id="1738f-p103">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de mensajería instantánea punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1738f-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="1738f-117">Filtros del informe de mensajería instantánea punto a punto</span><span class="sxs-lookup"><span data-stu-id="1738f-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1738f-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="1738f-118">Name</span></span></th>
<th><span data-ttu-id="1738f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1738f-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1738f-120"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1738f-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1738f-123">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="1738f-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1738f-p105">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="1738f-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1738f-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1738f-126">7/7/2012</span></span></p>
<p><span data-ttu-id="1738f-127">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="1738f-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1738f-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1738f-128">7/3/2012</span></span></p>
<p><span data-ttu-id="1738f-129">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="1738f-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1738f-130"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1738f-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1738f-133">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="1738f-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1738f-p107">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="1738f-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1738f-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1738f-136">7/7/2012</span></span></p>
<p><span data-ttu-id="1738f-137">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="1738f-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1738f-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1738f-138">7/3/2012</span></span></p>
<p><span data-ttu-id="1738f-139">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="1738f-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1738f-140"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1738f-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1738f-143">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1738f-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1738f-144">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="1738f-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1738f-145">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1738f-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1738f-146">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1738f-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1738f-147">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="1738f-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="1738f-148">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="1738f-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1738f-149"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-p110">Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1738f-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1738f-152">Recuento de sesiones</span><span class="sxs-lookup"><span data-stu-id="1738f-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="1738f-153">Recuento de mensajes</span><span class="sxs-lookup"><span data-stu-id="1738f-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="1738f-154">Métricas para la mensajería instantánea punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="1738f-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="1738f-155">En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1738f-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="1738f-156">Métricas para la mensajería instantánea punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="1738f-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1738f-157">Nombre</span><span class="sxs-lookup"><span data-stu-id="1738f-157">Name</span></span></th>
<th><span data-ttu-id="1738f-158">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="1738f-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1738f-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="1738f-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1738f-160"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-161">No</span><span class="sxs-lookup"><span data-stu-id="1738f-161">No</span></span></p></td>
<td><p><span data-ttu-id="1738f-162">Nombre del grupo de registradores o del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="1738f-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1738f-163"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-164">No</span><span class="sxs-lookup"><span data-stu-id="1738f-164">No</span></span></p></td>
<td><p><span data-ttu-id="1738f-165">Fecha y hora en las que tuvo lugar la sesión.</span><span class="sxs-lookup"><span data-stu-id="1738f-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1738f-166"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-167">No</span><span class="sxs-lookup"><span data-stu-id="1738f-167">No</span></span></p></td>
<td><p><span data-ttu-id="1738f-168">Cantidad total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1738f-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="1738f-169">Métricas para la mensajería instantánea punto a punto por tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="1738f-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="1738f-170">En la tabla siguiente, se muestra la información proporcionada en el informe de mensajería instantánea punto a punto para cada tipo de autenticación utilizado por los participantes de una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1738f-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="1738f-171">Métricas para la mensajería instantánea punto a punto por tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="1738f-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1738f-172">Nombre</span><span class="sxs-lookup"><span data-stu-id="1738f-172">Name</span></span></th>
<th><span data-ttu-id="1738f-173">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="1738f-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1738f-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="1738f-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1738f-175"><strong>Tipo de autenticación</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-176">No</span><span class="sxs-lookup"><span data-stu-id="1738f-176">No</span></span></p></td>
<td><p><span data-ttu-id="1738f-p111">Tipo de autenticación utilizado por los participantes de la sesión. Los valores suelen ser los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1738f-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1738f-179">Enterprise</span><span class="sxs-lookup"><span data-stu-id="1738f-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="1738f-180">Federated</span><span class="sxs-lookup"><span data-stu-id="1738f-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="1738f-181">PIC</span><span class="sxs-lookup"><span data-stu-id="1738f-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1738f-182"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-183">No</span><span class="sxs-lookup"><span data-stu-id="1738f-183">No</span></span></p></td>
<td><p><span data-ttu-id="1738f-184">Fecha y hora en las que tuvo lugar la sesión.</span><span class="sxs-lookup"><span data-stu-id="1738f-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1738f-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1738f-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1738f-186">No</span><span class="sxs-lookup"><span data-stu-id="1738f-186">No</span></span></p></td>
<td><p><span data-ttu-id="1738f-187">Cantidad total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1738f-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

