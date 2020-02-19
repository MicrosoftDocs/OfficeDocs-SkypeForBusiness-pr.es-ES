---
title: 'Lync Server 2013: tabla CodecDescription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5abaac01a17d89b39da4cc9d08bc40f04a801aab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="b551a-102">Tabla CodecDescription en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b551a-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b551a-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="b551a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="b551a-104">La tabla CodecDescription asigna identificadores de códec únicos a sus códecs correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b551a-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="b551a-105">Los códecs se utilizan para codificar señales digitales para la transmisión y la difusión, así como para la posterior descodificación de dichas señales para su reproducción.</span><span class="sxs-lookup"><span data-stu-id="b551a-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="b551a-106">Esta tabla se introdujo en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b551a-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b551a-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="b551a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b551a-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="b551a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b551a-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="b551a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b551a-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="b551a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b551a-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="b551a-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b551a-112">smallint</span><span class="sxs-lookup"><span data-stu-id="b551a-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="b551a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="b551a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b551a-114">Identificador único asignado a códec.</span><span class="sxs-lookup"><span data-stu-id="b551a-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b551a-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="b551a-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="b551a-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b551a-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b551a-117">Única</span><span class="sxs-lookup"><span data-stu-id="b551a-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="b551a-118">Descripción única del códec que corresponde a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="b551a-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

