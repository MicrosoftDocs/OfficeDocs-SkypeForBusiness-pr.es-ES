---
title: 'Lync Server 2013: tabla de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f51e05c9721ca789724dcd015c62c2a71d8731
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520645"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="52f04-102">Tabla de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52f04-102">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52f04-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="52f04-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="52f04-p101">La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="52f04-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52f04-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="52f04-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="52f04-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="52f04-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52f04-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="52f04-111">entero</span><span class="sxs-lookup"><span data-stu-id="52f04-111">int</span></span></p></td>
<td><p><span data-ttu-id="52f04-112">Principal</span><span class="sxs-lookup"><span data-stu-id="52f04-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="52f04-113">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="52f04-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52f04-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="52f04-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52f04-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="52f04-116">singular</span><span class="sxs-lookup"><span data-stu-id="52f04-116">unique</span></span></p></td>
<td><p><span data-ttu-id="52f04-117">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="52f04-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52f04-118"><strong>Suma de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="52f04-119">entero</span><span class="sxs-lookup"><span data-stu-id="52f04-119">int</span></span></p></td>
<td><p><span data-ttu-id="52f04-120">index</span><span class="sxs-lookup"><span data-stu-id="52f04-120">index</span></span></p></td>
<td><p><span data-ttu-id="52f04-p102">Suma de comprobación del URI de conferencia. Para uso interno.</span><span class="sxs-lookup"><span data-stu-id="52f04-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52f04-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="52f04-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="52f04-124">datetime</span><span class="sxs-lookup"><span data-stu-id="52f04-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52f04-125">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="52f04-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

