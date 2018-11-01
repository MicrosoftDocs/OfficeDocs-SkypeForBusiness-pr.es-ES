---
title: "Lync Server 2013: Implementación de conferencias de acceso telefónico local"
TOCTitle: Lista de comprobación para la implementación de las conferencias de acceso telefónico local
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48276218
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobación para la implementación de las conferencias de acceso telefónico local en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los componentes necesarios para conferencias de acceso telefónico local se implementan al implementar la carga de trabajo de conferencias. Para poder configurar la conferencia de acceso telefónico local, también debe implementar Telefonía IP empresarial o un Servidor de mediación y una puerta de enlace de red pública conmutada (RTC).

Todos los pasos indicados en la tabla siguiente deben realizarse antes de que los usuarios puedan obtener acceso telefónico desde la RTC para unirse a una conferencia de audio y vídeo.


> [!NOTE]
> Si migra desde Office Communications Server 2007 R2, debe aplicar como mínimo el paquete 5 de la actualización acumulativa (CU5) a su entorno de Office Communications Server 2007 R2 antes de implementar la conferencia de acceso telefónico local.



### Proceso de implementación de conferencia de acceso telefónico local

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
<td><p><strong>Crear una topología que incluya la carga de trabajo de conferencias, incluido un Servidor de mediación y una puerta de enlace RTC e implementar el Grupo de servidores front-end o el Servidor Standard Edition.</strong></p></td>
<td><ol>
<li><p>Ejecute la Generador de topologías para configurar su topología. Mientras configura la topología, seleccione la opción de conferencia de acceso telefónico local.</p></li>
<li><p>Publique la topología e implemente el Grupo de servidores front-end o el Servidor Standard Edition.</p></li>
<li><p>Si es preciso, cree un Servidor de mediación independiente y asócielo a una puerta de enlace RTC.</p>
<div>

> [!NOTE]
> Solo es necesario realizar este paso si no implementa Telefonía IP empresarial y no coloca el Servidor de mediación con el Enterprise EditionServidor front-end o el Servidor Standard Edition. Si implementa Telefonía IP empresarial, instalará y configurará los Servidores de mediación y las puertas de enlace RTC como parte de la implementación de Telefonía IP empresarial. Si coloca el Servidor de mediación, instalará y configurará el Servidor de mediación como parte de la implementación del Grupo de servidores front-end o del Servidor Standard Edition.


</div></li>
</ol></td>
<td><p>Administradores de dominio</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrador</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></p></li>
<li><p>Para crear un Grupo de servidores de mediación independiente: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configurar planes de marcado</strong></p></td>
<td><p>Un plan de marcado es un conjunto de reglas de normalización de números de teléfono que convierten los números de teléfono marcados desde una ubicación determinada a un formato estándar único (E.164) para la autorización telefónica y el enrutamiento de llamadas. El mismo número de teléfono marcado desde diferentes ubicaciones puede, basándose en los respectivos planes de marcado, resolverse en diferentes números E.164, según cada ubicación. Si implementa Telefonía IP empresarial, definirá planes de marcado que formarán parte de dicha implementación, y por tanto debe asegurarse de que los planes de marcado también admiten las conferencias de acceso telefónico local. Si no implementa Telefonía IP empresarial, deberá definir planes de marcado para conferencias de acceso telefónico local.</p>
<p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para definir planes de marcado tal y como se indica a continuación:</p>
<ol>
<li><p>Cree uno o más planes de marcado para enrutar números de teléfono de acceso.</p></li>
<li><p>Asigne un plan de marcado predeterminado a cada grupo de servidores. Defina <strong>Región de conferencia de acceso telefónico local</strong> en la ubicación geográfica a la que debe aplicarse el plan de marcado. La región asocia el plan de marcado con números de acceso telefónico.</p></li>
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
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Asegurarse de que los planes de marcado de Lync Server 2013 tienen regiones asignadas</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Comprobar o modificar los requisitos del número de identificación personal de los usuarios (PIN)</strong></p></td>
<td><p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para ver o modificar la <strong>directiva de PIN</strong> de conferencias. Puede especificar la longitud mínima del PIN, el número máximo de intentos de inicio de sesión, la expiración del PIN y si es posible usar patrones comunes.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Opcional) Comprobar la configuración de la directiva de PIN en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar la directiva de conferencias para admitir conferencias de acceso telefónico local</strong></p></td>
<td><p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para configurar las opciones de <strong>Directiva de conferencias</strong> . Especifique si:</p>
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
<td><p><strong>Configurar números de acceso telefónico</strong></p></td>
<td><p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para definir números de acceso telefónico que los usuarios marcan para obtener acceso a una conferencia, y especifique las regiones que asocian el número de acceso con los planes de marcado pertinentes. Los tres primeros números de acceso de la región especificada por el plan de marcado del organizador se incluyen en la invitación a la conferencia. Todos los números de acceso están disponibles en la Página Configuración de conferencia de acceso telefónico local.</p>
<div>

> [!NOTE]
> Una vez creados los números de acceso telefónico, puede usar el cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar de los objetos de contacto de Active Directory, de modo que los usuarios puedan identificar con mayor facilidad el número de acceso correcto.


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
<td><p>Use el cmdlet <strong>Set-CsDialinConferencingDtmfConfiguration</strong> para modificar las teclas usadas para comandos de tono de marcado de frecuencia múltiple (DTMF) que los participantes pueden usar para controlar la configuración de la conferencia (como activar y desactivar el audio o bloquear y desbloquear la conferencia).</p></td>
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
<td><p><strong>Implemente el Complemento para conferencia en línea para Lync 2013</strong></p></td>
<td><p>Implemente el Complemento para conferencia en línea para Lync 2013 para que los usuarios puedan programar conferencias que admitan conferencias de acceso telefónico local. El Complemento para conferencia en línea para Lync 2013 se instala automáticamente al instalar Lync 2013</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Implementar el complemento de conferencia en línea para Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configurar la cuenta de usuario</strong></p></td>
<td><p>Use el Panel de control de Lync Server 2013 o el Shell de administración de Lync Server para configurar el <strong>URI de línea</strong> de telefonía como un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Configurar la cuenta de usuario en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Recomendado) Configurar directorios de conferencia</p></td>
<td><p>Utilice el cmdlet <strong>New-CsConferenceDirectory</strong> para crear un directorio de conferencia para cada 999 usuarios del grupo.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Planeación de las conferencias de acceso telefónico local en Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recomendado) Crear directorios de conferencia</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Opcional) Dar la bienvenida a los usuarios a la conferencia de acceso telefónico local y definir el PIN inicial</strong></p></td>
<td><p>Use el script <strong>Set-CsPinSendCAWelcomeMail</strong> para definir los PIN iniciales de los usuarios y enviar un correo electrónico de bienvenida que contengan el PIN inicial y un vínculo a la Página Configuración de conferencia de acceso telefónico local.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Opcional) Dar la bienvenida a los usuarios de la conferencia de acceso telefónico local en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

