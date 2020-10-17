---
title: 'Lync Server 2013: administrar la recogida de llamadas de grupo durante la recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d181570b55ce175a63ac1ac1f218ee99aec7a5a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534537"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="34e81-102">Administrar la recepción de llamadas de grupo durante la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34e81-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e81-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="34e81-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="34e81-104">Cuando un grupo de servidores front-end deja de estar disponible debido a un incidente no planeado, el servicio se conmuta por error al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34e81-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="34e81-105">Durante la conmutación por error en el grupo de copia de seguridad, los usuarios se redirigen al grupo de copia de seguridad y están en modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="34e81-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="34e81-106">Mientras se está en el modo de resistencia, los usuarios no pueden recoger las llamadas de otros usuarios ni hacer que sus llamadas las recojan otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="34e81-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="34e81-107">Una vez completada la conmutación por error, los usuarios pueden volver a usar la recopilación de llamadas de grupo de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="34e81-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="34e81-108">Durante la conmutación por recuperación al grupo principal, los usuarios se redirigen al grupo principal y vuelven a estar en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="34e81-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="34e81-109">La funcionalidad de recogida de llamadas de grupo no está disponible hasta que los usuarios no tengan el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="34e81-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="34e81-110">En esta sección se describen algunas consideraciones sobre la recogida de llamadas de grupo durante la recuperación ante desastres y también se describe la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="34e81-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="34e81-111">Consideraciones para la recogida de llamadas de grupo durante la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="34e81-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="34e81-112">Durante la recuperación ante desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se ejecuta en el grupo de copia de seguridad para los números del grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="34e81-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="34e81-113">Por lo tanto, la compatibilidad con la recogida de llamadas de grupo durante la recuperación ante desastres requiere que la aplicación de estacionamiento de llamadas se implemente y esté habilitada en el grupo principal y en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34e81-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="34e81-114">Los intervalos de números de atención de llamadas grupales en la tabla de órbitas de estacionamiento de llamadas deben redirigirse al grupo de copia de seguridad una vez completado el proceso de conmutación por error al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34e81-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="34e81-115">Los intervalos de números se deben redirigir de vuelta al grupo principal una vez que se haya completado el proceso de conmutación por recuperación en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="34e81-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="34e81-116">Para redirigir los intervalos de recogida de llamadas de grupo, use el cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="34e81-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="34e81-117">Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo principal, tendrá que reasignar todos los intervalos de números de atención de llamadas de grupo asociados con el grupo principal al FQDN del nuevo grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="34e81-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="34e81-118">Para reasignar intervalos de números a la nueva agrupación, puede usar el cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="34e81-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="34e81-119">Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="34e81-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="34e81-120">Experiencia de recopilación de llamadas de grupo durante un error de grupo</span><span class="sxs-lookup"><span data-stu-id="34e81-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="34e81-121">En la tabla siguiente se resume la experiencia de llamada de llamada de grupo a través de las fases de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="34e81-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="34e81-122">Experiencia del usuario durante la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="34e81-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34e81-123">Estado de la llamada</span><span class="sxs-lookup"><span data-stu-id="34e81-123">Call state</span></span></th>
<th><span data-ttu-id="34e81-124">Conmutación por error en el grupo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="34e81-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="34e81-125">Conmutación por recuperación al grupo principal</span><span class="sxs-lookup"><span data-stu-id="34e81-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34e81-126">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="34e81-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="34e81-127"><strong>Durante el proceso de conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-128">La recopilación de llamadas de grupo no está disponible para los usuarios en el modo de resistencia</span><span class="sxs-lookup"><span data-stu-id="34e81-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="34e81-129"><strong>Una vez finalizada la conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-130">La recogida de llamadas de grupo está disponible cuando los usuarios de la resistencia y los intervalos de números de llamada de grupo se redirigen al grupo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="34e81-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="34e81-131"><strong>Durante el proceso de conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-132">La recopilación de llamadas de grupo no está disponible para los usuarios en el modo de resistencia</span><span class="sxs-lookup"><span data-stu-id="34e81-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="34e81-133"><strong>Una vez finalizada la conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-134">La recogida de llamadas de grupo está disponible cuando los usuarios de fuera de la resistencia y los intervalos de números de atención de llamadas de grupo se redirigen de vuelta al grupo principal</span><span class="sxs-lookup"><span data-stu-id="34e81-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e81-135">Llamadas en la cola de recogida de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="34e81-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="34e81-136"><strong>Durante el proceso de conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-137">No se puede responder a las llamadas de la cola a través de la llamada de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="34e81-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="34e81-138"><strong>Una vez finalizada la conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-139">No hay llamadas en este estado</span><span class="sxs-lookup"><span data-stu-id="34e81-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="34e81-140"><strong>Durante el proceso de conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-141">No se puede responder a las llamadas de la cola a través de la llamada de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="34e81-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="34e81-142"><strong>Una vez finalizada la conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-143">No se puede responder a las llamadas de la cola a través de la llamada de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="34e81-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e81-144">Llamada establecida</span><span class="sxs-lookup"><span data-stu-id="34e81-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="34e81-145"><strong>Durante el proceso de conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-146">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="34e81-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="34e81-147"><strong>Una vez finalizada la conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-148">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="34e81-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="34e81-149"><strong>Durante el proceso de conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-150">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="34e81-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="34e81-151"><strong>Una vez finalizada la conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="34e81-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="34e81-152">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="34e81-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

