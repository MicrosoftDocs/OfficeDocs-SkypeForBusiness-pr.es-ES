---
title: 'Lync Server 2013: administración de la recogida de llamadas de grupo durante la recuperación de desastres'
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
ms.openlocfilehash: 45ebe93ebc1711f49d4578a2a5d908104ca2a411
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="5c4d2-102">Administrar la recogida de llamadas grupales durante la recuperación de desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c4d2-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c4d2-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5c4d2-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5c4d2-104">Cuando un grupo front-end no está disponible debido a un incidente no planeado, el servicio se conmuta por error al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="5c4d2-105">Durante la conmutación por error al grupo de copia de seguridad, los usuarios se redirigen al grupo de copia de seguridad y están en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="5c4d2-106">En el modo de resistencia, los usuarios no pueden atender las llamadas de otros usuarios ni hacer que sus llamadas las recojan otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="5c4d2-107">Cuando se completa la conmutación por error, los usuarios pueden volver a usar la recogida de llamadas de grupo de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="5c4d2-108">Durante la conmutación por recuperación al grupo principal, los usuarios se redirigen al grupo principal y vuelven a estar en el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="5c4d2-109">La función de recogida de llamadas grupales no está disponible hasta que los usuarios no tengan el modo de resistencia.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="5c4d2-110">En esta sección se explican algunas consideraciones sobre la recogida de llamadas grupales durante la recuperación de desastres y también se describe la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="5c4d2-111">Consideraciones para la recogida de llamadas grupales durante la recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="5c4d2-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="5c4d2-112">Durante la recuperación de desastres, los usuarios que se han redirigido al grupo de copia de seguridad como parte del proceso de conmutación por error usan la aplicación estacionamiento de llamadas que se ejecuta en el grupo de copias de seguridad para los números del grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="5c4d2-113">Por lo tanto, la compatibilidad con la recogida de llamadas grupales durante la recuperación de desastres requiere que la aplicación de estacionamiento de llamadas se implemente y se habilite en el grupo primario y en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="5c4d2-114">Los intervalos de número de recogida de llamada grupal de la tabla llamada de estacionamiento orbital deben ser redireccionados al grupo de copia de seguridad una vez completado el proceso de conmutación por error al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="5c4d2-115">Los intervalos de números deben redirigirse al grupo principal una vez que se haya completado el proceso de conmutación por recuperación en el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="5c4d2-116">Para desviar los intervalos de recogida de llamadas grupales, use el cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="5c4d2-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="5c4d2-117">Si implementa un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente para reemplazar el grupo primario, tendrá que reasignar todos los intervalos de números de recogida de llamadas de grupo asociados con el grupo primario al FQDN del nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="5c4d2-118">Para reasignar intervalos numéricos a la nueva sección, puede usar el cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="5c4d2-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="5c4d2-119">Para obtener más información sobre el cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="5c4d2-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="5c4d2-120">Experiencia de recogida de llamada grupal durante un error de grupo</span><span class="sxs-lookup"><span data-stu-id="5c4d2-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="5c4d2-121">La siguiente tabla resume la experiencia de recopilación de llamadas grupales a través de las fases de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="5c4d2-122">Experiencia del usuario durante la recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="5c4d2-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c4d2-123">Estado de la llamada</span><span class="sxs-lookup"><span data-stu-id="5c4d2-123">Call state</span></span></th>
<th><span data-ttu-id="5c4d2-124">Conmutación por error de grupo de copia</span><span class="sxs-lookup"><span data-stu-id="5c4d2-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="5c4d2-125">Conmutación por recuperación al grupo principal</span><span class="sxs-lookup"><span data-stu-id="5c4d2-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c4d2-126">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="5c4d2-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="5c4d2-127"><strong>Durante el proceso de conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-128">La recogida de llamada grupal no está disponible para los usuarios en el modo de resistencia</span><span class="sxs-lookup"><span data-stu-id="5c4d2-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5c4d2-129"><strong>Después de completar la conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-130">La recogida de llamadas grupales está disponible cuando los usuarios de la resistencia y los intervalos numéricos de recogida de llamadas se redirigen al grupo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="5c4d2-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5c4d2-131"><strong>Durante el proceso de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-132">La recogida de llamada grupal no está disponible para los usuarios en el modo de resistencia</span><span class="sxs-lookup"><span data-stu-id="5c4d2-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5c4d2-133"><strong>Una vez completada la conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-134">La recogida de llamadas grupales está disponible cuando los usuarios de la resistencia y los intervalos numéricos de recogida de llamadas se redirigen al grupo principal</span><span class="sxs-lookup"><span data-stu-id="5c4d2-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c4d2-135">Llamadas en la cola de recopilación de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="5c4d2-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="5c4d2-136"><strong>Durante el proceso de conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-137">Las llamadas en cola no se pueden responder a través de la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5c4d2-138"><strong>Después de completar la conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-139">No hay llamadas en este estado</span><span class="sxs-lookup"><span data-stu-id="5c4d2-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5c4d2-140"><strong>Durante el proceso de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-141">Las llamadas en cola no se pueden responder a través de la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5c4d2-142"><strong>Una vez completada la conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-143">Las llamadas en cola no se pueden responder a través de la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="5c4d2-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c4d2-144">Llamada establecida</span><span class="sxs-lookup"><span data-stu-id="5c4d2-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="5c4d2-145"><strong>Durante el proceso de conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-146">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="5c4d2-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5c4d2-147"><strong>Después de completar la conmutación por error:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-148">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="5c4d2-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5c4d2-149"><strong>Durante el proceso de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-150">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="5c4d2-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5c4d2-151"><strong>Una vez completada la conmutación por recuperación:</strong></span><span class="sxs-lookup"><span data-stu-id="5c4d2-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5c4d2-152">Las llamadas permanecen conectadas</span><span class="sxs-lookup"><span data-stu-id="5c4d2-152">Calls stay connected</span></span></p></li>
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

