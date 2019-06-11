---
title: 'Lync Server 2013: tabla PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="e2eb6-102">Tabla PurgeSettings en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2eb6-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2eb6-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e2eb6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e2eb6-104">La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="e2eb6-105">Tenga en cuenta que la información relacionada con la purga también puede obtenerse en el shell de administración de Microsoft Lync Server 2013 ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e2eb6-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="e2eb6-106">Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios en la configuración de depuración de detalles de llamada solo deben realizarse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) o [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e2eb6-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="e2eb6-107">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2eb6-108">Columna</span><span class="sxs-lookup"><span data-stu-id="e2eb6-108">Column</span></span></th>
<th><span data-ttu-id="e2eb6-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e2eb6-109">Data Type</span></span></th>
<th><span data-ttu-id="e2eb6-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="e2eb6-110">Key/Index</span></span></th>
<th><span data-ttu-id="e2eb6-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="e2eb6-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2eb6-112"><strong>Identificar</strong></span><span class="sxs-lookup"><span data-stu-id="e2eb6-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="e2eb6-113">int</span><span class="sxs-lookup"><span data-stu-id="e2eb6-113">int</span></span></p></td>
<td><p><span data-ttu-id="e2eb6-114">Primary</span><span class="sxs-lookup"><span data-stu-id="e2eb6-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="e2eb6-115">Identificador único de la colección de configuración de purga de CDR.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2eb6-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="e2eb6-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="e2eb6-117">bit</span><span class="sxs-lookup"><span data-stu-id="e2eb6-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2eb6-118">Cuando se establece en true (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="e2eb6-119">La purga se realizará cada día a la tomé especificada por el valor PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="e2eb6-120">Si se establece en false (0), los registros no se purgarán automáticamente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="e2eb6-121">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2eb6-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="e2eb6-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="e2eb6-123">int</span><span class="sxs-lookup"><span data-stu-id="e2eb6-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2eb6-124">Especifica la antigüedad de los registros de CDR (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros CDR anteriores a este valor se eliminarán de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="e2eb6-125">El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2eb6-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="e2eb6-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="e2eb6-127">int</span><span class="sxs-lookup"><span data-stu-id="e2eb6-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2eb6-128">Especifica los registros de informe de antigüedad de errores (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros de informe de errores anteriores a este valor se quitarán de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="e2eb6-129">El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2eb6-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="e2eb6-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="e2eb6-131">int</span><span class="sxs-lookup"><span data-stu-id="e2eb6-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e2eb6-132">Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="e2eb6-133">La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM.</span><span class="sxs-lookup"><span data-stu-id="e2eb6-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="e2eb6-134">Tenga en cuenta que solo se puede especificar la hora del día: un valor de 10 (indicando 10:00 A.M.), pero no se permite un valor de 10:30 de 10,5 (que indica 10:30 A.M.).</span><span class="sxs-lookup"><span data-stu-id="e2eb6-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="e2eb6-135">El valor predeterminado es 2 (2:00 AM).</span><span class="sxs-lookup"><span data-stu-id="e2eb6-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

