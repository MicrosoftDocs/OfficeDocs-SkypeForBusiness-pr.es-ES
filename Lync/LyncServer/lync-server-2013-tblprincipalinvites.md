---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564676"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="71696-103">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71696-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71696-104">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="71696-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="71696-105">La tabla tblPrincipalInvites contiene invitaciones para todos los usuarios y para todos los nodos con la opción de invitación automática activada.</span><span class="sxs-lookup"><span data-stu-id="71696-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="71696-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="71696-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71696-107">Columna</span><span class="sxs-lookup"><span data-stu-id="71696-107">Column</span></span></th>
<th><span data-ttu-id="71696-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="71696-108">Type</span></span></th>
<th><span data-ttu-id="71696-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="71696-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71696-110">prinID</span><span class="sxs-lookup"><span data-stu-id="71696-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="71696-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="71696-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="71696-112">Id. de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="71696-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71696-113">invID</span><span class="sxs-lookup"><span data-stu-id="71696-113">invID</span></span></p></td>
<td><p><span data-ttu-id="71696-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="71696-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="71696-115">Número secuencial único (por identificador de la entidad de seguridad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="71696-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71696-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="71696-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="71696-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="71696-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="71696-118">Identificador de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="71696-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71696-119">created</span><span class="sxs-lookup"><span data-stu-id="71696-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="71696-120">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="71696-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="71696-121">Momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="71696-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="71696-122">Keys</span><span class="sxs-lookup"><span data-stu-id="71696-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71696-123">Columna</span><span class="sxs-lookup"><span data-stu-id="71696-123">Column</span></span></th>
<th><span data-ttu-id="71696-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="71696-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71696-125">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="71696-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="71696-126">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="71696-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71696-127">prinID</span><span class="sxs-lookup"><span data-stu-id="71696-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="71696-128">Clave externa con búsqueda en la tabla tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="71696-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71696-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="71696-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="71696-130">Clave externa con búsqueda en la tabla tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="71696-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

