---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: ddab28b269cf2b720d6935fa6d50f4bf9ea3084a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="f7af6-102">tblPrincipalRole en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7af6-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7af6-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f7af6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f7af6-104">La tabla PrincipalRole contiene roles explícitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="f7af6-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="f7af6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f7af6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7af6-106">Columna</span><span class="sxs-lookup"><span data-stu-id="f7af6-106">Column</span></span></th>
<th><span data-ttu-id="f7af6-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f7af6-107">Type</span></span></th>
<th><span data-ttu-id="f7af6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7af6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7af6-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f7af6-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="f7af6-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f7af6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7af6-111">Identificador de nodo al que se aplica el rol.</span><span class="sxs-lookup"><span data-stu-id="f7af6-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7af6-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f7af6-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="f7af6-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f7af6-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7af6-114">Identificador de la entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7af6-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7af6-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f7af6-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="f7af6-116">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f7af6-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7af6-117">Identificador de tipo de función (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="f7af6-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7af6-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f7af6-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f7af6-119">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="f7af6-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7af6-120">Id. de la entidad que actualizó esta entrada por última vez.</span><span class="sxs-lookup"><span data-stu-id="f7af6-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f7af6-121">Keys</span><span class="sxs-lookup"><span data-stu-id="f7af6-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7af6-122">Columna</span><span class="sxs-lookup"><span data-stu-id="f7af6-122">Column</span></span></th>
<th><span data-ttu-id="f7af6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7af6-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7af6-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="f7af6-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f7af6-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f7af6-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7af6-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f7af6-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="f7af6-127">Clave externa con búsqueda en la tabla RoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="f7af6-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7af6-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f7af6-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="f7af6-129">Clave externa con búsqueda en la tabla Node.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f7af6-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7af6-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f7af6-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="f7af6-131">Clave externa con búsqueda en la tabla Principal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f7af6-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

