---
title: Lync Server 2013 experiencia de grupo de respuesta durante un error de grupo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e7867af15eb5e8824562eb03244280cfbc84f7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="50de6-102">Experiencia de grupo de respuesta en Lync Server 2013 durante un error de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="50de6-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50de6-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="50de6-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="50de6-104">En este apartado se describe con detalle cómo la actividad del grupo de respuesta se ve afectada en las siguientes etapas:</span><span class="sxs-lookup"><span data-stu-id="50de6-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="50de6-105">Se produce una interrupción en el grupo principal pero aún no se ha iniciado la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="50de6-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="50de6-106">El servicio se conmuta por error en el grupo de reserva.</span><span class="sxs-lookup"><span data-stu-id="50de6-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="50de6-107">El servicio se conmuta por recuperación en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="50de6-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="50de6-108">Experiencia del usuario cuando se produce la interrupción</span><span class="sxs-lookup"><span data-stu-id="50de6-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="50de6-109">Cuando se produce una interrupción del grupo o del sitio, pero el administrador aún no ha iniciado la conmutación por error, la actividad del grupo de respuesta se administra tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="50de6-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50de6-p101">Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="50de6-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="50de6-112">Se produce la interrupción</span><span class="sxs-lookup"><span data-stu-id="50de6-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50de6-113">Tipo de llamada o intervención de usuario</span><span class="sxs-lookup"><span data-stu-id="50de6-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="50de6-114">Durante una interrupción</span><span class="sxs-lookup"><span data-stu-id="50de6-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50de6-115">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="50de6-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-116">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-117">Las llamadas anónimas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-118">Las llamadas en curso aún no se conectaron a un agente</span><span class="sxs-lookup"><span data-stu-id="50de6-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="50de6-119">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50de6-120">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="50de6-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-121">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-122">Si los grupos de respuesta se han importado, las llamadas se conectarán al grupo de reserva pero no se podrá acceder a los agentes hospedados en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="50de6-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-123">Llamadas de agentes en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="50de6-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="50de6-124">La característica se deshabilita durante esta etapa.</span><span class="sxs-lookup"><span data-stu-id="50de6-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50de6-125">Inicio de sesión e información de los agentes</span><span class="sxs-lookup"><span data-stu-id="50de6-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-126">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-127">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-128">Los grupos de agentes importados no se muestran en la consola de los agentes.</span><span class="sxs-lookup"><span data-stu-id="50de6-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-129">Configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="50de6-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-130">Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-131">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-132">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50de6-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="50de6-133">Experiencia de usuario durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="50de6-133">User Experience During Failover</span></span>

<span data-ttu-id="50de6-p102">Cuando un administrador invoca la conmutación por error a un grupo de copia de seguridad, la actividad del grupo de respuesta se controla durante y después de la conmutación por error como se describe en la siguiente tabla. La primera columna describe el tipo de actividad que podría estar ocurriendo. La columna central describe cómo se controla cada actividad durante el breve tiempo que se tarda en conmutar por error al grupo de copia de seguridad. La última columna describe cómo se controla la actividad de la duración, después de finalizar el proceso de conmutación por error y el grupo de copia de seguridad se mantiene en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="50de6-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50de6-p103">Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="50de6-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="50de6-140">Se ha iniciado la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="50de6-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50de6-141">Tipo de llamada o intervención de usuario</span><span class="sxs-lookup"><span data-stu-id="50de6-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="50de6-142">Durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="50de6-142">During Failover</span></span></th>
<th><span data-ttu-id="50de6-143">Después de que finalice la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="50de6-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50de6-144">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="50de6-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-145">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-146">Las llamadas anónimas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-147">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-148">Para los grupos de respuesta importados, las llamadas anónimas que han alcanzado el grupo de reserva permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-149">Las llamadas en curso aún no se conectaron a un agente</span><span class="sxs-lookup"><span data-stu-id="50de6-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="50de6-150">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-151">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</span><span class="sxs-lookup"><span data-stu-id="50de6-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="50de6-152">Para los grupos de respuesta importados, las llamadas que han alcanzado el grupo de reserva permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50de6-153">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="50de6-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-154">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-155">Para los grupos de respuesta importados, las llamadas se conectan al grupo de reserva, pero no se pueden alcanzar los agentes hospedados en el grupo principal</span><span class="sxs-lookup"><span data-stu-id="50de6-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-156">Si los grupos de respuesta no se importaron, las llamadas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="50de6-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-157">Para los grupos de respuesta importados, las llamadas se conectan al grupo de reserva.</span><span class="sxs-lookup"><span data-stu-id="50de6-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-158">Llamadas de agentes en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="50de6-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="50de6-159">La característica se deshabilita durante esta etapa</span><span class="sxs-lookup"><span data-stu-id="50de6-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-160">Si los grupos de respuesta no se han importado, la llamada fallará.</span><span class="sxs-lookup"><span data-stu-id="50de6-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="50de6-161">Para los grupos de respuesta importados, las llamadas se realizan con éxito.</span><span class="sxs-lookup"><span data-stu-id="50de6-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50de6-162">Inicio de sesión e información de los agentes</span><span class="sxs-lookup"><span data-stu-id="50de6-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-163">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-164">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-165">Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-166">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-167">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-168">Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-169">Configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="50de6-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-170">Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-171">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-172">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50de6-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-173">Los grupos de respuesta del grupo principal se pueden visualizar, en función de la disponibilidad de la base de datos de back-end, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="50de6-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-174">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-175">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50de6-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="50de6-176">Experiencia de usuario durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="50de6-176">User Experience During Failback</span></span>

<span data-ttu-id="50de6-177">Cuando un administrador invoca la conmutación por recuperación al grupo principal, la actividad del grupo de respuesta se administra durante y después de la conmutación por recuperación tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="50de6-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50de6-p104">Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="50de6-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="50de6-180">Administración de llamadas en la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="50de6-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50de6-181">Tipo de llamada o intervención de usuario</span><span class="sxs-lookup"><span data-stu-id="50de6-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="50de6-182">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="50de6-182">During Failback</span></span></th>
<th><span data-ttu-id="50de6-183">Después de que la conmutación por recuperación haya finalizado</span><span class="sxs-lookup"><span data-stu-id="50de6-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50de6-184">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="50de6-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-185">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-186">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada anónima en este estado.</span><span class="sxs-lookup"><span data-stu-id="50de6-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="50de6-187">Para los grupos de respuestas importados, las llamadas anónimas permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-188">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="50de6-189">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada anónima en este estado.</span><span class="sxs-lookup"><span data-stu-id="50de6-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="50de6-190">Para los grupos de respuestas importados, las llamadas anónimas permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="50de6-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-191">Las llamadas en curso aún no se conectaron a un agente</span><span class="sxs-lookup"><span data-stu-id="50de6-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-192">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</span><span class="sxs-lookup"><span data-stu-id="50de6-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="50de6-193">Para los grupos de respuestas importados, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-194">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</span><span class="sxs-lookup"><span data-stu-id="50de6-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="50de6-195">Para los grupos de respuestas importados, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="50de6-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50de6-196">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="50de6-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="50de6-197">Las llamadas se conectan al grupo principal, pero no se puede alcanzar a los agentes hospedados en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="50de6-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="50de6-198">Las llamadas se conectan al grupo principal</span><span class="sxs-lookup"><span data-stu-id="50de6-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-199">Llamadas de agentes en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="50de6-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="50de6-200">La característica se deshabilita durante esta etapa.</span><span class="sxs-lookup"><span data-stu-id="50de6-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="50de6-201">Las llamadas se realizan con éxito.</span><span class="sxs-lookup"><span data-stu-id="50de6-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50de6-202">Inicio de sesión e información de los agentes</span><span class="sxs-lookup"><span data-stu-id="50de6-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-203">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-204">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-205">Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-206">Los grupos de agentes del grupo principal se pueden ver en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-207">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="50de6-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="50de6-208">Los grupos de agentes importados no se muestran en la consola de los agentes.</span><span class="sxs-lookup"><span data-stu-id="50de6-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50de6-209">Configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="50de6-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="50de6-210">Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-211">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-212">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50de6-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="50de6-213">Los grupos de respuesta del grupo principal se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="50de6-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-214">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="50de6-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="50de6-215">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="50de6-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

