---
title: Requisitos de conferencia web
TOCTitle: Requisitos de conferencia web
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49115270
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de conferencia web

 

_**Última modificación del tema:** 2016-12-08_

Si ha elegido habilitar la conferencia web, tiene que planear lo siguiente:

   Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.  

   Integración con Servidor Office Web Apps, que es necesaria para compartir archivos de PowerPoint durante una conferencia.  

## Almacén de archivos

El servicio de conferencia web de Lync Server 2013 almacena contenido compartido durante las reuniones en el almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivo para usarlo como el almacén de archivos para el servidor de Standard Edition o Enterprise EditionGrupo de servidores front-end. Para ello, use un recurso compartido de archivos ya creado o especificar uno nuevo indicando el nombre de dominio completo del servidor de archivos donde debe ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso. Para obtener más información, vea Generador de topologías – Definir el almacén de archivos para el front-end. El servicio de conferencia web cifra el contenido antes de almacenarlo en el almacén de archivos.

Lync Server 2013 admite el uso de recursos compartidos de red en el almacenamiento conectado directo (DAS) o una red de área de almacenamiento (SAN), incluyendo el Sistema de archivos distribuido (DFS) en una matriz redundante de discos independientes (RAID) para almacenes de archivos. Una vez que la Asistente para la implementación de Lync Server ha definido la ubicación de un recurso compartido de archivos, Lync Server crea una estructura de carpetas dentro del mismo recurso compartido de archivos similar a la siguiente:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

El servicio de conferencia web almacena entonces el contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta WebServices.

El administrador debe establecer permisos en el recurso compartido de archivos de manera que los grupos RTC tengan el acceso de lectura y escritura necesario.

> [!WARNING]  
> Si encuentra errores con los permisos, abra el Generador de topologías, descargue la topología existente y vuelva a publicarla. La publicación de la topología comprobará los permisos de recurso compartido de archivos y los restablecerá en caso necesario.



Puede usar los siguientes valores para administrar la manera en que se almacena el contenido para una reunión:

  - **ContentGracePeriod**, que se encuentra en [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration), establece cuánto tiempo la conferencia web permanecerá en el servidor una vez haya acabado la reunión.

  - **MaxContentStorageMb**, que se encuentra en [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration), establece la cantidad máxima del espacio de archivo permitido para el almacenamiento de contenido durante una reunión única.

**MaxUploadFileSizeMb** no limita la configuración de carga de archivos para Lync Web App. El límite de carga de tamaño de archivo para Lync Web App se establece en aproximadamente 30 MB y se controla por el archivo web.config de IIS: /DataCollabWeb/Int\[Ext\]/Handler/web.config. Para configurar el límite de carga de tamaño de archivo para Lync Web App, actualice `maxRequestLength` y `maxAllowedContentLength` en el archivo web.config que se muestra a continuación.

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

Debe actualizar el archivo web.config para cada Servidor front-end.

## Servidor Office Web Apps

Para usar nuevas capacidades los administradores deben instalar Servidor Office Web Apps y deben configurar Lync Server 2013 para comunicarse con Servidor Office Web Apps. Esta documentación ofrece información acerca de cómo configurar Lync Server 2013 para que trabaje con Servidor Office Web Apps. Lo que esta documentación no ofrece es información acerca de cómo instalar Servidor Office Web Apps. Para obtener detalles de instalación, vea el sitio web de implementación de aplicación web de Microsoft Office en <http://go.microsoft.com/fwlink/?linkid=257525>. Esa guía incluye información completa de requisitos previos para Servidor Office Web Apps. Tenga en cuenta que se debe instalar Servidor Office Web Apps en un equipo independiente que no está ejecutando Lync Server, SQL Server, o cualquier otra aplicación de servidor. (No debe tener ninguna versión de Office instalada en dicho equipo.) Cualquier equipo usado para ejecutar Servidor Office Web Apps también debe tener un conjunto específico de software instalado (incluido .NET Framework 4.5 y Windows PowerShell 3.0). Estos requisitos, junto con información acerca de la configuración de certificados y Servicios de Internet Information Server (IIS), se tratan detenidamente en el sitio web de implementación de aplicaciones web de Microsoft Office en <http://go.microsoft.com/fwlink/?linkid=257525>.

## Vea también

#### Conceptos

[Información general sobre la conferencia web en Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Lista de comprobaciones para la implementación de conferencias web en Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)

