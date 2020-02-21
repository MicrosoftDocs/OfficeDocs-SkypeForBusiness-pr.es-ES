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
ms.openlocfilehash: cf7b6627f6976001bdb1440db9aa40c33d89cfc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="6b70d-102">Tabla de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b70d-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b70d-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6b70d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6b70d-p101">La tabla Conference es una tabla auxiliar. Cada registro representa una conferencia o sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="6b70d-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b70d-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6b70d-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6b70d-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6b70d-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b70d-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6b70d-111">int</span><span class="sxs-lookup"><span data-stu-id="6b70d-111">int</span></span></p></td>
<td><p><span data-ttu-id="6b70d-112">Principal</span><span class="sxs-lookup"><span data-stu-id="6b70d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6b70d-113">Número único que identifica este registro de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6b70d-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b70d-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="6b70d-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6b70d-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6b70d-116">singular</span><span class="sxs-lookup"><span data-stu-id="6b70d-116">unique</span></span></p></td>
<td><p><span data-ttu-id="6b70d-117">ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="6b70d-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b70d-118"><strong>Suma de comprobación</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="6b70d-119">int</span><span class="sxs-lookup"><span data-stu-id="6b70d-119">int</span></span></p></td>
<td><p><span data-ttu-id="6b70d-120">index</span><span class="sxs-lookup"><span data-stu-id="6b70d-120">index</span></span></p></td>
<td><p><span data-ttu-id="6b70d-p102">Suma de comprobación del URI de conferencia. Para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6b70d-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b70d-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="6b70d-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="6b70d-124">datetime</span><span class="sxs-lookup"><span data-stu-id="6b70d-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b70d-125">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6b70d-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

