---
title: 'Lync Server 2013: tabla PurgeSettings (QoE)'
description: 'Lync Server 2013: tabla PurgeSettings (QoE).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d515d799a7cc442dc6d34f2ece1a968de51cdad6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571446"
---
# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="6274b-103">Tabla PurgeSettings (QoE) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6274b-103">PurgeSettings table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6274b-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6274b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6274b-105">La tabla PurgeSettings contiene información que especifica si (y cuándo) los registros de calidad de experiencia obsoletos se eliminarán automáticamente de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="6274b-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="6274b-106">Tenga en cuenta que también se puede obtener información relacionada con la purga desde el shell de administración de Microsoft Lync Server 2013 ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="6274b-106">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="6274b-107">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6274b-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6274b-108"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6274b-109"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6274b-110"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6274b-111"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6274b-112"><strong>Id.</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-112"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="6274b-113">entero</span><span class="sxs-lookup"><span data-stu-id="6274b-113">int</span></span></p></td>
<td><p><span data-ttu-id="6274b-114">Principal</span><span class="sxs-lookup"><span data-stu-id="6274b-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="6274b-115">Identificador único para la colección de valores de depuración de QoE.</span><span class="sxs-lookup"><span data-stu-id="6274b-115">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6274b-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="6274b-117">bit</span><span class="sxs-lookup"><span data-stu-id="6274b-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6274b-118">Cuando se establece en true (1), Microsoft Lync Server 2013 depurará periódicamente los registros obsoletos de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="6274b-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="6274b-119">La depuración tendrá lugar todos los días en el tomo especificado por la configuración PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="6274b-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="6274b-120">Si se establece en False (0), los registros no se depurarán automáticamente desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6274b-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="6274b-121">El valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="6274b-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6274b-122"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-122"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="6274b-123">entero</span><span class="sxs-lookup"><span data-stu-id="6274b-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6274b-p103">Especifica la antigüedad de los registros de QoE (en días) que se depurarán desde la base de datos: si la depuración está habilitada, se eliminarán de la base de datos los registros de QoE anteriores a este valor. El valor predeterminado es 60 días.</span><span class="sxs-lookup"><span data-stu-id="6274b-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6274b-126"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="6274b-126"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="6274b-127">entero</span><span class="sxs-lookup"><span data-stu-id="6274b-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6274b-p104">Especifica la hora local del día en la que tendrá lugar la depuración de la base de datos. La hora del día se especifica con el formato de 24 horas, donde 0 representa la media noche (12:00 AM) y 23 representa las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (indicando 10:00 \*AM) pero no se permite un valor de 10:30 de 10.5 (indicando 10:30 AM). El valor predeterminado es 1 (1:00 AM). Especifica la hora local del día en que tendrá lugar la depuración de la base de datos. La hora del día se especifica mediante un reloj de 24 horas, representando el 0 la medianoche (12:00 AM) y el 23, las 11:00 PM. Tenga en cuenta que solo puede especificar la hora del día: se permite un valor de 10 (que indica 10:00 AM) pero no se permite un valor de 10:30 de 10.5 (que indica 10:30 AM). El valor predeterminado es 1 (1:00 AM).</span><span class="sxs-lookup"><span data-stu-id="6274b-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

