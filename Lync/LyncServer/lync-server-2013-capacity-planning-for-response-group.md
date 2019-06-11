---
title: 'Lync Server 2013: Planificar la capacidad para el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="48a22-102">Planificar la capacidad para el grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48a22-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48a22-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="48a22-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="48a22-104">En la siguiente tabla se describe el modelo de usuario de grupo de respuesta que puede usar como base para los requisitos de planes de capacidad.</span><span class="sxs-lookup"><span data-stu-id="48a22-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48a22-p101">En las cantidades de la tabla siguiente se presupone que usas archivos wave (.wav) mono de 16 bits a 16 kHz para todos los archivos de audio del grupo de respuesta. Si usas otros formatos de archivo, como audio de Windows Media (.wma), las cantidades pueden variar.</span><span class="sxs-lookup"><span data-stu-id="48a22-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="48a22-107">Ten en cuenta que, para planificar la capacidad de la recuperación ante desastres, cada grupo de un grupo emparejado necesita poder gestionar las cargas de trabajo para todos los grupos de respuesta en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="48a22-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="48a22-108">Modelo de usuario del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="48a22-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48a22-109">Métrica</span><span class="sxs-lookup"><span data-stu-id="48a22-109">Metric</span></span></th>
<th><span data-ttu-id="48a22-110">Por grupo de servidores Enterprise (con 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="48a22-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="48a22-111">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="48a22-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48a22-112">Llamadas entrantes por segundo</span><span class="sxs-lookup"><span data-stu-id="48a22-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="48a22-113">apartado</span><span class="sxs-lookup"><span data-stu-id="48a22-113">16</span></span></p></td>
<td><p><span data-ttu-id="48a22-114">2</span><span class="sxs-lookup"><span data-stu-id="48a22-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48a22-115">Llamadas simultáneas conectadas a IVR o a la música en espera</span><span class="sxs-lookup"><span data-stu-id="48a22-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="48a22-116">480</span><span class="sxs-lookup"><span data-stu-id="48a22-116">480</span></span></p></td>
<td><p><span data-ttu-id="48a22-117">60</span><span class="sxs-lookup"><span data-stu-id="48a22-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48a22-118">Sesiones anónimas simultáneas (sin MI)</span><span class="sxs-lookup"><span data-stu-id="48a22-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="48a22-119">224</span><span class="sxs-lookup"><span data-stu-id="48a22-119">224</span></span></p></td>
<td><p><span data-ttu-id="48a22-120">apartado</span><span class="sxs-lookup"><span data-stu-id="48a22-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48a22-121">Sesiones anónimas simultáneas (con MI)</span><span class="sxs-lookup"><span data-stu-id="48a22-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="48a22-122">64</span><span class="sxs-lookup"><span data-stu-id="48a22-122">64</span></span></p></td>
<td><p><span data-ttu-id="48a22-123">4,8</span><span class="sxs-lookup"><span data-stu-id="48a22-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48a22-124">Agentes activos (formales e informales)</span><span class="sxs-lookup"><span data-stu-id="48a22-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="48a22-125">1200</span><span class="sxs-lookup"><span data-stu-id="48a22-125">1200</span></span></p></td>
<td><p><span data-ttu-id="48a22-126">1200</span><span class="sxs-lookup"><span data-stu-id="48a22-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48a22-127">Cantidad de grupos de extensiones</span><span class="sxs-lookup"><span data-stu-id="48a22-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="48a22-128">400</span><span class="sxs-lookup"><span data-stu-id="48a22-128">400</span></span></p></td>
<td><p><span data-ttu-id="48a22-129">400</span><span class="sxs-lookup"><span data-stu-id="48a22-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48a22-130">Cantidad de grupos de IVR (uso del reconocimiento de voz)</span><span class="sxs-lookup"><span data-stu-id="48a22-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="48a22-131">200</span><span class="sxs-lookup"><span data-stu-id="48a22-131">200</span></span></p></td>
<td><p><span data-ttu-id="48a22-132">200</span><span class="sxs-lookup"><span data-stu-id="48a22-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

