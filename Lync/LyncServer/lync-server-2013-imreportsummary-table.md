---
title: 'Lync Server 2013: tabla IMReportSummary'
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
ms.openlocfilehash: 5e750da3fd42a726012f089291d3e2c770e52b44
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526637"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="5b9c6-102">Tabla IMReportSummary en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9c6-102">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b9c6-103">_**Última modificación del tema:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="5b9c6-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="5b9c6-104">La IMReportSummaryTable ofrece un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="5b9c6-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b9c6-106">Columna</span><span class="sxs-lookup"><span data-stu-id="5b9c6-106">Column</span></span></th>
<th><span data-ttu-id="5b9c6-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5b9c6-107">Data Type</span></span></th>
<th><span data-ttu-id="5b9c6-108">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="5b9c6-108">Key/Index</span></span></th>
<th><span data-ttu-id="5b9c6-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b9c6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b9c6-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b9c6-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b9c6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5b9c6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-112">Principal</span><span class="sxs-lookup"><span data-stu-id="5b9c6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-113">Fecha y hora en que comenzó la sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9c6-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="5b9c6-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="5b9c6-115">Char (1)</span><span class="sxs-lookup"><span data-stu-id="5b9c6-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-116">Principal</span><span class="sxs-lookup"><span data-stu-id="5b9c6-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b9c6-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="5b9c6-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="5b9c6-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="5b9c6-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-119">Principal</span><span class="sxs-lookup"><span data-stu-id="5b9c6-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-120">Nombre de dominio completo del grupo de servidores que hospeda la sesión.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9c6-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="5b9c6-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="5b9c6-122">entero</span><span class="sxs-lookup"><span data-stu-id="5b9c6-122">int</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-123">Principal</span><span class="sxs-lookup"><span data-stu-id="5b9c6-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="5b9c6-124">Prioridad (por ejemplo, urgente o no urgente) de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="5b9c6-125">La información de prioridad se almacena en la <a href="lync-server-2013-callpriorities-table.md">tabla CallPriorities en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b9c6-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="5b9c6-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5b9c6-127">BIGINT</span><span class="sxs-lookup"><span data-stu-id="5b9c6-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9c6-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="5b9c6-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5b9c6-129">BIGINT</span><span class="sxs-lookup"><span data-stu-id="5b9c6-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5b9c6-130">Número total de mensajes instantáneos intercambiados durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="5b9c6-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

