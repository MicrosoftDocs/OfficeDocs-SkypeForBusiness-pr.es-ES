---
title: Lync Server 2013 escalabilidad
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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="ba3fb-102">Escalabilidad con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba3fb-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba3fb-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ba3fb-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ba3fb-104">Lync Server se ofrece en dos ediciones, Enterprise Edition y Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ba3fb-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="ba3fb-105">Las diferentes ediciones están destinadas principalmente a organizaciones de distinto tamaño.</span><span class="sxs-lookup"><span data-stu-id="ba3fb-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="ba3fb-106">Como se muestra en la tabla siguiente, ambas ediciones admiten todas las funcionalidades en todos los flujos de trabajo, excepto la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="ba3fb-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba3fb-107">Característica</span><span class="sxs-lookup"><span data-stu-id="ba3fb-107">Feature</span></span></th>
<th><span data-ttu-id="ba3fb-108">¿Se admite en Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="ba3fb-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="ba3fb-109">¿Se admite en Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="ba3fb-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba3fb-110">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="ba3fb-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-111">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-112">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba3fb-113">Conferencia</span><span class="sxs-lookup"><span data-stu-id="ba3fb-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-114">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-115">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba3fb-116">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="ba3fb-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-117">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-118">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba3fb-119">Conferencia de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="ba3fb-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-120">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-121">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba3fb-122">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="ba3fb-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-123">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-124">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba3fb-125">Virtualización</span><span class="sxs-lookup"><span data-stu-id="ba3fb-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-126">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-127">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba3fb-128">Alta disponibilidad, conmutación por error y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="ba3fb-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-129">Sí</span><span class="sxs-lookup"><span data-stu-id="ba3fb-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="ba3fb-130">No</span><span class="sxs-lookup"><span data-stu-id="ba3fb-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

