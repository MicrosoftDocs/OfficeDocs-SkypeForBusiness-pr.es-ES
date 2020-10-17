---
title: 'Lync Server 2013: tabla IMReportSummary'
description: 'Lync Server 2013: tabla IMReportSummary.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfafa81d1605845b29a3627321fcbc0f72ca7ac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547746"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="077aa-103">Tabla IMReportSummary en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="077aa-103">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="077aa-104">_**Última modificación del tema:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="077aa-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="077aa-105">La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización.</span><span class="sxs-lookup"><span data-stu-id="077aa-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="077aa-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="077aa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="077aa-107">Columna</span><span class="sxs-lookup"><span data-stu-id="077aa-107">Column</span></span></th>
<th><span data-ttu-id="077aa-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="077aa-108">Data Type</span></span></th>
<th><span data-ttu-id="077aa-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="077aa-109">Key/Index</span></span></th>
<th><span data-ttu-id="077aa-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="077aa-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="077aa-111"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="077aa-111"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="077aa-112">datetime</span><span class="sxs-lookup"><span data-stu-id="077aa-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="077aa-113">Principal</span><span class="sxs-lookup"><span data-stu-id="077aa-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="077aa-114">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="077aa-114">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="077aa-115"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="077aa-115"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="077aa-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="077aa-116">char(1)</span></span></p></td>
<td><p><span data-ttu-id="077aa-117">Principal</span><span class="sxs-lookup"><span data-stu-id="077aa-117">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="077aa-118"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="077aa-118"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="077aa-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="077aa-119">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="077aa-120">Principal</span><span class="sxs-lookup"><span data-stu-id="077aa-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="077aa-121">Nombre de dominio completo del grupo de servidores que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="077aa-121">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="077aa-122"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="077aa-122"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="077aa-123">entero</span><span class="sxs-lookup"><span data-stu-id="077aa-123">int</span></span></p></td>
<td><p><span data-ttu-id="077aa-124">Principal</span><span class="sxs-lookup"><span data-stu-id="077aa-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="077aa-125">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="077aa-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="077aa-126">La información de prioridad se almacena en la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="077aa-126">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="077aa-127"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="077aa-127"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="077aa-128">BIGINT</span><span class="sxs-lookup"><span data-stu-id="077aa-128">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="077aa-129"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="077aa-129"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="077aa-130">BIGINT</span><span class="sxs-lookup"><span data-stu-id="077aa-130">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="077aa-131">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="077aa-131">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

