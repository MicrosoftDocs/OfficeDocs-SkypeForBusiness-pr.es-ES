---
title: 'Lync Server 2013: tabla SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="783b0-102">Tabla SIPResponseMetaData en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="783b0-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="783b0-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="783b0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="783b0-104">El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP, así como la clasificación y la definición de cada uno de esos códigos.</span><span class="sxs-lookup"><span data-stu-id="783b0-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="783b0-105">Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta la solicitud.</span><span class="sxs-lookup"><span data-stu-id="783b0-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="783b0-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="783b0-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="783b0-107">Columna</span><span class="sxs-lookup"><span data-stu-id="783b0-107">Column</span></span></th>
<th><span data-ttu-id="783b0-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="783b0-108">Data Type</span></span></th>
<th><span data-ttu-id="783b0-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="783b0-109">Key/Index</span></span></th>
<th><span data-ttu-id="783b0-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="783b0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="783b0-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="783b0-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="783b0-112">int</span><span class="sxs-lookup"><span data-stu-id="783b0-112">int</span></span></p></td>
<td><p><span data-ttu-id="783b0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="783b0-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="783b0-114">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="783b0-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="783b0-115"><strong>Las</strong></span><span class="sxs-lookup"><span data-stu-id="783b0-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="783b0-116">int</span><span class="sxs-lookup"><span data-stu-id="783b0-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="783b0-117">Clasificación general para el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="783b0-117">General classification for the response code.</span></span> <span data-ttu-id="783b0-118">Las clasificaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="783b0-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="783b0-119">1: respuestas informativas</span><span class="sxs-lookup"><span data-stu-id="783b0-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="783b0-120">2: respuestas correctas</span><span class="sxs-lookup"><span data-stu-id="783b0-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="783b0-121">3: respuestas de redireccionamiento</span><span class="sxs-lookup"><span data-stu-id="783b0-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="783b0-122">4-respuestas de error del cliente</span><span class="sxs-lookup"><span data-stu-id="783b0-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="783b0-123">5--respuestas de error de servidor</span><span class="sxs-lookup"><span data-stu-id="783b0-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="783b0-124">6: respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="783b0-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="783b0-125"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="783b0-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="783b0-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="783b0-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="783b0-127">Descripción del código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="783b0-127">Description of the SIP response code.</span></span> <span data-ttu-id="783b0-128">Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="783b0-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="783b0-129">La llamada se está reenviando</span><span class="sxs-lookup"><span data-stu-id="783b0-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

