---
title: Procedimientos de recuperación ante desastres del grupo de respuesta 2013 de Lync Server
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
ms.openlocfilehash: 73b5dba010da09fb20c96ca6b14de2f881e32b60
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="933c2-102">Procedimientos de recuperación ante desastres del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="933c2-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="933c2-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="933c2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="933c2-104">Durante la fase de conmutación por error de la recuperación ante desastres, los grupos de respuesta residen en varios grupos de servidores: en el grupo de servidores principal (que no está disponible) y en el grupo de servidores de reserva.</span><span class="sxs-lookup"><span data-stu-id="933c2-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="933c2-105">Los grupos de respuesta de ambos grupos de servidores tienen el mismo nombre y el mismo propietario (el grupo de servidores principal), pero diferentes elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="933c2-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="933c2-106">Durante este tiempo, los cmdlets del grupo de respuesta funcionan de manera ligeramente distinta.</span><span class="sxs-lookup"><span data-stu-id="933c2-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="933c2-107">Asegúrese de usar los parámetros como se especifica en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="933c2-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="933c2-108">Para obtener más información sobre cómo funcionan los cmdlets durante la fase de conmutación por error, vea el artículo del blog NextHop "Lync Server 2013: [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)recuperación de grupos de respuesta durante la recuperación ante desastres" en.</span><span class="sxs-lookup"><span data-stu-id="933c2-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="933c2-109">Este artículo del blog también se aplica a la versión publicada de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="933c2-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="933c2-110">Siga los pasos descritos en el siguiente procedimiento para preparar y realizar la recuperación ante desastres para el servicio de grupo de respuesta de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="933c2-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="933c2-111">Para la conmutación por error y conmutación por recuperación del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="933c2-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="933c2-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="933c2-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="933c2-p102">Haga copias de seguridad periódicamente. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="933c2-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="933c2-p103">Durante una interrupción, después de la conmutación por error en el grupo de servidores de reserva, importe los grupos de respuesta al grupo de servidores de reserva. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="933c2-p104">Si desea reemplazar la configuración de nivel de aplicación del grupo de servidores de reserva por la configuración del grupo de servidores principal, incluya el parámetro ReplaceExistingSettings. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="933c2-120">Si no reemplaza la configuración del grupo de servidores de reserva y no se puede recuperar el grupo de servidores principal, se perderá la configuración del grupo de servidores principal.</span><span class="sxs-lookup"><span data-stu-id="933c2-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="933c2-121">Para obtener más información, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planeación de la recuperación ante desastres del grupo de respuesta en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="933c2-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="933c2-p106">Compruebe que la importación se haya realizado correctamente. Para ello, muestre los grupos de respuesta importados. Los grupos de respuesta importados siguen siendo propiedad del grupo de servidores principal. Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="933c2-p107">Muestre todos los flujos de trabajo del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todos los flujos de trabajo del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="933c2-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="933c2-p108">Muestre todas las colas del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todas las colas del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="933c2-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="933c2-p109">Muestre todos los grupos de agentes del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todos los grupos de agentes del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="933c2-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="933c2-p110">Muestre todo el horario comercial del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se haya incluido todo el horario comercial del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="933c2-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="933c2-p111">Muestre todos los conjuntos de vacaciones del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todos los conjuntos de vacaciones del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="933c2-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="933c2-p112">También puede mostrar todos los grupos de respuesta del grupo de servidores de reserva, incluidos los que son propiedad del grupo de servidores principal y los que son propiedad del grupo de servidores de reserva, con el parámetro –ShowAll en lugar del parámetro –Owner. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="933c2-p113">Debe usar el parámetro –ShowAll o el parámetro –Owner. Si no usa ninguno de estos parámetros, los grupos de respuesta importados al grupo de servidores de reserva no aparecerán en los resultados que devuelven los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="933c2-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="933c2-144">Compruebe que la importación se haya realizado correctamente. Para ello, realice una llamada a un grupo de respuesta importado y compruebe que la llamada se atienda correctamente.</span><span class="sxs-lookup"><span data-stu-id="933c2-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="933c2-145">Pida a los agentes que son miembros de grupos de agentes formales que inicien sesión en sus grupos de agentes en el grupo de servidores de reserva.</span><span class="sxs-lookup"><span data-stu-id="933c2-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="933c2-146">Administre y modifique los grupos de respuesta importados de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="933c2-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="933c2-147">Mientras los grupos de respuesta se encuentran en el grupo de copia de seguridad, debe usar el shell de administración de Lync Server para administrarlos.</span><span class="sxs-lookup"><span data-stu-id="933c2-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="933c2-148">No puede usar el panel de control de Lync Server para administrar los grupos de respuesta que importó al grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="933c2-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="933c2-p115">Una vez que se ha restaurado el grupo de servidores principal y se ha completado la conmutación por recuperación, exporte los grupos de respuesta del grupo de servidores principal que se importaron al grupo de servidores de reserva. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="933c2-p116">Importe los grupos de respuesta nuevamente al grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="933c2-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="933c2-p117">Si vuelve a generar un grupo de servidores durante la recuperación, ya sea con el mismo nombre de dominio completo (FQDN) o con uno diferente, debe usar el parámetro –OverwriteOwner. Como regla general, siempre puede usar el parámetro –OverwriteOwner al importar grupos de respuesta nuevamente al grupo de servidores principal.</span><span class="sxs-lookup"><span data-stu-id="933c2-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="933c2-p118">Si implementó un nuevo grupo de servidores (con el mismo FQDN o con uno diferente) para reemplazar el grupo de servidores principal, y desea usar la configuración de nivel de aplicación del grupo de servidores de reserva para el nuevo grupo, incluya el parámetro –ReplaceExistingSettings. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="933c2-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="933c2-159">Si no desea reemplazar la configuración de nivel de aplicación ni el archivo de audio de música en espera predeterminado del nuevo grupo de servidores por la configuración del grupo de servidores de reserva, el nuevo grupo usará la configuración de nivel de aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="933c2-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="933c2-p119">Compruebe que la importación al grupo de servidores principal se haya realizado correctamente. Para ello, muestre la configuración del grupo de respuesta importado. Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="933c2-p120">Muestre todos los flujos de trabajo del grupo de servidores principal y compruebe que se hayan incluido todos los flujos de trabajo importados. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="933c2-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="933c2-p121">Muestre todas las colas del grupo de servidores principal y compruebe que se hayan incluido todas las colas importadas. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="933c2-167">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="933c2-p122">Muestre todos los grupos de agentes del grupo de servidores principal y compruebe que se hayan incluido todos los grupos de agentes importados. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="933c2-170">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="933c2-p123">Muestre todo el horario comercial del grupo de servidores principal y compruebe que se haya incluido todo el horario comercial importado. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="933c2-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="933c2-p124">Muestre todos los conjuntos de vacaciones del grupo de servidores principal y compruebe que se hayan incluido todos los conjuntos de vacaciones importados. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="933c2-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="933c2-177">Compruebe que la importación se haya realizado correctamente. Para ello, realice una llamada a un grupo de respuesta importado y compruebe que la llamada se atienda correctamente.</span><span class="sxs-lookup"><span data-stu-id="933c2-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="933c2-p125">También puede quitar del grupo de servidores de reserva los grupos de respuesta que son propiedad del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="933c2-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="933c2-180">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="933c2-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="933c2-181">Este paso crea un nuevo archivo con la configuración exportada y luego lo elimina del grupo de servidores de reserva.</span><span class="sxs-lookup"><span data-stu-id="933c2-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

