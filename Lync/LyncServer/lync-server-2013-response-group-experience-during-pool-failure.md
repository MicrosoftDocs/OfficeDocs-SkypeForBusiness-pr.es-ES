---
title: 'Lync Server 2013: Experiencia de grupo de respuesta durante errores del grupo de servidores'
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
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="da6c8-102">Experiencia de grupo de respuesta durante errores del grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da6c8-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da6c8-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="da6c8-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="da6c8-104">En esta sección se describe detalladamente cómo afecta la actividad de grupos de respuesta en las siguientes etapas:</span><span class="sxs-lookup"><span data-stu-id="da6c8-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="da6c8-105">Se produce una interrupción en el grupo principal, pero aún no se ha iniciado la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="da6c8-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="da6c8-106">El servicio se conmuta por error al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da6c8-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="da6c8-107">El servicio no puede recuperarse en el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="da6c8-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="da6c8-108">Experiencia de usuario cuando se produce una interrupción</span><span class="sxs-lookup"><span data-stu-id="da6c8-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="da6c8-109">Cuando se produce una interrupción en un grupo o sitio, pero el administrador aún no ha iniciado la conmutación por error, la actividad del grupo de respuesta se controla como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da6c8-110">Durante la recuperación de desastres, las llamadas se comportan de forma diferente en función de si los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="da6c8-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="da6c8-111">En la tabla siguiente, las referencias a grupos de respuesta importados significan que los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="da6c8-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="da6c8-112">Se produce una interrupción</span><span class="sxs-lookup"><span data-stu-id="da6c8-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da6c8-113">Tipo de acción de usuario o llamada</span><span class="sxs-lookup"><span data-stu-id="da6c8-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="da6c8-114">Durante la interrupción</span><span class="sxs-lookup"><span data-stu-id="da6c8-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-115">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-116">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-117">Las llamadas anónimas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="da6c8-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-118">Llamadas en curso que aún no están conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="da6c8-119">Las llamadas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="da6c8-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-120">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="da6c8-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-121">Las llamadas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="da6c8-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-122">Si se importaron grupos de respuesta, las llamadas se conectan al grupo de copia de seguridad, pero no se pueden alcanzar los agentes alojados en el bloque principal.</span><span class="sxs-lookup"><span data-stu-id="da6c8-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-123">Llamadas del agente en nombre del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="da6c8-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="da6c8-124">La característica está deshabilitada durante este paso.</span><span class="sxs-lookup"><span data-stu-id="da6c8-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-125">Inicio de sesión del agente e información del agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-126">Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-127">Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-128">Los grupos de agentes importados no se muestran en la consola del agente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-129">Configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="da6c8-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-130">Los grupos de respuesta que pertenecen al grupo primario se pueden ver, en función de la disponibilidad de la base de datos back-end del grupo principal, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-131">Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-132">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da6c8-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="da6c8-133">Experiencia del usuario durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="da6c8-133">User Experience During Failover</span></span>

<span data-ttu-id="da6c8-134">Cuando un administrador invoca la conmutación por error a un grupo de copia de seguridad, la actividad del grupo de respuesta se controla durante y después de la conmutación por error, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="da6c8-135">En la primera columna se describe el tipo de actividad que se puede llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="da6c8-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="da6c8-136">La columna central describe cómo se administra cada actividad durante el breve tiempo que se tarda en conmutar por error al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da6c8-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="da6c8-137">La última columna describe cómo se controla la actividad durante la duración, una vez completada la conmutación por error y en la que se encuentra el grupo de copia de seguridad para el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="da6c8-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da6c8-138">Durante la recuperación de desastres, las llamadas se comportan de forma diferente en función de si los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="da6c8-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="da6c8-139">En la tabla siguiente, las referencias a grupos de respuesta importados significan que los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="da6c8-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="da6c8-140">Se inicia la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="da6c8-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da6c8-141">Tipo de acción de usuario o llamada</span><span class="sxs-lookup"><span data-stu-id="da6c8-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="da6c8-142">Durante la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="da6c8-142">During Failover</span></span></th>
<th><span data-ttu-id="da6c8-143">Después de que se complete la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="da6c8-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-144">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-145">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-146">Las llamadas anónimas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="da6c8-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-147">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-148">Para los grupos de respuesta importados, las llamadas anónimas que hayan llegado al grupo de backup seguirán estando conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-149">Llamadas en curso que aún no están conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="da6c8-150">Las llamadas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="da6c8-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-151">Si los grupos de respuesta no se importaron, no hay llamadas en este estado.</span><span class="sxs-lookup"><span data-stu-id="da6c8-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-152">Para los grupos de respuesta importados, las llamadas que hayan llegado al grupo de copia de seguridad seguirán estando conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-153">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="da6c8-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-154">Las llamadas se desconectan.</span><span class="sxs-lookup"><span data-stu-id="da6c8-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-155">Para los grupos de respuesta importados, las llamadas se conectan al grupo de copia de seguridad, pero los agentes alojados en el grupo primario son inaccesibles.</span><span class="sxs-lookup"><span data-stu-id="da6c8-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-156">Si los grupos de respuesta no se importaron, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="da6c8-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-157">Para los grupos de respuesta importados, las llamadas se conectan al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="da6c8-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-158">Llamadas del agente en nombre del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="da6c8-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="da6c8-159">La característica está deshabilitada durante esta fase</span><span class="sxs-lookup"><span data-stu-id="da6c8-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-160">Si los grupos de respuesta no se importaron, no se pueden realizar llamadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-161">Para grupos de respuesta importados, las llamadas se realizarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-162">Inicio de sesión del agente e información del agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-163">Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-164">Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-165">Los grupos de agentes importados se muestran en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-166">Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-167">Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-168">Los grupos de agentes importados se muestran en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-169">Configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="da6c8-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-170">Los grupos de respuesta que pertenecen al grupo primario se pueden ver, en función de la disponibilidad de la base de datos back-end del grupo principal, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-171">Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-172">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da6c8-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-173">Los grupos de respuesta que pertenecen al grupo primario se pueden ver, dependiendo de la disponibilidad de la base de datos back-end, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-174">Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-175">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da6c8-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="da6c8-176">Experiencia de usuario durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="da6c8-176">User Experience During Failback</span></span>

<span data-ttu-id="da6c8-177">Cuando un administrador invoca la conmutación por recuperación al grupo principal, la actividad del grupo de respuesta se controla durante y después de la conmutación por recuperación, como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da6c8-178">Durante la recuperación de desastres, las llamadas se comportan de forma diferente en función de si los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="da6c8-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="da6c8-179">En la tabla siguiente, las referencias a grupos de respuesta importados significan que los grupos de respuesta del grupo principal se importaron al grupo de copia de seguridad durante el modo de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="da6c8-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="da6c8-180">Control de llamadas en failback</span><span class="sxs-lookup"><span data-stu-id="da6c8-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da6c8-181">Tipo de acción de usuario o llamada</span><span class="sxs-lookup"><span data-stu-id="da6c8-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="da6c8-182">Durante la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="da6c8-182">During Failback</span></span></th>
<th><span data-ttu-id="da6c8-183">Tras completar la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="da6c8-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-184">Llamadas conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-185">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-186">Si los grupos de respuesta no se importaron, no hay llamadas anónimas en este estado.</span><span class="sxs-lookup"><span data-stu-id="da6c8-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-187">Para los grupos de respuesta importados, las llamadas anónimas permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-188">Las llamadas regulares permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-189">Si los grupos de respuesta no se importaron, no hay llamadas anónimas en este estado.</span><span class="sxs-lookup"><span data-stu-id="da6c8-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-190">Para los grupos de respuesta importados, las llamadas anónimas permanecen conectadas.</span><span class="sxs-lookup"><span data-stu-id="da6c8-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-191">Llamadas en curso que aún no están conectadas a un agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-192">Si los grupos de respuesta no se importaron, no hay llamadas en este estado.</span><span class="sxs-lookup"><span data-stu-id="da6c8-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-193">Para los grupos de respuesta importados, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="da6c8-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-194">Si los grupos de respuesta no se importaron, no hay llamadas en este estado.</span><span class="sxs-lookup"><span data-stu-id="da6c8-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-195">Para los grupos de respuesta importados, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="da6c8-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-196">Llamadas nuevas</span><span class="sxs-lookup"><span data-stu-id="da6c8-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="da6c8-197">Las llamadas se conectan al grupo de servidores principal, pero los agentes alojados en el grupo primario no son accesibles.</span><span class="sxs-lookup"><span data-stu-id="da6c8-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="da6c8-198">Las llamadas se conectan al grupo primario.</span><span class="sxs-lookup"><span data-stu-id="da6c8-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-199">Llamadas del agente en nombre del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="da6c8-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="da6c8-200">La característica está deshabilitada durante este paso.</span><span class="sxs-lookup"><span data-stu-id="da6c8-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="da6c8-201">Las llamadas se realizaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da6c8-202">Inicio de sesión del agente e información del agente</span><span class="sxs-lookup"><span data-stu-id="da6c8-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-203">Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente, pero los agentes no pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-204">Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-205">Los grupos de agentes importados se muestran en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-206">Los grupos de agentes que pertenecen al repositorio principal pueden verse en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-207">Los grupos de agentes que pertenecen al grupo de copia de seguridad pueden verse en la consola del agente y los agentes pueden iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da6c8-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-208">Los grupos de agentes importados no se muestran en la consola del agente.</span><span class="sxs-lookup"><span data-stu-id="da6c8-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da6c8-209">Configuración del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="da6c8-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-210">Los grupos de respuesta que pertenecen al grupo primario se pueden ver, en función de la disponibilidad de la base de datos back-end del grupo principal, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-211">Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-212">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da6c8-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="da6c8-213">Los grupos de respuesta que pertenecen al grupo principal se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-214">Los grupos de respuesta que pertenecen al grupo de copias de seguridad se pueden ver y modificar.</span><span class="sxs-lookup"><span data-stu-id="da6c8-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="da6c8-215">Los grupos de respuesta importados no se pueden ver con el panel de control de Lync Server o la herramienta de configuración de grupo de respuesta, pero se pueden configurar mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da6c8-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

