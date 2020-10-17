---
title: 'Lync Server 2013: subinforme de Resumen de P2P'
description: 'Lync Server 2013: subinforme de Resumen de P2P.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557386"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="8bce2-103">Subinforme de Resumen de P2P en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bce2-103">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bce2-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8bce2-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8bce2-105">El Subinforme de resumen de P2P ofrecer una vista general de todas las sesiones de comunicación de punto a punto que han presentado error.</span><span class="sxs-lookup"><span data-stu-id="8bce2-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="8bce2-106">Filtros</span><span class="sxs-lookup"><span data-stu-id="8bce2-106">Filters</span></span>

<span data-ttu-id="8bce2-p101">Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. La tabla siguiente muestra los filtros que se pueden utilizar con el Subinforme de resumen de P2P.</span><span class="sxs-lookup"><span data-stu-id="8bce2-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="8bce2-109">Filtros del Subinforme de resumen de P2P</span><span class="sxs-lookup"><span data-stu-id="8bce2-109">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bce2-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="8bce2-110">Name</span></span></th>
<th><span data-ttu-id="8bce2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bce2-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bce2-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-p102">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8bce2-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8bce2-115">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="8bce2-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8bce2-p103">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="8bce2-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8bce2-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8bce2-118">7/7/2012</span></span></p>
<p><span data-ttu-id="8bce2-119">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="8bce2-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8bce2-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8bce2-120">7/3/2012</span></span></p>
<p><span data-ttu-id="8bce2-121">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="8bce2-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bce2-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-p104">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8bce2-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8bce2-125">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="8bce2-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8bce2-p105">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="8bce2-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8bce2-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8bce2-128">7/7/2012</span></span></p>
<p><span data-ttu-id="8bce2-129">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="8bce2-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8bce2-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8bce2-130">7/3/2012</span></span></p>
<p><span data-ttu-id="8bce2-131">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="8bce2-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bce2-132"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-p106">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8bce2-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8bce2-136">Métricas</span><span class="sxs-lookup"><span data-stu-id="8bce2-136">Metrics</span></span>

<span data-ttu-id="8bce2-137">En la tabla siguiente se muestra la información recogida en el Subinforme de resumen de P2P.</span><span class="sxs-lookup"><span data-stu-id="8bce2-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="8bce2-138">Métricas del Subinforme de resumen de P2P</span><span class="sxs-lookup"><span data-stu-id="8bce2-138">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bce2-139">Nombre</span><span class="sxs-lookup"><span data-stu-id="8bce2-139">Name</span></span></th>
<th><span data-ttu-id="8bce2-140">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8bce2-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8bce2-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bce2-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bce2-142"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-142"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-143">No</span><span class="sxs-lookup"><span data-stu-id="8bce2-143">No</span></span></p></td>
<td><p><span data-ttu-id="8bce2-144">Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.</span><span class="sxs-lookup"><span data-stu-id="8bce2-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bce2-145"><strong>Porcentaje de errores</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-145"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-146">No</span><span class="sxs-lookup"><span data-stu-id="8bce2-146">No</span></span></p></td>
<td><p><span data-ttu-id="8bce2-147">Porcentaje de las sesiones punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="8bce2-147">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bce2-148"><strong>Sesiones por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-148"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-149">No</span><span class="sxs-lookup"><span data-stu-id="8bce2-149">No</span></span></p></td>
<td><p><span data-ttu-id="8bce2-150">Número total de sesiones agrupadas por modalidad (por ejemplo, mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="8bce2-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bce2-151"><strong>Porcentaje de errores por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="8bce2-151"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="8bce2-152">No</span><span class="sxs-lookup"><span data-stu-id="8bce2-152">No</span></span></p></td>
<td><p><span data-ttu-id="8bce2-153">Número total de sesiones con error agrupadas por modalidad (por ejemplo, mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="8bce2-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

