---
title: 'Lync Server 2013: proceso de implementación para la recogida de llamadas grupales'
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
ms.openlocfilehash: 015aa2817b7d829d1714288182775b42ba2bb1f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Proceso de implementación para la recogida de llamadas grupales en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

Esta sección proporciona una descripción general de los pasos implicados en la implementación de la recogida de llamadas grupales. Debe implementar Enterprise Edition o Standard Edition con telefonía IP empresarial antes de configurar la recogida de llamadas grupales. Los componentes requeridos por la recogida de llamadas grupales se instalan y se habilitan al implementar la telefonía IP empresarial.

### <a name="group-call-pickup-deployment-process"></a>Proceso de implementación de la atención de llamadas grupales

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
<li><p>Use el cmdlet <strong>New-CsTrustedApplication</strong> para especificar la herramienta SEFAUtil como una aplicación de confianza.</p></li>
<li><p>Ejecute el cmdlet <strong>Enable-CsTopology</strong> para habilitar la topología.</p></li>
<li><p>Instale las herramientas del kit de recursos en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza creado en el paso 1.</p></li>
<li><p>Compruebe que SEFAUtil se esté ejecutando correctamente; para ello, ejecútelo para mostrar la configuración de desvío de llamadas de un usuario de la implementación.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar los intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas</p></td>
<td><p>Use el cmdlet <strong>New-CSCallParkOrbit</strong> para crear rangos de números de recopilación de llamadas en la tabla llamada en órbita de la llamada y asignar a los intervalos de recogida de llamadas el tipo GroupPickup.</p>
<div>

> [!NOTE]  
> Debe usar el shell de administración de Lync Server para crear, modificar, quitar y ver los intervalos de números de recogida de llamadas grupales en la tabla de llamadas en órbita de estacionamiento. Los intervalos de números de recogida de llamadas grupales no están disponibles en el panel de control de Lync Server.


</div>
<div>

> [!NOTE]  
> A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de intervalo.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar números de grupo de recogida de llamadas en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Asignar un número de llamada a los usuarios y habilitar la recogida de llamadas grupales para los usuarios</p></td>
<td><p>Use el parámetro/enablegrouppickup en la herramienta del kit de recursos de SEFAUtil para habilitar la recogida de llamadas grupales y asignar un número de llamada para los usuarios.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo</a></p></td>
</tr>
<tr class="even">
<td><p>Notificar a los usuarios el número de atención de llamadas que se les ha asignado y cualquier otro número de interés</p></td>
<td><p>Como cualquier usuario puede recuperar una llamada realizada a un usuario de llamada grupal de grupo, es posible que los usuarios deseen supervisar más de un grupo.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar las tareas de recogida de llamadas grupales a los usuarios en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificar la implementación de la recogida de llamadas grupales</p></td>
<td><p>Realice pruebas de llamadas y recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Faculta Comprobar la implementación de la llamada grupal en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

