---
title: Lync Server 2013 lista de comprobación para la implementación de conferencias web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0085f2990d2541c27392d52143ff69b4fb4711bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lista de comprobación para la implementación de conferencias web en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Al igual que con la implementación de los otros componentes de Lync Server 2013, la implementación de la conferencia web requiere que use el generador de topologías para crear y publicar una topología que incorpore conferencias.

<div>

## <a name="deployment-sequence"></a>Secuencia de implementación

Puede implementar las conferencias al mismo tiempo que implementa la topología inicial o después de haber implementado al menos un grupo de servidores front-end o un servidor Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Proceso de implementación de la característica de conferencia

En la siguiente tabla se ofrece información general sobre los pasos necesarios para implementar la característica de conferencia en una topología existente.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Roles y pertenencia a grupos</th>
<th>Documentación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instale el hardware y el software necesario como requisito previo</strong></p></td>
<td><p>Las conferencias se ejecutan en los servidores front-end de un grupo de servidores front-end y servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.</p>
<div>

> [!NOTE]  
> Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y la representación de presentaciones de PowerPoint. Para obtener información sobre la instalación y la configuración de Office Web Apps Server, vea <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring Integration with Office Web Apps Server and Lync server 2013</A>.


</div></td>
<td><p>Usuario de dominio miembro del grupo Administradores locales</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinación de los requisitos del sistema para Lync Server 2013</a> en la documentación referente a la planeación.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para el archivado en Lync Server 2013</a> en la documentación referente a la planeación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir conferencias</strong></p></td>
<td><p>Ejecute el generador de topologías para agregar conferencias a la topología y, a continuación, publique la topología.</p></td>
<td><p>Para definir una topología, debe usarse una cuenta que sea miembro del grupo Usuarios local</p>
<p>Para publicar la topología, una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para su uso en el almacén de archivos de Lync Server 2013 (para que el generador de topologías pueda configurar las DACL necesarias)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Defina y configure una topología en el generador de topologías para Lync Server 2013</a> en la documentación sobre implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar compatibilidad y directivas de conferencia</strong></p></td>
<td><p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar las opciones de conferencia.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asignar usuarios al rol [] o CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Directivas de conferencia en Lync Server 2013</a> en la documentación de operaciones.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 ahora incluye la configuración **MaxUploadFileSizeMb** , que limita el tamaño de los archivos que se pueden cargar durante una reunión. El valor predeterminado de esta opción es 500 MB. Puede ajustar **MaxUploadFileSizeMb** usando el cmdlet **Set-CsConferencingConfiguration**.

**MaxUploadFileSizeMb** no limita la configuración de carga de archivos para Lync Web App. El límite de carga de tamaño de archivo para Lync Web App se establece en aproximadamente 30 MB y se controla mediante el archivo Web.\[config\]de IIS:/DataCollabWeb/int ext/handler/Web.config. Para configurar el límite de carga de tamaño de archivo para Lync Web `maxRequestLength` APP `maxAllowedContentLength` , actualice y en el archivo Web. config tal como se muestra a continuación.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Debe actualizar el archivo Web. config para cada servidor front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

