---
title: 'Lync Server 2013: requisitos previos de copia de seguridad para la conmutación por error de grupo ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="95ea2-102">Requisitos previos de copia de seguridad de la conmutación por error de grupo ABC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95ea2-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95ea2-103">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="95ea2-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="95ea2-104">Para sacar el máximo provecho del uso del procedimiento de failover de grupo ABC, debe realizar ciertas copias de seguridad antes de que se produzca el desastre y el failover:</span><span class="sxs-lookup"><span data-stu-id="95ea2-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="95ea2-105">Debe realizar una copia de seguridad de los datos de configuración del servicio de información de ubicación (LIS) desde el grupo A mediante el cmdlet **Export-CsLISConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="95ea2-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="95ea2-106">Debe realizar una copia de seguridad de los datos de configuración del grupo de respuesta en el grupo A mediante el cmdlet **Export-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="95ea2-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="95ea2-107">En general, le recomendamos que realice copias de seguridad diarias pero, si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="95ea2-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="95ea2-108">La cantidad de información que puede perder en caso de que se produzca un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.</span><span class="sxs-lookup"><span data-stu-id="95ea2-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="95ea2-109">La aplicación de grupo de respuesta solo puede almacenar un conjunto de parámetros de nivel de aplicación por grupo.</span><span class="sxs-lookup"><span data-stu-id="95ea2-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="95ea2-110">Se puede acceder a esta configuración a través de los cmdlets **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="95ea2-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="95ea2-111">La configuración incluye la configuración predeterminada de música en espera, el archivo de audio de música activada predeterminada, el período de gracia con anillo de los agentes y la configuración del contexto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="95ea2-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="95ea2-112">Esta configuración se puede transferir de una agrupación a otra mediante el cmdlet **Import-CsRgsConfiguration** mediante el parámetro **ReplaceExistingSettings** , pero esta operación invalidará cualquier configuración de nivel de aplicación en el destino. agrupa.</span><span class="sxs-lookup"><span data-stu-id="95ea2-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="95ea2-113">En una ubicación independiente, mantenga una copia de seguridad de todos los archivos de audio originales que se han usado para configurar la aplicación de grupo de respuesta (es decir, cualquier grabación o música en suspensión).</span><span class="sxs-lookup"><span data-stu-id="95ea2-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="95ea2-114">Si tiene algún archivo de música personalizada habilitada que se haya cargado para el servicio de estacionamiento de llamadas en un grupo, debe guardar una copia en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="95ea2-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="95ea2-115">No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se hayan borrado.</span><span class="sxs-lookup"><span data-stu-id="95ea2-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95ea2-116">La aplicación de estacionamiento de llamadas solo puede almacenar un conjunto de configuraciones y un archivo de audio de música en espera personalizado por grupo.</span><span class="sxs-lookup"><span data-stu-id="95ea2-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="95ea2-117">Se puede acceder a esta configuración a través del cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="95ea2-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="95ea2-118">Puesto que el mecanismo de recuperación de desastres para el parque de llamadas depende de la aplicación de estacionamiento de llamadas del grupo de copias de seguridad, no se hace una copia de seguridad de la configuración del grupo principal ni se conserva si se produce un desastre.</span><span class="sxs-lookup"><span data-stu-id="95ea2-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="95ea2-119">Si el grupo primario se pierde, esta configuración no se puede recuperar y cuando se implementa un nuevo grupo para reemplazar el grupo principal, la configuración de la suspensión de llamada y el archivo de audio de música personalizada en espera tendría que volver a configurarse.</span><span class="sxs-lookup"><span data-stu-id="95ea2-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="95ea2-120">Si configura cualquier anuncio como parte de la característica de voz número no asignado, le recomendamos que se mantenga en otro lugar una copia de cualquier archivo de audio original que se haya usado durante la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="95ea2-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="95ea2-121">Si no lo hizo, puede obtener una copia de los archivos de audio configurados en el almacén de archivos del servidor o del grupo en el que se han importado los archivos de audio.</span><span class="sxs-lookup"><span data-stu-id="95ea2-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="95ea2-122">No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se hayan borrado.</span><span class="sxs-lookup"><span data-stu-id="95ea2-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="95ea2-123">Para copiar todos los archivos de audio que se usan para configurar la característica de voz de número sin asignar desde el almacén de archivos de un servidor o grupo, use:</span><span class="sxs-lookup"><span data-stu-id="95ea2-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="95ea2-124">Si tiene bases de datos de supervisión y archivado en un grupo, debe usar las herramientas de administración de SQL Server para realizar copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="95ea2-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="95ea2-125">En el procedimiento de conmutación por error ABC, las bases de datos de supervisión y archivado no se conservan si se colocan en el grupo A, porque estas bases de datos no se copian mediante el servicio de copia de seguridad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95ea2-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

