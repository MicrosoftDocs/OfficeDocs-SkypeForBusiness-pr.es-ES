---
title: 'Lync Server 2013: experiencia de estacionamiento de llamadas durante un error de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1834c9872dc9b8c1045c6e5e638f86f760b4ad4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="cc318-102">Experiencia de estacionamiento de llamadas en Lync Server 2013 durante un error de grupo</span><span class="sxs-lookup"><span data-stu-id="cc318-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc318-103">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="cc318-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="cc318-104">Cuando un grupo de servidores front-end no está disponible debido a un incidente no planeado, las llamadas que se han estacionado pero todavía no se han recuperado se desconectan.</span><span class="sxs-lookup"><span data-stu-id="cc318-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="cc318-105">Durante la conmutación por error a un grupo de servidores de copia de seguridad, los usuarios son redirigidos al grupo de servidores de copia de seguridad y están en modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="cc318-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="cc318-106">En el modo de resistencia, los usuarios no pueden estacionar llamadas, pero pueden realizar llamadas en espera y transferirlas.</span><span class="sxs-lookup"><span data-stu-id="cc318-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="cc318-107">Cuando finaliza la conmutación por error, las llamadas se pueden volver a estacionar y recuperar como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="cc318-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="cc318-108">Durante la conmutación por recuperación, los usuarios no pueden estacionar llamadas hasta que estén fuera del modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="cc318-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="cc318-109">Durante la recuperación ante desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se implementa en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cc318-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="cc318-110">Por lo tanto, los usuarios que se redirigen al grupo de copia de seguridad usan la configuración del estacionamiento de llamadas que están configurados para la aplicación estacionamiento de llamadas en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cc318-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="cc318-111">En la tabla siguiente se resume la experiencia del estacionamiento de llamadas a través de las fases de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="cc318-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="cc318-112">Experiencia del usuario durante la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="cc318-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc318-113">Estado de la llamada</span><span class="sxs-lookup"><span data-stu-id="cc318-113">Call state</span></span></th>
<th><span data-ttu-id="cc318-114">Cuando se produce la interrupción</span><span class="sxs-lookup"><span data-stu-id="cc318-114">When outage occurs</span></span></th>
<th><span data-ttu-id="cc318-115">Durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="cc318-115">During failover</span></span></th>
<th><span data-ttu-id="cc318-116">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="cc318-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc318-117">Llamada no estacionada aún</span><span class="sxs-lookup"><span data-stu-id="cc318-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="cc318-118">La llamada permanece conectada pero no se puede estacionar.</span><span class="sxs-lookup"><span data-stu-id="cc318-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cc318-119">Durante la conmutación por error, la llamada no se puede estacionar mientras los usuarios están en modo de resistencia, pero se puede poner en espera y transferirse.</span><span class="sxs-lookup"><span data-stu-id="cc318-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="cc318-120">Cuando se completa la conmutación por error, la llamada se puede estacionar y recuperar.</span><span class="sxs-lookup"><span data-stu-id="cc318-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="cc318-121">Durante la conmutación por recuperación, la llamada no se puede estacionar mientras los usuarios están en modo de resistencia, pero se puede poner en espera y transferirse</span><span class="sxs-lookup"><span data-stu-id="cc318-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="cc318-122">Cuando se completa la conmutación por recuperación, la llamada se puede estacionar y recuperar.</span><span class="sxs-lookup"><span data-stu-id="cc318-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc318-123">Llamada estacionada pero no recuperada aún</span><span class="sxs-lookup"><span data-stu-id="cc318-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="cc318-124">La llamada está desconectada.</span><span class="sxs-lookup"><span data-stu-id="cc318-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="cc318-125">No hay llamadas en este estado.</span><span class="sxs-lookup"><span data-stu-id="cc318-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="cc318-126">La llamada permanece estacionada.</span><span class="sxs-lookup"><span data-stu-id="cc318-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc318-127">Llamada estacionada ya recuperada</span><span class="sxs-lookup"><span data-stu-id="cc318-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="cc318-128">La llamada permanece conectada.</span><span class="sxs-lookup"><span data-stu-id="cc318-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="cc318-129">La llamada permanece conectada.</span><span class="sxs-lookup"><span data-stu-id="cc318-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="cc318-130">La llamada permanece conectada.</span><span class="sxs-lookup"><span data-stu-id="cc318-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

