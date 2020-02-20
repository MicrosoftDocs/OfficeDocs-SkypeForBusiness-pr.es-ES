---
title: 'Lync Server 2013: tabla MCU'
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
ms.openlocfilehash: ad3037f81ccfe2b54f464a3e84d34a97366a3bb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="ad41a-102">Tabla MCU en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad41a-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad41a-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ad41a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ad41a-104">La tabla MCU es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="ad41a-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="ad41a-105">Cada registro almacena información sobre un servicio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ad41a-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="ad41a-106">Estos pueden incluir el servicio de conferencia de mensajería instantánea y el servicio de conferencia de telefonía (que se ejecutan como procesos en los servidores front-end) y el servicio de conferencia web y el servicio de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="ad41a-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad41a-107">Columna</span><span class="sxs-lookup"><span data-stu-id="ad41a-107">Column</span></span></th>
<th><span data-ttu-id="ad41a-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ad41a-108">Data Type</span></span></th>
<th><span data-ttu-id="ad41a-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="ad41a-109">Key/Index</span></span></th>
<th><span data-ttu-id="ad41a-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="ad41a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad41a-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="ad41a-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad41a-112">int</span><span class="sxs-lookup"><span data-stu-id="ad41a-112">int</span></span></p></td>
<td><p><span data-ttu-id="ad41a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="ad41a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ad41a-114">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="ad41a-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad41a-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="ad41a-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ad41a-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ad41a-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad41a-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ad41a-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad41a-118">inyint</span><span class="sxs-lookup"><span data-stu-id="ad41a-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="ad41a-119"> Externa</span><span class="sxs-lookup"><span data-stu-id="ad41a-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="ad41a-120">Tipo de servidor de conferencia, como conf: chat (para IMs) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="ad41a-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="ad41a-121">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ad41a-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

