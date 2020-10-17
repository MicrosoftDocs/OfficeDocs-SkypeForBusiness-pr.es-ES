---
title: 'Lync Server 2013: topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia'
description: 'Lync Server 2013: topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550296"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="fe81a-103">Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe81a-103">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe81a-104">_**Última modificación del tema:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="fe81a-104">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="fe81a-105">Los únicos componentes necesarios para la mensajería instantánea (mi) y la presencia son:</span><span class="sxs-lookup"><span data-stu-id="fe81a-105">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="fe81a-106">Los servidores front-end de la organización o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fe81a-106">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="fe81a-107">Las capacidades de mensajería instantánea y presencia siempre están habilitadas en estos servidores.</span><span class="sxs-lookup"><span data-stu-id="fe81a-107">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="fe81a-108">Un equilibrador de carga, si tiene un grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="fe81a-108">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="fe81a-109">Para obtener más información, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe81a-109">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="fe81a-110">Planeación de la implementación de grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fe81a-110">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="fe81a-111">En Lync Server 2013, la arquitectura del grupo de servidores front-end ha cambiado y estos cambios afectan a la planeación y el mantenimiento de los grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fe81a-111">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="fe81a-112">Se recomienda que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fe81a-112">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="fe81a-113">En Lync Server, la arquitectura de los grupos de servidores front-end usa un modelo de sistemas distribuidos, donde los datos de cada usuario se guardan en tres servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-113">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="fe81a-114">Para obtener más información acerca de esta nueva arquitectura, vea [cambios en la topología en Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="fe81a-114">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="fe81a-115">Si no desea implementar tres servidores front-end Enterprise Edition y desea realizar una recuperación ante desastres, le recomendamos que use Lync Server Standard Edition y cree dos grupos de servidores con una relación de copia de seguridad emparejada.</span><span class="sxs-lookup"><span data-stu-id="fe81a-115">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="fe81a-116">Esto proporcionará una solución de recuperación ante desastres con solo dos servidores.</span><span class="sxs-lookup"><span data-stu-id="fe81a-116">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="fe81a-117">Para obtener más información sobre las topologías y características de alta disponibilidad y recuperación ante desastres, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="fe81a-117">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="fe81a-118">Planeación de la administración de grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fe81a-118">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="fe81a-119">Para los grupos de servidores front-end, siga las instrucciones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="fe81a-119">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="fe81a-120">Garantizar la funcionalidad de los grupos</span><span class="sxs-lookup"><span data-stu-id="fe81a-120">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="fe81a-121">Con el nuevo modelo distribuido para los grupos de servidores front-end, se deben ejecutar ciertos números de servidores de grupo para que el grupo funcione.</span><span class="sxs-lookup"><span data-stu-id="fe81a-121">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="fe81a-122">Hay dos modos de pérdida para un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="fe81a-122">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="fe81a-123">Pérdida de quórum de nivel de grupo de enrutamiento, debido a que no hay suficientes servidores de réplica para un grupo de enrutamiento en particular.</span><span class="sxs-lookup"><span data-stu-id="fe81a-123">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="fe81a-124">Un grupo de enrutamiento es una agregación de un conjunto de usuarios hospedados en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="fe81a-124">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="fe81a-125">Cada grupo de enrutamiento tiene tres réplicas en el Grupo: una principal y dos secundarias.</span><span class="sxs-lookup"><span data-stu-id="fe81a-125">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="fe81a-126">Pérdida de quórum de nivel de grupo de servidores, que se produce cuando no hay suficientes servidores semilla ejecutándose en el grupo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-126">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="fe81a-127">Pérdida de quórum en el nivel de grupo de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="fe81a-127">Routing Group Level quorum loss</span></span>

<span data-ttu-id="fe81a-128">La primera vez que inicie un nuevo grupo de servidores front-end, es esencial que 85% de los servidores estén en funcionamiento, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="fe81a-128">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="fe81a-129">Si se están ejecutando menos servidores, es posible que los servicios estén atascados en el estado inicial y que el grupo no se inicie.</span><span class="sxs-lookup"><span data-stu-id="fe81a-129">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe81a-130">Número total de servidores del grupo</span><span class="sxs-lookup"><span data-stu-id="fe81a-130">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="fe81a-131">Número de servidores que deben estar en ejecución para que el grupo se inicie por primera vez</span><span class="sxs-lookup"><span data-stu-id="fe81a-131">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-132">segundo</span><span class="sxs-lookup"><span data-stu-id="fe81a-132">2</span></span></p></td>
<td><p><span data-ttu-id="fe81a-133">1</span><span class="sxs-lookup"><span data-stu-id="fe81a-133">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-134">3</span><span class="sxs-lookup"><span data-stu-id="fe81a-134">3</span></span></p></td>
<td><p><span data-ttu-id="fe81a-135">3</span><span class="sxs-lookup"><span data-stu-id="fe81a-135">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-136">4 </span><span class="sxs-lookup"><span data-stu-id="fe81a-136">4</span></span></p></td>
<td><p><span data-ttu-id="fe81a-137">3</span><span class="sxs-lookup"><span data-stu-id="fe81a-137">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-138">5 </span><span class="sxs-lookup"><span data-stu-id="fe81a-138">5</span></span></p></td>
<td><p><span data-ttu-id="fe81a-139">4 </span><span class="sxs-lookup"><span data-stu-id="fe81a-139">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-140">6 </span><span class="sxs-lookup"><span data-stu-id="fe81a-140">6</span></span></p></td>
<td><p><span data-ttu-id="fe81a-141">5 </span><span class="sxs-lookup"><span data-stu-id="fe81a-141">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-142">7 </span><span class="sxs-lookup"><span data-stu-id="fe81a-142">7</span></span></p></td>
<td><p><span data-ttu-id="fe81a-143">5 </span><span class="sxs-lookup"><span data-stu-id="fe81a-143">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-144">8 </span><span class="sxs-lookup"><span data-stu-id="fe81a-144">8</span></span></p></td>
<td><p><span data-ttu-id="fe81a-145">6 </span><span class="sxs-lookup"><span data-stu-id="fe81a-145">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-146">9 </span><span class="sxs-lookup"><span data-stu-id="fe81a-146">9</span></span></p></td>
<td><p><span data-ttu-id="fe81a-147">7 </span><span class="sxs-lookup"><span data-stu-id="fe81a-147">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-148">10  </span><span class="sxs-lookup"><span data-stu-id="fe81a-148">10</span></span></p></td>
<td><p><span data-ttu-id="fe81a-149">8 </span><span class="sxs-lookup"><span data-stu-id="fe81a-149">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-150">12</span><span class="sxs-lookup"><span data-stu-id="fe81a-150">11</span></span></p></td>
<td><p><span data-ttu-id="fe81a-151">9 </span><span class="sxs-lookup"><span data-stu-id="fe81a-151">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-152">12 </span><span class="sxs-lookup"><span data-stu-id="fe81a-152">12</span></span></p></td>
<td><p><span data-ttu-id="fe81a-153">10  </span><span class="sxs-lookup"><span data-stu-id="fe81a-153">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe81a-154">Cada vez que se inicia el grupo, se debe iniciar el 85% de los servidores (como se muestra en la tabla anterior).</span><span class="sxs-lookup"><span data-stu-id="fe81a-154">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="fe81a-155">Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores para que no se pierda el quórum en el nivel de grupo), puede usar el cmdlet **RESET-CsPoolRegistrarState – ResetType QuorumLossRecovery** para permitir que el grupo se recupere de esta pérdida de quórum en el nivel de grupo de enrutamiento y realice el progreso.</span><span class="sxs-lookup"><span data-stu-id="fe81a-155">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="fe81a-156">Para obtener más información acerca de cómo usar este cmdlet, consulte [RESET-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="fe81a-156">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe81a-157">Debido a que Lync Server usa la base de datos SQL principal como testigo, si apaga la base de datos principal y cambia a la copia reflejada, y apaga los servidores front-end suficientes para que no haya suficiente de acuerdo con la tabla anterior, se producirá todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-157">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="fe81a-158">Para obtener más información, consulte <A href="https://go.microsoft.com/fwlink/?linkid=393672">testigo de creación de reflejo</A>de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fe81a-158">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="fe81a-159">Pérdida de quórum de nivel de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="fe81a-159">Pool-level quorum loss</span></span>

<span data-ttu-id="fe81a-160">Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-160">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="fe81a-161">Si el número de servidores que se ejecutan está por debajo del nivel funcional, como se muestra en la siguiente tabla, los demás servidores del grupo detendrán todos los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe81a-161">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="fe81a-162">Tenga en cuenta que los números de la siguiente tabla suponen que se están ejecutando los servidores back-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-162">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe81a-163">Número total de servidores front-end en el grupo</span><span class="sxs-lookup"><span data-stu-id="fe81a-163">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="fe81a-164">Número necesario de servidores en ejecución para que el grupo sea funcional</span><span class="sxs-lookup"><span data-stu-id="fe81a-164">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-165">segundo</span><span class="sxs-lookup"><span data-stu-id="fe81a-165">2</span></span></p></td>
<td><p><span data-ttu-id="fe81a-166">1</span><span class="sxs-lookup"><span data-stu-id="fe81a-166">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-167">3-4</span><span class="sxs-lookup"><span data-stu-id="fe81a-167">3-4</span></span></p></td>
<td><p><span data-ttu-id="fe81a-168">Cualquier 2</span><span class="sxs-lookup"><span data-stu-id="fe81a-168">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-169">5-6</span><span class="sxs-lookup"><span data-stu-id="fe81a-169">5-6</span></span></p></td>
<td><p><span data-ttu-id="fe81a-170">Cualquier 3</span><span class="sxs-lookup"><span data-stu-id="fe81a-170">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-171">7 </span><span class="sxs-lookup"><span data-stu-id="fe81a-171">7</span></span></p></td>
<td><p><span data-ttu-id="fe81a-172">Cualquier 4</span><span class="sxs-lookup"><span data-stu-id="fe81a-172">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe81a-173">8-9</span><span class="sxs-lookup"><span data-stu-id="fe81a-173">8-9</span></span></p></td>
<td><p><span data-ttu-id="fe81a-174">4 de los primeros 7 servidores</span><span class="sxs-lookup"><span data-stu-id="fe81a-174">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe81a-175">10-12</span><span class="sxs-lookup"><span data-stu-id="fe81a-175">10-12</span></span></p></td>
<td><p><span data-ttu-id="fe81a-176">5 de los primeros 9 servidores</span><span class="sxs-lookup"><span data-stu-id="fe81a-176">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe81a-177">En la tabla anterior, los "primeros servidores" son los servidores que se pusieron en primer lugar, de forma cronológica, cuando se inició el grupo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="fe81a-177">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="fe81a-178">Para determinar estos servidores, puede usar el cmdlet **Get-CsComputer** con la opción **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="fe81a-178">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="fe81a-179">Este cmdlet mostrará los servidores en el orden en que aparecen en la topología y los que se encuentran en la parte superior de la lista son los primeros servidores.</span><span class="sxs-lookup"><span data-stu-id="fe81a-179">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="fe81a-180">Grupos de servidores front-end con dos servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fe81a-180">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="fe81a-181">No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="fe81a-181">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="fe81a-182">Si alguna vez necesita implementar ese grupo de servidores, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="fe81a-182">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="fe81a-183">Si uno de los dos servidores front-end deja de funcionar, debería intentar volver a conectar el servidor con el error tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="fe81a-183">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="fe81a-184">De forma similar, si necesita actualizar uno de los dos servidores, vuelva a conectarlo tan pronto como finalice la actualización.</span><span class="sxs-lookup"><span data-stu-id="fe81a-184">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="fe81a-185">Si, por algún motivo, necesita poner ambos servidores al mismo tiempo, haga lo siguiente cuando finalice el tiempo de inactividad del Grupo:</span><span class="sxs-lookup"><span data-stu-id="fe81a-185">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="fe81a-186">El procedimiento recomendado es reiniciar ambos servidores front-end al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-186">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="fe81a-187">Si no se pueden reiniciar los dos servidores al mismo tiempo, deberá ponerlos en marcha de nuevo en el orden inverso al orden en que se encontraban.</span><span class="sxs-lookup"><span data-stu-id="fe81a-187">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="fe81a-188">Si no puede realizar una copia de seguridad en ese orden, use el siguiente cmdlet antes de volver a poner el grupo de servidores:.</span><span class="sxs-lookup"><span data-stu-id="fe81a-188">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="fe81a-189">Pasos adicionales para garantizar que los grupos de servidores son funcionales</span><span class="sxs-lookup"><span data-stu-id="fe81a-189">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="fe81a-190">Debe vigilar un par de otros factores para asegurarse de que los grupos de servidores front-end sigan siendo funcionales.</span><span class="sxs-lookup"><span data-stu-id="fe81a-190">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="fe81a-191">Al mover usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="fe81a-191">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="fe81a-192">Si establece una relación de emparejamiento entre este grupo de servidores y otro grupo para fines de recuperación ante desastres, después de establecer esa relación, debe asegurarse de que este grupo tenga tres servidores front-end que se ejecuten simultáneamente para sincronizar correctamente los datos con el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fe81a-192">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="fe81a-193">Para obtener más información sobre el emparejamiento de grupos de servidores y las características de recuperación ante desastres, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="fe81a-193">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="fe81a-194">Mejorar la confiabilidad de las actualizaciones de los grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="fe81a-194">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="fe81a-195">Cuando necesite actualizar o aplicar una revisión a los servidores de un grupo de servidores front-end, siga el flujo de trabajo que se muestra en [actualizar o actualizar los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)y las siguientes directrices:</span><span class="sxs-lookup"><span data-stu-id="fe81a-195">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="fe81a-196">Al pasar de un dominio de actualización a otro para actualizaciones (siguiendo el flujo de trabajo en la [actualización o actualización de los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), usará el cmdlet **Get-CsPoolUpgradeReadinessState** y comprobará el estado Ready.</span><span class="sxs-lookup"><span data-stu-id="fe81a-196">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="fe81a-197">Agregar una espera de 20 minutos entre cada dominio de actualización después de que se alcance "listo" hará que las actualizaciones sean más confiables.</span><span class="sxs-lookup"><span data-stu-id="fe81a-197">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="fe81a-198">Si no está **listo** durante estos 20 minutos, reinicie el temporizador de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="fe81a-198">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="fe81a-199">Además, puede ejecutar el cmdlet **Get-CsPoolFabricState** antes y después de iniciar el intervalo de 20 minutos y asegurarse de que no haya cambios en las principales y secundarias de los grupos de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="fe81a-199">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="fe81a-200">No continúe con el siguiente dominio de actualización si alguno de los servidores del último dominio de actualización revisado están detenidos o no se han reiniciado.</span><span class="sxs-lookup"><span data-stu-id="fe81a-200">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="fe81a-201">Esto también se aplica si no se puede iniciar ninguno de los servidores que hay en una actualización.</span><span class="sxs-lookup"><span data-stu-id="fe81a-201">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="fe81a-202">Ejecute **Get-CsPoolFabricState** para asegurarse de que todos los grupos de enrutamiento tienen un primario y al menos uno secundario; se confirmará si todos los usuarios tienen servicio.</span><span class="sxs-lookup"><span data-stu-id="fe81a-202">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="fe81a-203">Si algunos usuarios tienen servicio y otros no, ejecute **Get-CsPoolFabricState** con la opción – verbose para comprobar los grupos de enrutamiento que tienen réplicas que faltan.</span><span class="sxs-lookup"><span data-stu-id="fe81a-203">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="fe81a-204">No reinicie todo el grupo de servidores como primer paso de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="fe81a-204">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="fe81a-205">Para obtener más información sobre este cmdlet, consulte [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="fe81a-205">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="fe81a-206">Asegúrese de que todas las instancias del visor de eventos o de las ventanas del monitor de rendimiento estén cerradas para las instalaciones o desinstalaciones de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="fe81a-206">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="fe81a-207">Cambio de la configuración del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="fe81a-207">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="fe81a-208">Siempre que agregue servidores front-end a un grupo o los quite del grupo y, a continuación, publique la nueva topología, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="fe81a-208">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="fe81a-209">Una vez publicada la nueva topología, debe reiniciar cada uno de los servidores front-end del grupo.</span><span class="sxs-lookup"><span data-stu-id="fe81a-209">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="fe81a-210">Reinícielo a la vez.</span><span class="sxs-lookup"><span data-stu-id="fe81a-210">Restart them one at a time.</span></span>

  - <span data-ttu-id="fe81a-211">Si todo el grupo de servidores ha estado inactivo durante el cambio de configuración, ejecute el siguiente cmdlet después de publicar la nueva topología:</span><span class="sxs-lookup"><span data-stu-id="fe81a-211">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="fe81a-212">Si se produce un error en un servidor front-end y es improbable que se reemplace durante unos cuantos días o más, quite el servidor de la topología.</span><span class="sxs-lookup"><span data-stu-id="fe81a-212">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="fe81a-213">Agregue el nuevo servidor front-end a la topología cuando vuelva a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="fe81a-213">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

