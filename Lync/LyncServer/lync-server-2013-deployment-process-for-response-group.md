---
title: 'Lync Server 2013: proceso de implementación para el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Proceso de implementación para un grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-27_

Esta sección proporciona una descripción general de las fases y los pasos necesarios para implementar la aplicación de grupo de respuesta.

### <a name="response-group-deployment-process"></a>Proceso de implementación de grupos de respuesta

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
<td><p>Instalar la aplicación de grupo de respuesta</p></td>
<td><p>La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implementación de telefonía IP empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Instalar componentes para grupo de respuesta</p></td>
<td><p>Los cmdlets de Lync Server, el panel de control de Lync Server, la herramienta de configuración de grupos de respuesta, la consola de inicio de sesión y cierre de sesión de los agentes y el servicio Web cliente de grupo de respuesta se instalan como parte de los servicios Web. Los servicios web se instalan al implementar un grupo de servidores Enterprise Edition o un servidor Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilitar usuarios para Lync 2013 y para telefonía IP empresarial</p></td>
<td><p>Habilitar usuarios que serán agentes de Lync Server y Enterprise Voice. Estos usuarios necesitan estar habilitados para agregarlos a grupos de agentes. Normalmente, los usuarios están habilitados para Lync Server durante la implementación de servidor Standard Edition o Enterprise Edition. Los usuarios están habilitados para telefonía IP empresarial durante la implementación de telefonía IP empresarial.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Crear y configurar grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo</p></td>
<td><ol>
<li><p>Use el panel de control de Lync Server o el shell de administración de Lync Server para hacer lo siguiente:</p>
<ol>
<li><p>Crear y configurar grupos de respuesta</p></li>
<li><p>Crear y configurar colas</p></li>
</ol></li>
<li><p>De manera opcional, use el shell de administración de Lync Server para crear vacaciones y días laborables de grupo de respuesta predefinidos.</p></li>
<li><p>Use la herramienta de configuración de grupos de respuesta o el shell de administración de Lync Server para crear flujos de trabajo (grupos de captura o flujos de llamada de voz interactiva (IVR), incluidos los días laborables y las horas laborables de grupo de respuesta personalizado.</p>
<div>

> [!NOTE]  
> Puede acceder a la herramienta de configuración de grupos de respuesta a través del panel de control de Lync Server.


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
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Faculta Definir las horas de trabajo del grupo de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Faculta Definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Crear o modificar un flujo de trabajo en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Opcional) Personalizar la configuración de la aplicación</p></td>
<td><p>Use el shell de administración de Lync Server para personalizar la configuración predeterminada de música en espera, el archivo de audio de música activa predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Administrar la configuración de grupo de respuesta de nivel de aplicación en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Opcional) Delegar la administración de los grupos de respuesta</p></td>
<td><p>Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de grupos de respuesta. Los administradores de grupos de respuesta pueden configurar los grupos de respuesta que tienen asignados.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobar la implementación del grupo de respuesta</p></td>
<td><p>Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

