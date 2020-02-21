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
ms.openlocfilehash: 10bf167538158e0f427b1522738374ae7c2b5320
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="0b608-102">Escalabilidad con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b608-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b608-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="0b608-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="0b608-104">Lync Server se ofrece en dos ediciones, Enterprise Edition y Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0b608-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="0b608-105">Las diferentes ediciones están destinadas principalmente a organizaciones de distinto tamaño.</span><span class="sxs-lookup"><span data-stu-id="0b608-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="0b608-106">Como se muestra en la tabla siguiente, ambas ediciones admiten todas las funcionalidades en todos los flujos de trabajo, excepto la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="0b608-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b608-107">Característica</span><span class="sxs-lookup"><span data-stu-id="0b608-107">Feature</span></span></th>
<th><span data-ttu-id="0b608-108">¿Se admite en Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="0b608-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="0b608-109">¿Se admite en Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="0b608-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b608-110">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="0b608-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="0b608-111">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-112">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b608-113">Conferencia</span><span class="sxs-lookup"><span data-stu-id="0b608-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="0b608-114">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-115">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b608-116">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="0b608-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="0b608-117">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-118">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b608-119">Conferencia de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="0b608-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="0b608-120">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-121">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b608-122">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="0b608-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="0b608-123">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-124">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b608-125">Virtualización</span><span class="sxs-lookup"><span data-stu-id="0b608-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="0b608-126">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-127">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b608-128">Alta disponibilidad, conmutación por error y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="0b608-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="0b608-129">Sí</span><span class="sxs-lookup"><span data-stu-id="0b608-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="0b608-130">No</span><span class="sxs-lookup"><span data-stu-id="0b608-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

