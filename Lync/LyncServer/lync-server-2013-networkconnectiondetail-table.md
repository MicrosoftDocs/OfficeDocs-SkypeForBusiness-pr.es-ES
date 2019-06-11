---
title: 'Lync Server 2013: tabla NetworkConnectionDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 281e2d87088a56fdf46c045171772df00b1d9cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="1b4f0-102">Tabla NetworkConnectionDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b4f0-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b4f0-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1b4f0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1b4f0-104">La tabla NetworkConnectionDetail se asigna a los identificadores de conexión de red que se usan en otras partes de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="1b4f0-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b4f0-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="1b4f0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1b4f0-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="1b4f0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1b4f0-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="1b4f0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1b4f0-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="1b4f0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b4f0-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="1b4f0-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4f0-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="1b4f0-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1b4f0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1b4f0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b4f0-113">Identificador único del tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b4f0-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="1b4f0-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="1b4f0-115">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="1b4f0-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1b4f0-116">Solo</span><span class="sxs-lookup"><span data-stu-id="1b4f0-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="1b4f0-117">Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-117">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="1b4f0-118">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="1b4f0-118">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="1b4f0-119">0: conectado</span><span class="sxs-lookup"><span data-stu-id="1b4f0-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="1b4f0-120">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="1b4f0-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="1b4f0-121">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="1b4f0-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

