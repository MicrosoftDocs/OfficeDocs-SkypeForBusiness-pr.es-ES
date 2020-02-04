---
title: 'Lync Server 2013: Procedimientos de recuperación ante desastres del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="b67a6-102">Procedimientos de recuperación ante desastres del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b67a6-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b67a6-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b67a6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b67a6-104">Durante la fase de conmutación por error de recuperación ante desastres, los grupos de respuesta residen en varios grupos: en el grupo primario (que no está disponible) y en el grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="b67a6-105">Los grupos de respuesta de ambos grupos tienen el mismo nombre y el mismo propietario (el grupo principal), pero tienen diferentes padres.</span><span class="sxs-lookup"><span data-stu-id="b67a6-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="b67a6-106">Durante este tiempo, los cmdlets del grupo de respuesta funcionan de manera algo diferente.</span><span class="sxs-lookup"><span data-stu-id="b67a6-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="b67a6-107">Asegúrese de usar parámetros según se especifica en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="b67a6-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="b67a6-108">Para más información sobre cómo funcionan los cmdlets durante la fase de conmutación por error, vea el artículo del blog de NextHop "Lync Server 2013: [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)recuperación de grupos de respuesta durante la recuperación ante desastres" en.</span><span class="sxs-lookup"><span data-stu-id="b67a6-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="b67a6-109">Este artículo del blog también se aplica a la versión de lanzamiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b67a6-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="b67a6-110">Siga los pasos que se indican en el siguiente procedimiento para preparar y realizar la recuperación de desastres para el servicio de grupo de respuesta de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b67a6-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="b67a6-111">Para deshacer la conmutación por error y el grupo de respuesta failback</span><span class="sxs-lookup"><span data-stu-id="b67a6-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="b67a6-112">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b67a6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b67a6-113">Realizar copias de seguridad rutinariamente.</span><span class="sxs-lookup"><span data-stu-id="b67a6-113">Routinely perform backups.</span></span> <span data-ttu-id="b67a6-114">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="b67a6-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="b67a6-116">Durante una interrupción, después de la conmutación por error en el grupo de copias de seguridad, importe los grupos de respuesta al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="b67a6-117">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b67a6-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="b67a6-118">Si desea reemplazar la configuración de nivel de aplicación del grupo de copias de seguridad por la configuración del grupo principal, incluya el parámetro – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="b67a6-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="b67a6-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b67a6-120">Si no reemplaza la configuración del grupo de copias de seguridad y no se puede recuperar el repositorio principal, se perderá la configuración de la agrupación principal.</span><span class="sxs-lookup"><span data-stu-id="b67a6-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="b67a6-121">Para obtener más información, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planeación de la recuperación ante desastres de grupos de respuesta en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b67a6-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="b67a6-122">Compruebe que la importación se ha realizado correctamente; para ello, muestra los grupos de respuesta importados.</span><span class="sxs-lookup"><span data-stu-id="b67a6-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="b67a6-123">Los grupos de respuesta importados siguen siendo propiedad del grupo primario.</span><span class="sxs-lookup"><span data-stu-id="b67a6-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="b67a6-124">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b67a6-124">Do the following:</span></span>
    
      - <span data-ttu-id="b67a6-125">Mostrar todos los flujos de trabajo del grupo de copias de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los flujos de trabajo de grupo primario.</span><span class="sxs-lookup"><span data-stu-id="b67a6-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="b67a6-126">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="b67a6-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="b67a6-128">Muestre todas las colas del grupo de copia de seguridad que pertenecen al grupo principal y compruebe que se incluyen todas las colas de grupo principales.</span><span class="sxs-lookup"><span data-stu-id="b67a6-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="b67a6-129">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="b67a6-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="b67a6-131">Mostrar todos los grupos de agentes del grupo de copias de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los grupos de agentes de grupo principales.</span><span class="sxs-lookup"><span data-stu-id="b67a6-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="b67a6-132">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="b67a6-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="b67a6-134">Mostrar todas las horas de actividad en el grupo de copia de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los horarios de negocio principales de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="b67a6-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="b67a6-135">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="b67a6-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="b67a6-137">Mostrar todos los conjuntos de días no laborables del grupo de copias de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los conjuntos de días no laborables de la agrupación principal.</span><span class="sxs-lookup"><span data-stu-id="b67a6-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="b67a6-138">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="b67a6-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="b67a6-140">Como alternativa, puede mostrar todos los grupos de respuesta en el grupo de copias de seguridad, incluidos los que pertenecen al grupo principal y los que pertenecen al grupo de copias de seguridad, con el parámetro – ShowAll en lugar del parámetro – Owner.</span><span class="sxs-lookup"><span data-stu-id="b67a6-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="b67a6-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b67a6-142">Debe usar el parámetro – ShowAll o el parámetro-Owner.</span><span class="sxs-lookup"><span data-stu-id="b67a6-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="b67a6-143">Si no usa ninguno de estos parámetros, los grupos de respuesta que importó al grupo de copias de seguridad no se mostrarán en los resultados devueltos por los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b67a6-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="b67a6-144">Verifique que la importación se haya realizado correctamente colocando una llamada a un grupo de respuesta importado y verificando que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="b67a6-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="b67a6-145">Solicitar agentes que sean miembros de grupos de agentes formales para iniciar sesión en sus grupos de agentes en el grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="b67a6-146">Administrar y modificar los grupos de respuesta importados de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="b67a6-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b67a6-147">Mientras los grupos de respuesta están en el grupo de copia de seguridad, necesita usar el shell de administración de Lync Server para administrarlos.</span><span class="sxs-lookup"><span data-stu-id="b67a6-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="b67a6-148">No puede usar el panel de control de Lync Server para administrar los grupos de respuesta que importó al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="b67a6-149">Una vez que se haya restaurado el grupo principal y se haya completado la conmutación por recuperación, exporte los grupos de respuesta del grupo principal que se importaron al grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="b67a6-150">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b67a6-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="b67a6-151">Vuelva a importar los grupos de respuesta al grupo primario.</span><span class="sxs-lookup"><span data-stu-id="b67a6-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="b67a6-152">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="b67a6-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b67a6-154">Si reconstruye un grupo durante la recuperación, ya sea con el mismo nombre de dominio completo (FQDN) u otro diferente, debe usar el parámetro – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="b67a6-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="b67a6-155">Como regla general, siempre puede usar el parámetro – OverwriteOwner al importar grupos de respuesta al grupo primario.</span><span class="sxs-lookup"><span data-stu-id="b67a6-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="b67a6-156">Si implementó un nuevo grupo (con el mismo FQDN u otro diferente) para reemplazar el grupo primario y desea usar la configuración de nivel de aplicación del grupo de copias de seguridad para el nuevo grupo, incluya el parámetro – ReplaceExistingSettings.</span><span class="sxs-lookup"><span data-stu-id="b67a6-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="b67a6-157">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="b67a6-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b67a6-159">Si no quiere reemplazar la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado para el nuevo grupo con la configuración del grupo de copias de seguridad, el nuevo grupo usará la configuración predeterminada de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b67a6-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="b67a6-160">Compruebe que la importación al grupo primario se ha realizado correctamente mostrando la configuración del grupo de respuesta importado.</span><span class="sxs-lookup"><span data-stu-id="b67a6-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="b67a6-161">Siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b67a6-161">Do the following:</span></span>
    
      - <span data-ttu-id="b67a6-162">Mostrar todos los flujos de trabajo del grupo principal y comprobar que se incluyen todos los flujos de trabajo importados.</span><span class="sxs-lookup"><span data-stu-id="b67a6-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="b67a6-163">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="b67a6-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="b67a6-165">Muestre todas las colas del grupo principal y compruebe que todas las colas importadas están incluidas.</span><span class="sxs-lookup"><span data-stu-id="b67a6-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="b67a6-166">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="b67a6-167">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="b67a6-168">Mostrar todos los grupos de agentes en el repositorio principal y comprobar que se incluyen todos los grupos de agentes importados.</span><span class="sxs-lookup"><span data-stu-id="b67a6-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="b67a6-169">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="b67a6-170">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="b67a6-171">Mostrar todas las horas de actividad en el grupo primario y comprobar que se incluyen todos los horarios de negocios importados.</span><span class="sxs-lookup"><span data-stu-id="b67a6-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="b67a6-172">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="b67a6-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="b67a6-174">Mostrar todos los conjuntos de días no laborables del repositorio principal y comprobar que están incluidos todos los conjuntos de festividades importados.</span><span class="sxs-lookup"><span data-stu-id="b67a6-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="b67a6-175">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="b67a6-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="b67a6-177">Verifique que la importación se haya realizado correctamente colocando una llamada a un grupo de respuesta importado y verificando que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="b67a6-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="b67a6-178">Si lo desea, puede quitar los grupos de respuesta que pertenecen al grupo principal del grupo de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="b67a6-179">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b67a6-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="b67a6-180">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b67a6-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b67a6-181">Este paso crea un nuevo archivo con la configuración exportada y, a continuación, lo quita del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b67a6-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

