---
title: 'Lync Server 2013: Proceso de implementación para grupos de respuesta'
TOCTitle: Proceso de implementación para grupos de respuesta
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48276780
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de implementación para grupos de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describe de forma general el proceso necesario para implementar la Aplicación de grupo de respuesta.

### Proceso de implementación de grupos de respuesta

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
<th>Permisos</th>
<th>Documentación de implementación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Instalación de la Aplicación de grupo de respuesta</p></td>
<td><p>La Aplicación de grupo de respuestase instala y activa cuando implementa Telefonía IP empresarial.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Instalación de los componentes para el Grupo de respuesta</p></td>
<td><p>Los cmdlets de Lync Server, el Panel de control de Lync Server, la Herramienta de configuración de grupo de respuesta, la consola de inicio de sesión y de cierre de sesión de los agentes, y el servicio web de grupo de respuesta se instalan como parte de los servicios web. Los servicios web se instalan cuando implementa un grupo de servidores Enterprise Edition o un Servidor Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilitación de usuarios para Lync 2013 y para Telefonía IP empresarial</p></td>
<td><p>Habilite los usuarios que van a ser agentes de Lync Server y de Telefonía IP empresarial. Los usuarios deben estar habilitados para agregarlos a grupos de agentes. En general, los usuarios quedan habilitados para Lync Server al implementarEnterprise Edition o Servidor Standard Edition. Los usuarios quedan habilitados para Telefonía IP empresarial durante la implementación de Telefonía IP empresarial.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Creación y configuración de grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo</p></td>
<td><ol>
<li><p>Use los cmdlets Panel de control de Lync Server o Shell de administración de Lync Server para efectuar las acciones siguientes:</p>
<ol>
<li><p>Crear y configurar grupos de respuesta</p></li>
<li><p>Crear y configurar colas</p></li>
</ol></li>
<li><p>Opcionalmente, use Shell de administración de Lync Server para crear horas laborables y vacaciones para el grupo de respuesta predefinido.</p></li>
<li><p>Use los cmdlets Herramienta de configuración de grupo de respuesta o Shell de administración de Lync Server para configurar flujos de trabajo (grupos de búsqueda o flujos de llamadas de respuesta de voz interactiva o IVR), con el horario laboral y los días de vacaciones de los grupos de respuesta.</p>
<div>

> [!NOTE]
> Puede obtener acceso a la Herramienta de configuración de grupo de respuesta con Panel de control de Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>AdministradorGrupoRespuestaCs</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Crear grupos de agentes de grupos de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Crear colas de grupo de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Opcional) Definir horarios laborales de grupos de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Opcional) Definición de conjuntos de días festivos para grupos de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Creación o modificación de un flujo de trabajo en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Opcional) Personalización de la configuración de nivel de aplicación</p></td>
<td><p>Use Shell de administración de Lync Server para personalizar la configuración de música en espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada del agente y la configuración del contexto de la llamada.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Administración de la configuración de grupos de respuesta a nivel de aplicación en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Opcional) Delegación de la administración de los grupos de respuesta</p></td>
<td><p>Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de los grupos de respuesta. Así, los administradores de Grupo de respuesta podrán configurar los grupos de respuesta que tengan asignados.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobación de la implementación del grupo de respuesta</p></td>
<td><p>Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>

