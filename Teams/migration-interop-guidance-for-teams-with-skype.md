---
title: 'Migración e interoperabilidad: Skype Empresarial'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Comprender los conceptos fundamentales para administrar la transición de su organización a Teams desde Skype Empresarial.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b03a31865504507db1c1b0da0fb9c30eb3e1444
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955927"
---
# <a name="coexistence-modes---reference"></a>Modos de coexistencia - Referencia

Los modos de coexistencia proporcionan una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones pasan de Skype Empresarial a Teams. En el caso de una organización que pase a Teams, el modo de TeamsOnly es el destino final de cada usuario, aunque no es necesario que todos los usuarios tengan asignados TeamsOnly (o cualquier modo) al mismo tiempo. Antes de que los usuarios alcancen el modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar una comunicación predecible entre los usuarios que son TeamsOnly y aquellos que aún no lo están.

Desde una perspectiva técnica, el modo de usuario rige varios aspectos de la experiencia del usuario:

- *Enrutamiento de entrada*: ¿en qué cliente (Teams o Skype Empresarial) llegan los chats y llamadas entrantes? 
- *Publicación de presencia*: ¿se muestra la presencia del usuario a otros usuarios en función de su actividad en Teams o Skype Empresarial? 
- *Programación de reuniones*: ¿qué servicio se usa para programar nuevas reuniones y asegurarse de que el complemento adecuado se encuentra en Outlook? TeamsUpgradePolicy no rige la unión a la reunión. Los usuarios siempre pueden *unirse* cualquier reunión, tanto si se trata de una reunión de Skype Empresarial como de una reunión Teams.
- *Experiencia del cliente*: ¿Qué funcionalidad está disponible en el cliente de Teams o de Skype Empresarial? ¿Los usuarios pueden iniciar llamadas y chats en Teams, Skype Empresarial o ambos? ¿La experiencia de equipos y canales está disponible?  

Para obtener más información sobre el enrutamiento y el comportamiento de presencia basado en el modo, vea [Coexistencia con Skype Empresarial.](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)

Sin embargo, desde una perspectiva de la experiencia, el modo puede describirse al definir la experiencia para:
- *Chat y llamadas*: ¿qué cliente usa un usuario?
- *Programación de reuniones*: ¿los usuarios pueden programar reuniones nuevas como reuniones de Teams o de Skype Empresarial?
- *La disponibilidad de las funciones de colaboración en el cliente de Teams*. ¿La funcionalidad de archivos, equipos y canales está disponible mientras los usuarios todavía tienen Skype Empresarial?

Los modos se muestran a continuación.
</br>
</br>

|Modo|Llamada y chat|Programación de reuniones<sup>1</sup>|Equipos y canales|Caso de uso|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Requiere inicio en Skype Empresarial Online*|Teams|Teams|Sí|Estado final de la actualización. También es el valor predeterminado para los nuevos espacios empresariales.|
|Aplicaciones aisladas|Ambos|Ambos|Sí|Configuración predeterminada. Permite a un solo usuario evaluar los dos clientes en paralelo. Los chats y las llamadas pueden llegar a cualquier cliente, de modo que los usuarios siempre deban ejecutar ambos clientes. Para evitar que su experiencia de uso de Skype Empresarial sea confusa o un retroceso, las comunicaciones externas (federadas), Skype Empresarial sigue manejando las comunicaciones externas (federadas), los servicios de voz PSTN y las aplicaciones de voz, la integración de Office y varias otras integraciones.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Empresarial|Teams|Sí|"Reuniones primero". Principalmente para que las organizaciones locales se beneficien de la funcionalidad de reunión de Teams, si aún no están listas para mover las llamadas a la nube.|
|SfBWithTeamsCollab|Skype Empresarial|Skype Empresarial|Sí|El punto de partida alternativo para las organizaciones complejas que necesitan un control administrativo más estricto.|
|SfBOnly|Skype Empresarial|Skype Empresarial|No<sup>3</sup>|Situación especializada para las organizaciones con requisitos estrictos en torno al control de datos. Teams se usa solo para unirse a reuniones programadas por otros usuarios.|
||||||

</br>
</br>

**Notas**:

<sup>1</sup> La posibilidad de unirse a una reunión existente (ya sea en Teams o en Skype Empresarial) no se rige por el modo. De forma predeterminada, los usuarios siempre podrán unirse a cualquier reunión a la que hayan sido invitados.

<sup>2</sup> de forma predeterminada, al asignar TeamsOnly o SfbWithTeamsCollabAndMeetings a un usuario individual, todas las reuniones de Skype Empresarial existentes programadas por ese usuario para el futuro se convierten en reuniones de Teams. Si lo desea, puede dejar estas reuniones como reuniones de Skype Empresarial al especificar `-MigrateMeetingsToTeams $false` al otorgar permisos de TeamsUpgradePolicy o anular la selección de la casilla en el portal de administración de Teams. La capacidad para convertir reuniones de Skype Empresarial a Teams no está disponible al conceder TeamsUpgradePolicy para todo el espacio empresarial. 

<sup>3</sup> en este momento, Teams no tiene la capacidad de deshabilitar la funcionalidad de equipos y canales, por lo que permanece habilitada por ahora.


## <a name="using-teamsupgradepolicy"></a>Using TeamsUpgradePolicy

TeamsUpgradePolicy muestra dos propiedades clave: NotifySfbUsers y modo. 
</br>
</br>

|Parámetro|Tipo|Valores permitidos</br>(valor predeterminado en cursiva)|Descripción|
|---|---|---|---|
|Modo|Enum|*Aplicaciones aisladas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica el modo en el que se debe ejecutar el cliente.|
|NotifySfbUsers|Booleano|*Falso* o verdadero|Indica si se muestra un banner en el cliente de Skype Empresarial para informar al usuario de que Teams reemplazarán pronto Skype Empresarial. Esto no puede ser verdadero si Mode=TeamsOnly.|
|||||

Teams proporciona todas las instancias relevantes de TeamsUpgradePolicy mediante directivas integradas de solo lectura. Por lo tanto, solo están disponibles los cmdlets: obtener y concesión. Las instancias integradas se muestran a continuación.
</br>
</br>

|Identidad|Modo|NotifySfbUsers|
|---|---|---|
|Aplicaciones aisladas|Aplicaciones aisladas|Falso|
|IslandsWithNotify|Aplicaciones aisladas|Verdadero|
|SfBOnly|SfBOnly|Falso|
|SfBOnlyWithNotify|SfBOnly|Verdadero|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falso|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Verdadero|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|Falso|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Verdadero|
|UpgradeToTeams|TeamsOnly|Falso|
|Global</br>*Predeterminado*|Aplicaciones aisladas|Falso|
||||

Estas instancias de directivas se pueden otorgar a usuarios individuales o a espacios empresariales. Por ejemplo:
- Para actualizar un usuario ($SipAddress) a Teams, conceda la instancia "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para actualizar todo el espacio empresarial, omita el parámetro identidad del comando "concesión":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>La experiencia de usuario del cliente de Teams al usar los modos de Skype Empresarial

Cuando un usuario se encuentra en cualquiera de los modos de Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todos los chats y llamadas entrantes se enruten al cliente de Skype Empresarial del usuario. Para evitar la confusión del usuario final y asegurarse de que se haya enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de Teams se deshabilita automáticamente cuando un usuario se encuentra en cualquiera de los modos de Skype Empresarial. De forma similar, la programación de reuniones se deshabilita automáticamente cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, y se habilita automáticamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings. Para obtener más información, vea [Experiencia del cliente Teams y conformidad con los modos de coexistencia](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Antes de entregar el cumplimiento automático de los equipos y canales, los modos SfbOnly y SfBWithTeamsCollab se comportan de la misma manera.


## <a name="detailed-mode-descriptions"></a>Descripciones detalladas del modo
</br>
</br>

|Modo|Explicación|
|---|---|
|**Aplicaciones aisladas**</br>(predeterminado)|Un usuario ejecuta Skype Empresarial y Teams en paralelo. Este usuario:</br><ul><li>Puede iniciar chats y llamadas VoIP en un cliente de Skype Empresarial o de Teams. Nota: los usuarios con Skype Empresarial alojado localmente no pueden iniciar desde Teams para llegar a otro usuario de Skype Empresarial, independientemente del modo del destinatario.<li>Recibe chats y llamadas VoIP iniciadas en Skype Empresarial por otro usuario en su cliente de Skype Empresarial.<li>Recibe chats y llamadas VoIP iniciadas en Teams por otro usuario en su cliente de Teams si se encuentran en el *mismo espacio empresarial*.<li>Recibe chats y llamadas VoIP iniciadas en Teams por otro usuario en su cliente de Skype Empresarial si se encuentran en un *espacio empresarial federado*. <li>Tiene la función RTC como se indica a continuación:<ul><li>Si el usuario está alojado en Skype Empresarial local y tiene telefonía IP empresarial, las llamadas RTC siempre se inician y reciben en Skype Empresarial.<li>Cuando el usuario se ha alojado en Skype Empresarial Online y tiene el sistema telefónico de Microsoft, el usuario siempre inicia y recibe llamadas RTC en Skype Empresarial:<ul><li>Esto ocurre tanto si el usuario tiene un plan de llamadas de Microsoft como si se conecta a la red RTC a través de Skype Empresarial Cloud Connector Edition o una implementación local de Skype Empresarial Server (voz híbrida).<li>**Nota: El enrutamiento directo de sistema telefónico no se admite en el modo de islas.**</ul></ul><li>Recibe colas de llamadas de Microsoft y llamadas del operador automático en Skype Empresarial:<ul><li>Los números de teléfono asignados a las colas de llamadas y los operadores automáticos **no** pueden ser números de enrutamiento directo del sistema telefónico en el modo de islas.</ul></ul><li>Puede programar reuniones en Teams o Skype Empresarial y, de forma predeterminada, verá los dos complementos.<li>Puede participar en una reunión de Skype Empresarial o de Teams, la reunión se abrirá en el cliente correspondiente.</ul>|
|**SfBOnly**|Un usuario solo se ejecuta en Skype Empresarial. Este usuario:</br><ul><li>Puede iniciar chats y llamadas de Skype Empresarial únicamente.<li>Recibe cualquier chat o llamada en su cliente de Skype Empresarial, independientemente de dónde se inicie, a menos que el iniciador sea un usuario de Teams con Skype Empresarial de alojamiento local.*<li>Puede programar solo reuniones de Skype Empresarial, pero puede unirse a reuniones de Skype Empresarial o de Teams.</br>\** No es recomendable usar el modo aplicaciones aisladas con usuarios locales en combinación con otros usuarios en el modo SfBOnly. Si un usuario de Teams con Skype Empresarial local inicia una llamada o un chat con un usuario de SfBOnly, no se puede obtener acceso al usuario de SfBOnly y recibe un chat perdido o un correo electrónico de llamada.*|
|**SfBWithTeamsCollab**|Un usuario ejecuta Skype Empresarial y Teams en paralelo. Este usuario:</br><ul><li>Tiene la funcionalidad de un usuario en modo SfBOnly.<li>Tiene Teams habilitado solo para la colaboración en grupo (canales), y está deshabilitada la programación de chat/llamadas/reuniones.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un usuario ejecuta Skype Empresarial y Teams en paralelo. Este usuario:<ul><li>Tiene la funcionalidad de chat y llamada del usuario en el modo SfBOnly.<li>Tiene Teams habilitado para la colaboración en grupo (canales: se incluyen conversaciones del canal) y están deshabilitados el chat y las llamadas.<li>Solo puede programar reuniones de Teams, pero puede unirse a reuniones de Skype Empresarial o de Teams.</ul>|
|**TeamsOnly**</br>(requiere Skype Empresarial Online versión home)|Un usuario solo ejecuta Teams. Este usuario:<ul><li>Recibe cualquier chat y llamada en su cliente de Teams, independientemente de dónde se haya iniciado.<li>Puede iniciar chats y llamadas de Teams únicamente.<li>Puede programar reuniones solo en Teams, pero puede unirse a reuniones de Skype Empresarial o de Teams.<li>Puede seguir usando los teléfonos IP de Skype Empresarial.<br><br>*No se recomienda usar el modo TeamsOnly junto con otros usuarios en modo islas hasta que la adopción de Teams esté saturada; es decir, todos los usuarios del modo Islas usan y supervisan activamente los clientes de Teams y Skype Empresarial. Si un usuario de TeamsOnly inicia una llamada o chat con un usuario de las Islas, dicha llamada o chat llegará al cliente de Teams del usuario de las Islas. si el usuario de las Islas no usa ni supervisa Teams, aparecerá sin conexión y el usuario de TeamsOnly no podrá tendrán acceso a él.*</ul> |
|||




## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
