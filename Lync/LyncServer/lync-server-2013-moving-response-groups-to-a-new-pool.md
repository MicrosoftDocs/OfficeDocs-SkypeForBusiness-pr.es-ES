---
title: 'Lync Server 2013: mover grupos de respuesta a un grupo nuevo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="e4588-102">Mover grupos de respuesta a un grupo nuevo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4588-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4588-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e4588-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e4588-104">Lync Server 2013 introduce nuevos cmdlets que permiten mover grupos de respuesta de un grupo a otro, incluso cuando el nombre de dominio completo (FQDN) es diferente.</span><span class="sxs-lookup"><span data-stu-id="e4588-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="e4588-105">Siga los pasos que se indican en el siguiente procedimiento para mover grupos de respuesta de un grupo de servidores front-end a otro grupo de servidores front-end con un FQDN diferente.</span><span class="sxs-lookup"><span data-stu-id="e4588-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4588-106">En un entorno de coexistencia, solo puede mover grupos de respuesta entre grupos&nbsp;front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4588-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="e4588-107">Para mover grupos de respuesta a un grupo con un FQDN diferente</span><span class="sxs-lookup"><span data-stu-id="e4588-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="e4588-108">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e4588-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e4588-109">Exporte los grupos de respuesta en el grupo de origen.</span><span class="sxs-lookup"><span data-stu-id="e4588-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="e4588-110">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4588-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="e4588-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e4588-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="e4588-112">Para quitar los grupos de respuesta del grupo de origen durante la exportación, incluya el parámetro – RemoveExportedConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e4588-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="e4588-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e4588-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="e4588-114">Importe los grupos de respuesta al grupo de destino y asigne el grupo de destino como nuevo propietario.</span><span class="sxs-lookup"><span data-stu-id="e4588-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="e4588-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e4588-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="e4588-116">Si también desea copiar la configuración del nivel de aplicación del grupo de respuesta del grupo de origen al grupo de destino, incluya el parámetro – ReplaceExistingRgsSettings.</span><span class="sxs-lookup"><span data-stu-id="e4588-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="e4588-117">Solo puede definir un conjunto de opciones de configuración de la aplicación por grupo.</span><span class="sxs-lookup"><span data-stu-id="e4588-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="e4588-118">Si copia la configuración de nivel de aplicación del grupo de origen en el grupo de destino, la configuración del grupo de origen reemplaza la configuración del grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="e4588-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="e4588-119">Si no copia la configuración de nivel de aplicación del grupo de origen, la configuración existente del grupo de destino se aplicará a los grupos de respuesta importados.</span><span class="sxs-lookup"><span data-stu-id="e4588-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="e4588-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e4588-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4588-121">La configuración de nivel de aplicación incluye la configuración predeterminada de música en espera, el archivo de audio de música activada predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="e4588-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="e4588-122">Para ver estas opciones de configuración, ejecute el cmdlet <STRONG>Get-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e4588-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="e4588-123">Para obtener más información sobre este cmdlet, vea <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="e4588-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="e4588-124">Para comprobar que la importación se ha realizado correctamente, muestre la configuración del grupo de respuesta importado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e4588-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="e4588-125">Compruebe que se importaron todos los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4588-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="e4588-126">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e4588-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="e4588-127">Compruebe que se han importado todas las colas.</span><span class="sxs-lookup"><span data-stu-id="e4588-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="e4588-128">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e4588-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="e4588-129">Verifique que se hayan importado todos los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="e4588-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="e4588-130">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e4588-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="e4588-131">Verifique que se hayan importado todas las horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4588-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="e4588-132">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e4588-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="e4588-133">Verifique que se hayan importado todos los conjuntos de días festivos.</span><span class="sxs-lookup"><span data-stu-id="e4588-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="e4588-134">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e4588-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="e4588-135">Verifique que la importación se haya realizado correctamente colocando una llamada a uno de los grupos de respuesta y verificando que la llamada se controla correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4588-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="e4588-136">Solicitar agentes que sean miembros de grupos de agentes formales para iniciar sesión en sus grupos de agentes en el grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="e4588-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="e4588-137">Si no ha quitado previamente grupos de respuesta del grupo de origen, quite los grupos de respuesta del grupo de origen.</span><span class="sxs-lookup"><span data-stu-id="e4588-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="e4588-138">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e4588-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="e4588-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e4588-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

