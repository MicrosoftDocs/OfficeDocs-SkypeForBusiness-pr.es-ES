---
title: 'Lync Server 2013: tabla MCU'
description: 'Lync Server 2013: tabla MCU.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b5d0bcbebb5efc1d767776b4581b18d9f2ed18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556486"
---
# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="4974d-103">Tabla MCU en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4974d-103">Mcus table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4974d-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4974d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4974d-105">La tabla MCU es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="4974d-105">The Mcus table is a supporting table.</span></span> <span data-ttu-id="4974d-106">Cada registro almacena información sobre un servicio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4974d-106">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="4974d-107">Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en los servidores front-end) y el servicio de conferencia web y el servicio de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="4974d-107">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4974d-108">Columna</span><span class="sxs-lookup"><span data-stu-id="4974d-108">Column</span></span></th>
<th><span data-ttu-id="4974d-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4974d-109">Data Type</span></span></th>
<th><span data-ttu-id="4974d-110">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="4974d-110">Key/Index</span></span></th>
<th><span data-ttu-id="4974d-111">Detalles</span><span class="sxs-lookup"><span data-stu-id="4974d-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4974d-112"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="4974d-112"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="4974d-113">entero</span><span class="sxs-lookup"><span data-stu-id="4974d-113">int</span></span></p></td>
<td><p><span data-ttu-id="4974d-114">Principal</span><span class="sxs-lookup"><span data-stu-id="4974d-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4974d-115">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4974d-115">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4974d-116"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="4974d-116"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4974d-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4974d-117">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4974d-118"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4974d-118"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4974d-119">inyint</span><span class="sxs-lookup"><span data-stu-id="4974d-119">inyint</span></span></p></td>
<td><p><span data-ttu-id="4974d-120"> Externa</span><span class="sxs-lookup"><span data-stu-id="4974d-120"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="4974d-121">Tipo de servidor de conferencia, como conf: chat (para IMs) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="4974d-121">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="4974d-122">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4974d-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

