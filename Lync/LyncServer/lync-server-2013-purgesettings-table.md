---
title: 'Lync Server 2013: tabla PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="58368-102">Tabla PurgeSettings en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58368-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58368-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="58368-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="58368-104">La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="58368-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="58368-105">Tenga en cuenta que la información relacionada con la purga también puede obtenerse en el shell de administración de Microsoft Lync Server 2013 ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="58368-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="58368-106">Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios en la configuración de depuración de detalles de llamada solo deben realizarse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) o [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="58368-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="58368-107">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58368-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58368-108">Columna</span><span class="sxs-lookup"><span data-stu-id="58368-108">Column</span></span></th>
<th><span data-ttu-id="58368-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="58368-109">Data Type</span></span></th>
<th><span data-ttu-id="58368-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="58368-110">Key/Index</span></span></th>
<th><span data-ttu-id="58368-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="58368-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58368-112"><strong>Identificar</strong></span><span class="sxs-lookup"><span data-stu-id="58368-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="58368-113">int</span><span class="sxs-lookup"><span data-stu-id="58368-113">int</span></span></p></td>
<td><p><span data-ttu-id="58368-114">Primary</span><span class="sxs-lookup"><span data-stu-id="58368-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="58368-115">Identificador único de la colección de configuración de purga de CDR.</span><span class="sxs-lookup"><span data-stu-id="58368-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58368-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="58368-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="58368-117">bit</span><span class="sxs-lookup"><span data-stu-id="58368-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58368-118">Cuando se establece en true (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="58368-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="58368-119">La purga se realizará cada día a la tomé especificada por el valor PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="58368-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="58368-120">Si se establece en false (0), los registros no se purgarán automáticamente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="58368-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="58368-121">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="58368-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58368-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="58368-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="58368-123">int</span><span class="sxs-lookup"><span data-stu-id="58368-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58368-124">Especifica la antigüedad de los registros de CDR (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros CDR anteriores a este valor se eliminarán de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="58368-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="58368-125">El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="58368-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58368-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="58368-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="58368-127">int</span><span class="sxs-lookup"><span data-stu-id="58368-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58368-128">Especifica los registros de informe de antigüedad de errores (en días) que se purgarán de la base de datos: Si la purga está habilitada, los registros de informe de errores anteriores a este valor se quitarán de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="58368-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="58368-129">El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="58368-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58368-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="58368-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="58368-131">int</span><span class="sxs-lookup"><span data-stu-id="58368-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58368-132">Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="58368-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="58368-133">La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM.</span><span class="sxs-lookup"><span data-stu-id="58368-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="58368-134">Tenga en cuenta que solo se puede especificar la hora del día: un valor de 10 (indicando 10:00 A.M.), pero no se permite un valor de 10:30 de 10,5 (que indica 10:30 A.M.).</span><span class="sxs-lookup"><span data-stu-id="58368-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="58368-135">El valor predeterminado es 2 (2:00 AM).</span><span class="sxs-lookup"><span data-stu-id="58368-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

