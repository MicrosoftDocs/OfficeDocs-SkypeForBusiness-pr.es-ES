---
title: 'Lync Server 2013: subinforme de Resumen de P2P'
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
ms.openlocfilehash: ee8b2b914779cf8fde4f1e3a58d827dd355d28e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515997"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="83fd8-102">Subinforme de Resumen de P2P en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83fd8-102">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83fd8-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="83fd8-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="83fd8-104">El Subinforme de resumen de P2P ofrecer una vista general de todas las sesiones de comunicación de punto a punto que han presentado error.</span><span class="sxs-lookup"><span data-stu-id="83fd8-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="83fd8-105">Filtros</span><span class="sxs-lookup"><span data-stu-id="83fd8-105">Filters</span></span>

<span data-ttu-id="83fd8-p101">Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. La tabla siguiente muestra los filtros que se pueden utilizar con el Subinforme de resumen de P2P.</span><span class="sxs-lookup"><span data-stu-id="83fd8-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="83fd8-108">Filtros del Subinforme de resumen de P2P</span><span class="sxs-lookup"><span data-stu-id="83fd8-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83fd8-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="83fd8-109">Name</span></span></th>
<th><span data-ttu-id="83fd8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="83fd8-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83fd8-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-p102">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="83fd8-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="83fd8-114">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="83fd8-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="83fd8-p103">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="83fd8-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="83fd8-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="83fd8-117">7/7/2012</span></span></p>
<p><span data-ttu-id="83fd8-118">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="83fd8-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="83fd8-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="83fd8-119">7/3/2012</span></span></p>
<p><span data-ttu-id="83fd8-120">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="83fd8-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83fd8-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-p104">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="83fd8-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="83fd8-124">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="83fd8-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="83fd8-p105">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="83fd8-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="83fd8-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="83fd8-127">7/7/2012</span></span></p>
<p><span data-ttu-id="83fd8-128">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="83fd8-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="83fd8-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="83fd8-129">7/3/2012</span></span></p>
<p><span data-ttu-id="83fd8-130">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="83fd8-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83fd8-131"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-p106">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="83fd8-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="83fd8-135">Métricas</span><span class="sxs-lookup"><span data-stu-id="83fd8-135">Metrics</span></span>

<span data-ttu-id="83fd8-136">En la tabla siguiente se muestra la información recogida en el Subinforme de resumen de P2P.</span><span class="sxs-lookup"><span data-stu-id="83fd8-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="83fd8-137">Métricas del Subinforme de resumen de P2P</span><span class="sxs-lookup"><span data-stu-id="83fd8-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83fd8-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="83fd8-138">Name</span></span></th>
<th><span data-ttu-id="83fd8-139">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="83fd8-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="83fd8-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="83fd8-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83fd8-141"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-142">No</span><span class="sxs-lookup"><span data-stu-id="83fd8-142">No</span></span></p></td>
<td><p><span data-ttu-id="83fd8-143">Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.</span><span class="sxs-lookup"><span data-stu-id="83fd8-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83fd8-144"><strong>Porcentaje de errores</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-145">No</span><span class="sxs-lookup"><span data-stu-id="83fd8-145">No</span></span></p></td>
<td><p><span data-ttu-id="83fd8-146">Porcentaje de las sesiones punto a punto con errores.</span><span class="sxs-lookup"><span data-stu-id="83fd8-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83fd8-147"><strong>Sesiones por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-148">No</span><span class="sxs-lookup"><span data-stu-id="83fd8-148">No</span></span></p></td>
<td><p><span data-ttu-id="83fd8-149">Número total de sesiones agrupadas por modalidad (por ejemplo, mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="83fd8-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83fd8-150"><strong>Porcentaje de errores por modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="83fd8-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="83fd8-151">No</span><span class="sxs-lookup"><span data-stu-id="83fd8-151">No</span></span></p></td>
<td><p><span data-ttu-id="83fd8-152">Número total de sesiones con error agrupadas por modalidad (por ejemplo, mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="83fd8-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

