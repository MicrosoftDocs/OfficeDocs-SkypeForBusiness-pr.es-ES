---
title: 'Lync Server 2013: Planeación de la capacidad para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1192ef9b5b30c722a4f62973cf4992da3ca7300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="30cf3-102">Planeación de la capacidad para el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30cf3-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30cf3-103">_**Última modificación del tema:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="30cf3-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="30cf3-104">En la tabla siguiente se describe el modelo de usuario de estacionamiento de llamadas que puede usar como base para los requisitos de planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="30cf3-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="30cf3-105">Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores emparejados debe poder administrar las cargas de trabajo para los servicios de estacionamiento de llamadas en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="30cf3-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="30cf3-106">Modelo de usuario de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="30cf3-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30cf3-107">Biometría</span><span class="sxs-lookup"><span data-stu-id="30cf3-107">Metric</span></span></th>
<th><span data-ttu-id="30cf3-108">Por grupo de servidores front-end (con 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="30cf3-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="30cf3-109">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="30cf3-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30cf3-110">Tasa de estacionamiento</span><span class="sxs-lookup"><span data-stu-id="30cf3-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="30cf3-111">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="30cf3-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="30cf3-112">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="30cf3-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30cf3-113">Recuperar la tasa de llamadas estacionadas</span><span class="sxs-lookup"><span data-stu-id="30cf3-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="30cf3-114">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="30cf3-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="30cf3-115">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="30cf3-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30cf3-116">Duración media del estacionamiento</span><span class="sxs-lookup"><span data-stu-id="30cf3-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="30cf3-117">60 segundos</span><span class="sxs-lookup"><span data-stu-id="30cf3-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="30cf3-118">60 segundos</span><span class="sxs-lookup"><span data-stu-id="30cf3-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

