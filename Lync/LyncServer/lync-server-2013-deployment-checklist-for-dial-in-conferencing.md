---
title: 'Lync Server 2013: Lista de comprobación para la implementación de las conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf496dcb24c021246bfbb6e7a5ef7b3a3a5acc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lista de comprobación para la implementación de las conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-03_

Los componentes necesarios para las conferencias de acceso telefónico local se implementan al implementar la carga de trabajo de las conferencias. Para poder configurar las conferencias de acceso telefónico local, debe implementar la telefonía IP empresarial o un servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC).

Todos los pasos de la tabla siguiente deben realizarse antes de que los usuarios puedan llamar desde la RTC para unirse a una conferencia de audio o vídeo.

<div>


> [!NOTE]  
> Si va a migrar desde Office Communications Server 2007 R2, debe aplicar las actualizaciones más recientes al entorno de Office Communications Server 2007 R2 antes de implementar la Conferencia de acceso telefónico local.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Proceso de implementación de conferencias de acceso telefónico local

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
<td><p><strong>Crear una topología que incluya la carga de trabajo de las conferencias, incluido un servidor de mediación y una puerta de enlace RTC, e implementar el grupo de servidores front-end o el servidor Standard Edition</strong></p></td>
<td><ol>
<li><p>Ejecute el generador de topología para configurar su topología. Mientras configura la topología, seleccione la opción de conferencia de acceso telefónico local.</p></li>
<li><p>Publicar la topología e implementar el grupo de servidores front-end o el servidor Standard Edition.</p></li>
<li><p>Si es necesario, cree un servidor de mediación independiente y asócielo con una puerta de enlace RTC.</p>
<div>

> [!NOTE]  
> Este paso solo es necesario si no implementa la telefonía IP empresarial y no Collocate el servidor de mediación con el servidor Standard Edition o Enterprise EditionFront end. Si implementa la telefonía IP empresarial, instale y configure los servidores de mediación y las puertas de enlace RTC como parte de la implementación de telefonía IP empresarial. Si Collocate el servidor de mediación, debe instalar y configurar el servidor de mediación como parte de la implementación del grupo de servidores front-end o del servidor Standard Edition.


</div></li>
</ol></td>
<td><p>Administradores de dominio</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrador</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></p></li>
<li><p>Para crear un grupo de servidores de mediación independiente: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">implementar servidores de mediación y definir pares en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial plans</strong></p></td>
<td><p>Un plan de marcado es un conjunto de reglas de normalización de números de teléfono que convierten los números de teléfono marcados desde una ubicación determinada a un formato estándar único (E.164) para la autorización telefónica y el enrutamiento de llamadas. El mismo número de teléfono marcado desde diferentes ubicaciones puede, basándose en los respectivos planes de marcado, resolverse en diferentes números E.164, según cada ubicación. Si implementa la telefonía IP empresarial, configurará planes de marcado como parte de esa implementación y tendrá que asegurarse de que los planes de marcado también admitan las conferencias de acceso telefónico local. Si no implementa la telefonía IP empresarial, debe configurar los planes de marcado para las conferencias de acceso telefónico local.</p>
<p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar los planes de marcado de la siguiente manera:</p>
<ol>
<li><p>Cree uno o más planes de marcado para enrutar números de teléfono de acceso.</p></li>
<li><p>Asigne un plan de marcado predeterminado a cada grupo de servidores. Establezca la <strong>Región de conferencia de acceso telefónico local</strong> en la ubicación geográfica a la que necesita aplicarse el plan de marcado. La región asocia el plan de marcado con números de acceso telefónico local.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Asegurarse de que los planes de marcado tengan regiones asignadas</strong></p></td>
<td><p>Ejecute los cmdlets <strong>Get-CsDialPlan</strong> y <strong>Set-CsDialPlan</strong> para garantizar que todos los planes de marcado tengan asignada una región.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Asegúrese de que los planes de marcado de Lync Server 2013 tienen regiones asignadas</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Comprobar o modificar los requisitos del número de identificación personal de los usuarios (PIN)</strong></p></td>
<td><p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para ver o modificar la <strong>Directiva de PIN</strong>de conferencia. Puede especificar la longitud mínima del PIN, el número máximo de intentos de inicio de sesión, la expiración del PIN y si es posible usar patrones comunes.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Opcional) Comprobar la configuración de la directiva de PIN en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar la directiva de conferencias para admitir conferencias de acceso telefónico local</strong></p></td>
<td><p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar la configuración de <strong>Directiva de conferencia</strong> . Especifique si:</p>
<ul>
<li><p>Está habilitado el acceso telefónico a conferencias por RTC.</p></li>
<li><p>Los usuarios pueden invitar a participantes anónimos.</p></li>
<li><p>Los usuarios no autenticados pueden unirse a una conferencia mediante llamadas de salida. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurar la directiva de conferencias para el acceso telefónico local en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial-in access numbers</strong></p></td>
<td><p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar los números de acceso telefónico local a los que los usuarios llaman para llamar a una conferencia y especificar las regiones que asocian el número de acceso a los planes de marcado adecuados. Los tres primeros números de acceso de la región especificada por el plan de marcado del organizador se incluyen en la invitación a la conferencia. Todos los números de acceso están disponibles en la página Configuración de conferencia de acceso telefónico local.</p>
<div>

> [!NOTE]  
> Después de crear los números de acceso telefónico local, puede usar el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar de los objetos de contacto de Active Directory, de modo que los usuarios puedan identificar más fácilmente el número de acceso correcto.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurar números de conferencia de acceso telefónico en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Opcional) Comprobar la configuración de conferencia de acceso telefónico local</strong></p></td>
<td><p>Use el cmdlet <strong>Get-CsDialinConferencingAccessNumber</strong> para buscar planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada ninguna región.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Opcional) Comprobar la configuración de conferencia de acceso telefónico local en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Modificar la asignación de teclas de comandos DTMF</strong></p></td>
<td><p>Use el cmdlet <strong>set-CsDialinConferencingDtmfConfiguration</strong> para modificar las teclas usadas para los comandos multifrecuencia de tono dual (DTMF), que los participantes pueden usar para controlar la configuración de la Conferencia (como desactivar y reactivar el audio o bloquear y desbloquear).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Opcional) Modificar la asignación de teclas para comandos DTMF en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Opcional) Modificar el comportamiento de los anuncios al unirse y abandonar conferencias</strong></p></td>
<td><p>Use el cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> para cambiar el funcionamiento de los anuncios cuando los participantes se unen a conferencias o las abandonan.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Opcional) Habilitar y deshabilitar los anuncios de participación y abandono de conferencias en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Comprobar la conferencia de acceso telefónico local</strong></p></td>
<td><p>Use el cmdlet <strong>Test-CsDialInConferencing</strong> para comprobar si los números de acceso del grupo de servidores especificado funcionan correctamente.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Opcional) Comprobar la conferencia de acceso telefónico local en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Implementar el complemento de conferencia en línea para Lync 2013</strong></p></td>
<td><p>Implementar el complemento de reunión en línea para Lync 2013 para que los usuarios puedan programar conferencias que admitan conferencias de acceso telefónico local. El complemento de reunión en línea para Lync 2013 se instala automáticamente al instalar Lync 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Implementar el complemento de conferencia en línea para Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurar una cuenta de usuario</strong></p></td>
<td><p>Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar el URI de la <strong>línea</strong> de telefonía como un número de teléfono normalizado único (por ejemplo, Tel: + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Configurar la cuenta de usuario en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Recomendado) Configurar directorios de conferencia</p></td>
<td><p>Use el cmdlet <strong>New-CsConferenceDirectory</strong> para crear un directorio de conferencia para cada 999 usuarios del grupo.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Requisitos de conferencia de acceso telefónico local en Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(recomendado) crear directorios de conferencia</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Dar la bienvenida a los usuarios a la conferencia de acceso telefónico local y definir el PIN inicial</strong></p></td>
<td><p>Use el script <strong>set-CsPinSendCAWelcomeMail</strong> para configurar los pines iniciales de los usuarios y enviar un correo electrónico de bienvenida que contenga el PIN inicial y un vínculo a la página de configuración de conferencia de acceso telefónico local.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Opcional) Dar la bienvenida a los usuarios de la conferencia de acceso telefónico local en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

