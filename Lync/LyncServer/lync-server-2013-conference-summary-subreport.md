---
title: 'Lync Server 2013: subinforme del Resumen de la Conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b87ea9648404f495f487a639a3b11900f91dcda4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="97d0b-102">Informe subinforme Resumen de la Conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97d0b-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97d0b-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="97d0b-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="97d0b-p101">El Subinforme de resumen de conferencia proporciona información general de sesiones de conferencia fallidas. Estas sesiones fallidas se dividen además por tipo de sesión: sesiones de foco y sesiones MCU.</span><span class="sxs-lookup"><span data-stu-id="97d0b-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="97d0b-106">Filtros</span><span class="sxs-lookup"><span data-stu-id="97d0b-106">Filters</span></span>

<span data-ttu-id="97d0b-p102">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Subinforme de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="97d0b-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="97d0b-109">Filtros del Subinforme de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="97d0b-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97d0b-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="97d0b-110">Name</span></span></th>
<th><span data-ttu-id="97d0b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="97d0b-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-112"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-p103">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="97d0b-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="97d0b-115">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="97d0b-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="97d0b-p104">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="97d0b-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="97d0b-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="97d0b-118">7/7/2012</span></span></p>
<p><span data-ttu-id="97d0b-119">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="97d0b-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="97d0b-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="97d0b-120">7/3/2012</span></span></p>
<p><span data-ttu-id="97d0b-121">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="97d0b-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d0b-122"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-p105">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="97d0b-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="97d0b-125">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="97d0b-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="97d0b-p106">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="97d0b-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="97d0b-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="97d0b-128">7/7/2012</span></span></p>
<p><span data-ttu-id="97d0b-129">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="97d0b-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="97d0b-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="97d0b-130">7/3/2012</span></span></p>
<p><span data-ttu-id="97d0b-131">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="97d0b-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-132"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-p107">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="97d0b-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="97d0b-136">Métricas</span><span class="sxs-lookup"><span data-stu-id="97d0b-136">Metrics</span></span>

<span data-ttu-id="97d0b-137">La siguiente tabla contiene la información que recoge el Subinforme de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="97d0b-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="97d0b-138">Métricas del Subinforme de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="97d0b-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97d0b-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="97d0b-139">Name</span></span></th>
<th><span data-ttu-id="97d0b-140">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="97d0b-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="97d0b-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="97d0b-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-142"><strong>Total de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-143">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-143">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-144">Cantidad total de conferencias que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="97d0b-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d0b-145"><strong>Total de sesiones de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-146">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-146">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-p108">Cantidad total de sesiones de conferencia. Una única conferencia puede tener varias sesiones; por ejemplo, una conferencia podría incluir tanto una sesión de foco como una sesión MCU.</span><span class="sxs-lookup"><span data-stu-id="97d0b-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-149"><strong>Porcentaje de errores de sesión generales</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-150">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-150">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-151">Porcentaje de todas las conferencias fallidas.</span><span class="sxs-lookup"><span data-stu-id="97d0b-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d0b-152"><strong>Sesiones de foco</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-153">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-153">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-154">Cantidad total de sesiones de foco.</span><span class="sxs-lookup"><span data-stu-id="97d0b-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-155"><strong>Porcentaje de errores de foco</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-156">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-156">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-157">Porcentaje de sesiones de foco fallidas.</span><span class="sxs-lookup"><span data-stu-id="97d0b-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d0b-158">Sesiones MCU</span><span class="sxs-lookup"><span data-stu-id="97d0b-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="97d0b-159">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-159">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-160">Cantidad total de sesiones MCU.</span><span class="sxs-lookup"><span data-stu-id="97d0b-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-161"><strong>Porcentaje de errores de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-162">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-162">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-163">Porcentaje de sesiones MCU fallidas.</span><span class="sxs-lookup"><span data-stu-id="97d0b-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97d0b-164"><strong>Sesiones MCU por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-165">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-165">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-166">Cantidad total de sesiones MCU, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="97d0b-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97d0b-167"><strong>Porcentaje de errores por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="97d0b-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="97d0b-168">No</span><span class="sxs-lookup"><span data-stu-id="97d0b-168">No</span></span></p></td>
<td><p><span data-ttu-id="97d0b-169">Porcentaje de sesiones MCU fallidas, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="97d0b-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

