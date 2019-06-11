---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="8eb6f-102">tblPrincipalInvites en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8eb6f-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eb6f-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8eb6f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8eb6f-104">tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con la opción de autoinvitar activada.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="8eb6f-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="8eb6f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eb6f-106">Columna</span><span class="sxs-lookup"><span data-stu-id="8eb6f-106">Column</span></span></th>
<th><span data-ttu-id="8eb6f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="8eb6f-107">Type</span></span></th>
<th><span data-ttu-id="8eb6f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8eb6f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eb6f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8eb6f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="8eb6f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-111">IDENTIFICADOR principal.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eb6f-112">invID</span><span class="sxs-lookup"><span data-stu-id="8eb6f-112">invID</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="8eb6f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-114">Número secuencial único (por identificador de entidad de identidad) generado desde la tabla tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8eb6f-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="8eb6f-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="8eb6f-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-117">IDENTIFICADOR de nodo (solo salón de chat).</span><span class="sxs-lookup"><span data-stu-id="8eb6f-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eb6f-118">creado</span><span class="sxs-lookup"><span data-stu-id="8eb6f-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="8eb6f-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-120">Momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8eb6f-121">Sus</span><span class="sxs-lookup"><span data-stu-id="8eb6f-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eb6f-122">Columna</span><span class="sxs-lookup"><span data-stu-id="8eb6f-122">Column</span></span></th>
<th><span data-ttu-id="8eb6f-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="8eb6f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eb6f-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="8eb6f-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-125">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eb6f-126">prinID</span><span class="sxs-lookup"><span data-stu-id="8eb6f-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-127">Clave externa con la búsqueda en la tabla tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8eb6f-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="8eb6f-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="8eb6f-129">Clave externa con la búsqueda en la tabla tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="8eb6f-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

