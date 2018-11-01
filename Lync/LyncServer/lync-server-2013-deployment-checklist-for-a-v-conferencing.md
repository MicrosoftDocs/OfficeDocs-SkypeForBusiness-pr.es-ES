---
title: "Implementar la lista de comprobación para conferencias de A/V en Lync Server 2013"
TOCTitle: "Liste de vérif. du déploiement pour la conférence A/V dans Lync Server 2013"
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49115292
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de la lista de comprobación para conferencias de A/V en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Al igual que con la implementación de los otros componentes de Lync Server 2013, para implementar la característica de conferencia A/V es necesario que utilice Generador de topologías para crear y publicar una topología que incorpore conferencias.

## Secuencia de implementación

Puede implementar la característica de conferencias a la vez que implementa la topología inicial o después de haber implementado, como mínimo, menos un Grupo de servidores front-end o un Servidor Standard Edition.

## Proceso de implementación de la característica de conferencia

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
<td><p>Las conferencias se ejecutan en Servidores front-end de un Grupo de servidores front-end y en Servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.</p>
<div>

> [!NOTE]
> Lync Server 2013 usa Office Web Apps y el Servidor Office Web Apps para administrar el uso compartido y la exposición de presentaciones de PowerPoint. Para más detalles sobre la instalación y la configuración del Servidor Office Web Apps, vea <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuración de la integración de Office Web Apps Server y Lync Server 2013</A>.


</div></td>
<td><p>Usuario de dominio miembro del grupo Administradores locales</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware admitido en Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a> en la documentación sobre planeación</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para archivado en Lync Server 2013</a> en la documentación sobre planeación</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir conferencias</strong></p></td>
<td><p>Ejecute el Generador de topologías para agregar conferencias a la topología y publique la topología.</p></td>
<td><p>Para definir una topología, debe usarse una cuenta que sea miembro del grupo Usuarios local</p>
<p>Para publicar la topología, debe usarse una cuenta que sea miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control completos (lectura/escritura/modificación) en el almacén de archivos de Lync Server 2013 (de modo que el Generador de topologías pueda configurar las listas de control de acceso discrecional (DACL) necesarias)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definir y configurar una topología en Topology Builder para Lync Server 2013</a> en la documentación sobre implementación</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar compatibilidad y directivas de conferencia</strong></p></td>
<td><p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para configurar los ajustes de conferencia.</p></td>
<td><p>Se necesita el grupo RTCUniversalServerAdmins (solo de Windows PowerShell) o asignar usuarios a [] o el rol CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Directivas de conferencia de Lync Server 2013</a> en la documentación sobre operaciones</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Otros recursos

[Información general sobre conferencias en Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Definición de requisitos para conferencias en Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

