---
title: 'Lync Server 2013: Planeación de la recuperación ante desastres del grupo de respuesta'
description: 'Lync Server 2013: Planeación de la recuperación ante desastres del grupo de respuesta.'
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
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549266"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="1a63e-103">Planeación de la recuperación ante desastres del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a63e-103">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a63e-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1a63e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1a63e-105">En esta sección se describen maneras para la preparación de grupos de respuesta para la recuperación ante desastres y se proporciona una visión general del proceso de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="1a63e-105">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="1a63e-106">Preparación para la recuperación ante desastres del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="1a63e-106">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="1a63e-107">Tenga en cuenta lo siguiente al preparar y llevar a cabo los procedimientos de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="1a63e-107">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a63e-108">En un entorno de coexistencia, solo se admiten los grupos de respuesta 2013 de Lync Server para los procedimientos de recuperación ante desastres descritos en este documento.</span><span class="sxs-lookup"><span data-stu-id="1a63e-108">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="1a63e-109">Planifique para la recuperación ante desastres cuando realice el planeamiento de capacidad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-109">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="1a63e-110">Para la capacidad de recuperación ante desastres, cada grupo de servidores de un grupo de par debe ser capaz de manejar las cargas de trabajo de todos los grupos de respuesta de ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="1a63e-110">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="1a63e-111">Para obtener más información sobre la planeación de la capacidad del grupo de respuesta, consulte [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="1a63e-111">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="1a63e-112">Realice copias de seguridad periódicas de todas las configuraciones de grupo de respuesta en todos los grupos de servidores front-end donde implementó la aplicación de grupo de respuesta mediante el procedimiento de exportación que se describe en este documento.</span><span class="sxs-lookup"><span data-stu-id="1a63e-112">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="1a63e-113">Para obtener más información, consulte [Response Group Disaster Recovery Procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1a63e-113">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="1a63e-114">Mantenga las copias de seguridad en una ubicación protegida y segura.</span><span class="sxs-lookup"><span data-stu-id="1a63e-114">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="1a63e-115">Conserve una copia de seguridad independiente de todos los archivos de audio originales que ha usado para la aplicación de grupo de respuesta, incluidas las grabaciones y los archivos de música en espera.</span><span class="sxs-lookup"><span data-stu-id="1a63e-115">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="1a63e-116">Mantenga los archivos de seguridad en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="1a63e-116">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="1a63e-117">Para la recuperación ante desastres de Lync Server 2013, todas las opciones de configuración del grupo de respuesta deben tener nombres únicos en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="1a63e-117">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="1a63e-118">Este requisito se aplica a los flujos de trabajo, colas, grupos de agentes, conjuntos de vacaciones y horas laborales.</span><span class="sxs-lookup"><span data-stu-id="1a63e-118">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="1a63e-119">Debe comprobar que se cumple este requisito cuando los grupos primarios y de reserva están todavía activos y antes de iniciar cualquier procedimiento de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1a63e-119">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="1a63e-120">Si encuentra conflictos de nombres al importar datos de grupo de respuesta al grupo de copia de seguridad, se produce un error en la importación.</span><span class="sxs-lookup"><span data-stu-id="1a63e-120">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="1a63e-121">Para completar la importación y el procedimiento de conmutación por error, tiene que resolver los conflictos de nombre cambiando el nombre del objeto de grupo de respuesta en el grupo de copia de seguridad o usando el cmdlet **Import-CsRgsConfiguration** con el parámetro –ResolveNameConflicts para resolver el conflicto anexando un número de identificación único al objeto de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1a63e-121">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="1a63e-p105">En general, se recomienda que realice copias de seguridad diarias, pero si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de cambios.</span><span class="sxs-lookup"><span data-stu-id="1a63e-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="1a63e-124">Es posible importar grupos de respuesta a un grupo de servidores de copia de seguridad antes de que se produzca un desastre o una operación de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1a63e-124">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="1a63e-125">La importación de grupos de respuesta de antemano reduce el tiempo de inactividad, ya que el servicio del grupo de respuesta de Lync Server se puede restaurar en el grupo de copia de seguridad en cuanto las llamadas se enruten al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-125">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a63e-126">La aplicación de grupo de respuesta no puede llegar a ningún agente hospedado en un grupo de servidores inactivo hasta que se complete la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1a63e-126">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="1a63e-127">Durante este tiempo, la aplicación de grupo de respuesta procesa las llamadas como si dichos agentes no estuvieran disponibles.</span><span class="sxs-lookup"><span data-stu-id="1a63e-127">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="1a63e-128">Proceso de recuperación ante desastres de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="1a63e-128">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="1a63e-129">En el caso de un desastre, puede recuperar grupos de respuesta usando cualquiera de los siguientes enfoques de recuperación:</span><span class="sxs-lookup"><span data-stu-id="1a63e-129">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="1a63e-130">Realice la conmutación por error a un grupo de servidores de copia de seguridad y, a continuación, la conmutación por recuperación del grupo de servidores original.</span><span class="sxs-lookup"><span data-stu-id="1a63e-130">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="1a63e-131">Realice la conmutación por error a un grupo de servidores de copia de seguridad, cree un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente y, a continuación, importe los grupos de respuesta al nuevo grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="1a63e-131">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="1a63e-p108">Durante la fase de conmutación por error de la recuperación ante desastres, los grupos de respuesta se encuentran en varios grupos de servidores: en el grupo de servidores principal (que no está disponible) y en el grupo de servidores de copia de seguridad. Los grupos de respuesta de ambos grupos de servidores tienen el mismo nombre y el mismo propietario (el grupo de servidores principal) pero tienen principales diferentes.</span><span class="sxs-lookup"><span data-stu-id="1a63e-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="1a63e-134">Cuando recupera creando un nuevo grupo de servidores con un FQDN diferente, tiene que asignar el nuevo grupo de servidores como el propietario de los grupos de respuesta al importarlos.</span><span class="sxs-lookup"><span data-stu-id="1a63e-134">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="1a63e-135">La propiedad de los grupos de respuesta permanece con el grupo de servidores original a menos o hasta que vuelva a asignar de manera explícita la propiedad mediante el parámetro –OverwriteOwner con el cmdlet **Import-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1a63e-135">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a63e-136">También debe usar el parámetro – OverwriteOwner si ha reconstruido el grupo de servidores durante la recuperación (es decir, la base de datos del grupo de respuesta está vacía), independientemente de si usa el mismo FQDN.</span><span class="sxs-lookup"><span data-stu-id="1a63e-136">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="1a63e-137">No tiene que usar el parámetro –OverwriteOwner si no ha vuelto a crear el grupo de servidores pero es permisible usar este parámetro siempre que importe grupos de respuesta de nuevo al grupo de servidores principal.</span><span class="sxs-lookup"><span data-stu-id="1a63e-137">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="1a63e-138">Solo se puede definir un conjunto de opciones de configuración de grupo de respuesta de nivel de aplicación por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="1a63e-138">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="1a63e-139">Estos valores incluyen la configuración de música de espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada de agente y la configuración de contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="1a63e-139">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="1a63e-140">Para ver estos valores de configuración, ejecute el cmdlet de **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1a63e-140">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="1a63e-141">Para obtener más información sobre el cmdlet **Get-CsRgsConfiguration** , consulte [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1a63e-141">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="1a63e-142">Puede transferir esta configuración de nivel de aplicación de un grupo de servidores a otro mediante el cmdlet **Import-CsRgsConfiguration**  con el parámetro –ReplaceExistingSettings, pero al hacerlo se invalidará la configuración en el grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="1a63e-142">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a63e-p112">Esta restricción acerca de la transferencia de configuración a otro grupo de servidores es verdadera solo para la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado. No se aplica a grupos de agente, a colas, a flujos de trabajo, a horas de oficina y a conjuntos de días festivos.</span><span class="sxs-lookup"><span data-stu-id="1a63e-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="1a63e-p113">Si no desea reemplazar la configuración de nivel de aplicación en el grupo de servidores de copia de seguridad durante un desastre y el grupo de servidores principal no se puede recuperar, se perderá la configuración de nivel de aplicación del grupo de servidores principal. Si tiene que crear un nuevo grupo de servidores para reemplazar el grupo de servidores principal durante la recuperación, con el mismo FQDN o con un FQDN diferente, no podrá recuperar la configuración de nivel de aplicación original. En este caso, tiene que configurar el nuevo grupo de servidores con esta configuración e incluir el archivo de audio de música en espera.</span><span class="sxs-lookup"><span data-stu-id="1a63e-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="1a63e-148">Si decide usar el cmdlet **Import-CsRgsConfiguration**  para transferir la configuración de nivel de aplicación desde el grupo de servidores principal al grupo de servidores de copia de seguridad durante un desastre, a continuación, puede transferir la configuración del grupo de servidores de copia de seguridad al nuevo grupo de servidores durante la recuperación de la misma manera que los ha transferido desde le grupo de servidores principal al grupo de servidores de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-148">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="1a63e-149">La tabla siguiente es una visión general de los pasos implicados en la recuperación de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1a63e-149">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="1a63e-150">Para más detalles sobre cómo realizar estos pasos, consulte [Response Group Disaster Recovery Procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1a63e-150">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="1a63e-151">Pasos de recuperación ante desastres de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="1a63e-151">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a63e-152">Fase</span><span class="sxs-lookup"><span data-stu-id="1a63e-152">Phase</span></span></th>
<th><span data-ttu-id="1a63e-153">Pasos</span><span class="sxs-lookup"><span data-stu-id="1a63e-153">Steps</span></span></th>
<th><span data-ttu-id="1a63e-154">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="1a63e-154">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a63e-155">Antes de una interrupción</span><span class="sxs-lookup"><span data-stu-id="1a63e-155">Before outage</span></span></p></td>
<td><p><span data-ttu-id="1a63e-156">De forma rutinaria, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> para crear copias de seguridad de todas las configuraciones de grupo de respuesta en todos los grupos de servidores front-end donde se implemente la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1a63e-156">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="1a63e-157">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1a63e-157">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1a63e-158">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a63e-158">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a63e-159">Durante la interrupción</span><span class="sxs-lookup"><span data-stu-id="1a63e-159">During outage</span></span></p></td>
<td><p><span data-ttu-id="1a63e-160">Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar la configuración del servicio del grupo de respuesta de Lync Server de la copia de seguridad del grupo principal al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-160">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1a63e-161">Use el parámetro – ReplaceExistingSettings si desea reemplazar la configuración del grupo de respuesta de nivel de aplicación en el grupo de servidores de reserva con la configuración del grupo principal.</span><span class="sxs-lookup"><span data-stu-id="1a63e-161">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="1a63e-162">Si no transfiere la configuración de nivel de aplicación desde el grupo de servidores principal al grupo de servidores de copia de seguridad, y no se puede recuperar el grupo de servidores principal, perderá la configuración del grupo de servidores principal.</span><span class="sxs-lookup"><span data-stu-id="1a63e-162">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="1a63e-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1a63e-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1a63e-164">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a63e-164">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a63e-165">Después de importar</span><span class="sxs-lookup"><span data-stu-id="1a63e-165">After importing</span></span></p></td>
<td><p><span data-ttu-id="1a63e-166">Ejecute cmdlets de grupo de respuesta con el parámetro – ShowAll (para mostrar todos los grupos de respuesta) o el parámetro – Owner (para mostrar solo los grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se han importado al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-166">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1a63e-167">Si usa el parámetro –ShowAll o el parámetro –Owner, los grupos de respuesta que ha importado al grupo de servidores de copia de seguridad no se mostrarán en los resultados devueltos por los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1a63e-167">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="1a63e-168">Ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="1a63e-168">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="1a63e-169"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-169"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-170"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-170"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-171"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-171"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-172"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-172"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-173"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-173"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1a63e-174">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1a63e-174">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1a63e-175">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a63e-175">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a63e-176">Luego de la conmutación por error</span><span class="sxs-lookup"><span data-stu-id="1a63e-176">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1a63e-177">Realice una llamada de prueba a un grupo de respuesta que se importó al grupo de copia de seguridad y compruebe que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a63e-177">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="1a63e-178">Todos los agentes formales deben iniciar sesión de nuevo en sus grupos formales en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-178">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="1a63e-179">Administrar los cambios de configuración:</span><span class="sxs-lookup"><span data-stu-id="1a63e-179">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="1a63e-180">Los grupos de respuesta del grupo de servidores de copia de seguridad, ya sean importados para el grupo de copia de seguridad o que pertenecen al grupo de copia de seguridad, se pueden modificar de la forma habitual durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="1a63e-180">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1a63e-181">Debe usar el shell de administración de Lync Server para administrar los grupos de respuesta que importó al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-181">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="1a63e-182">No puede usar el panel de control de Lync Server para administrar estos grupos de respuesta mientras están en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-182">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="1a63e-183">N/D</span><span class="sxs-lookup"><span data-stu-id="1a63e-183">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a63e-184">Después de la recuperación, antes de la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="1a63e-184">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="1a63e-185">Ejecutar el cmdlet <strong>Export-CsRgsConfiguration</strong> especificando el parámetro -Source como el grupo de copia de seguridad y el parámetro -Owner como el grupo primario para exportar los grupos de respuesta que son propiedad del grupo principal del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-185">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="1a63e-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1a63e-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1a63e-187">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a63e-187">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a63e-188">Después de la conmutación por recuperación</span><span class="sxs-lookup"><span data-stu-id="1a63e-188">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1a63e-189">Ejecutar el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar los grupos de respuesta de vuelta al grupo principal.</span><span class="sxs-lookup"><span data-stu-id="1a63e-189">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1a63e-p116">Si el grupo de servidores principal no se puede recuperar e implementa un nuevo grupo de servidores para reemplazarlo, use el parámetro –ReplaceExistingSettings para transferir la configuración de nivel de aplicación del grupo de servidores de copia de seguridad al nuevo grupo de servidores. Si no transfiere la configuración del grupo de servidores de la copia de seguridad, el nuevo grupo de servidores usará la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1a63e-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="1a63e-192">Ejecute los siguientes cmdlets con el parámetro –ShowAll (para mostrar todos los grupos de respuestas) o el parámetro –Owner (para mostrar solo los grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se han importado correctamente de vuelta al grupo primario:</span><span class="sxs-lookup"><span data-stu-id="1a63e-192">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="1a63e-193"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-193"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-194"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-194"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-195"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-195"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-196"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-196"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="1a63e-197"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="1a63e-197"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="1a63e-198">Realice una llamada de prueba a un grupo de respuesta que se importó de vuelta al grupo primario y compruebe que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a63e-198">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="1a63e-199">Opcionalmente, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> en el grupo de copia de seguridad con el parámetro –RemoveExportedConfiguration para quitar los grupos de respuesta que son propiedad del grupo principal del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a63e-199">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1a63e-200">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1a63e-200">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1a63e-201">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a63e-201">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

