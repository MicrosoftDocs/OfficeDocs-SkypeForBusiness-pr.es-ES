---
title: 'Lync Server 2013: tblPrincipalRole'
description: 'Lync Server 2013: tblPrincipalRole.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573636"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="b3be1-103">tblPrincipalRole en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3be1-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3be1-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b3be1-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b3be1-105">La tabla PrincipalRole contiene roles explícitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="b3be1-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="b3be1-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="b3be1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3be1-107">Columna</span><span class="sxs-lookup"><span data-stu-id="b3be1-107">Column</span></span></th>
<th><span data-ttu-id="b3be1-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="b3be1-108">Type</span></span></th>
<th><span data-ttu-id="b3be1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3be1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3be1-110">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b3be1-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="b3be1-111">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3be1-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b3be1-112">Identificador de nodo al que se aplica el rol.</span><span class="sxs-lookup"><span data-stu-id="b3be1-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3be1-113">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b3be1-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="b3be1-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3be1-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b3be1-115">Identificador de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="b3be1-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3be1-116">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b3be1-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="b3be1-117">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3be1-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b3be1-118">Identificador de tipo de función (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="b3be1-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3be1-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b3be1-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="b3be1-120">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3be1-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b3be1-121">Id. de la entidad que actualizó esta entrada por última vez.</span><span class="sxs-lookup"><span data-stu-id="b3be1-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b3be1-122">Keys</span><span class="sxs-lookup"><span data-stu-id="b3be1-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3be1-123">Columna</span><span class="sxs-lookup"><span data-stu-id="b3be1-123">Column</span></span></th>
<th><span data-ttu-id="b3be1-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3be1-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3be1-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="b3be1-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b3be1-126">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b3be1-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3be1-127">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b3be1-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="b3be1-128">Clave externa con búsqueda en la tabla RoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="b3be1-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3be1-129">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b3be1-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="b3be1-130">Clave externa con búsqueda en la tabla Node.nodeID.</span><span class="sxs-lookup"><span data-stu-id="b3be1-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3be1-131">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b3be1-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="b3be1-132">Clave externa con búsqueda en la tabla Principal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b3be1-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

