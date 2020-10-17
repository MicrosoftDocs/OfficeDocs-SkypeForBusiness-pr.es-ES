---
title: 'Lync Server 2013: proceso de implementación para la recogida de llamadas grupales'
description: 'Lync Server 2013: proceso de implementación para la recogida de llamadas grupales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552496"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Proceso de implementación para la recogida de llamadas grupales en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

En esta sección se proporciona información general sobre los pasos necesarios para implementar la recogida de llamadas de grupo. Debe implementar Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar la atención de llamadas grupales. Los componentes requeridos por la atención de llamadas grupales están instalados y habilitados al implementar la telefonía IP empresarial.

### <a name="group-call-pickup-deployment-process"></a>Proceso de implementación de recogida de llamadas grupales

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
<th>Grupos y roles necesarios</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Habilitar la herramienta del kit de recursos de SEFAUtil en la topología</p></td>
<td><ol>
<li><p>Use el cmdlet <strong>New-CsTrustedApplicationPool</strong> para crear un nuevo grupo de aplicaciones de confianza.</p></li>
<li><p>Use el cmdlet <strong>New-CsTrustedApplication</strong> para especificar la herramienta SEFAUtil como aplicación de confianza.</p></li>
<li><p>Ejecute el cmdlet <strong>enable-CsTopology</strong> para habilitar la topología.</p></li>
<li><p>Instale las herramientas del kit de recursos en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza creado en el paso 1.</p></li>
<li><p>Compruebe que SEFAUtil se está ejecutando correctamente; para ello, ejecute el para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Implementar la herramienta SEFAUtil en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar intervalos de números de llamada de llamadas en la tabla de órbitas de estacionamiento de llamadas</p></td>
<td><p>Use el cmdlet <strong>New-CSCallParkOrbit</strong> para crear intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas y asignar el tipo GroupPickup a los intervalos de recogida de llamadas.</p>
<div>

> [!NOTE]  
> Debe usar el shell de administración de Lync Server para crear, modificar, quitar y ver intervalos de números de llamada de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas. Los intervalos de números de llamada de grupo no están disponibles en el panel de control de Lync Server.


</div>
<div>

> [!NOTE]  
> Para la integración perfecta con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales. No se admite la asignación de números de llamada directa (DID) como números de intervalo en la tabla de órbitas de estacionamiento de llamadas.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar números de grupo de atención de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Asignar un número de llamada de llamada a los usuarios y habilitar la atención de llamadas grupales para los usuarios</p></td>
<td><p>Use el parámetro/enablegrouppickup de la herramienta del kit de recursos de SEFAUtil para habilitar la atención de llamadas grupales y asignar un número de llamada para los usuarios.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo</a></p></td>
</tr>
<tr class="even">
<td><p>Notificar a los usuarios el número de atención de llamadas que tienen asignado y cualquier otro número de interés</p></td>
<td><p>Como cualquier usuario puede recuperar una llamada realizada a un usuario de llamada de llamada de grupo, es posible que los usuarios deseen supervisar más de un grupo.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar las asignaciones de atención de llamadas grupales a los usuarios en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobar la implementación de llamada de grupo</p></td>
<td><p>Pruebe la colocación y recuperación de llamadas para asegurarse de que la configuración funciona como se esperaba.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opcional Comprobar la implementación de la llamada de grupo en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

