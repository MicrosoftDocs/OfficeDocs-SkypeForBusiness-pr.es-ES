---
title: 'Lync Server 2013: Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia'
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
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="89fff-102">Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89fff-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89fff-103">_**Última modificación del tema:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="89fff-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="89fff-104">Los únicos componentes necesarios para la mensajería instantánea (MI) y la presencia son:</span><span class="sxs-lookup"><span data-stu-id="89fff-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="89fff-105">Los servidores front-end de su organización o los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="89fff-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="89fff-106">Las capacidades de presencia y de mensajería instantánea (MI) siempre se encuentran habilitadas en estos servidores.</span><span class="sxs-lookup"><span data-stu-id="89fff-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="89fff-107">Un equilibrador de carga, si se dispone de un grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="89fff-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="89fff-108">Para obtener más información, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89fff-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="89fff-109">Planear la implementación de grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="89fff-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="89fff-110">En Lync Server 2013, la arquitectura del grupo de servidores front-end ha cambiado y estos cambios afectan a la manera en que debe planear y mantener los grupos de aplicaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="89fff-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="89fff-111">Recomendamos que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores frontales.</span><span class="sxs-lookup"><span data-stu-id="89fff-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="89fff-112">En Lync Server, la arquitectura de los grupos front-end usa un modelo de sistemas distribuidos, con los datos de cada usuario guardados en tres servidores front-end en el grupo.</span><span class="sxs-lookup"><span data-stu-id="89fff-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="89fff-113">Para obtener más información acerca de esta nueva arquitectura, consulte [cambios de topología en Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="89fff-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="89fff-114">Si no desea implementar tres servidores Enterprise Edition front-end y desea recuperar desastres, le recomendamos que use Lync Server Standard Edition y cree dos grupos con una relación de copia de seguridad emparejada.</span><span class="sxs-lookup"><span data-stu-id="89fff-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="89fff-115">Esto proporcionará una solución de recuperación ante desastres con solo dos servidores.</span><span class="sxs-lookup"><span data-stu-id="89fff-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="89fff-116">Para obtener más información, sobre las características y las topologías de alta disponibilidad y recuperación ante desastres, consulte [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="89fff-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="89fff-117">Planificación de la administración de grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="89fff-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="89fff-118">Para los grupos de servidores front-end, siga las instrucciones de esta sección.</span><span class="sxs-lookup"><span data-stu-id="89fff-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="89fff-119">Garantizar la funcionalidad de los grupos</span><span class="sxs-lookup"><span data-stu-id="89fff-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="89fff-120">Con el nuevo modelo distribuido para los grupos de servidores front-end, se deben ejecutar ciertos números de servidores de grupo para que el grupo funcione.</span><span class="sxs-lookup"><span data-stu-id="89fff-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="89fff-121">Hay dos modos de pérdida para un grupo</span><span class="sxs-lookup"><span data-stu-id="89fff-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="89fff-122">Pérdida de cuórum en el grupo de enrutamiento, provocada por una cantidad insuficiente de servidores de réplicas para un determinado grupo de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="89fff-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="89fff-123">Un grupo de enrutamiento es una agregación de un conjunto de usuarios alojados en el grupo.</span><span class="sxs-lookup"><span data-stu-id="89fff-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="89fff-124">Cada grupo de enrutamiento tiene tres réplicas en el Grupo: uno principal y dos secundarios.</span><span class="sxs-lookup"><span data-stu-id="89fff-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="89fff-125">Pérdida de cuórum en el grupo de servidores, que ocurre cuando no hay una cantidad suficiente de servidores semilla en ejecución en el grupo.</span><span class="sxs-lookup"><span data-stu-id="89fff-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="89fff-126">Pérdida de cuórum en el grupo de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="89fff-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="89fff-p107">La primera vez que inicia un nuevo grupo de servidores front-end, es fundamental que el 85 % de los servidores estén en funcionamiento, tal como se muestra en la tabla siguiente. Si hay menos servidores en ejecución, es posible que los servicios queden interrumpidos en el estado de inicio y que el grupo no se inicie.</span><span class="sxs-lookup"><span data-stu-id="89fff-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89fff-129">Cantidad total de servidores en el grupo</span><span class="sxs-lookup"><span data-stu-id="89fff-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="89fff-130">Cantidad de servidores que necesitan estar en ejecución para que el grupo se inicie por primera vez</span><span class="sxs-lookup"><span data-stu-id="89fff-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89fff-131">1</span><span class="sxs-lookup"><span data-stu-id="89fff-131">2</span></span></p></td>
<td><p><span data-ttu-id="89fff-132">1</span><span class="sxs-lookup"><span data-stu-id="89fff-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-133">3</span><span class="sxs-lookup"><span data-stu-id="89fff-133">3</span></span></p></td>
<td><p><span data-ttu-id="89fff-134">3</span><span class="sxs-lookup"><span data-stu-id="89fff-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-135">4</span><span class="sxs-lookup"><span data-stu-id="89fff-135">4</span></span></p></td>
<td><p><span data-ttu-id="89fff-136">3</span><span class="sxs-lookup"><span data-stu-id="89fff-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-137">5</span><span class="sxs-lookup"><span data-stu-id="89fff-137">5</span></span></p></td>
<td><p><span data-ttu-id="89fff-138">4</span><span class="sxs-lookup"><span data-stu-id="89fff-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-139">6</span><span class="sxs-lookup"><span data-stu-id="89fff-139">6</span></span></p></td>
<td><p><span data-ttu-id="89fff-140">5</span><span class="sxs-lookup"><span data-stu-id="89fff-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-141">7</span><span class="sxs-lookup"><span data-stu-id="89fff-141">7</span></span></p></td>
<td><p><span data-ttu-id="89fff-142">5</span><span class="sxs-lookup"><span data-stu-id="89fff-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-143">4,8</span><span class="sxs-lookup"><span data-stu-id="89fff-143">8</span></span></p></td>
<td><p><span data-ttu-id="89fff-144">6</span><span class="sxs-lookup"><span data-stu-id="89fff-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-145">99,999</span><span class="sxs-lookup"><span data-stu-id="89fff-145">9</span></span></p></td>
<td><p><span data-ttu-id="89fff-146">7</span><span class="sxs-lookup"><span data-stu-id="89fff-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-147">base10</span><span class="sxs-lookup"><span data-stu-id="89fff-147">10</span></span></p></td>
<td><p><span data-ttu-id="89fff-148">4,8</span><span class="sxs-lookup"><span data-stu-id="89fff-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-149">once</span><span class="sxs-lookup"><span data-stu-id="89fff-149">11</span></span></p></td>
<td><p><span data-ttu-id="89fff-150">99,999</span><span class="sxs-lookup"><span data-stu-id="89fff-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-151">2007</span><span class="sxs-lookup"><span data-stu-id="89fff-151">12</span></span></p></td>
<td><p><span data-ttu-id="89fff-152">base10</span><span class="sxs-lookup"><span data-stu-id="89fff-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="89fff-153">Cada vez subsiguiente que se inicie el grupo, es preciso iniciar el 85 % de los servidores (tal como se muestra en la tabla anterior).</span><span class="sxs-lookup"><span data-stu-id="89fff-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="89fff-154">Si no se puede iniciar esta cantidad de servidores (pero se puede iniciar una cantidad de servidores suficiente para que no haya pérdida de cuórum en el grupo de servidores), puede usar el cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** para permitir que el grupo se recupere de esta pérdida de cuórum en el grupo de enrutamiento y pueda progresar.</span><span class="sxs-lookup"><span data-stu-id="89fff-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="89fff-155">Para obtener más información sobre cómo usar este cmdlet, consulte [RESET-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="89fff-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89fff-156">Puesto que Lync Server usa la base de datos principal de SQL como testigo, si cierra la base de datos principal y cambia a la copia reflejada, y cierra los suficientes servidores frontales para que no haya suficiente ejecución según la tabla anterior, todo el grupo se cerrará.</span><span class="sxs-lookup"><span data-stu-id="89fff-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="89fff-157">Para obtener más información, consulte <A href="http://go.microsoft.com/fwlink/?linkid=393672">testigo de creación de reflejo de base de datos</A>.</span><span class="sxs-lookup"><span data-stu-id="89fff-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="89fff-158">Pérdida de cuórum en el grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="89fff-158">Pool-level quorum loss</span></span>

<span data-ttu-id="89fff-159">Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="89fff-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="89fff-160">Si el número de servidores que se ejecutan está por debajo del nivel funcional, como se muestra en la tabla siguiente, el resto de los servidores del grupo detendrán todos los servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89fff-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="89fff-161">Tenga en cuenta que los números de la tabla siguiente suponen que los servidores de servicios de fondo del grupo se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="89fff-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89fff-162">Número total de servidores front-end en el grupo</span><span class="sxs-lookup"><span data-stu-id="89fff-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="89fff-163">Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione</span><span class="sxs-lookup"><span data-stu-id="89fff-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89fff-164">1</span><span class="sxs-lookup"><span data-stu-id="89fff-164">2</span></span></p></td>
<td><p><span data-ttu-id="89fff-165">1</span><span class="sxs-lookup"><span data-stu-id="89fff-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-166">3-4</span><span class="sxs-lookup"><span data-stu-id="89fff-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="89fff-167">2 cualesquiera</span><span class="sxs-lookup"><span data-stu-id="89fff-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-168">5-6</span><span class="sxs-lookup"><span data-stu-id="89fff-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="89fff-169">3 cualesquiera</span><span class="sxs-lookup"><span data-stu-id="89fff-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-170">7</span><span class="sxs-lookup"><span data-stu-id="89fff-170">7</span></span></p></td>
<td><p><span data-ttu-id="89fff-171">4 cualesquiera</span><span class="sxs-lookup"><span data-stu-id="89fff-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89fff-172">8-9</span><span class="sxs-lookup"><span data-stu-id="89fff-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="89fff-173">4 cualesquiera de los primeros 7 servidores</span><span class="sxs-lookup"><span data-stu-id="89fff-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89fff-174">10-12</span><span class="sxs-lookup"><span data-stu-id="89fff-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="89fff-175">5 cualesquiera de los primeros 9 servidores</span><span class="sxs-lookup"><span data-stu-id="89fff-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="89fff-176">En la tabla anterior, los "primeros servidores" son los servidores que aparecieron primero, en orden cronológico, cuando se inició el grupo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="89fff-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="89fff-177">Para determinar estos servidores, puede usar el cmdlet **Get-CsComputer** con la opción **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="89fff-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="89fff-178">Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.</span><span class="sxs-lookup"><span data-stu-id="89fff-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="89fff-179">Pools front end con dos servidores front-end</span><span class="sxs-lookup"><span data-stu-id="89fff-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="89fff-180">No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="89fff-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="89fff-181">Si alguna vez necesita implementar ese grupo, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="89fff-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="89fff-182">Si uno de los dos servidores de solicitudes de cliente deja de funcionar, debe intentar volver a ponerlo en marcha tan pronto como pueda.</span><span class="sxs-lookup"><span data-stu-id="89fff-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="89fff-183">Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en línea tan pronto como termine la actualización.</span><span class="sxs-lookup"><span data-stu-id="89fff-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="89fff-184">Si, por algún motivo, necesita detener los dos servidores en algún momento, realice lo siguiente cuando termine el tiempo de inactividad del grupo:</span><span class="sxs-lookup"><span data-stu-id="89fff-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="89fff-185">Lo mejor es reiniciar ambos servidores front-end al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="89fff-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="89fff-186">Si no se pueden reiniciar los dos servidores al mismo tiempo, será necesario ponerlos en funcionamiento nuevamente en el orden inverso al orden en que se detuvieron.</span><span class="sxs-lookup"><span data-stu-id="89fff-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="89fff-187">Si no puede hacer una copia de seguridad en ese orden, use el siguiente cmdlet antes de volver a poner el grupo de servidores:.</span><span class="sxs-lookup"><span data-stu-id="89fff-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="89fff-188">Pasos adicionales para garantizar que los grupos sean funcionales</span><span class="sxs-lookup"><span data-stu-id="89fff-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="89fff-189">Es necesario tener en cuenta algunos otros factores a fin de asegurarse de que los grupos de servidores front-end sigan siendo funcionales.</span><span class="sxs-lookup"><span data-stu-id="89fff-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="89fff-190">Al mover usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se estén ejecutando.</span><span class="sxs-lookup"><span data-stu-id="89fff-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="89fff-191">Si establece una relación de emparejamiento entre este grupo y otro grupo para fines de recuperación ante desastres, después de establecer dicha relación, debe asegurarse de que este grupo tenga tres servidores front-end ejecutándose de forma simultánea en algún momento para sincronizar correctamente datos con el grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="89fff-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="89fff-192">Para obtener más información sobre el emparejamiento de bloqueos y las características de recuperación ante desastres, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="89fff-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="89fff-193">Mejorar la confiabilidad de las actualizaciones de grupos</span><span class="sxs-lookup"><span data-stu-id="89fff-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="89fff-194">Cuando necesite actualizar o aplicar revisiones a los servidores de un grupo de servidores front-end, siga el flujo de trabajo que se muestra en [actualizar o actualizar los servidores front-end de Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)y las siguientes pautas:</span><span class="sxs-lookup"><span data-stu-id="89fff-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="89fff-195">Al pasar de un dominio de actualización a otro para actualizaciones (siguiendo el flujo de trabajo de actualización [o actualización de los servidores front-end de Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), deberá usar el cmdlet **Get-CsPoolUpgradeReadinessState** y comprobar el estado de lista.</span><span class="sxs-lookup"><span data-stu-id="89fff-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="89fff-196">Agregar una espera de 20 minutos entre cada dominio de actualización después de que se encuentre "listo" hará que las actualizaciones sean más confiables.</span><span class="sxs-lookup"><span data-stu-id="89fff-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="89fff-197">Si no está **listo** durante los 20 minutos, reinicie el temporizador de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="89fff-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="89fff-198">Además, puede ejecutar el cmdlet **Get-CsPoolFabricState** antes y después de iniciar el intervalo de 20 minutos y asegurarse de que no haya cambios en las principales y secundarias de los grupos de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="89fff-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="89fff-199">No pase al siguiente dominio de actualización si alguno de los servidores del último dominio de actualización revisada se bloquea o no se reinicia.</span><span class="sxs-lookup"><span data-stu-id="89fff-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="89fff-200">Esto también se aplica si no se puede iniciar ninguno de los servidores dentro de una actualización.</span><span class="sxs-lookup"><span data-stu-id="89fff-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="89fff-201">Ejecute **Get-CsPoolFabricState** para asegurarse de que todos los grupos de enrutamiento tienen como principal y como mínimo un secundario; Esto confirmará si todos los usuarios tienen servicio.</span><span class="sxs-lookup"><span data-stu-id="89fff-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="89fff-202">Si algunos usuarios tienen servicio y otros no, ejecute **Get-CsPoolFabricState** con la opción – verboso para comprobar si hay grupos de enrutamiento con réplicas que faltan.</span><span class="sxs-lookup"><span data-stu-id="89fff-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="89fff-203">No reinicie todo el grupo como primer paso de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="89fff-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="89fff-204">Para obtener más información sobre este cmdlet, vea [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="89fff-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="89fff-205">Asegúrese de que todas las instancias del visor de eventos o de las ventanas de monitor de rendimiento estén cerradas para que Windows fabric se instale o desinstale.</span><span class="sxs-lookup"><span data-stu-id="89fff-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="89fff-206">Cambiar la configuración del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="89fff-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="89fff-207">Cada vez que agregue servidores front-end a un grupo, o quítelos del grupo y, a continuación, publique la nueva topología, siga estas pautas:</span><span class="sxs-lookup"><span data-stu-id="89fff-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="89fff-208">Una vez publicada la nueva topología, debe reiniciar cada servidor front-end en el grupo.</span><span class="sxs-lookup"><span data-stu-id="89fff-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="89fff-209">Reinícielos de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="89fff-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="89fff-210">Si se ha desactivado todo el grupo durante el cambio de configuración, ejecute el siguiente cmdlet una vez publicada la nueva topología:</span><span class="sxs-lookup"><span data-stu-id="89fff-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="89fff-211">Si se produce un error en un servidor front-end y es improbable que se cambie por unos días o más, quite el servidor de la topología.</span><span class="sxs-lookup"><span data-stu-id="89fff-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="89fff-212">Agregue el nuevo servidor front-end a la topología cuando esté disponible de nuevo.</span><span class="sxs-lookup"><span data-stu-id="89fff-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

