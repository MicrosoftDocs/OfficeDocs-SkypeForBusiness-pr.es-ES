---
title: "Lista de comprobación para la implementación de conferencias web en Lync Server 2013"
TOCTitle: "Liste de vérif. du déploiement pour la conférence web dans Lync Server 2013"
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48276105
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobaciones para la implementación de conferencias web en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Al igual que con la implementación de los componentes de Lync Server 2013, la implementación de la conferencia web requiere el uso del Generador de topologías para crear y publicar una topología que incorpore conferencias.

## Secuencia de implementación

Puede implementar una conferencia a la vez que implementa su topología inicial o después de haber implementado, como mínimo, un Grupo de servidores front-end o Servidor Standard Edition.

## Proceso de implementación de conferencias

En la siguiente tabla se ofrece información general sobre los pasos necesarios para implementar una conferencia en una topología existente.


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
<td><p>Las conferencias se ejecutan en Servidores front-end, en un Grupo de servidores front-end y en Servidores Standard Edition. No requiere ningún hardware o software adicional más allá de los necesarios para instalar estos servidores.</p>
<div>

> [!NOTE]
> Lync Server 2013 usa Office Web Apps y el Servidor Office Web Apps para administrar el uso compartido y la representación de presentaciones de PowerPoint. Para obtener más información acerca de cómo instalar y configurar el Servidor Office Web Apps, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuración de la integración de Office Web Apps Server y Lync Server 2013</A>.


</div></td>
<td><p>Usuario de dominio miembro del grupo Administradores locales</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware admitido en Lync Server 2013</a> en la documentación referente a la compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación referente a la compatibilidad</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a> en la documentación referente a la planificación.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para archivado en Lync Server 2013</a> en la documentación referente a la planificación.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir la conferencia</strong></p></td>
<td><p>Ejecute el Generador de topologías para agregar una conferencia a la topología y, luego, publique la topología.</p></td>
<td><p>Para definir una topología, una cuenta que sea miembro del grupo Usuarios locales</p>
<p>Para publicar la topología, debe usarse una cuenta que sea miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control completos (lectura/escritura/modificación) en el uso compartido de archivos para el almacén de archivos de Lync Server 2013 (de modo que el Generador de topologías pueda configurar las DACL necesarias)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definir y configurar una topología en Topology Builder para Lync Server 2013</a> en la documentación referente a la implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar compatibilidad y directivas para conferencias</strong></p></td>
<td><p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para configurar las opciones de conferencias.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne usuarios al rol [] o CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Directivas de conferencia de Lync Server 2013</a> en la documentación referente a la implementación .</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 ahora incluye la opción **MaxUploadFileSizeMb**, que limita el tamaño de los archivos que se pueden cargar durante una reunión. El valor predeterminado de esta opción es 500 MB. Puede ajustar **MaxUploadFileSizeMb** usando el cmdlet **Set-CsConferencingConfiguration**.

**MaxUploadFileSizeMb** no limita el valor de carga de archivos de Lync Web App. El límite de carga de tamaño de archivo para Lync Web App es de 30 MB aproximadamente y se controla mediante el archivo web.config de IIS: /DataCollabWeb/Int\[Ext\]/Handler/web.config. Para configurar el límite de carga de tamaño de archivo para Lync Web App, actualice `maxRequestLength` y `maxAllowedContentLength` en el archivo web.config como se muestra a continuación.

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

Debe actualizar el archivo web.config para cada Servidor front-end.

