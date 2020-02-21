---
title: 'Lync Server 2013: requisitos de conferencia Web'
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
ms.openlocfilehash: 56a030329f9d69a3748b2b76179c7a783b13cb0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Requisitos de conferencia web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Si ha elegido habilitar la conferencia Web, tiene que planear lo siguiente:

  - <span></span>  
    Acceso al almacén de archivos, que se usa para almacenar contenido de conferencia Web.

  - <span></span>  
    Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.

<div>

## <a name="file-store"></a>Almacén de archivos

El servicio de conferencia Web de Lync Server 2013 almacena contenido compartido durante las reuniones en el almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivos que se usará como almacén de archivos para el grupo de servidores front-end Standard Edition o Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especifique uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso.Para obtener más información, consulte Topology Builder: definir el almacén de archivos para el front-end. El servicio de conferencia web cifra el contenido antes de almacenar el contenido en el almacén de archivos.

Lync Server 2013 admite el uso de recursos compartidos de archivos en el almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS) y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Una vez que el Asistente para la implementación de Lync Server haya definido la ubicación del recurso compartido de archivos, Lync Server creará una estructura de carpetas dentro del recurso compartido de archivos similar a la siguiente:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-webservices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - Conf

A continuación, el servicio de conferencia Web almacena contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta webservices.

El administrador debe establecer permisos en el recurso compartido de archivos para que los grupos de RTC tengan el acceso de lectura y escritura necesario.

<div>


> [!WARNING]  
> Si encuentra errores con los permisos, abra el generador de topologías, descargue y vuelva a publicar la topología existente. La publicación de la topología comprobará los permisos de recursos compartidos de archivos y los restablecerá si es necesario.



</div>

Puede usar los siguientes valores para administrar la forma en que se almacena el contenido de una reunión:

  - **ContentGracePeriod**, que se encuentra en [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), establece cuánto tiempo permanecerá el contenido de conferencia web en el servidor una vez finalizada la reunión.

  - **MaxContentStorageMb**, que se encuentra en [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), establece la cantidad máxima de espacio en archivo permitida para el almacenamiento de contenido durante una única reunión.

**MaxUploadFileSizeMb** no limita la configuración de carga de archivos para Lync Web App. El límite de carga de tamaño de archivo para Lync Web App se establece en aproximadamente 30 MB y se controla mediante el archivo Web.\[config\]de IIS:/DataCollabWeb/int ext/handler/Web.config. Para configurar el límite de carga de tamaño de archivo para Lync Web `maxRequestLength` APP `maxAllowedContentLength` , actualice y en el archivo Web. config tal como se muestra a continuación.

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

Para poder usar estas nuevas funciones, los administradores deben instalar Office Web Apps Server y deben configurar Lync Server 2013 para comunicarse con Office Web Apps Server. En esta documentación se proporciona información sobre cómo configurar Lync Server 2013 para que funcione con Office Web Apps Server. Lo que no proporciona esta documentación es información sobre cómo instalar Office Web Apps Server. Para obtener información sobre la instalación, consulte el sitio web de implementación <https://go.microsoft.com/fwlink/p/?linkid=257525>de Microsoft Office Web Apps en. Esta guía incluye la información de requisitos previos completos para Office Web Apps Server. Tenga en cuenta que Office Web Apps Server debe instalarse en un equipo independiente que no ejecute Lync Server, SQL Server o cualquier otra aplicación de servidor. (No debe tener ninguna versión de Office instalada en ese equipo). Cualquier equipo que se use para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluido .NET Framework 4,5 y Windows PowerShell 3,0). Estos requisitos, junto con información sobre la configuración de certificados y servicios de Internet Information Server (IIS), se describen en detalle en el sitio web de <https://go.microsoft.com/fwlink/p/?linkid=257525>implementación de Microsoft Office Web Apps en.

</div>

<div>

## <a name="see-also"></a>Consulta también


[Información general sobre conferencias web en Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Lista de comprobación para la implementación de conferencias web en Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

