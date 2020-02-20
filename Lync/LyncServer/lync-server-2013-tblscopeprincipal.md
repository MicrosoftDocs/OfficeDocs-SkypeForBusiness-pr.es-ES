---
title: 'Lync Server 2013: tblScopePrincipal'
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
ms.openlocfilehash: 147d71ada1d0db26e95868a7115556d30cbc2435
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="a5f47-102">tblScopePrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5f47-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5f47-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a5f47-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a5f47-104">La tabla tblScopePrincipal contiene ámbitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="a5f47-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="a5f47-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a5f47-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5f47-106">Columna</span><span class="sxs-lookup"><span data-stu-id="a5f47-106">Column</span></span></th>
<th><span data-ttu-id="a5f47-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5f47-107">Type</span></span></th>
<th><span data-ttu-id="a5f47-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5f47-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5f47-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a5f47-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="a5f47-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="a5f47-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a5f47-111">Id. de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="a5f47-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5f47-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a5f47-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="a5f47-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="a5f47-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a5f47-114">Id. de entidad</span><span class="sxs-lookup"><span data-stu-id="a5f47-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5f47-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="a5f47-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="a5f47-116">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="a5f47-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="a5f47-117">True si el tipo de ámbito es Denegar; False si es Permitir.</span><span class="sxs-lookup"><span data-stu-id="a5f47-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5f47-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a5f47-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="a5f47-119">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="a5f47-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a5f47-120">Id. de la entidad que actualizó esta entrada por última vez.</span><span class="sxs-lookup"><span data-stu-id="a5f47-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a5f47-121">Keys</span><span class="sxs-lookup"><span data-stu-id="a5f47-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5f47-122">Columna</span><span class="sxs-lookup"><span data-stu-id="a5f47-122">Column</span></span></th>
<th><span data-ttu-id="a5f47-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5f47-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5f47-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="a5f47-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a5f47-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="a5f47-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5f47-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a5f47-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="a5f47-127">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="a5f47-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5f47-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a5f47-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="a5f47-129">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="a5f47-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

