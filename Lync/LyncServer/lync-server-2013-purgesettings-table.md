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
ms.openlocfilehash: 32522f0818b95e829bbb643dea8749e2f91d1f31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="27a87-102">Tabla PurgeSettings en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27a87-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27a87-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="27a87-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="27a87-104">La tabla PurgeSettings contiene información que especifica si los registros de detalles de llamadas obsoletos se eliminarán automáticamente de la base de datos de CDR (y, en caso de que sí, cuándo).</span><span class="sxs-lookup"><span data-stu-id="27a87-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="27a87-105">Tenga en cuenta que también se puede obtener información relacionada con la purga desde el shell de administración de Microsoft Lync Server 2013 ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="27a87-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="27a87-106">Los administradores deben tratar la tabla PurgeSettings como de solo lectura: los cambios en la configuración de depuración de detalles de llamadas solo deben realizarse con los cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) o [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="27a87-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="27a87-107">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27a87-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27a87-108">Columna</span><span class="sxs-lookup"><span data-stu-id="27a87-108">Column</span></span></th>
<th><span data-ttu-id="27a87-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="27a87-109">Data Type</span></span></th>
<th><span data-ttu-id="27a87-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="27a87-110">Key/Index</span></span></th>
<th><span data-ttu-id="27a87-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="27a87-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27a87-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="27a87-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="27a87-113">int</span><span class="sxs-lookup"><span data-stu-id="27a87-113">int</span></span></p></td>
<td><p><span data-ttu-id="27a87-114">Principal</span><span class="sxs-lookup"><span data-stu-id="27a87-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="27a87-115">Identificador único de la recopilación de opciones de configuración para depuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="27a87-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27a87-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="27a87-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="27a87-117">bit</span><span class="sxs-lookup"><span data-stu-id="27a87-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27a87-118">Cuando se establece en true (1), Microsoft Lync Server 2013 purgará periódicamente los registros obsoletos de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="27a87-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="27a87-119">La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="27a87-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="27a87-120">Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="27a87-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="27a87-121">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="27a87-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27a87-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="27a87-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="27a87-123">int</span><span class="sxs-lookup"><span data-stu-id="27a87-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27a87-p103">Especifica la antigüedad de los registros de CDR (en días) que se depurarán de la base de datos: si se habilita la depuración, los registros de CDR cuya antigüedad sea mayor que este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="27a87-p103">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27a87-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="27a87-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="27a87-127">int</span><span class="sxs-lookup"><span data-stu-id="27a87-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27a87-p104">Especifica la antigüedad de los registros de informe de errores (en días) que se depurarán de la base de datos: si se habilita la depuración, los registros de informe de errores cuya antigüedad sea mayor que este valor se eliminarán de la base de datos. El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="27a87-p104">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27a87-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="27a87-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="27a87-131">int</span><span class="sxs-lookup"><span data-stu-id="27a87-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27a87-p105">Especifica la hora local del día a la que se realizará la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo se pueden especificar horas en formato convencional: se permite un valor 10 (que indicaría las 10:00 a.m.), pero no un valor 10:30 o 10.5 (que indicaría las 10:30 a.m.). El valor predeterminado es 2 (2:00 AM).</span><span class="sxs-lookup"><span data-stu-id="27a87-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

