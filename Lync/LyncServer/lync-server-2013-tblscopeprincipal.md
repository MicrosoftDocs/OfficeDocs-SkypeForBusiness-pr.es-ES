---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555616"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="22e8a-103">tblScopePrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22e8a-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22e8a-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="22e8a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="22e8a-105">La tabla tblScopePrincipal contiene ámbitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="22e8a-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="22e8a-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="22e8a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22e8a-107">Columna</span><span class="sxs-lookup"><span data-stu-id="22e8a-107">Column</span></span></th>
<th><span data-ttu-id="22e8a-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="22e8a-108">Type</span></span></th>
<th><span data-ttu-id="22e8a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="22e8a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22e8a-110">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="22e8a-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="22e8a-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="22e8a-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22e8a-112">Id. de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="22e8a-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22e8a-113">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="22e8a-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="22e8a-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="22e8a-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22e8a-115">Id. de entidad</span><span class="sxs-lookup"><span data-stu-id="22e8a-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22e8a-116">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="22e8a-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="22e8a-117">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="22e8a-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="22e8a-118">True si el tipo de ámbito es Denegar; False si es Permitir.</span><span class="sxs-lookup"><span data-stu-id="22e8a-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22e8a-119">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="22e8a-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="22e8a-120">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="22e8a-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="22e8a-121">Id. de la entidad que actualizó esta entrada por última vez.</span><span class="sxs-lookup"><span data-stu-id="22e8a-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="22e8a-122">Keys</span><span class="sxs-lookup"><span data-stu-id="22e8a-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22e8a-123">Columna</span><span class="sxs-lookup"><span data-stu-id="22e8a-123">Column</span></span></th>
<th><span data-ttu-id="22e8a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="22e8a-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22e8a-125">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="22e8a-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="22e8a-126">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="22e8a-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22e8a-127">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="22e8a-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="22e8a-128">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="22e8a-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22e8a-129">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="22e8a-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="22e8a-130">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="22e8a-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

