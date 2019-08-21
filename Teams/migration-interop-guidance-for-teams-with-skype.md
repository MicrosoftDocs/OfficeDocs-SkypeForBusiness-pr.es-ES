---
title: Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Instrucciones para administrar la transición a teams desde Skype empresarial
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ac2b42094484ce711760a793053bf619aab66884
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484009"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial

> [!Tip] 
> Vea la siguiente sesión para obtener información sobre la coexistencia [y](https://aka.ms/teams-upgrade-coexistence-interop) la interoperabilidad

Como una organización con Skype empresarial comienza a adoptar equipos, los administradores pueden administrar la experiencia de usuario de su organización mediante el concepto de coexistencia "modo", que es una propiedad de TeamsUpgradePolicy. Usar el modo, los administradores administran la interoperabilidad y la migración a medida que administran la transición de Skype empresarial a teams.  El modo de usuario determina en qué conversaciones entrantes de clientes y llama a tierras, así como en qué servicio (equipos o Skype empresarial) se programan nuevas reuniones. También rige Qué funcionalidad está disponible en el cliente de Teams. 


## <a name="fundamental-concepts"></a>Conceptos fundamentales

1.  ** Interoperabilidad: 1 a 1 comunicación entre un usuario de Lync/Skype para empresas y un usuario de Teams.

2.  *Federación* : comunicación entre usuarios de diferentes inquilinos.

3.  Todos los usuarios de Teams tienen una cuenta de Skype empresarial subyacente que está "alojada" en línea o local:
    - Los usuarios que ya usan Skype empresarial online usan su cuenta en línea existente.
    - Los usuarios que ya usan Skype empresarial o Lync local usan su cuenta local existente.
    - Los usuarios para los que no se puede detectar una cuenta existente de Skype empresarial tendrán una cuenta de Skype empresarial online automáticamente aprovisionada cuando se cree el usuario de Teams.

4.  Si dispone de una implementación local de Skype empresarial o de Lync, y desea que esos usuarios sean usuarios de equipos, debe tener como mínimo asegurarse de que Azure AD Connect está sincronizando el atributo msRTCSIP-DeploymentLocator en AAD, de modo que los equipos/Skype para empresas Online detecta correctamente el entorno local. Además, para mover cualquier usuario al modo de solo equipos (es decir, actualizar un usuario), *primero debe configurar el modo híbrido de Skype empresarial*. Para obtener más información, vea [configurar Azure ad Connect para Skype empresarial y Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  La interoperabilidad entre equipos y usuarios de Skype empresarial solo es posible *si el usuario del equipo está conectado en Skype empresarial*. El destinatario del usuario de Skype empresarial puede estar alojado en el entorno local (y requiere la configuración de Skype empresarial híbrido) o en línea. Los usuarios alojados en Skype empresarial local pueden usar Teams en modo islas (definidas más adelante en este documento), pero no pueden usar Teams para interoperar o federar a otros usuarios que usan Skype empresarial.  

6.  El comportamiento de actualización e interoperabilidad se determina en función del modo de coexistencia de un usuario, que se describe más adelante. El modo es administrado por TeamsUpgradePolicy. 

7.  La actualización de un usuario al modo TeamsOnly garantiza que todas las conversaciones y llamadas entrantes siempre estarán en el cliente de equipos del usuario, independientemente del cliente del que se haya originado. Estos usuarios también programarán todas las reuniones nuevas en Teams. Para estar en el modo de TeamsOnly, un usuario debe estar conectado a Internet en Skype empresarial. Esto es necesario para garantizar la interoperabilidad, la Federación y la administración completa del usuario de Teams. Para actualizar un usuario a TeamsOnly:
    - Si el usuario se ha alojado en Skype empresarial online (o nunca ha tenido ninguna cuenta de Skype), concédales TeamsUpgradePolicy con MODE = TeamsOnly con la instancia "UpgradeToTeams" mediante PowerShell, o bien use el centro de administración de Teams para seleccionar el modo TeamsOnly.
    - Si el usuario se ha alojado en local, use `Move-CsUser` desde las herramientas de administración locales para mover primero el usuario a Skype empresarial online.  Si tiene Skype empresarial Server 2019 u CU8 para Skype empresarial Server 2015, puede especificar el `-MoveToTeams` modificador `Move-CsUser` para mover el usuario directamente a teams como parte del movimiento en línea. Esta opción también migrará las reuniones del usuario a teams. Si `-MoveToTeams` no se especifica o no está disponible, después `Move-CsUser` de completarse, asigne el modo TeamsOnly a ese usuario mediante PowerShell o el centro de administración de Teams. Para obtener más información, consulta [mover usuarios entre locales y la nube](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obtener más información sobre la migración de reuniones, consulte [usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Para usar Microsoft Phone System con Teams, los usuarios deben estar en modo TeamsOnly (es decir, alojados en Skype empresarial online y actualizados a teams) y deben estar configurados para el [enrutamiento directo](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) de Microsoft Phone System (que le permite usar el sistema telefónico con sus propios troncos y SBC) o tener un plan de llamadas de Office 365. El enrutamiento directo de Microsoft Phone System no es compatible con el modo islas.    

9.  La programación de reuniones de Teams con conferencias de audio (acceso telefónico local o acceso telefónico telefónico a través de RTC) está disponible independientemente de si el usuario está alojado en Skype empresarial online o en Skype empresarial local. 


## <a name="coexistence-modes"></a>Modos de coexistencia

La interoperabilidad y la migración se administran según el "modo de coexistencia" con TeamsUpgradePolicy. Los modos de coexistencia proporcionan una experiencia sencilla y predecible para los usuarios finales, a medida que las organizaciones pasan de Skype empresarial a teams. Para una organización que se desplaza a Teams, el modo TeamsOnly es el destino final de cada usuario, aunque no es necesario que todos los usuarios tengan asignado TeamsOnly (o cualquier modo) al mismo tiempo. Antes de que los usuarios alcanzaran el modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar una comunicación predecible entre los usuarios que son TeamsOnly y aquellos que aún no lo están.


Desde un punto de vista técnico, el modo de un usuario rige varios aspectos de la experiencia del usuario:

- *Enrutamiento de entrada*: ¿en qué cliente (equipos o Skype empresarial) hacen conversaciones entrantes y llama a tierra? 
- *Publicación de presencia*: ¿es la presencia del usuario la que se muestra a otros usuarios en función de su actividad en Teams o Skype empresarial? 
- *Programación de reuniones*: ¿qué servicio se usa para programar nuevas reuniones y asegurarse de que el complemento adecuado está presente en Outlook? Tenga en cuenta que TeamsUpgradePolicy no rige la combinación de reuniones. Los usuarios siempre pueden *unirse* a cualquier reunión, ya sea una reunión de Skype empresarial o una reunión de Teams.
- *Experiencia de cliente*: ¿Qué funcionalidad está disponible en Teams o en el cliente de Skype empresarial? ¿Pueden los usuarios iniciar llamadas y chats en Teams, Skype empresarial o ambos? ¿Está disponible la experiencia de Teams &s?  

Para obtener más información sobre el comportamiento de enrutamiento y presencia basado en el modo, vea coexistencia [con Skype empresarial](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

Sin embargo, desde una perspectiva de experiencia, el modo se puede describir con más facilidad como la definición de la experiencia de:
- *Chatear y llamar*: ¿qué cliente usa el usuario?
- *Programación de reuniones*: ¿los usuarios programan nuevas reuniones como equipos o reuniones de Skype empresarial?
- *Disponibilidad de las funciones de colaboración en el cliente de Teams*. ¿Teams & funcionalidad de canales y archivos está disponible mientras los usuarios siguen teniendo Skype empresarial?

A continuación se enumeran los modos.
</br>
</br>

|Multimodo|Llamadas y chat|Programación de reuniones<sup>1</sup>|Canales &s de Teams|Caso de uso|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Requiere hogar en Skype empresarial online*|Microsoft Teams|Microsoft Teams|Sí|El estado final de la actualización. También es el valor predeterminado para los nuevos inquilinos con asientos <500.|
|Logra|Ni|Ni|Sí|Configuración predeterminada. Permite que un solo usuario Evalúe ambos clientes en paralelo. Los chats y las llamadas pueden encontrarse en cualquiera de los dos clientes, de modo que los usuarios siempre deben ejecutar ambos clientes. Para evitar una experiencia de Skype empresarial confusa o recargada, las comunicaciones externas (federadas), los servicios de voz RTC y las aplicaciones de voz, la integración de Office y muchas otras integraciones continúan siendo manejadas por Skype empresarial.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Empresarial|Microsoft Teams|Sí|"Primero reuniones". Principalmente para las organizaciones locales para beneficiarse de las funciones de reunión de Teams, si aún no están listas para mover las llamadas a la nube.|
|SfBWithTeamsCollab|Skype Empresarial|Skype Empresarial|Sí|Punto de partida alternativo para organizaciones complejas que necesitan un control administrativo más estricto.|
|SfBOnly|Skype Empresarial|Skype Empresarial|No<sup>3</sup>|Escenario especializado para organizaciones con requisitos estrictos relacionados con el control de datos. Teams solo se usa para unirse a reuniones programadas por otros usuarios.|
||||||

</br>
</br>

**Lotus**

<sup>1</sup> la posibilidad de unirse a una reunión existente (ya sea programada en Teams o en Skype empresarial) no se rige por el modo en curso. De forma predeterminada, los usuarios siempre pueden unirse a cualquier reunión a la que hayan sido invitados.

<sup>2</sup> de forma predeterminada, al asignar TeamsOnly o SfbWithTeamsCollabAndMeetings a un usuario individual, cualquier reunión existente de Skype empresarial programada por ese usuario para el futuro se convierte en reuniones de Teams. Si lo desea, puede dejar estas reuniones como reuniones de Skype empresarial especificando `-MigrateMeetingsToTeams $false` al conceder TeamsUpgradePolicy o anulando la selección de la casilla en el portal de administración de Teams.   Tenga en cuenta que la capacidad de convertir reuniones de Skype empresarial en Teams no se avaialble al otorgar TeamsUpgradePolicy en un espacio empresarial. 

<sup>3</sup> actualmente, Teams no tiene la capacidad de deshabilitar la funcionalidad de los equipos y los canales para que esto permanezca habilitado por el momento.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: administración de la migración y coexistencia

TeamsUpgradePolicy expone dos propiedades clave: Mode y NotifySfbUsers. 
</br>
</br>

|Parámetro|Tipo|Valores permitidos</br>(predeterminado en cursiva)|Descripción|
|---|---|---|---|
|Multimodo|Enumeración|*Logra*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica el modo en el que se debe ejecutar el cliente.|
|NotifySfbUsers|Booleano|*Falso* o verdadero|Indica si se muestra un banner en el cliente de Skype empresarial que informa al usuario de que Teams va a reemplazar pronto a Skype empresarial. Esto no puede ser verdadero si Mode = TeamsOnly.|
|||||

Teams proporciona todas las instancias relevantes de TeamsUpgradePolicy mediante directivas integradas de solo lectura. Por lo tanto, solo están disponibles los cmdlets para obtener y conceder permisos. Las instancias integradas se muestran a continuación.
</br>
</br>

|Identity |Multimodo|NotifySfbUsers|
|---|---|---|
|Logra|Logra|False|
|IslandsWithNotify|Logra|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Global</br>*Valor predeterminado*|Logra|False|
||||

Estas instancias de Directiva se pueden conceder a usuarios individuales o a escala de inquilinos. Por ejemplo:
- Para actualizar un usuario ($SipAddress) a Teams, conceda la instancia "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para actualizar todo el inquilino, omita el parámetro Identity del comando Grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Consideraciones sobre la Federación

La Federación de equipos a otro usuario que use Skype empresarial requiere que el usuario de Teams se conecte en línea en Skype empresarial. En el futuro, los usuarios de equipos alojados en Skype empresarial local podrán federarse a los usuarios de Teams solo.

TeamsUpgradePolicy rige el enrutamiento de llamadas y chats federados entrantes. El comportamiento del enrutamiento federado es el mismo que el de los escenarios en los que se encuentra el inquilino, *excepto en el modo islas*.  Cuando los destinatarios se encuentran en el modo islas: 
- Chats y llamadas iniciadas desde la tierra de un equipo en SfB si el destinatario está en un *inquilino federado*.
- Chats y llamadas iniciadas desde la tierra de los equipos en Teams si el destinatario está en el *mismo inquilino*.
- Chats y llamadas iniciadas desde SfB siempre en Skype para empresas.

Para obtener más información, consulte coexistencia [con Skype empresarial](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>La experiencia de usuario del cliente de Teams cuando se usan modos de SfB
Cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todas las conversaciones y llamadas entrantes se dirigen al cliente de Skype empresarial del usuario. Para evitar la confusión del usuario final y garantizar el enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de Teams se desactiva automáticamente cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial. De forma similar, la programación de reuniones de Teams se desactiva automáticamente cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, y se habilita automáticamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings. Para obtener más información, vea [experiencia del cliente de Teams y cumplimiento de los modos de](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)coexistencia.

> [!Note] 
> - Antes de la entrega del cumplimiento automático de los equipos y canales, los modos SfbOnly y SfBWithTeamsCollab se comportan de la misma.


## <a name="detailed-mode-descriptions"></a>Descripciones del modo detallado
</br>
</br>

|Multimodo|Explicación|
|---|---|
|**Logra**</br>programas|Un usuario ejecuta tanto Skype empresarial como los equipos en paralelo. Este usuario:</br><ul><li>Puede iniciar conversaciones y llamadas VoIP en Skype empresarial o en el cliente de Teams. Nota: los usuarios con Skype empresarial Home local no pueden iniciarse desde Teams para comunicarse con otro usuario de Skype empresarial, independientemente del modo del destinatario.<li>Recibe conversaciones & las llamadas de VoIP iniciadas en Skype empresarial por otro usuario en el cliente de Skype empresarial.<li>Recibe conversaciones & las llamadas de VoIP iniciadas en Teams por otro usuario en el cliente de su equipo si se encuentran en el *mismo inquilino*.<li>Recibe conversaciones & las llamadas de VoIP iniciadas en el equipo de otro usuario en el cliente de Skype empresarial, si se encuentran en un *inquilino federado*. <li>Tiene la funcionalidad de RTC según se indica a continuación:<ul><li>Cuando el usuario se hospeda en Skype empresarial local y tiene telefonía IP empresarial, las llamadas RTC siempre se inician y reciben en Skype empresarial.<li>Cuando el usuario se ha alojado en Skype empresarial online y tiene Microsoft Phone System, el usuario siempre inicia y recibe llamadas RTC en Skype empresarial:<ul><li>Esto ocurre independientemente de si el usuario tiene un plan de llamadas de Microsoft o se conecta a la red PSTN a través de Skype empresarial Cloud Connector Edition o de una implementación local de Skype empresarial Server (voz híbrida).<li>**Nota: el enrutamiento directo de Microsoft Teams Phone System no es compatible con el modo islas.**</ul></ul><li>Recibe las colas de llamadas de Microsoft y de operador automático en Skype empresarial.<li>Puede programar reuniones en Teams o Skype empresarial (y verá ambos complementos de forma predeterminada).<li>Puede unirse a cualquier reunión de Skype empresarial o de Teams; la reunión se abrirá en el cliente respectivo.</ul>|
|**SfBOnly**|Un usuario solo ejecuta Skype empresarial. Este usuario:</br><ul><li>Puede iniciar chats y llamadas desde Skype empresarial solamente.<li>Recibe cualquier chat o llamada en el cliente de Skype empresarial, independientemente de dónde se inicie, a menos que el iniciador sea un usuario de equipo con Skype empresarial, local. *Puede programar solo reuniones de Skype empresarial, pero puede unirse a reuniones de Skype empresarial o de Teams. <li> </br> *No se recomienda usar el modo islas con usuarios locales en combinación con otros usuarios en el modo SfBOnly. Si un usuario de un equipo con Skype empresarial alojado en local inicia una llamada o un chat a un usuario de SfBOnly, no se puede contactar con el usuario de SfBOnly y recibe un mensaje de correo electrónico de chat/llamada perdido. *|
|**SfBWithTeamsCollab**|Un usuario ejecuta tanto Skype empresarial como los equipos en paralelo. Este usuario:</br><ul><li>Tiene la funcionalidad de un usuario en el modo SfBOnly.<li>Tiene equipos habilitados solo para la colaboración en grupo (canales); la programación de chats, llamadas y reuniones está deshabilitada.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un usuario ejecuta tanto Skype empresarial como los equipos en paralelo. Este usuario:<ul><li>Tiene la funcionalidad de chat y de llamada del usuario en el modo SfBOnly.<li>Tiene equipos habilitados para la colaboración en grupo (canales: incluye conversaciones de canal); la conversación y las llamadas están deshabilitadas.<li>Puede programar solo reuniones de Teams, pero puede unirse a reuniones de Skype empresarial o de Teams.</ul>|
|**TeamsOnly**</br>(requiere SfB online Home)|Un usuario solo ejecuta equipos. Este usuario:<ul><li>Recibe conversaciones y llamadas en el cliente de su equipo, independientemente de dónde se inicie.<li>Puede iniciar chats y llamadas desde Teams.<li>Puede programar reuniones solo en Teams, pero puede unirse a reuniones de Skype empresarial o de Teams.<li>Puede seguir usando los teléfonos IP de Skype empresarial.<br><br>*El uso del modo TeamsOnly en combinación con otros usuarios en el modo islas no se recomienda hasta que se satura la adopción de equipos, es decir, los usuarios del modo de islas que usan activamente los equipos y los clientes de Skype empresarial. Si un usuario de TeamsOnly inicia una llamada o un chat a un usuario de islas, la llamada o el chat se incluirá en el cliente de equipos del usuario de las islas; Si el usuario de las islas no usa ni supervisa Teams, ese usuario aparecerá como desconectado y no será accesible para el usuario de TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
