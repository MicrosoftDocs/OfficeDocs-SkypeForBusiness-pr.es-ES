---
title: 'Lync Server 2013: requisitos de conferencia Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Requisitos de conferencia web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Si ha elegido habilitar la conferencia web, tiene que planear lo siguiente:

  - <span></span>  
    Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.

  - <span></span>  
    Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.

<div>

## <a name="file-store"></a>Almacén de archivos

El servicio de conferencias web de Lync Server 2013 almacena contenido compartido durante las reuniones del almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivos para usarlo como el almacén de archivos para el servidor Standard Edition o el grupo front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.Para obtener más información, vea generador de topologías: defina el almacén de archivos para el front-end. El servicio de conferencia web cifra el contenido antes de almacenarlo en el almacén de archivos.

Lync Server 2013 admite el uso de recursos compartidos de archivos en almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS) y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Una vez que el Asistente para la implementación de Lync Server haya definido la ubicación del recurso compartido de archivos, Lync Server creará una estructura de carpetas dentro del recurso compartido de archivos similar a:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

El servicio de conferencia web almacena entonces el contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta WebServices.

El administrador debe establecer permisos en el recurso compartido de archivos para que los grupos de RTC tengan el acceso necesario de lectura y escritura.

<div>


> [!WARNING]  
> Si encuentra algún error con los permisos, abra el generador de topologías, descargue y vuelva a publicar la topología existente. La publicación de la topología comprobará los permisos de uso compartido de archivos y los restablecerá si es necesario.



</div>

Puede usar la siguiente configuración para administrar la forma en que se almacena el contenido de una reunión:

  - **ContentGracePeriod**, que se encuentra en [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), establece cuánto tiempo permanecerá contenido en el servidor una vez que la reunión haya finalizado.

  - **MaxContentStorageMb**, que se encuentra en [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), establece la cantidad máxima de espacio de archivo permitido para el almacenamiento de contenido durante una sola reunión.

**MaxUploadFileSizeMb** no limita la configuración de carga de archivos de Lync Web App. El límite de carga de tamaño de archivo para Lync Web App se establece en aproximadamente 30 MB y está controlado por el archivo Web.\[config\]de IIS:/DataCollabWeb/int ext/handler/Web.config. Para configurar el límite de carga del tamaño de archivo de Lync Web `maxRequestLength` APP `maxAllowedContentLength` , actualice y en el archivo Web. config tal como se muestra a continuación.

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

Debe actualizar el archivo Web. config para cada servidor front-end.

</div>

<div>

## <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para poder usar estas nuevas funciones, los administradores deben instalar Office Web Apps Server y deben configurar Lync Server 2013 para comunicarse con Office Web Apps Server. Esta documentación proporciona información sobre cómo configurar Lync Server 2013 para que funcione con Office Web Apps Server. Lo que no ofrece esta documentación es información sobre cómo instalar Office Web Apps Server. Para obtener información sobre la instalación, vea el sitio web de implementación <http://go.microsoft.com/fwlink/p/?linkid=257525>de Microsoft Office Web Apps en. Esta guía incluye información completa de requisitos previos para Office Web Apps Server. Tenga en cuenta que Office Web Apps Server debe instalarse en un equipo independiente que no ejecute Lync Server, SQL Server ni ninguna otra aplicación de servidor. (No debe tener ninguna versión de Office instalada en ese equipo). Cualquier equipo usado para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluidos .NET Framework 4,5 y Windows PowerShell 3,0). Estos requisitos, junto con información sobre cómo configurar certificados y servicios de información de Internet (IIS), se tratan en detalle en el sitio web de implementación <http://go.microsoft.com/fwlink/p/?linkid=257525>de Microsoft Office Web Apps en.

</div>

<div>

## <a name="see-also"></a>Vea también


[Información general sobre las conferencias web en Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Lista de comprobación de implementación para conferencias web en Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

