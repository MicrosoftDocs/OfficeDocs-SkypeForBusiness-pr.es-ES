---
title: 'Lync Server 2013: tabla NetworkConnectionDetail'
description: 'Lync Server 2013: tabla NetworkConnectionDetail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd0f429999b6629826a9f9369d154afe3c1af2f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561406"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="3f563-103">Tabla NetworkConnectionDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f563-103">NetworkConnectionDetail table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f563-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3f563-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3f563-105">La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="3f563-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3f563-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f563-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f563-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="3f563-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3f563-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="3f563-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3f563-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="3f563-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3f563-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="3f563-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f563-111"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="3f563-111"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3f563-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f563-112">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f563-113">Principal</span><span class="sxs-lookup"><span data-stu-id="3f563-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f563-114">Identificador único del tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="3f563-114">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f563-115"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="3f563-115"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="3f563-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="3f563-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3f563-117">Única</span><span class="sxs-lookup"><span data-stu-id="3f563-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="3f563-p102">Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="3f563-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="3f563-120">0: cableada</span><span class="sxs-lookup"><span data-stu-id="3f563-120">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="3f563-121">1: Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3f563-121">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="3f563-122">2: Ethernet</span><span class="sxs-lookup"><span data-stu-id="3f563-122">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

