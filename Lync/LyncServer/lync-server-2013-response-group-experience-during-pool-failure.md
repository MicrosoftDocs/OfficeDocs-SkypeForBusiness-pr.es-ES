---
title: Lync Server 2013 experiencia de grupo de respuesta durante un error de grupo
description: Lync Server 2013 la experiencia del grupo de respuesta durante un error en el grupo.
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564576"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="6fbb3-103">Experiencia de grupo de respuesta en Lync Server 2013 durante un error de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="6fbb3-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fbb3-104">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6fbb3-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6fbb3-105">En este apartado se describe con detalle cómo la actividad del grupo de respuesta se ve afectada en las siguientes etapas:</span><span class="sxs-lookup"><span data-stu-id="6fbb3-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="6fbb3-106">Se produce una interrupción en el grupo principal pero aún no se ha iniciado la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="6fbb3-107">El servicio se conmuta por error en el grupo de reserva.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="6fbb3-108">El servicio se conmuta por recuperación en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="6fbb3-109">Experiencia del usuario cuando se produce la interrupción</span><span class="sxs-lookup"><span data-stu-id="6fbb3-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="6fbb3-110">Cuando se produce una interrupción del grupo o del sitio, pero el administrador aún no ha iniciado la conmutación por error, la actividad del grupo de respuesta se administra tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fbb3-p101">Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="6fbb3-113">Se produce la interrupción</span><span class="sxs-lookup"><span data-stu-id="6fbb3-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fbb3-114">Tipo de llamada o intervención de usuario</span><span class="sxs-lookup"><span data-stu-id="6fbb3-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="6fbb3-115">Durante una interrupción</span><span class="sxs-lookup"><span data-stu-id="6fbb3-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-116">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-117">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-118">Las llamadas anónimas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-119">Las llamadas en curso aún no se conectaron a un agente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-120">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-121">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="6fbb3-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-122">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-123">Si los grupos de respuesta se han importado, las llamadas se conectarán al grupo de reserva pero no se podrá acceder a los agentes hospedados en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-124">Llamadas de agentes en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fbb3-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-125">La característica se deshabilita durante esta etapa.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-126">Inicio de sesión e información de los agentes</span><span class="sxs-lookup"><span data-stu-id="6fbb3-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-127">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-128">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-129">Los grupos de agentes importados no se muestran en la consola de los agentes.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-130">Configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fbb3-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-131">Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-132">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-133">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="6fbb3-134">Experiencia de usuario durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="6fbb3-134">User Experience During Failover</span></span>

<span data-ttu-id="6fbb3-p102">Cuando un administrador invoca la conmutación por error a un grupo de copia de seguridad, la actividad del grupo de respuesta se controla durante y después de la conmutación por error como se describe en la siguiente tabla. La primera columna describe el tipo de actividad que podría estar ocurriendo. La columna central describe cómo se controla cada actividad durante el breve tiempo que se tarda en conmutar por error al grupo de copia de seguridad. La última columna describe cómo se controla la actividad de la duración, después de finalizar el proceso de conmutación por error y el grupo de copia de seguridad se mantiene en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fbb3-p103">Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="6fbb3-141">Se ha iniciado la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="6fbb3-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fbb3-142">Tipo de llamada o intervención de usuario</span><span class="sxs-lookup"><span data-stu-id="6fbb3-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="6fbb3-143">Durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="6fbb3-143">During Failover</span></span></th>
<th><span data-ttu-id="6fbb3-144">Después de que finalice la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="6fbb3-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-145">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-146">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-147">Las llamadas anónimas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-148">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-149">Para los grupos de respuesta importados, las llamadas anónimas que han alcanzado el grupo de reserva permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-150">Las llamadas en curso aún no se conectaron a un agente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-151">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-152">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-153">Para los grupos de respuesta importados, las llamadas que han alcanzado el grupo de reserva permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-154">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="6fbb3-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-155">Las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-156">Para los grupos de respuesta importados, las llamadas se conectan al grupo de reserva, pero no se pueden alcanzar los agentes hospedados en el grupo principal</span><span class="sxs-lookup"><span data-stu-id="6fbb3-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-157">Si los grupos de respuesta no se importaron, las llamadas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-158">Para los grupos de respuesta importados, las llamadas se conectan al grupo de reserva.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-159">Llamadas de agentes en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fbb3-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-160">La característica se deshabilita durante esta etapa</span><span class="sxs-lookup"><span data-stu-id="6fbb3-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-161">Si los grupos de respuesta no se han importado, la llamada fallará.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-162">Para los grupos de respuesta importados, las llamadas se realizan con éxito.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-163">Inicio de sesión e información de los agentes</span><span class="sxs-lookup"><span data-stu-id="6fbb3-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-164">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-165">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-166">Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-167">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-168">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-169">Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-170">Configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fbb3-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-171">Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-172">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-173">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-174">Los grupos de respuesta del grupo principal se pueden visualizar, en función de la disponibilidad de la base de datos de back-end, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-175">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-176">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="6fbb3-177">Experiencia de usuario durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="6fbb3-177">User Experience During Failback</span></span>

<span data-ttu-id="6fbb3-178">Cuando un administrador invoca la conmutación por recuperación al grupo principal, la actividad del grupo de respuesta se administra durante y después de la conmutación por recuperación tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fbb3-p104">Durante la recuperación de desastres, las llamadas se comportan de manera diferente en función de si los grupos de respuesta del grupo principal se han importado al grupo de reserva durante la recuperación o no. En la tabla siguiente, las referencias a los grupos de respuesta importados indican que los grupos de respuesta del grupo principal se han importado al grupo de reserva durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="6fbb3-181">Administración de llamadas en la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="6fbb3-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fbb3-182">Tipo de llamada o intervención de usuario</span><span class="sxs-lookup"><span data-stu-id="6fbb3-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="6fbb3-183">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="6fbb3-183">During Failback</span></span></th>
<th><span data-ttu-id="6fbb3-184">Después de que la conmutación por recuperación haya finalizado</span><span class="sxs-lookup"><span data-stu-id="6fbb3-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-185">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-186">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-187">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada anónima en este estado.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-188">Para los grupos de respuestas importados, las llamadas anónimas permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-189">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-190">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada anónima en este estado.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-191">Para los grupos de respuestas importados, las llamadas anónimas permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-192">Las llamadas en curso aún no se conectaron a un agente</span><span class="sxs-lookup"><span data-stu-id="6fbb3-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-193">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-194">Para los grupos de respuestas importados, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-195">Si no se ha importado ningún grupo de respuestas, no habrá ninguna llamada en este estado.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-196">Para los grupos de respuestas importados, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-197">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="6fbb3-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-198">Las llamadas se conectan al grupo principal, pero no se puede alcanzar a los agentes hospedados en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-199">Las llamadas se conectan al grupo principal</span><span class="sxs-lookup"><span data-stu-id="6fbb3-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-200">Llamadas de agentes en nombre de un grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fbb3-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-201">La característica se deshabilita durante esta etapa.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="6fbb3-202">Las llamadas se realizan con éxito.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fbb3-203">Inicio de sesión e información de los agentes</span><span class="sxs-lookup"><span data-stu-id="6fbb3-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-204">Los grupos de agentes pertenecientes al grupo principal pueden verse en la consola de los agentes, pero estos no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-205">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-206">Los grupos de agentes importados se muestran en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-207">Los grupos de agentes del grupo principal se pueden ver en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-208">Los grupos de agentes pertenecientes al grupo de reserva pueden verse en la consola de los agentes y estos pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-209">Los grupos de agentes importados no se muestran en la consola de los agentes.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fbb3-210">Configuración de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="6fbb3-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-211">Los grupos de respuesta que pertenecen al grupo principal pueden verse, en función de la disponibilidad de la base de datos de back-end del grupo principal, pero no pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-212">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-213">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6fbb3-214">Los grupos de respuesta del grupo principal se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-215">Los grupos de respuesta que pertenecen al grupo de reserva pueden verse y modificarse.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="6fbb3-216">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fbb3-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

