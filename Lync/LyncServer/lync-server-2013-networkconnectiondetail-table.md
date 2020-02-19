---
title: 'Lync Server 2013: tabla NetworkConnectionDetail'
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
ms.openlocfilehash: bb192385cfd5d04712b0e66169326aedd6c0f1b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42128333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="6cbf4-102">Tabla NetworkConnectionDetail en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cbf4-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cbf4-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6cbf4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6cbf4-104">La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="6cbf4-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="6cbf4-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6cbf4-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cbf4-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="6cbf4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6cbf4-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="6cbf4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6cbf4-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="6cbf4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6cbf4-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="6cbf4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cbf4-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="6cbf4-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6cbf4-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="6cbf4-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6cbf4-112">Principal</span><span class="sxs-lookup"><span data-stu-id="6cbf4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6cbf4-113">Identificador único del tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="6cbf4-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cbf4-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="6cbf4-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="6cbf4-115">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="6cbf4-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6cbf4-116">Única</span><span class="sxs-lookup"><span data-stu-id="6cbf4-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="6cbf4-p102">Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="6cbf4-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="6cbf4-119">0: cableada</span><span class="sxs-lookup"><span data-stu-id="6cbf4-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="6cbf4-120">1: Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6cbf4-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="6cbf4-121">2: Ethernet</span><span class="sxs-lookup"><span data-stu-id="6cbf4-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

