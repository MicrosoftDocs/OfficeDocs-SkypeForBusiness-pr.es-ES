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
ms.openlocfilehash: 72c6f15b2f0a219871436fe4451984abfddc947a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="8a0cd-102">tblScopePrincipal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a0cd-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a0cd-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8a0cd-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8a0cd-104">tblScopePrincipal contiene ámbitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="8a0cd-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="8a0cd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a0cd-106">Columna</span><span class="sxs-lookup"><span data-stu-id="8a0cd-106">Column</span></span></th>
<th><span data-ttu-id="8a0cd-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a0cd-107">Type</span></span></th>
<th><span data-ttu-id="8a0cd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a0cd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a0cd-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="8a0cd-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="8a0cd-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-111">IDENTIFICADOR de nodo al que se aplica el ámbito.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a0cd-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="8a0cd-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="8a0cd-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-114">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a0cd-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="8a0cd-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="8a0cd-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-117">Verdadero si el tipo de ámbito es denegar; False si la opción permitir.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a0cd-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8a0cd-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="8a0cd-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-120">IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8a0cd-121">Sus</span><span class="sxs-lookup"><span data-stu-id="8a0cd-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a0cd-122">Columna</span><span class="sxs-lookup"><span data-stu-id="8a0cd-122">Column</span></span></th>
<th><span data-ttu-id="8a0cd-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a0cd-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a0cd-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="8a0cd-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a0cd-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="8a0cd-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-127">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a0cd-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="8a0cd-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="8a0cd-129">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="8a0cd-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

