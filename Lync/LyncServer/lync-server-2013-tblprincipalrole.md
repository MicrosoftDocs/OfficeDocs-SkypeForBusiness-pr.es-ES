---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="5fbc5-102">tblPrincipalRole en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fbc5-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fbc5-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5fbc5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5fbc5-104">tblPrincipalRole contiene los roles explícitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="5fbc5-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="5fbc5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fbc5-106">Columna</span><span class="sxs-lookup"><span data-stu-id="5fbc5-106">Column</span></span></th>
<th><span data-ttu-id="5fbc5-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5fbc5-107">Type</span></span></th>
<th><span data-ttu-id="5fbc5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fbc5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fbc5-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5fbc5-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5fbc5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-111">IDENTIFICADOR de nodo al que se aplica el rol.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbc5-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5fbc5-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5fbc5-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-114">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbc5-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5fbc5-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="5fbc5-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-117">IDENTIFICADOR de tipo de rol (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="5fbc5-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbc5-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5fbc5-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="5fbc5-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-120">IDENTIFICADOR de la entidad de identidad que actualizó por última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5fbc5-121">Sus</span><span class="sxs-lookup"><span data-stu-id="5fbc5-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fbc5-122">Columna</span><span class="sxs-lookup"><span data-stu-id="5fbc5-122">Column</span></span></th>
<th><span data-ttu-id="5fbc5-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fbc5-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fbc5-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="5fbc5-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbc5-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5fbc5-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-127">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbc5-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5fbc5-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-129">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbc5-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5fbc5-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="5fbc5-131">Clave externa con la búsqueda en la tabla tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

