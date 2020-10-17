---
title: 'Lync Server 2013: mover grupos de respuesta a un nuevo grupo de servidores'
description: 'Lync Server 2013: mover grupos de respuesta a un nuevo grupo de servidores.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b696963a28abbcd258f53fae12c3e281efa6ae4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542004"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="3ca20-103">Mover grupos de respuesta a un nuevo grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ca20-103">Moving response groups to a new pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ca20-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3ca20-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3ca20-105">Lync Server 2013 introduce una nueva compatibilidad de cmdlet para mover grupos de respuesta de un grupo a otro, incluso cuando el nombre de dominio completo (FQDN) es diferente.</span><span class="sxs-lookup"><span data-stu-id="3ca20-105">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="3ca20-106">Siga los pasos del siguiente procedimiento para mover grupos de respuesta de un grupo de servidores front-end a otro grupo de servidores front-end con un FQDN diferente.</span><span class="sxs-lookup"><span data-stu-id="3ca20-106">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3ca20-107">En un entorno de coexistencia, puede mover grupos de respuesta solo entre &nbsp; grupos de servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ca20-107">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="3ca20-108">Para mover grupos de respuesta a un grupo de servidores con un FQDN diferente</span><span class="sxs-lookup"><span data-stu-id="3ca20-108">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="3ca20-109">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3ca20-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3ca20-p101">Exporte los grupos de respuesta del grupo de servidores de origen. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="3ca20-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ca20-112">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="3ca20-p102">Para quitar los grupos de respuesta del grupo de servidores durante la exportación, incluya el parámetro –RemoveExportedConfiguration. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="3ca20-p103">Importe los grupos de respuesta al grupo de servidores de destino y asigne el grupo de destino como nuevo propietario. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="3ca20-117">Si también desea copiar la configuración del nivel de aplicación del grupo de respuesta del grupo de origen al grupo de servidores de destino, incluya el parámetro – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="3ca20-117">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="3ca20-118">Defina solo un conjunto de configuraciones de nivel de aplicación por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="3ca20-118">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="3ca20-119">Si copia la configuración de nivel de aplicación del grupo de servidores de origen en el grupo de servidores de destino, la configuración del grupo de servidores de origen sustituirá la configuración del grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="3ca20-119">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="3ca20-120">Si no copia la configuración de nivel de aplicación del grupo de servidores de origen, la configuración existente del grupo de servidores de destino se aplicará a los grupos de respuesta importados.</span><span class="sxs-lookup"><span data-stu-id="3ca20-120">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="3ca20-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ca20-121">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ca20-122">La configuración de nivel de aplicación incluye la configuración de música en espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada del agente y la configuración del contexto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ca20-122">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="3ca20-123">Para ver los valores de la configuración, ejecute el cmdlet <STRONG>Get-CsRgsConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3ca20-123">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="3ca20-124">Para obtener más información sobre este cmdlet, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="3ca20-124">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="3ca20-125">Compruebe que la importación haya sido correcta visualizando la configuración del grupo de respuesta importado tal como indicamos a continuación:</span><span class="sxs-lookup"><span data-stu-id="3ca20-125">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="3ca20-p106">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="3ca20-p107">Compruebe que se hayan importado todas las colas. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="3ca20-p108">Compruebe que se hayan importado todos los grupos de agentes. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="3ca20-p109">Compruebe que se hayan importado todos los horarios laborales. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="3ca20-p110">Compruebe que se hayan importado todos los conjuntos de vacaciones. En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="3ca20-136">Compruebe que la importación haya tenido éxito realizando una llamada a uno de los grupos de respuesta y verificando que la llamada se ha gestionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ca20-136">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="3ca20-137">Solicite a los agentes que son miembros de grupos de agentes formales que inicien sesión en sus grupos de agentes en el grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="3ca20-137">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="3ca20-p111">Si no ha quitado previamente grupos de respuesta del grupo de servidores de origen, hágalo ahora. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="3ca20-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="3ca20-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ca20-140">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

