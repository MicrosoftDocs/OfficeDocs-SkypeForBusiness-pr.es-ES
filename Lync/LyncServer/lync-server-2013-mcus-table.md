---
title: 'Lync Server 2013: Tabla Mcus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="1221d-102">Tabla Mcus en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1221d-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1221d-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1221d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1221d-104">La tabla MCU es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="1221d-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="1221d-105">Cada registro almacena información acerca de un servicio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1221d-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="1221d-106">Estos pueden incluir el servicio de conferencias de mensajería instantánea y el servicio de conferencias de telefonía (que se ejecutan como procesos en servidores de aplicaciones para el usuario), así como el servicio de conferencias por Internet y el servicio de conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="1221d-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1221d-107">Columna</span><span class="sxs-lookup"><span data-stu-id="1221d-107">Column</span></span></th>
<th><span data-ttu-id="1221d-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1221d-108">Data Type</span></span></th>
<th><span data-ttu-id="1221d-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="1221d-109">Key/Index</span></span></th>
<th><span data-ttu-id="1221d-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="1221d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1221d-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="1221d-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="1221d-112">int</span><span class="sxs-lookup"><span data-stu-id="1221d-112">int</span></span></p></td>
<td><p><span data-ttu-id="1221d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1221d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1221d-114">Número único que identifica este servidor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1221d-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1221d-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="1221d-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1221d-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1221d-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1221d-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1221d-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1221d-118">inyint</span><span class="sxs-lookup"><span data-stu-id="1221d-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="1221d-119"> Extranjero</span><span class="sxs-lookup"><span data-stu-id="1221d-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="1221d-120">Tipo de servidor de conferencia, como conf: chat (para mensajes instantáneos) o conf: audio-video.</span><span class="sxs-lookup"><span data-stu-id="1221d-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="1221d-121">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1221d-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

