---
title: Lista de comprobación de implementación de Lync Server 2013 para conferencias A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d787cbc1e2bbefcc2cb125e64ab7143ddbd6cf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Lista de comprobación de implementación para conferencias A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Al igual que con la implementación de otros componentes de Lync Server 2013, la implementación de conferencias A/V requiere que use el generador de topología para crear y publicar una topología que incorpore conferencias.

<div>

## <a name="deployment-sequence"></a>Secuencia de implementación

Puede implementar conferencias al mismo tiempo que implementa su Topología inicial o después de haber implementado al menos un grupo de servidores front-end o un servidor Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Proceso de implementación de conferencia

En la tabla siguiente se proporciona una descripción general de los pasos necesarios para implementar las conferencias en una topología existente.


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
<th>Roles y pertenencias a grupos</th>
<th>Documentación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar los requisitos previos de hardware y software</strong></p></td>
<td><p>La Conferencia se ejecuta en servidores front-end de un grupo de servidores front-end y servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.</p>
<div>

> [!NOTE]  
> Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y el procesamiento de presentaciones de PowerPoint. Para obtener más información sobre cómo instalar y configurar el servidor de Office Web Apps, vea <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurar la integración con Office Web Apps Server y Lync server 2013</A>.


</div></td>
<td><p>Usuario de dominio miembro del grupo Administradores locales</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible con Lync Server 2013</a> en la documentación de soporte técnico</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Compatibilidad con el software de servidor y la infraestructura en Lync Server 2013</a> en la documentación de soporte técnico</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinar los requisitos del sistema para Lync Server 2013</a> en la documentación de planificación.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para archivar en Lync Server 2013</a> en la documentación de planeación.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir la conferencia</strong></p></td>
<td><p>Ejecute el generador de topología para agregar conferencias a la topología y, a continuación, publique la topología.</p></td>
<td><p>Para definir una topología, una cuenta que sea miembro del grupo Usuarios locales</p>
<p>Para publicar la topología, una cuenta que sea miembro del grupo administradores del dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para el almacén de archivos de Lync Server 2013 (para que topología pueda configurar las DACL obligatorias)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Defina y configure una topología en el generador de topologías para Lync Server 2013</a> en la documentación de implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar directivas de conferencia y soporte técnico</strong></p></td>
<td><p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar las opciones de conferencia.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asignar usuarios al rol [] o CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Directivas de conferencia en Lync Server 2013</a> en la documentación de operaciones.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Información general sobre conferencias en Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Definición de requisitos para conferencias en Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

