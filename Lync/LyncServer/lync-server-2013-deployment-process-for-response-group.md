---
title: 'Lync Server 2013: proceso de implementación de grupo de respuesta'
description: 'Lync Server 2013: proceso de implementación de grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b50fb7903a2fcc301bbf435013b8f8df4e775a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551036"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Proceso de implementación del grupo de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-27_

En esta sección se proporciona información general sobre las fases y los pasos necesarios para implementar la aplicación grupo de respuesta.

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
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Instalación de componentes para el grupo de respuesta</p></td>
<td><p>Los cmdlets de Lync Server, el panel de control de Lync Server, la herramienta de configuración de grupos de respuesta, la consola de inicio y de cierre de sesión de los agentes y el servicio Web de cliente del grupo de respuesta se instalan como parte de los servicios Web. Los servicios web se instalan al implementar un grupo de Enterprise Edition o un servidor Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilitar usuarios para Lync 2013 y Enterprise Voice</p></td>
<td><p>Habilite a los usuarios que van a ser agentes para Lync Server y Enterprise Voice. Los usuarios deben estar habilitados antes de poder agregarlos a grupos de agentes. Normalmente, los usuarios están habilitados para Lync Server durante la implementación de servidor Standard Edition o Enterprise Edition. Los usuarios están habilitados para telefonía IP empresarial durante la implementación de la telefonía IP empresarial.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Creación y configuración de grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo</p></td>
<td><ol>
<li><p>Use el panel de control de Lync Server o el shell de administración de Lync Server para hacer lo siguiente:</p>
<ol>
<li><p>Crear y configurar grupos de respuesta</p></li>
<li><p>Crear y configurar colas</p></li>
</ol></li>
<li><p>De forma opcional, use el shell de administración de Lync Server para crear días laborables y horas laborables para el grupo de respuesta predefinido.</p></li>
<li><p>Use la herramienta de configuración del grupo de respuesta o el shell de administración de Lync Server para crear flujos de trabajo (grupos de extensiones o flujos de llamadas de respuesta de voz interactiva (IVR), incluido el horario laboral del grupo de respuesta personalizado y los días festivos.</p>
<div>

> [!NOTE]  
> Puede obtener acceso a la herramienta de configuración del grupo de respuesta a través del panel de control de Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Crear grupos de agentes de grupo de respuesta Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Crear colas de grupo de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Crear o modificar un flujo de trabajo en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Opcional) Personalización de la configuración de nivel de aplicación</p></td>
<td><p>Use el shell de administración de Lync Server para personalizar la configuración predeterminada de la música en espera, el archivo de audio de música en espera predeterminado, el período de gracia de timbre del agente y la configuración del contexto de llamada.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Administración de la configuración del grupo de respuesta de nivel de aplicación en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Opcional) Delegación de la administración de los grupos de respuesta</p></td>
<td><p>Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de los grupos de respuesta. A continuación, los administradores del grupo de respuesta pueden configurar los grupos de respuesta que tienen asignados.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Comprobación del grupo de respuesta</p></td>
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

