---
title: 'Lync Server 2013: Planeación de la capacidad para el grupo de respuesta'
description: 'Lync Server 2013: Planeación de la capacidad para el grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544436"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="010f0-103">Planeación de la capacidad para el grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="010f0-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="010f0-104">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="010f0-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="010f0-105">En la tabla siguiente se describe el modelo de usuario del grupo de respuesta que puede usar como base para los requisitos de planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="010f0-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="010f0-106">Los números de la tabla siguiente suponen que usa archivos de onda de 16 bits (. wav) de 16 kHz para todos los archivos de audio del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="010f0-106">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="010f0-107">Si usa otros formatos de archivo, como audio de Windows Media (. WMA), los números pueden variar.</span><span class="sxs-lookup"><span data-stu-id="010f0-107">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="010f0-108">Tenga en cuenta que para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores emparejados debe poder administrar las cargas de trabajo de todos los grupos de respuesta en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="010f0-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="010f0-109">Modelo de usuario del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="010f0-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="010f0-110">Métrica</span><span class="sxs-lookup"><span data-stu-id="010f0-110">Metric</span></span></th>
<th><span data-ttu-id="010f0-111">Por grupo de servidores Enterprise Edition (con 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="010f0-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="010f0-112">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="010f0-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="010f0-113">Llamadas entrantes por segundo</span><span class="sxs-lookup"><span data-stu-id="010f0-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="010f0-114">16 </span><span class="sxs-lookup"><span data-stu-id="010f0-114">16</span></span></p></td>
<td><p><span data-ttu-id="010f0-115">segundo</span><span class="sxs-lookup"><span data-stu-id="010f0-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="010f0-116">Llamadas simultáneas conectadas a IVR o música</span><span class="sxs-lookup"><span data-stu-id="010f0-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="010f0-117">480</span><span class="sxs-lookup"><span data-stu-id="010f0-117">480</span></span></p></td>
<td><p><span data-ttu-id="010f0-118">60</span><span class="sxs-lookup"><span data-stu-id="010f0-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="010f0-119">Sesiones anónimas simultáneas (sin mi)</span><span class="sxs-lookup"><span data-stu-id="010f0-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="010f0-120">224</span><span class="sxs-lookup"><span data-stu-id="010f0-120">224</span></span></p></td>
<td><p><span data-ttu-id="010f0-121">28</span><span class="sxs-lookup"><span data-stu-id="010f0-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="010f0-122">Sesiones anónimas simultáneas (con mi)</span><span class="sxs-lookup"><span data-stu-id="010f0-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="010f0-123">64</span><span class="sxs-lookup"><span data-stu-id="010f0-123">64</span></span></p></td>
<td><p><span data-ttu-id="010f0-124">8 </span><span class="sxs-lookup"><span data-stu-id="010f0-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="010f0-125">Agentes activos (formales e informales)</span><span class="sxs-lookup"><span data-stu-id="010f0-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="010f0-126">1200</span><span class="sxs-lookup"><span data-stu-id="010f0-126">1200</span></span></p></td>
<td><p><span data-ttu-id="010f0-127">1200</span><span class="sxs-lookup"><span data-stu-id="010f0-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="010f0-128">Número de grupos de extensiones</span><span class="sxs-lookup"><span data-stu-id="010f0-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="010f0-129">400</span><span class="sxs-lookup"><span data-stu-id="010f0-129">400</span></span></p></td>
<td><p><span data-ttu-id="010f0-130">400</span><span class="sxs-lookup"><span data-stu-id="010f0-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="010f0-131">Número de grupos IVR (usar el reconocimiento de voz)</span><span class="sxs-lookup"><span data-stu-id="010f0-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="010f0-132">200</span><span class="sxs-lookup"><span data-stu-id="010f0-132">200</span></span></p></td>
<td><p><span data-ttu-id="010f0-133">200</span><span class="sxs-lookup"><span data-stu-id="010f0-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

