---
title: 'Lync Server 2013: subinforme de Resumen de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cc0e61333b491a4d28e42167a9e60823e0331d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="2f00e-102">Subinforme de Resumen de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f00e-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f00e-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2f00e-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2f00e-p101">El Subinforme de resumen de conferencia proporciona información general de sesiones de conferencia fallidas. Estas sesiones fallidas se dividen además por tipo de sesión: sesiones de foco y sesiones MCU.</span><span class="sxs-lookup"><span data-stu-id="2f00e-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="2f00e-106">Filtros</span><span class="sxs-lookup"><span data-stu-id="2f00e-106">Filters</span></span>

<span data-ttu-id="2f00e-p102">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Subinforme de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f00e-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="2f00e-109">Filtros del Subinforme de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="2f00e-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f00e-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="2f00e-110">Name</span></span></th>
<th><span data-ttu-id="2f00e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f00e-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-p103">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2f00e-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2f00e-115">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="2f00e-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2f00e-p104">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="2f00e-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2f00e-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2f00e-118">7/7/2012</span></span></p>
<p><span data-ttu-id="2f00e-119">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="2f00e-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2f00e-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2f00e-120">7/3/2012</span></span></p>
<p><span data-ttu-id="2f00e-121">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="2f00e-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f00e-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-p105">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2f00e-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2f00e-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2f00e-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2f00e-p106">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="2f00e-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2f00e-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2f00e-128">7/7/2012</span></span></p>
<p><span data-ttu-id="2f00e-129">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="2f00e-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2f00e-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2f00e-130">7/3/2012</span></span></p>
<p><span data-ttu-id="2f00e-131">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="2f00e-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-p107">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f00e-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2f00e-136">Métricas</span><span class="sxs-lookup"><span data-stu-id="2f00e-136">Metrics</span></span>

<span data-ttu-id="2f00e-137">La siguiente tabla contiene la información que recoge el Subinforme de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="2f00e-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="2f00e-138">Métricas del Subinforme de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="2f00e-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f00e-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="2f00e-139">Name</span></span></th>
<th><span data-ttu-id="2f00e-140">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="2f00e-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2f00e-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f00e-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-142"><strong>Total de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-143">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-143">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-144">Número total de conferencias que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="2f00e-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f00e-145"><strong>Total de sesiones de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-146">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-146">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-p108">Número total de sesiones de conferencia. Una única conferencia puede tener varias sesiones; por ejemplo, una conferencia podría incluir tanto una sesión de foco como una sesión MCU.</span><span class="sxs-lookup"><span data-stu-id="2f00e-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-149"><strong>Porcentaje de errores de sesión generales</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-150">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-150">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-151">Porcentaje de todas las conferencias fallidas.</span><span class="sxs-lookup"><span data-stu-id="2f00e-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f00e-152"><strong>Sesiones de foco</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-153">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-153">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-154">Número total de sesiones de foco.</span><span class="sxs-lookup"><span data-stu-id="2f00e-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-155"><strong>Porcentaje de errores de foco</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-156">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-156">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-157">Porcentaje de sesiones de foco fallidas.</span><span class="sxs-lookup"><span data-stu-id="2f00e-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f00e-158">Sesiones MCU</span><span class="sxs-lookup"><span data-stu-id="2f00e-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="2f00e-159">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-159">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-160">Número total de sesiones MCU.</span><span class="sxs-lookup"><span data-stu-id="2f00e-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-161"><strong>Porcentaje de errores de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-162">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-162">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-163">Porcentaje de sesiones MCU fallidas.</span><span class="sxs-lookup"><span data-stu-id="2f00e-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f00e-164"><strong>Sesiones MCU por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-165">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-165">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-166">Número total de sesiones MCU, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="2f00e-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f00e-167"><strong>Porcentaje de errores por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="2f00e-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="2f00e-168">No</span><span class="sxs-lookup"><span data-stu-id="2f00e-168">No</span></span></p></td>
<td><p><span data-ttu-id="2f00e-169">Porcentaje de sesiones MCU fallidas, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="2f00e-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

