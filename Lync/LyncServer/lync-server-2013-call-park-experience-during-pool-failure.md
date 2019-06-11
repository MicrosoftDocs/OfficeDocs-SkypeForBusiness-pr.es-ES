---
title: 'Lync Server 2013: Experiencia de estacionamiento de llamadas durante un error del grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="42637-102">Experiencia de estacionamiento de llamadas durante un error del grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42637-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42637-103">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="42637-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="42637-104">Cuando un grupo front-end no está disponible debido a un incidente no planeado, se desconectan las llamadas que se han detenido pero que aún no se han recuperado.</span><span class="sxs-lookup"><span data-stu-id="42637-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="42637-105">Durante la conmutación por error a un grupo de copia de seguridad, los usuarios se redirigen al grupo de copia de seguridad y están en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="42637-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="42637-106">Mientras se encuentra en el modo de resistencia, los usuarios no pueden detener las llamadas, pero pueden poner las llamadas en espera y transferirlas.</span><span class="sxs-lookup"><span data-stu-id="42637-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="42637-107">Cuando se completa la conmutación por error, las llamadas se pueden detener de nuevo y recuperar de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="42637-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="42637-108">Durante la conmutación por recuperación, los usuarios no pueden detener las llamadas hasta que no estén fuera del modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="42637-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="42637-109">Durante la recuperación de desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se implementa en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42637-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="42637-110">Por lo tanto, los usuarios redirigidos al grupo de copias de seguridad usan la configuración de estacionamiento de llamadas que están configurados para la aplicación de estacionamiento de llamada en el grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42637-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="42637-111">La siguiente tabla resume la experiencia del parque de llamadas a través de las fases de la recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="42637-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="42637-112">Experiencia del usuario durante la recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="42637-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42637-113">Estado de la llamada</span><span class="sxs-lookup"><span data-stu-id="42637-113">Call state</span></span></th>
<th><span data-ttu-id="42637-114">Cuando se produce una interrupción</span><span class="sxs-lookup"><span data-stu-id="42637-114">When outage occurs</span></span></th>
<th><span data-ttu-id="42637-115">Durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="42637-115">During failover</span></span></th>
<th><span data-ttu-id="42637-116">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="42637-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42637-117">Llamada aún no deestacionada</span><span class="sxs-lookup"><span data-stu-id="42637-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="42637-118">La llamada permanece conectada, pero no se puede detener.</span><span class="sxs-lookup"><span data-stu-id="42637-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="42637-119">Durante la conmutación por error, no se puede detener la llamada cuando los usuarios están en modo de resistencia, pero se pueden suspender y transferir.</span><span class="sxs-lookup"><span data-stu-id="42637-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="42637-120">Cuando se complete la conmutación por error, se podrá detener y recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="42637-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="42637-121">Durante la conmutación por recuperación, la llamada no se puede detener cuando los usuarios tienen el modo de resistencia, pero se pueden suspender y transferir.</span><span class="sxs-lookup"><span data-stu-id="42637-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="42637-122">Cuando se complete la conmutación por recuperación, se podrá detener y recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="42637-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42637-123">Llamada estacionada, pero no recuperada aún</span><span class="sxs-lookup"><span data-stu-id="42637-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="42637-124">La llamada está desconectada.</span><span class="sxs-lookup"><span data-stu-id="42637-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="42637-125">No hay llamadas en este estado.</span><span class="sxs-lookup"><span data-stu-id="42637-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="42637-126">La llamada permanece aparcada.</span><span class="sxs-lookup"><span data-stu-id="42637-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42637-127">Ya se ha recuperado una llamada estacionada</span><span class="sxs-lookup"><span data-stu-id="42637-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="42637-128">La llamada permanece conectada.</span><span class="sxs-lookup"><span data-stu-id="42637-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="42637-129">La llamada permanece conectada.</span><span class="sxs-lookup"><span data-stu-id="42637-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="42637-130">La llamada permanece conectada.</span><span class="sxs-lookup"><span data-stu-id="42637-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

