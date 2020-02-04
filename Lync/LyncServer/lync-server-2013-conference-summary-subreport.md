---
title: 'Lync Server 2013: subinforme del Resumen de la Conferencia'
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
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="683d8-102">Informe subinforme Resumen de la Conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="683d8-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="683d8-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="683d8-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="683d8-p101">El Subinforme de resumen de conferencia proporciona información general de sesiones de conferencia fallidas. Estas sesiones fallidas se dividen además por tipo de sesión: sesiones de foco y sesiones MCU.</span><span class="sxs-lookup"><span data-stu-id="683d8-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="683d8-106">Filtros</span><span class="sxs-lookup"><span data-stu-id="683d8-106">Filters</span></span>

<span data-ttu-id="683d8-p102">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. En la tabla siguiente, se muestran los filtros que se pueden utilizar en el Subinforme de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="683d8-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="683d8-109">Filtros del Subinforme de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="683d8-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="683d8-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="683d8-110">Name</span></span></th>
<th><span data-ttu-id="683d8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="683d8-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="683d8-112"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-p103">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="683d8-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="683d8-115">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="683d8-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="683d8-p104">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="683d8-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="683d8-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="683d8-118">7/7/2012</span></span></p>
<p><span data-ttu-id="683d8-119">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="683d8-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="683d8-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="683d8-120">7/3/2012</span></span></p>
<p><span data-ttu-id="683d8-121">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="683d8-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683d8-122"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-p105">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="683d8-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="683d8-125">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="683d8-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="683d8-p106">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="683d8-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="683d8-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="683d8-128">7/7/2012</span></span></p>
<p><span data-ttu-id="683d8-129">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="683d8-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="683d8-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="683d8-130">7/3/2012</span></span></p>
<p><span data-ttu-id="683d8-131">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="683d8-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="683d8-132"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-p107">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todos]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="683d8-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="683d8-136">Métricas</span><span class="sxs-lookup"><span data-stu-id="683d8-136">Metrics</span></span>

<span data-ttu-id="683d8-137">La siguiente tabla contiene la información que recoge el Subinforme de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="683d8-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="683d8-138">Métricas del Subinforme de resumen de conferencia</span><span class="sxs-lookup"><span data-stu-id="683d8-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="683d8-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="683d8-139">Name</span></span></th>
<th><span data-ttu-id="683d8-140">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="683d8-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="683d8-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="683d8-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="683d8-142"><strong>Total de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-143">No</span><span class="sxs-lookup"><span data-stu-id="683d8-143">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-144">Cantidad total de conferencias que ha tenido lugar.</span><span class="sxs-lookup"><span data-stu-id="683d8-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683d8-145"><strong>Total de sesiones de conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-146">No</span><span class="sxs-lookup"><span data-stu-id="683d8-146">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-p108">Cantidad total de sesiones de conferencia. Una única conferencia puede tener varias sesiones; por ejemplo, una conferencia podría incluir tanto una sesión de foco como una sesión MCU.</span><span class="sxs-lookup"><span data-stu-id="683d8-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="683d8-149"><strong>Porcentaje de errores de sesión generales</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-150">No</span><span class="sxs-lookup"><span data-stu-id="683d8-150">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-151">Porcentaje de todas las conferencias fallidas.</span><span class="sxs-lookup"><span data-stu-id="683d8-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683d8-152"><strong>Sesiones de foco</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-153">No</span><span class="sxs-lookup"><span data-stu-id="683d8-153">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-154">Cantidad total de sesiones de foco.</span><span class="sxs-lookup"><span data-stu-id="683d8-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="683d8-155"><strong>Porcentaje de errores de foco</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-156">No</span><span class="sxs-lookup"><span data-stu-id="683d8-156">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-157">Porcentaje de sesiones de foco fallidas.</span><span class="sxs-lookup"><span data-stu-id="683d8-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683d8-158">Sesiones MCU</span><span class="sxs-lookup"><span data-stu-id="683d8-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="683d8-159">No</span><span class="sxs-lookup"><span data-stu-id="683d8-159">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-160">Cantidad total de sesiones MCU.</span><span class="sxs-lookup"><span data-stu-id="683d8-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="683d8-161"><strong>Porcentaje de errores de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-162">No</span><span class="sxs-lookup"><span data-stu-id="683d8-162">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-163">Porcentaje de sesiones MCU fallidas.</span><span class="sxs-lookup"><span data-stu-id="683d8-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683d8-164"><strong>Sesiones MCU por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-165">No</span><span class="sxs-lookup"><span data-stu-id="683d8-165">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-166">Cantidad total de sesiones MCU, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="683d8-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="683d8-167"><strong>Porcentaje de errores por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="683d8-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="683d8-168">No</span><span class="sxs-lookup"><span data-stu-id="683d8-168">No</span></span></p></td>
<td><p><span data-ttu-id="683d8-169">Porcentaje de sesiones MCU fallidas, agrupadas por modalidad (por ejemplo, conferencia de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="683d8-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

