---
title: Proceso de implementación de la respuesta de llamadas en grupo
TOCTitle: Proceso de implementación de la respuesta de llamadas en grupo
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945615(v=OCS.15)
ms:contentKeyID: 52061587
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación de la respuesta de llamadas en grupo

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describe de forma general el proceso necesario para implementar la atención de llamadas grupales. Debe implementar Enterprise Edition o Standard Edition con Telefonía IP empresarial antes de configurar la atención de llamadas grupales. Los componentes requeridos por la atención de llamadas grupales se instalan y habilitan al implementar Telefonía IP empresarial.

### Proceso de implementación de la atención de llamadas grupales

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
<td><p>Habilitar las herramientas del kit de recursos de SEFAUtil en la topología</p></td>
<td><ol>
<li><p>Use el cmdlet <strong>New-CsTrustedApplicationPool</strong> para crear un nuevo grupo de aplicaciones de confianza.</p></li>
<li><p>Use el cmdlet <strong>New-CsTrustedApplication</strong> para especificar la herramienta SEFAUtil como una aplicación de confianza.</p></li>
<li><p>Ejecute el cmdlet <strong>Enable-CsTopology</strong> para habilitar la topología.</p></li>
<li><p>Instale las herramientas del kit de recursos en un Servidor front-end que se encuentre en el grupo de aplicaciones de confianza creado en el paso 1.</p></li>
<li><p>Compruebe que SEFAUtil se esté ejecutando correctamente; para ello, ejecútelo para mostrar la configuración de desvío de llamadas de un usuario de la implementación.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Implementar la herramienta SEFAUtil</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar los intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas</p></td>
<td><p>Use el cmdlet <strong>New-CSCallParkOrbit</strong> para crear intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas y asígneles el tipo GroupPickup.</p>
<div>

> [!NOTE]
> Debe usar Shell de administración de Lync Server para crear, modificar, quitar y ver intervalos de números de atención de llamadas grupales en la tabla de órbitas de estacionamiento de llamadas. Los intervalos de números de atención de llamadas grupales no están disponibles en Panel de control de Lync Server.


</div>
<div>

> [!NOTE]
> A fin de lograr una integración sin fisuras con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales. En la tabla de órbitas de estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de intervalo.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar los números de grupo de respuesta de llamadas</a></p></td>
</tr>
<tr class="odd">
<td><p>Asignar a los usuarios un número de atención de llamadas y habilitar la atención de llamadas grupales</p></td>
<td><p>Use el parámetro /enablegrouppickup de las herramientas del kit de recursos de SEFAUtil para habilitar la atención de llamadas grupales y asignar a los usuarios un número de atención de llamadas.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar la respuesta de llamadas en grupo para los usuarios y asignar un número de grupo</a></p></td>
</tr>
<tr class="even">
<td><p>Notificar a los usuarios el número de atención de llamadas que se les ha asignado y cualquier otro número de interés</p></td>
<td><p>Puesto que cualquier usuario puede recuperar una llamada realizada a un usuario de la atención de llamadas grupales, es posible que los usuarios deseen supervisar más de un grupo.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar asignaciones de respuesta de llamadas en grupo a los usuarios</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobar la implementación de la atención de llamadas grupales</p></td>
<td><p>Realice pruebas de llamadas y recuperación de llamadas para asegurarse de que la configuración funcione del modo deseado.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Opcional) Comprobar la implementación de la respuesta de llamadas en grupo</a></p></td>
</tr>
</tbody>
</table>

