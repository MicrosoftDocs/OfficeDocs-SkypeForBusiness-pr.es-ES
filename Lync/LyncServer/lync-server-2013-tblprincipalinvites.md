---
title: 'Lync Server 2013: tblPrincipalInvites'
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
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="f7ba7-102">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7ba7-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7ba7-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f7ba7-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f7ba7-104">tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="f7ba7-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="f7ba7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7ba7-106">Columna</span><span class="sxs-lookup"><span data-stu-id="f7ba7-106">Column</span></span></th>
<th><span data-ttu-id="f7ba7-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f7ba7-107">Type</span></span></th>
<th><span data-ttu-id="f7ba7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7ba7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7ba7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f7ba7-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f7ba7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7ba7-112">invID</span><span class="sxs-lookup"><span data-stu-id="f7ba7-112">invID</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="f7ba7-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-114">Número secuencial único (por identificador de entidad de identidad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7ba7-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="f7ba7-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="f7ba7-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-117">IDENTIFICADOR de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="f7ba7-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7ba7-118">creado</span><span class="sxs-lookup"><span data-stu-id="f7ba7-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="f7ba7-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-120">Momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f7ba7-121">Sus</span><span class="sxs-lookup"><span data-stu-id="f7ba7-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7ba7-122">Columna</span><span class="sxs-lookup"><span data-stu-id="f7ba7-122">Column</span></span></th>
<th><span data-ttu-id="f7ba7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7ba7-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7ba7-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="f7ba7-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7ba7-126">prinID</span><span class="sxs-lookup"><span data-stu-id="f7ba7-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-127">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7ba7-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="f7ba7-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f7ba7-129">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

