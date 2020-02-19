---
title: 'Lync Server 2013: procedimiento de conmutación por error ABC del grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38943d8e7d374fdd5b1fe202eaef44101bfeb321
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="bf612-102">Procedimiento de conmutación por error ABC del grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf612-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf612-103">_**Última modificación del tema:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="bf612-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="bf612-104">Siga estos pasos para realizar el procedimiento de conmutación por error ABC.</span><span class="sxs-lookup"><span data-stu-id="bf612-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="bf612-105">Este procedimiento contiene una descripción de alto nivel de cada paso, seguido de los comandos y los cmdlets que se van a ejecutar en cada paso.</span><span class="sxs-lookup"><span data-stu-id="bf612-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="bf612-106">Para ejecutar los cmdlets, abra un shell de administración de Lync Server con ejecutar como administrador.</span><span class="sxs-lookup"><span data-stu-id="bf612-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="bf612-107">Para realizar una conmutación por error ABC</span><span class="sxs-lookup"><span data-stu-id="bf612-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="bf612-108">Compruebe si el grupo de servidores es el host para el servidor de administración central (CMS).</span><span class="sxs-lookup"><span data-stu-id="bf612-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="bf612-109">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="bf612-110">Si el campo identidad del CMS activo señala al nombre de dominio completo (FQDN) del grupo A, siga los pasos 2 y 3 de este procedimiento para realizar la conmutación por error primero en el servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="bf612-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="bf612-111">De lo contrario, vaya al paso 4.</span><span class="sxs-lookup"><span data-stu-id="bf612-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="bf612-112">Conmute por error el CMS al grupo B en modo de recuperación ante desastres, para ello, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="bf612-113">Después de hacerlo, le recomendamos que mueva el CMS del grupo B a otro grupo emparejado existente para obtener resistencia adicional.</span><span class="sxs-lookup"><span data-stu-id="bf612-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="bf612-114">Para obtener más información, consulte [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="bf612-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="bf612-115">Si el grupo A contiene CMS, importe la configuración de LIS del grupo A en la base de datos LIS del grupo B (LIS. MDF).</span><span class="sxs-lookup"><span data-stu-id="bf612-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="bf612-116">Esto sólo funcionará si ha realizado una copia de seguridad de los datos de LIS de manera regular.</span><span class="sxs-lookup"><span data-stu-id="bf612-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="bf612-117">Para importar la configuración de LIS, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bf612-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="bf612-118">Importación de copias de seguridad de los flujos de trabajo del servicio de grupo de respuesta de Lync Server del grupo A en el grupo B.</span><span class="sxs-lookup"><span data-stu-id="bf612-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf612-119">Actualmente, el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> requiere que los nombres de la cola y del flujo de trabajo del grupo a sean distintos de los nombres de la cola y del flujo de trabajo del grupo B. Si los nombres no son distintos, se producirá un error al ejecutar el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> y será necesario cambiar el nombre de las colas y flujos de trabajo en el grupo B antes de continuar con el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="bf612-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="bf612-120">Tiene dos opciones para importar la configuración del grupo de respuesta del grupo A al grupo B. La opción que use dependerá de si desea sobrescribir la configuración de nivel de aplicación del grupo de servidores B con la configuración de nivel de aplicación en el grupo A.</span><span class="sxs-lookup"><span data-stu-id="bf612-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="bf612-121">Si desea sobrescribir la configuración del grupo B, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="bf612-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="bf612-122">Si no desea sobrescribir la configuración del grupo B, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="bf612-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bf612-123">Tenga en cuenta que si no desea sobrescribir la configuración de nivel de aplicación del grupo de copia de seguridad (grupo B) con la configuración del grupo principal (grupo A), la configuración de nivel de aplicación del grupo A se perderá si se pierde el grupo A, ya que la aplicación del grupo de respuesta puede Almacene solo un conjunto de opciones de configuración de nivel de aplicación por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bf612-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="bf612-124">Cuando se implementa el grupo C para reemplazar el grupo A, se debe volver a configurar la configuración del nivel de la aplicación, incluido el archivo de audio de música en espera predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bf612-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="bf612-125">Compruebe que la importación de configuración del grupo de respuesta se haya realizado correctamente mediante la ejecución de los siguientes cmdlets para mostrar los grupos de respuesta importados.</span><span class="sxs-lookup"><span data-stu-id="bf612-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="bf612-126">Tenga en cuenta que los grupos de respuesta importados todavía son propiedad del grupo A.</span><span class="sxs-lookup"><span data-stu-id="bf612-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="bf612-127">Para los números sin asignar, mueva los intervalos de números sin asignar que usan "anuncio" como servicio de anuncio seleccionado del grupo A al grupo B. Para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="bf612-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="bf612-128">Vuelva a crear todos los anuncios que se implementaron en el grupo A del grupo B. Si se usaron archivos de audio al implementar los anuncios en el grupo A, estos archivos serán necesarios para volver a crear los anuncios en el grupo B. Para volver a crear los anuncios en el grupo B, use los cmdlets **New-CsAnnouncement** con el grupo b como servicio primario.</span><span class="sxs-lookup"><span data-stu-id="bf612-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="bf612-129">Redestinar todos los intervalos de números sin asignar dirigidos a un anuncio del grupo A a los anuncios recién implementados en el grupo B. Ejecute el siguiente cmdlet para cada intervalo numérico sin asignar destinado a un anuncio del grupo A:</span><span class="sxs-lookup"><span data-stu-id="bf612-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf612-130">Este paso no es necesario para los intervalos de números sin asignar que usan "mensajería unificada de Exchange" como servicio de anuncio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bf612-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="bf612-131">Conmute por error el grupo a al grupo B en modo de recuperación ante desastres (DR), ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="bf612-132">Cree el grupo de servidores C, pero no inicie ningún servicio en el grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="bf612-133">Tenga en cuenta que este paso se puede llevar a cabo simultáneamente con los pasos 5 y 6.</span><span class="sxs-lookup"><span data-stu-id="bf612-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="bf612-134">Fuerce a los usuarios hospedados en el grupo A para que se muevan al grupo C ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="bf612-135">En este momento, los usuarios hospedados en el grupo A empezarán a experimentar una interrupción del servicio.</span><span class="sxs-lookup"><span data-stu-id="bf612-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="bf612-136">Esta interrupción continuará hasta el paso 16, momento en el que se inician los servicios en el grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="bf612-137">Fuerce el directorio de conferencia del grupo a para que se mueva al grupo C ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="bf612-138">Fuerce el objeto de contacto operador automático de conferencia (CAA) para que desplace del grupo A al grupo C mediante la ejecución del siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="bf612-139">Copie el contenido de la Conferencia del grupo B al grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="bf612-140">Exportar datos de usuario desde el grupo B e importar los datos de usuario en el grupo de servidores C ejecutando los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bf612-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="bf612-141">Restaure la copia de seguridad de los datos de la aplicación de estacionamiento de llamadas del grupo a en el grupo C y asigne los intervalos de órbita de estacionamiento de llamadas del grupo a al grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="bf612-142">Puede reasignar un intervalo de órbitas de estacionamiento de llamadas del grupo a al grupo C a través del panel de control de Lync Server o del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf612-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="bf612-143">Para el shell de administración de Lync Server, ejecute el siguiente cmdlet para cada intervalo de órbitas de estacionamiento de llamadas asignado al grupo a (tenga en cuenta que el parámetro Identity hace referencia a los intervalos de órbita de estacionamiento de llamadas que pertenecen al grupo a):</span><span class="sxs-lookup"><span data-stu-id="bf612-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="bf612-144">Si se ha configurado una música en espera personalizada para el estacionamiento de llamadas en el grupo A, restaure el archivo de música en espera personalizado para el estacionamiento de llamadas en el grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="bf612-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf612-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="bf612-146">Por último, vuelva a configurar las opciones de estacionamiento de llamadas en el grupo C mediante el cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bf612-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="bf612-147">La aplicación estacionamiento de llamadas solo puede almacenar un conjunto de opciones de configuración y un archivo de audio de música en espera personalizado por grupo de servidores, y no se realiza una copia de seguridad ni se conservan en el caso de un desastre.</span><span class="sxs-lookup"><span data-stu-id="bf612-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="bf612-148">Si el grupo del próximo salto del chat persistente apunta al grupo a, realice y publique los cambios de la topología para que el servidor del próximo salto apunte al grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="bf612-149">En el generador de topologías, cambie el grupo de chat persistente para que apunte a grupo C como su próximo salto.</span><span class="sxs-lookup"><span data-stu-id="bf612-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="bf612-150">Para ello, haga clic con el botón secundario en el grupo de chat persistente, haga clic en la pestaña **General** y, a continuación, escriba el nombre de grupo C en el grupo de servidores del **próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="bf612-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="bf612-151">Inicie los servicios en el grupo de servidores C ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="bf612-152">En este punto, la interrupción del servicio finaliza para los usuarios hospedados originalmente en el grupo A.</span><span class="sxs-lookup"><span data-stu-id="bf612-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="bf612-153">Exporte los flujos de trabajo del servicio de grupo de respuesta de Lync Server del grupo B al que pertenece el grupo A para importarlos en el grupo C ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="bf612-154">Importe los flujos de trabajo del servicio del grupo de respuesta de Lync Server en el grupo C del grupo B.</span><span class="sxs-lookup"><span data-stu-id="bf612-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="bf612-155">Tiene dos opciones para importar la configuración del grupo de respuesta del grupo B al grupo C. La opción que use dependerá de si desea sobrescribir la configuración de nivel de aplicación del grupo C con la configuración de nivel de aplicación del grupo B.</span><span class="sxs-lookup"><span data-stu-id="bf612-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="bf612-156">Si desea sobrescribir la configuración C del grupo de servidores, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings** :</span><span class="sxs-lookup"><span data-stu-id="bf612-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="bf612-157">Si no desea sobrescribir la configuración C del grupo de servidores, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="bf612-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bf612-158">Tenga en cuenta que si no desea sobrescribir la configuración de nivel de aplicación del grupo C con la configuración del grupo de copia de seguridad (grupo B), la configuración del nivel de aplicación del grupo B se perderá porque la aplicación grupo de respuesta solo puede almacenar un conjunto de nivel de aplicación. configuración por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bf612-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="bf612-159">Compruebe que la importación de configuración del grupo de respuesta se haya realizado correctamente mediante la ejecución de los siguientes cmdlets para mostrar los grupos de respuesta que se han importado al grupo de servidores C.</span><span class="sxs-lookup"><span data-stu-id="bf612-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="bf612-160">Cuando se haya comprobado la configuración importada en el grupo C, quite los grupos de respuesta que pertenecen al grupo de servidores principal del grupo B. Esto reducirá el tiempo de inactividad de los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bf612-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="bf612-161">En este paso se crea un archivo nuevo con la configuración exportada y, a continuación, se quita el archivo del grupo B.</span><span class="sxs-lookup"><span data-stu-id="bf612-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="bf612-162">Mover a grupo C los intervalos de números sin asignar que se movieron del grupo A al grupo B.</span><span class="sxs-lookup"><span data-stu-id="bf612-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="bf612-163">Vuelva a crear en el grupo C todos los anuncios que se han vuelto a crear a partir del grupo A en el grupo B. Si se usaron archivos de audio al implementar los anuncios que se moverán, tendrá que usar estos archivos para volver a crear los anuncios en el grupo de servidores C. Para volver a crear los anuncios en el grupo C, use los cmdlets **New-CsAnnouncement** , con el grupo c como servicio primario.</span><span class="sxs-lookup"><span data-stu-id="bf612-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="bf612-164">Redestinar al grupo C todos los intervalos de números sin asignar que se redestinaron del grupo A al grupo B. Ejecute el siguiente cmdlet para cada intervalo de números sin asignar que deba redestinarse:</span><span class="sxs-lookup"><span data-stu-id="bf612-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="bf612-165">Opcional Quite del grupo B los anuncios que se han vuelto a crear en el grupo C si ya no se usan en el grupo B. Para quitar anuncios, use el cmdlet **Remove-CsAnnouncement** .</span><span class="sxs-lookup"><span data-stu-id="bf612-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bf612-166">Este paso no es necesario para los intervalos de números sin asignar que usan "mensajería unificada de Exchange" como servicio de anuncio.</span><span class="sxs-lookup"><span data-stu-id="bf612-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="bf612-167">Limpie los datos de usuario del grupo A en el grupo B ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="bf612-168">Haga lo siguiente en el generador de topologías:</span><span class="sxs-lookup"><span data-stu-id="bf612-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="bf612-169">Desemparejar el grupo A y el grupo B. emparejar grupo B y grupo C. A continuación, quite el grupo A de la topología y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="bf612-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="bf612-170">Para ello:</span><span class="sxs-lookup"><span data-stu-id="bf612-170">To do so:</span></span>
        
          - <span data-ttu-id="bf612-171">En el generador de topologías, haga clic con el botón secundario en grupo B y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf612-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="bf612-172">Haga clic en **resistencia** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="bf612-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="bf612-173">En el cuadro que se encuentra a continuación del **grupo de copia de seguridad asociado**, seleccione grupo C. tenga en cuenta que el cuadro de selección del grupo de copia de seguridad asociado mostrará inicialmente el grupo a, porque el grupo B estaba asociado anteriormente a este grupo.</span><span class="sxs-lookup"><span data-stu-id="bf612-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="bf612-174">Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf612-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="bf612-175">Cuando visualice los detalles sobre este grupo, el grupo asociado aparecerá en el panel derecho bajo **Resistencia**.</span><span class="sxs-lookup"><span data-stu-id="bf612-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="bf612-176">En el árbol de consola, haga clic con el botón secundario en Pool A y, a continuación, haga clic en eliminar.</span><span class="sxs-lookup"><span data-stu-id="bf612-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="bf612-177">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="bf612-177">Publish the topology.</span></span>

23. <span data-ttu-id="bf612-178">Ejecute la aplicación de programa previo en el grupo C para instalar la aplicación de servicio de copia de seguridad y, a continuación, inicie la aplicación de servicio de copia de seguridad ejecutando lo siguiente desde la carpeta de implementación en un equipo local en el grupo C:</span><span class="sxs-lookup"><span data-stu-id="bf612-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="bf612-179">Reinicie la aplicación de servicio de copia de seguridad en el grupo B; para ello, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bf612-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="bf612-180">Si el grupo C es un grupo de servidores Standard Edition (SE) y el grupo B tiene CMS, instale la base de datos de CMS manualmente en el grupo C ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="bf612-181">Invocar el servicio de copia de seguridad para sincronizar el contenido de conferencia antiguo del grupo B al grupo C que se generó antes de emparejar B y C, y para sincronizar el nuevo contenido de conferencia desde el grupo C al grupo B que se generó después de iniciar el grupo C y antes de que se emparejaran los dos.</span><span class="sxs-lookup"><span data-stu-id="bf612-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="bf612-182">Para ello, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bf612-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="bf612-183">Para cada aplicación de sucursal con funciones de supervivencia asociada con el grupo A:</span><span class="sxs-lookup"><span data-stu-id="bf612-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="bf612-184">Para apagar SBA X, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="bf612-185">Cree un archivo que contenga una lista de usuarios hospedados en SBA X. La lista será necesaria cuando los usuarios se muevan de nuevo a SBA X en el paso 30.</span><span class="sxs-lookup"><span data-stu-id="bf612-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="bf612-186">Para ello, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="bf612-187">Fuerce que los usuarios hospedados en SBA X se muevan al grupo C ejecutando el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bf612-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="bf612-188">Actualice los datos de estos usuarios ejecutando primero los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="bf612-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="bf612-189">Y, a continuación, ejecute este script:</span><span class="sxs-lookup"><span data-stu-id="bf612-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bf612-190">Se producirá una interrupción del servicio para los usuarios hospedados en las asociados al grupo A hasta que estos usuarios se muevan al grupo C.</span><span class="sxs-lookup"><span data-stu-id="bf612-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="bf612-191">En el generador de topologías, para cada X de SBA asociada anteriormente con el grupo A, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf612-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="bf612-192">Cambie la asociación al grupo C. Para ello, haga clic en el sitio de sucursal, expanda el nodo servidores y aplicaciones de sucursal con funciones de supervivencia y haga clic en **aplicación de sucursal**con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="bf612-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="bf612-193">A continuación, seleccione el grupo de **servidores front-end, el grupo de servicios de usuario** al que se conectará esta aplicación de sucursal con funciones de supervivencia como grupo C y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bf612-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="bf612-194">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="bf612-194">Publish the topology.</span></span> <span data-ttu-id="bf612-195">Para ello, en el árbol de la consola, haga clic con el botón secundario en la nueva **aplicación de sucursal**con funciones de supervivencia, haga clic en **topología**y, a continuación, en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="bf612-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="bf612-196">Para cada X de SBA ahora asociada con el grupo de servidores C:</span><span class="sxs-lookup"><span data-stu-id="bf612-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="bf612-197">Inicie SBA X ejecutando el siguiente cmdlet en la aplicación de sucursal con funciones de supervivencia:</span><span class="sxs-lookup"><span data-stu-id="bf612-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="bf612-198">Mueva los usuarios que se hospedaban originalmente en SBA X del grupo C a SBA X ejecutando el siguiente cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bf612-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

