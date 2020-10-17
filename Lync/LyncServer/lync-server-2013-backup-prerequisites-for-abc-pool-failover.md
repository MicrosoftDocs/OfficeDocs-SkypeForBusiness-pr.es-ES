---
title: 'Lync Server 2013: requisitos previos de copia de seguridad para la conmutación por error del grupo ABC'
description: 'Lync Server 2013: requisitos previos de copia de seguridad para la conmutación por error del grupo ABC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05eb0d2ad50f1ed4f04964158fb5d22d079f3b50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552336"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="5d536-103">Requisitos previos de copia de seguridad para la conmutación por error del grupo ABC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d536-103">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d536-104">_**Última modificación del tema:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="5d536-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="5d536-105">Para sacar el máximo provecho del uso del procedimiento de conmutación por error del grupo ABC, debe realizar ciertas copias de seguridad antes de que se produzca el desastre y la conmutación por error:</span><span class="sxs-lookup"><span data-stu-id="5d536-105">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="5d536-106">Debe realizar una copia de seguridad de los datos de configuración del servicio de información de ubicación (LIS) desde el grupo A con el cmdlet **Export-CsLISConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5d536-106">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="5d536-107">Debe hacer una copia de seguridad de los datos de configuración del grupo de respuesta en el grupo A mediante el cmdlet **Export-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5d536-107">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="5d536-108">En general, se recomienda que realice copias de seguridad diarias, pero si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="5d536-108">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="5d536-109">La cantidad de información que puede perder en caso de que se produzca un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.</span><span class="sxs-lookup"><span data-stu-id="5d536-109">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="5d536-110">La aplicación de grupo de respuesta solo puede almacenar un conjunto de opciones de configuración de nivel de aplicación por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5d536-110">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="5d536-111">Se puede tener acceso a esta configuración a través de los cmdlets **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="5d536-111">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="5d536-112">La configuración incluye la configuración predeterminada de música en espera, el archivo de audio de música en espera predeterminado, el período de gracia de timbre por anillo del agente y la configuración del contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="5d536-112">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="5d536-113">Esta configuración se puede transferir de un grupo de servidores a otro mediante el cmdlet **Import-CsRgsConfiguration** mediante el parámetro **ReplaceExistingSettings** , pero esta operación anulará cualquier configuración de nivel de aplicación en el grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="5d536-113">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5d536-114">En una ubicación independiente, conserve una copia de seguridad de todos los archivos de audio originales que se han usado para configurar la aplicación de grupo de respuesta (es decir, las grabaciones o los archivos de música en espera).</span><span class="sxs-lookup"><span data-stu-id="5d536-114">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="5d536-115">Si tiene archivos de música en espera personalizados que se han cargado para el estacionamiento de llamadas en un grupo de servidores, debe conservar una copia en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="5d536-115">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="5d536-116">No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se han borrado.</span><span class="sxs-lookup"><span data-stu-id="5d536-116">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d536-117">La aplicación estacionamiento de llamadas solo puede almacenar un conjunto de configuraciones y un archivo de audio de música en espera personalizado por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5d536-117">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="5d536-118">Se puede tener acceso a esta configuración a través del cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5d536-118">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="5d536-119">Debido a que el mecanismo de recuperación ante desastres para el estacionamiento de llamadas depende de la aplicación de estacionamiento de llamadas del grupo de copia de seguridad, no se realiza una copia de seguridad ni se conserva la configuración del grupo principal si se produce un desastre.</span><span class="sxs-lookup"><span data-stu-id="5d536-119">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="5d536-120">Si se pierde el grupo principal, esta configuración no se puede recuperar y, cuando se implementa un nuevo grupo de servidores para reemplazar el grupo principal, la configuración del estacionamiento de llamadas y el archivo de audio de música en espera personalizado tendría que volver a configurarse.</span><span class="sxs-lookup"><span data-stu-id="5d536-120">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="5d536-121">Si configura los anuncios como parte de la característica de voz de número sin asignar, le recomendamos que se mantenga en otra ubicación una copia de los archivos de audio originales que se usan durante la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="5d536-121">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="5d536-122">Si no lo hizo, puede obtener una copia de los archivos de audio configurados en el almacén de archivos del servidor o del grupo de servidores al que se han importado los archivos de audio.</span><span class="sxs-lookup"><span data-stu-id="5d536-122">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="5d536-123">No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se han borrado.</span><span class="sxs-lookup"><span data-stu-id="5d536-123">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="5d536-124">Para copiar todos los archivos de audio que se usan para configurar la característica de voz de número sin asignar desde el almacén de archivos de un servidor o grupo de servidores, use:</span><span class="sxs-lookup"><span data-stu-id="5d536-124">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="5d536-125">Si tiene bases de datos de supervisión y archivado en un grupo de servidores, debe usar las herramientas de administración de SQL Server para realizar una copia de seguridad de las mismas.</span><span class="sxs-lookup"><span data-stu-id="5d536-125">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="5d536-126">En el procedimiento de conmutación por error ABC, las bases de datos de supervisión y archivado no se conservan si se colocan en el grupo A, porque no se realiza una copia de seguridad de estas bases de datos a través del servicio de copia de seguridad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d536-126">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

