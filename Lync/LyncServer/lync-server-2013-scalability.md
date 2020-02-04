---
title: 'Lync Server 2013: Escalabilidad'
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
ms.openlocfilehash: e6ff4828bdfddbfca7734836fdfdbe24f0b90c4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="72ed2-102">Escalabilidad con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72ed2-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72ed2-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="72ed2-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="72ed2-104">Lync Server se ofrece en dos ediciones Enterprise Edition y Standard.</span><span class="sxs-lookup"><span data-stu-id="72ed2-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="72ed2-105">Las diferentes ediciones están pensadas principalmente para diferentes tamaños de organizaciones.</span><span class="sxs-lookup"><span data-stu-id="72ed2-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="72ed2-106">Como se muestra en la tabla siguiente, ambas ediciones admiten toda la funcionalidad de todas las cargas de trabajo, excepto para la alta disponibilidad y la recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="72ed2-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72ed2-107">Característica</span><span class="sxs-lookup"><span data-stu-id="72ed2-107">Feature</span></span></th>
<th><span data-ttu-id="72ed2-108">¿Es compatible con Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="72ed2-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="72ed2-109">¿Compatible con Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="72ed2-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72ed2-110">Mensajería instantánea (mi) y presencia</span><span class="sxs-lookup"><span data-stu-id="72ed2-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="72ed2-111">Sí </span><span class="sxs-lookup"><span data-stu-id="72ed2-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-112">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72ed2-113">Conferencias</span><span class="sxs-lookup"><span data-stu-id="72ed2-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="72ed2-114">Sí </span><span class="sxs-lookup"><span data-stu-id="72ed2-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-115">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72ed2-116">Conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="72ed2-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="72ed2-117">Sí </span><span class="sxs-lookup"><span data-stu-id="72ed2-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-118">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72ed2-119">Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="72ed2-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="72ed2-120">Sí </span><span class="sxs-lookup"><span data-stu-id="72ed2-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-121">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72ed2-122">Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="72ed2-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="72ed2-123">Sí </span><span class="sxs-lookup"><span data-stu-id="72ed2-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-124">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72ed2-125">Virtualización</span><span class="sxs-lookup"><span data-stu-id="72ed2-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="72ed2-126">Sí </span><span class="sxs-lookup"><span data-stu-id="72ed2-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-127">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72ed2-128">Alta disponibilidad, failover y recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="72ed2-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="72ed2-129">Sí</span><span class="sxs-lookup"><span data-stu-id="72ed2-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="72ed2-130">No</span><span class="sxs-lookup"><span data-stu-id="72ed2-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

