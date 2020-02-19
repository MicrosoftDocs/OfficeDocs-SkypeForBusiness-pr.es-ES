---
title: 'Lync Server 2013: informe de tendencias de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5ee9e9158532c2ac430c8a41426765d6b01d56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="7107a-102">Informe de tendencias de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7107a-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7107a-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7107a-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7107a-104">El informe de tendencias de ubicación proporciona información sobre la tendencia de calidad de las llamadas de las ubicaciones de red.</span><span class="sxs-lookup"><span data-stu-id="7107a-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="7107a-105">Filtros</span><span class="sxs-lookup"><span data-stu-id="7107a-105">Filters</span></span>

<span data-ttu-id="7107a-p101">Los filtros son un modo de recuperar un conjunto de datos más específico o de ver los datos devueltos de diferentes formas. Por ejemplo, el informe de tendencias de ubicación permite filtrar los datos devueltos por tipo de acceso (acceso interno o externo) o por tipo de conexión de red (cableada o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día o semana.</span><span class="sxs-lookup"><span data-stu-id="7107a-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="7107a-110">En la siguiente tabla se muestran los filtros que se pueden usar con el informe de tendencias de ubicación.</span><span class="sxs-lookup"><span data-stu-id="7107a-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="7107a-111">Filtros del informe de tendencias de ubicación</span><span class="sxs-lookup"><span data-stu-id="7107a-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7107a-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="7107a-112">Name</span></span></th>
<th><span data-ttu-id="7107a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7107a-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7107a-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7107a-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7107a-p102">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7107a-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7107a-117">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="7107a-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7107a-p103">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="7107a-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7107a-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7107a-120">7/7/2012</span></span></p>
<p><span data-ttu-id="7107a-121">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="7107a-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7107a-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7107a-122">7/3/2012</span></span></p>
<p><span data-ttu-id="7107a-123">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="7107a-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7107a-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7107a-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7107a-p104">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7107a-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7107a-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7107a-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7107a-p105">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="7107a-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7107a-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7107a-130">7/7/2012</span></span></p>
<p><span data-ttu-id="7107a-131">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="7107a-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7107a-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7107a-132">7/3/2012</span></span></p>
<p><span data-ttu-id="7107a-133">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="7107a-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7107a-134"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="7107a-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7107a-p106">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7107a-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7107a-137">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="7107a-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7107a-138">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="7107a-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7107a-139">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="7107a-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7107a-p107">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando por la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio 1/1/2011 y una fecha de finalización 28/2/2011, se mostrarán los datos correspondientes a los días entre el 1/8/2011 a las 12:00 horas y el 1/9/2011 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="7107a-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7107a-142"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="7107a-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="7107a-p108">Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7107a-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7107a-145">Todos</span><span class="sxs-lookup"><span data-stu-id="7107a-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="7107a-146">Interno</span><span class="sxs-lookup"><span data-stu-id="7107a-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="7107a-147">External</span><span class="sxs-lookup"><span data-stu-id="7107a-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7107a-148"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="7107a-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="7107a-p109">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7107a-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7107a-151">Todos</span><span class="sxs-lookup"><span data-stu-id="7107a-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="7107a-152">Cableada</span><span class="sxs-lookup"><span data-stu-id="7107a-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="7107a-153">Wireless</span><span class="sxs-lookup"><span data-stu-id="7107a-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7107a-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="7107a-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7107a-p110">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7107a-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7107a-157">Todos</span><span class="sxs-lookup"><span data-stu-id="7107a-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="7107a-158">VPN</span><span class="sxs-lookup"><span data-stu-id="7107a-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="7107a-159">No VPN</span><span class="sxs-lookup"><span data-stu-id="7107a-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

