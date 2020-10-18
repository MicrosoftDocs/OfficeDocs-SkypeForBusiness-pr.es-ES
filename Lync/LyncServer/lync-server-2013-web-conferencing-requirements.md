---
title: 'Lync Server 2013: requisitos de conferencia Web'
description: 'Lync Server 2013: requisitos de conferencia Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1fce932d3cc02ac29364d53d04ec336693e43b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576396"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="be18a-103">Requisitos de conferencia web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be18a-103">Web conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be18a-104">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="be18a-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="be18a-105">Si ha elegido habilitar la conferencia Web, tiene que planear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="be18a-105">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="be18a-106">Acceso al almacén de archivos, que se usa para almacenar contenido de conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="be18a-106">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="be18a-107">Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.</span><span class="sxs-lookup"><span data-stu-id="be18a-107">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="be18a-108">Almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="be18a-108">File Store</span></span>

<span data-ttu-id="be18a-109">El servicio de conferencia Web de Lync Server 2013 almacena contenido compartido durante las reuniones en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="be18a-109">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="be18a-110">Como parte de la implementación, debe especificar un recurso compartido de archivos que se usará como almacén de archivos para el grupo de servidores front-end Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="be18a-110">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="be18a-111">Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="be18a-111">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="be18a-112">Para obtener más información, consulte Topology Builder: definir el almacén de archivos para el front-end.</span><span class="sxs-lookup"><span data-stu-id="be18a-112">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="be18a-113">El servicio de conferencia web cifra el contenido antes de almacenar el contenido en el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="be18a-113">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="be18a-114">Lync Server 2013 admite el uso de recursos compartidos de archivos en el almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS) y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos.</span><span class="sxs-lookup"><span data-stu-id="be18a-114">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="be18a-115">Una vez que el Asistente para la implementación de Lync Server haya definido la ubicación del recurso compartido de archivos, Lync Server creará una estructura de carpetas dentro del recurso compartido de archivos similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="be18a-115">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="be18a-116">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="be18a-116">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="be18a-117">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="be18a-117">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="be18a-118">1-webservices-1</span><span class="sxs-lookup"><span data-stu-id="be18a-118">1-WebServices-1</span></span>
    
      - <span data-ttu-id="be18a-119">CollabContent</span><span class="sxs-lookup"><span data-stu-id="be18a-119">CollabContent</span></span>
    
      - <span data-ttu-id="be18a-120">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="be18a-120">CollabMetadata</span></span>
    
      - <span data-ttu-id="be18a-121">Conf</span><span class="sxs-lookup"><span data-stu-id="be18a-121">DataConf</span></span>

<span data-ttu-id="be18a-122">A continuación, el servicio de conferencia Web almacena contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta webservices.</span><span class="sxs-lookup"><span data-stu-id="be18a-122">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="be18a-123">El administrador debe establecer permisos en el recurso compartido de archivos para que los grupos de RTC tengan el acceso de lectura y escritura necesario.</span><span class="sxs-lookup"><span data-stu-id="be18a-123">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="be18a-124">Si encuentra errores con los permisos, abra el generador de topologías, descargue y vuelva a publicar la topología existente.</span><span class="sxs-lookup"><span data-stu-id="be18a-124">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="be18a-125">La publicación de la topología comprobará los permisos de recursos compartidos de archivos y los restablecerá si es necesario.</span><span class="sxs-lookup"><span data-stu-id="be18a-125">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="be18a-126">Puede usar los siguientes valores para administrar la forma en que se almacena el contenido de una reunión:</span><span class="sxs-lookup"><span data-stu-id="be18a-126">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="be18a-127">**ContentGracePeriod**, que se encuentra en [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), establece cuánto tiempo permanecerá el contenido de conferencia web en el servidor una vez finalizada la reunión.</span><span class="sxs-lookup"><span data-stu-id="be18a-127">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="be18a-128">**MaxContentStorageMb**, que se encuentra en [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), establece la cantidad máxima de espacio en archivo permitida para el almacenamiento de contenido durante una única reunión.</span><span class="sxs-lookup"><span data-stu-id="be18a-128">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="be18a-129">**MaxUploadFileSizeMb** no limita la configuración de carga de archivos para Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="be18a-129">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="be18a-130">El límite de carga de tamaño de archivo para Lync Web App se establece en aproximadamente 30 MB y se controla mediante el archivo web.config de IIS:/DataCollabWeb/Int \[ ext \] /handler/web.config. Para configurar el límite de carga de tamaño de archivo para Lync Web App, actualice `maxRequestLength` y `maxAllowedContentLength` en el archivo de web.config como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="be18a-130">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="be18a-131">Debe actualizar el archivo de web.config para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="be18a-131">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="be18a-132">Servidor Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="be18a-132">Office Web Apps Server</span></span>

<span data-ttu-id="be18a-133">Para poder usar estas nuevas funciones, los administradores deben instalar Office Web Apps Server y deben configurar Lync Server 2013 para comunicarse con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="be18a-133">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="be18a-134">En esta documentación se proporciona información sobre cómo configurar Lync Server 2013 para que funcione con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="be18a-134">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="be18a-135">Lo que no proporciona esta documentación es información sobre cómo instalar Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="be18a-135">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="be18a-136">Para obtener información sobre la instalación, consulte el sitio web de implementación de Microsoft Office Web Apps en <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="be18a-136">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="be18a-137">Esta guía incluye la información de requisitos previos completos para Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="be18a-137">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="be18a-138">Tenga en cuenta que Office Web Apps Server debe instalarse en un equipo independiente que no ejecute Lync Server, SQL Server o cualquier otra aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="be18a-138">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="be18a-139">(No debe tener ninguna versión de Office instalada en ese equipo). Cualquier equipo que se use para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluido .NET Framework 4,5 y Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="be18a-139">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="be18a-140">Estos requisitos, junto con información sobre la configuración de certificados y servicios de Internet Information Server (IIS), se describen en detalle en el sitio web de implementación de Microsoft Office Web Apps en <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="be18a-140">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="be18a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be18a-141">See Also</span></span>


[<span data-ttu-id="be18a-142">Información general sobre conferencias web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be18a-142">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="be18a-143">Lista de comprobación para la implementación de conferencias web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be18a-143">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

