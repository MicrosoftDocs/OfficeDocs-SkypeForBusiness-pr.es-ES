---
title: 'Lync Server 2013: administrar anuncios durante la recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c58859a6e92abfbb50b79c12b587c3b65c1a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3105e-102">Administrar anuncios durante la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3105e-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3105e-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3105e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3105e-104">Lync Server 2013 admite anuncios para las llamadas a números no asignados durante las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="3105e-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="3105e-105">La restauración de la funcionalidad de los anuncios durante una interrupción es opcional.</span><span class="sxs-lookup"><span data-stu-id="3105e-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="3105e-106">Si decide hacerlo, debe volver a crear la configuración de los anuncios en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3105e-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="3105e-107">En esta sección se describe cómo puede restaurar los anuncios durante una recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="3105e-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="3105e-108">Esta sección se aplica a los intervalos de números sin asignar que usan la aplicación de anuncio.</span><span class="sxs-lookup"><span data-stu-id="3105e-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="3105e-109">Esta sección no se aplica a los intervalos de números sin asignar que usan el operador automático de mensajería unificada (MU) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3105e-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="3105e-110">Antes de la interrupción del servicio</span><span class="sxs-lookup"><span data-stu-id="3105e-110">Before an Outage</span></span>

<span data-ttu-id="3105e-111">Independientemente de si decide usar anuncios durante las interrupciones, debe realizar copias de seguridad separadas de los archivos de audio personalizados que haya configurado para la aplicación de anuncio.</span><span class="sxs-lookup"><span data-stu-id="3105e-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="3105e-112">No se realiza una copia de seguridad de los anuncios personalizados como parte del proceso de recuperación ante desastres de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3105e-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="3105e-113">Si no hace copias de seguridad independientes, los archivos que ha cargado en el servidor o en el grupo se perderán si se dañan o se borran.</span><span class="sxs-lookup"><span data-stu-id="3105e-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="3105e-114">Si no tiene copias de seguridad de los archivos de audio personalizados y los archivos de audio originales ya no están disponibles, puede buscar los archivos de audio que configuró para una aplicación de anuncio en el almacén de archivos del servidor o grupo de servidores donde originalmente importado los archivos.</span><span class="sxs-lookup"><span data-stu-id="3105e-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="3105e-115">Puede copiar todos los archivos de audio que haya configurado para la aplicación de anuncio desde el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="3105e-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="3105e-116">**Para copiar archivos de audio desde el almacén de archivos**</span><span class="sxs-lookup"><span data-stu-id="3105e-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="3105e-117">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3105e-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="3105e-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3105e-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="3105e-119">Donde X-ApplicationServer-X se refiere al identificador de servicio del servidor de aplicaciones del grupo (por ejemplo, 1-ApplicationServer-1").</span><span class="sxs-lookup"><span data-stu-id="3105e-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="3105e-120">Durante la interrupción del servicio</span><span class="sxs-lookup"><span data-stu-id="3105e-120">During an Outage</span></span>

<span data-ttu-id="3105e-121">Para usar la aplicación de anuncio durante una interrupción, debe volver a crear la configuración del anuncio en el grupo de copia de seguridad; para ello, realice las tareas descritas en esta sección.</span><span class="sxs-lookup"><span data-stu-id="3105e-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3105e-122">Es aconsejable que realice estas tareas después de completar la conmutación por error del grupo de copia de seguridad, porque cuando realice las acciones del paso 2, el grupo de copia de seguridad se convertirá en propietario de los intervalos de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="3105e-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3105e-123">Estos pasos no son necesarios para los intervalos de números que usan el número de teléfono del Operador automático de la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3105e-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="3105e-124">**Para volver a crear la configuración del anuncio en el grupo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="3105e-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="3105e-125">Cree de nuevo en el grupo de copia de seguridad los anuncios que implementó en el grupo principal tal como se indica:</span><span class="sxs-lookup"><span data-stu-id="3105e-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="3105e-126">Importe los archivos de audio que ha usado en el grupo principal en el grupo de copia de seguridad con el cmdlet **Import-CsAnnouncementFile**, y especifique el grupo de copia de seguridad para el parámetro Principal.</span><span class="sxs-lookup"><span data-stu-id="3105e-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="3105e-127">Cree de nuevo cada anuncio con el cmdlet **New-CsAnnouncement** y especifique el grupo de copia de seguridad para el parámetro Principal.</span><span class="sxs-lookup"><span data-stu-id="3105e-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3105e-128">Para obtener información detallada sobre cómo usar estos parámetros para crear anuncios en el grupo de servidores de copia de seguridad, vea <A href="lync-server-2013-create-an-announcement.md">crear un anuncio en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3105e-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="3105e-129">Tras crear los anuncios en el grupo de copia de seguridad, redirija todos los intervalos de números sin asignar que usan anuncios del grupo principal a los anuncios recreados en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3105e-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="3105e-130">Para cada intervalo de números no asignados que use un anuncio en el grupo principal, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3105e-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="3105e-131">Después de la interrupción del servicio</span><span class="sxs-lookup"><span data-stu-id="3105e-131">After the Outage</span></span>

<span data-ttu-id="3105e-132">Cuando el grupo principal se encuentre disponible, deberá redirigir de nuevo a este grupo los intervalos de números no asignados que ha cambiado para la interrupción.</span><span class="sxs-lookup"><span data-stu-id="3105e-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3105e-133">Estos pasos no son necesarios para los intervalos de números que usan un número de teléfono del Operador automático de la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3105e-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="3105e-134">**Para restaurar anuncios en el grupo de servidores principal**</span><span class="sxs-lookup"><span data-stu-id="3105e-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="3105e-p105">Si ha creado de nuevo el grupo principal durante la recuperación, deberá volver a crear los anuncios en este grupo. Para ello, importe los archivos de audio y cree los anuncios como lo hizo en el grupo de copia de seguridad, con la excepción de que deberá especificar el grupo principal para el parámetro Principal. Para más información, consulte "Durante la interrupción del servicio", más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="3105e-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="3105e-137">Para cada intervalo de números no asignados que haya cambiado para la interrupción del servicio, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3105e-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="3105e-138">Si lo desea, quite los anuncios que ha creado de nuevo en el grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3105e-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="3105e-139">Obtenga una lista de anuncios para la aplicación de anuncio del grupo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3105e-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="3105e-140">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3105e-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="3105e-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3105e-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="3105e-p107">En la lista resultante, localice los anuncios que desea quitar y copie los GUID. Para cada anuncio que desee quitar, ejecute:</span><span class="sxs-lookup"><span data-stu-id="3105e-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="3105e-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3105e-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

