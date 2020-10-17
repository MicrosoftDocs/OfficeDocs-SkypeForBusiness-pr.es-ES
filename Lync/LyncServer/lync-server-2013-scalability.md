---
title: Lync Server 2013 escalabilidad
description: Lync Server 2013 escalabilidad.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543796"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="8d36d-103">Escalabilidad con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d36d-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d36d-104">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8d36d-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8d36d-105">Lync Server se ofrece en dos ediciones, Enterprise Edition y Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8d36d-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="8d36d-106">Las diferentes ediciones están destinadas principalmente a organizaciones de distinto tamaño.</span><span class="sxs-lookup"><span data-stu-id="8d36d-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="8d36d-107">Como se muestra en la tabla siguiente, ambas ediciones admiten todas las funcionalidades en todos los flujos de trabajo, excepto la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="8d36d-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d36d-108">Característica</span><span class="sxs-lookup"><span data-stu-id="8d36d-108">Feature</span></span></th>
<th><span data-ttu-id="8d36d-109">¿Se admite en Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="8d36d-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="8d36d-110">¿Se admite en Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="8d36d-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d36d-111">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="8d36d-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="8d36d-112">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-113">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d36d-114">Conferencia</span><span class="sxs-lookup"><span data-stu-id="8d36d-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="8d36d-115">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-116">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d36d-117">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="8d36d-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="8d36d-118">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-119">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d36d-120">Conferencia de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="8d36d-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="8d36d-121">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-122">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d36d-123">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="8d36d-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="8d36d-124">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-125">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d36d-126">Virtualización</span><span class="sxs-lookup"><span data-stu-id="8d36d-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="8d36d-127">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-128">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d36d-129">Alta disponibilidad, conmutación por error y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="8d36d-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="8d36d-130">Sí</span><span class="sxs-lookup"><span data-stu-id="8d36d-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="8d36d-131">No</span><span class="sxs-lookup"><span data-stu-id="8d36d-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

