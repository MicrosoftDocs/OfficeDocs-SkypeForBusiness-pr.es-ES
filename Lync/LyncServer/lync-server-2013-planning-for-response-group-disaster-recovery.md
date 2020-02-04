---
title: 'Lync Server 2013: Planeamiento de recuperación ante desastres del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="ae9a1-102">Planeamiento de recuperación ante desastres del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae9a1-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae9a1-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ae9a1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ae9a1-104">En esta sección se describen algunas formas de preparar grupos de respuesta para la recuperación de desastres y se ofrece información general sobre el proceso de recuperación de desastres.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="ae9a1-105">Prepararse para la recuperación de desastres de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae9a1-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="ae9a1-106">Tenga en cuenta lo siguiente cuando prepare y lleve a cabo procedimientos de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae9a1-107">En un entorno de coexistencia, solo se admiten los grupos de respuesta 2013 de Lync Server para los procedimientos de recuperación ante desastres que se describen en este documento.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="ae9a1-108">Planee la recuperación de desastres cuando realice su plan de capacidad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="ae9a1-109">Para la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder administrar las cargas de trabajo de todos los grupos de respuesta en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="ae9a1-110">Para obtener más información sobre la planeación de capacidad de los grupos de respuesta, consulte [planificación de capacidad para grupo de respuesta en Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="ae9a1-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="ae9a1-111">Realice copias de seguridad periódicas de todas las configuraciones de grupos de respuesta en todos los grupos de servidores front-end en los que implementó la aplicación de grupo de respuesta mediante el procedimiento de exportación descrito en este documento.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="ae9a1-112">Para obtener más información, consulte [procedimientos de recuperación ante desastres de grupos de respuesta en Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ae9a1-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="ae9a1-113">Guarde las copias de seguridad en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="ae9a1-114">Guarde una copia de seguridad separada de todos los archivos de audio originales que usó para la aplicación de grupo de respuesta, incluidas las grabaciones y los archivos de música en suspensión.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="ae9a1-115">Mantenga los archivos de copia de seguridad en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="ae9a1-116">Para la recuperación ante desastres de Lync Server 2013, toda la configuración del grupo de respuesta debe tener nombres únicos en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="ae9a1-117">Este requisito se aplica a flujos de trabajo, colas, grupos de agentes, conjuntos de días festivos y horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="ae9a1-118">Debe comprobar que este requisito se cumple cuando los grupos principal y de copia de seguridad siguen estando activos y antes de que usted necesite iniciar cualquier procedimiento de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="ae9a1-119">Si se produce un conflicto de nombres al importar datos de grupo de respuesta al grupo de copia de seguridad, se produce un error en la importación.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="ae9a1-120">Para completar el procedimiento de importación y conmutación por error, debe resolver los conflictos de nombre al cambiar el nombre del objeto de grupo de respuesta en el grupo de copias de seguridad o mediante el cmdlet **Import-CsRgsConfiguration** con el parámetro-ResolveNameConflicts para resolver automáticamente el conflicto anexando un número único de identificación al objeto de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="ae9a1-121">En general, le recomendamos que realice copias de seguridad diarias pero, si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="ae9a1-122">La cantidad de información que puede perder en caso de que se produzca un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="ae9a1-123">Es posible importar grupos de respuesta a un grupo de copia de seguridad antes de que se produzca una operación de recuperación ante desastres o de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="ae9a1-124">Importar grupos de respuesta anticipadamente reduce el tiempo de inactividad, porque el servicio de grupo de respuesta de Lync Server se puede restaurar en el grupo de copia de seguridad tan pronto como las llamadas se enruten al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ae9a1-125">La aplicación de grupo de respuesta no puede comunicarse con agentes alojados en un grupo inactivo hasta que se completa la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="ae9a1-126">Durante este tiempo, la aplicación de grupo de respuesta procesa las llamadas como si no estuvieran disponibles.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="ae9a1-127">Proceso de recuperación ante desastres de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae9a1-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="ae9a1-128">En caso de desastre, puede recuperar grupos de respuesta con uno de los siguientes métodos de recuperación:</span><span class="sxs-lookup"><span data-stu-id="ae9a1-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="ae9a1-129">Realice la conmutación por error a un grupo de copia de seguridad y luego vuelva a la agrupación original.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="ae9a1-130">Realice la conmutación por error a un grupo de copia de seguridad, cree un nuevo grupo con un nombre de dominio completo (FQDN) diferente y, a continuación, importe los grupos de respuesta al nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="ae9a1-131">Durante la fase de conmutación por error de recuperación ante desastres, los grupos de respuesta residen en varios grupos: en el grupo primario (que no está disponible) y en el grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="ae9a1-132">Los grupos de respuesta de ambos grupos tienen el mismo nombre y el mismo propietario (el grupo principal), pero tienen diferentes padres.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="ae9a1-133">Al recuperar mediante la creación de un nuevo grupo con un FQDN diferente, debe asignar el nuevo grupo como propietario de los grupos de respuesta al importarlos.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="ae9a1-134">La propiedad de los grupos de respuesta se mantiene con el grupo original, a menos que o hasta que se reasigne de forma explícita la propiedad mediante el parámetro – OverwriteOwner con el cmdlet **Import-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ae9a1-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae9a1-135">También necesita usar el parámetro – OverwriteOwner si reconstruyó el grupo durante la recuperación (es decir, la base de datos del grupo de respuesta está vacía), independientemente de si usa el mismo FQDN.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="ae9a1-136">No es necesario usar el parámetro – OverwriteOwner si no regeneizó el grupo, pero se permite que use este parámetro cada vez que importe los grupos de respuesta en el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="ae9a1-137">Solo puede definir un conjunto de valores de configuración de grupo de respuesta de nivel de aplicación por grupo.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="ae9a1-138">Esta configuración incluye la configuración predeterminada de música en espera, el archivo de audio con música activa predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="ae9a1-139">Para ver estas opciones de configuración, ejecute el cmdlet **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ae9a1-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="ae9a1-140">Para obtener más información sobre el cmdlet **Get-CsRgsConfiguration** , vea [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ae9a1-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="ae9a1-141">Puede transferir esta configuración de nivel de aplicación de un grupo a otro mediante el cmdlet **Import-CsRgsConfiguration** con el parámetro – ReplaceExistingSettings, pero si lo hace, se reemplazará la configuración del grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ae9a1-142">Esta restricción sobre la transferencia de la configuración a otro grupo solo es verdadera para la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="ae9a1-143">No se aplica a grupos de agentes, colas, flujos de trabajo, horas laborales ni conjuntos de días festivos.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="ae9a1-144">Si no quiere reemplazar la configuración de nivel de aplicación en el grupo de copias de seguridad durante un desastre y no se puede recuperar el grupo principal, se perderá la configuración de nivel de aplicación del grupo principal.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="ae9a1-145">Si necesita crear un nuevo grupo para reemplazar el grupo primario durante la recuperación, ya sea con el mismo FQDN o con un FQDN diferente, no puede recuperar la configuración de nivel de aplicación original.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="ae9a1-146">En este caso, debe configurar el nuevo grupo con esta configuración e incluir el archivo de audio de música en espera.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="ae9a1-147">Si decide usar el cmdlet **Import-CsRgsConfiguration** para transferir la configuración de nivel de aplicación del grupo principal al grupo de copia de seguridad durante un desastre, puede transferir la configuración del grupo de copias de seguridad al nuevo grupo durante la recuperación de la misma manera que lo transfirió del grupo principal al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="ae9a1-148">La tabla siguiente es una descripción general de los pasos necesarios para recuperar grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="ae9a1-149">Para obtener detalles sobre cómo realizar estos pasos, consulte [grupos de respuesta procedimientos de recuperación de desastres en Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ae9a1-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="ae9a1-150">Pasos de recuperación ante desastres de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ae9a1-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae9a1-151">Fase</span><span class="sxs-lookup"><span data-stu-id="ae9a1-151">Phase</span></span></th>
<th><span data-ttu-id="ae9a1-152">Pasos</span><span class="sxs-lookup"><span data-stu-id="ae9a1-152">Steps</span></span></th>
<th><span data-ttu-id="ae9a1-153">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="ae9a1-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae9a1-154">Antes de la interrupción</span><span class="sxs-lookup"><span data-stu-id="ae9a1-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="ae9a1-155">De forma rutinaria, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> para crear copias de seguridad de todas las configuraciones de grupo de respuesta en todas las agrupaciones front end donde se implementa la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="ae9a1-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ae9a1-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ae9a1-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ae9a1-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae9a1-158">Durante la interrupción</span><span class="sxs-lookup"><span data-stu-id="ae9a1-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="ae9a1-159">Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar la configuración del servicio del grupo de respuesta de Lync Server de la copia de seguridad del grupo principal al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ae9a1-160">Use el parámetro – ReplaceExistingSettings si desea reemplazar la configuración del grupo de respuesta de nivel de aplicación en el grupo de copias de seguridad con la configuración del grupo principal.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="ae9a1-161">Si no transfiere la configuración de nivel de aplicación del grupo principal al grupo de copias de seguridad y éste no se puede recuperar, perderá la configuración del grupo primario.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="ae9a1-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ae9a1-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ae9a1-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ae9a1-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae9a1-164">Después de importar</span><span class="sxs-lookup"><span data-stu-id="ae9a1-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="ae9a1-165">Ejecute cmdlets de grupo de respuesta con el parámetro – ShowAll (para mostrar todos los grupos de respuesta) o el parámetro-Owner (para mostrar solo grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se importaron al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="ae9a1-166">Si no usa el parámetro – ShowAll o el parámetro-Owner, los grupos de respuesta que importó al grupo de copia de seguridad no se mostrarán en los resultados devueltos por los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="ae9a1-167">Ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="ae9a1-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae9a1-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ae9a1-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ae9a1-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ae9a1-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ae9a1-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae9a1-175">Después de la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="ae9a1-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ae9a1-176">Realice una llamada de prueba a un grupo de respuesta que se importó al grupo de copia de seguridad y compruebe que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="ae9a1-177">Todos los agentes formales deben iniciar sesión de nuevo en sus grupos formales en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="ae9a1-178">Administrar cambios de configuración:</span><span class="sxs-lookup"><span data-stu-id="ae9a1-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="ae9a1-179">Los grupos de respuesta del grupo de copia de seguridad, ya se hayan importado al grupo de copia de seguridad o que pertenezcan al grupo de copias de seguridad, se pueden modificar como de costumbre durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="ae9a1-180">Debe usar el shell de administración de Lync Server para administrar los grupos de respuesta que importó al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="ae9a1-181">No puede usar el panel de control de Lync Server para administrar estos grupos de respuesta mientras se encuentran en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="ae9a1-182">N/D</span><span class="sxs-lookup"><span data-stu-id="ae9a1-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae9a1-183">Después de la recuperación, antes del failback</span><span class="sxs-lookup"><span data-stu-id="ae9a1-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="ae9a1-184">Ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> y especifique el parámetro-Source como grupo de copias de seguridad y el parámetro-Owner como grupo principal para exportar los grupos de respuesta que pertenecen al grupo principal del grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="ae9a1-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ae9a1-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ae9a1-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ae9a1-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae9a1-187">Después de la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="ae9a1-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ae9a1-188">Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para volver a importar los grupos de respuesta en el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ae9a1-189">Si el grupo principal no se puede recuperar e implementa un nuevo grupo de servidores para reemplazarlo, use el parámetro – ReplaceExistingSettings para transferir la configuración de nivel de aplicación del grupo de copias de seguridad al nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="ae9a1-190">Si no transfiere la configuración del grupo de copia de seguridad, el nuevo grupo usará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="ae9a1-191">Ejecute los siguientes cmdlets con el parámetro – ShowAll (para mostrar todos los grupos de respuesta) o el parámetro-Owner (para mostrar solo grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se importaron correctamente al grupo primario:</span><span class="sxs-lookup"><span data-stu-id="ae9a1-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae9a1-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="ae9a1-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="ae9a1-197">Realice una llamada de prueba a un grupo de respuesta que se haya importado al grupo de servidores principal y compruebe que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="ae9a1-198">De manera opcional, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> en el grupo de copias de seguridad con el parámetro – RemoveExportedConfiguration para quitar los grupos de respuesta que pertenecen al grupo principal del grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ae9a1-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ae9a1-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ae9a1-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ae9a1-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

