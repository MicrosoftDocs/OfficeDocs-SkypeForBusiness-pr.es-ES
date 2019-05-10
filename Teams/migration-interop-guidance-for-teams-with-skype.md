---
title: Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Instrucciones para la administración de la transición a los equipos de Skype para la empresa
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58b2548e4c1c409314146d1675bbc06b2f95f7e5
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835462"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial

> [!Tip] 
> Vea la sesión siguiente para obtener más información acerca de la [interoperabilidad y coexistencia](https://aka.ms/teams-upgrade-coexistence-interop)

Como una organización con Skype para la empresa comienza a adoptar los equipos, los administradores pueden administrar la experiencia del usuario en su organización con el concepto de "modo", que es una propiedad de TeamsUpgradePolicy de coexistencia. Con modo, los administradores administrar la interoperabilidad y migración como administran la transición de Skype para la empresa a los equipos.  Modo de un usuario determina en qué cliente se programan chats entrantes y las llamadas land, así como en qué las nuevas reuniones del servicio (los equipos o Skype para la empresa). En el futuro, modo también se usará para definir el comportamiento de los equipos cliente en términos de qué funcionalidad estará disponible. 


## <a name="fundamental-concepts"></a>Conceptos fundamentales

1.  *Interoperabilidad* : 1 a 1 la comunicación entre un Lync/Skype para usuarios de empresa y un usuario de los equipos.

2.  *Federación* : comunicación entre los usuarios de diferentes inquilinos.

3.  Todos los equipos de los usuarios tienen un Skype subyacente para cuenta de negocio que sea "alojados" ya sea en línea o local:
    - Los usuarios ya está usando Skype para profesionales Online usar su cuenta en línea existente.
    - Los usuarios que ya está usando Skype para profesionales y Lync local usar su cuenta local existente.
    - Los usuarios para los que no se puede detectar un Skype existente para la cuenta de empresa tendrán un Skype para cuenta en línea de negocio que se aprovisionan automáticamente cuando se crea el usuario de los equipos.

4.  Si tiene una implementación local de cualquier Skype para empresariales o de Lync y desea que los usuarios para que los usuarios de los equipos, debe como mínimo asegurarse de que Azure Connect AD está sincronizando el msRTCSIP-DeploymentLocator de atributo en AAD, por lo que los equipos y Skype para la empresa Online detecta correctamente su entorno local. Además, para mover los usuarios al modo de sólo los equipos (es decir, un usuario de actualización), *primero debe configurar Skype para modo híbrido de negocio*. Para obtener más detalles, vea [Configurar Azure AD conectar para Skype para profesionales y los equipos](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilidad entre los equipos y Skype para usuarios profesionales sólo es posible *Si el usuario de los equipos está hospedado en línea en Skype para la empresa*. El destinatario Skype para usuario empresarial puede estar alojado ya sea local (y requiere la configuración de Skype para entornos híbridos de negocio) o en línea. Los usuarios que están hospedados en Skype para empresarial local pueden usar los equipos en modo de islas (definido más adelante en este documento), pero que no se pueden usar los equipos a la interoperabilidad o federar con otros usuarios que utilizan Skype para la empresa.  

6.  Comportamiento de actualización e interoperabilidad se determina en función de modo de coexistencia de un usuario, que se describen posteriormente por debajo. Modo administrado por TeamsUpgradePolicy. TeamsInteropPolicy ya no está pagado y otorgar el modo = heredados ya no está permitido. 

7.  Actualización de un usuario para el modo de TeamsOnly garantiza que todos los chats entrantes y las llamadas siempre se colocarán en el cliente de los equipos del usuario, independientemente del cliente se originó en. Estos usuarios también va a programar todas las nuevas reuniones en los equipos. Para estar en modo de TeamsOnly, un usuario debe estar alojado en línea en Skype para la empresa. Este proceso es necesario para garantizar la interoperabilidad, la federación y la administración completa del usuario de los equipos. Para actualizar un usuario a TeamsOnly:
    - Si el usuario está hospedado en Skype para la empresa en línea (o nunca tenía cualquier cuenta de Skype), concederles TeamsUpgradePolicy con el modo = TeamsOnly utilizando la instancia de "UpgradeToTeams" con PowerShell, o use el centro de administración de equipos para seleccionar el modo de TeamsOnly.
    - Si el usuario es alojarse en local, use `Move-CsUser` desde el local herramientas admin al primer movimiento al usuario Skype para profesionales en línea.  Si tiene Skype para Business Server 2019 o CU8 de Skype para Business Server 2015, puede especificar el `-MoveToTeams` cambiar en `Move-CsUser` para mover el usuario directamente a los equipos como parte del movimiento en línea. Esta opción también migrará las reuniones del usuario a los equipos. Si `-MoveToTeams` no está especificado o no está disponible, a continuación, después de `Move-CsUser` completa, asignar el modo de TeamsOnly a ese usuario con PowerShell o el centro de administración de equipos. Para obtener más información, vea [mover usuarios entre local y la nube](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obtener más detalles sobre la migración de la reunión, vea [utilizar el servicio de migración de reunión (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Para usar las características del sistema de teléfono de los equipos con los equipos, los usuarios deben ser en modo de TeamsOnly (es decir, alojados en Skype para profesionales en línea y actualizar a los equipos), y se debe configurar para el sistema telefónico de Microsoft [Enrutamiento directo](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (que le permite usar el sistema telefónico con su propio troncos SIP y SBC) o disponer de un Plan de llamada de 365 de Office.   

9.  Programación de reuniones de los equipos con las conferencias de Audio (marcado o llamada de salida a través de RTC) está ahora disponible, independientemente de si el usuario está hospedado en Skype para profesionales en línea o Skype para empresarial local. 


## <a name="coexistence-modes"></a>Modos de coexistencia

Interoperabilidad y migración se administran en función de "modo de coexistencia" con TeamsUpgradePolicy. Modos de coexistencia proporcionan una experiencia sencilla y predecible para los usuarios finales como transición de las organizaciones de Skype para la empresa a los equipos. Para una organización mover a los equipos, el modo de TeamsOnly es el destino final de cada usuario, aunque no todos los usuarios deben asignarse TeamsOnly (o cualquier modo) al mismo tiempo. Antes de alcanzar el modo TeamsOnly de los usuarios, las organizaciones pueden usar cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantizar la comunicación entre los usuarios que están TeamsOnly y aquellos que no están todavía predecible.


Desde una perspectiva técnica, el modo de un usuario regula varios aspectos de la experiencia del usuario:

- *¿Enrutamiento entrante*: en qué hacer de cliente (los equipos o Skype para la empresa) entrante charlas y llama a land? 
- *¿Publicación de presencia*: es la presencia del usuario que se muestra a otros usuarios en función de sus actividades en los equipos o Skype para la empresa? 
- *¿Programación de la reunión*: el servicio que se usa para programar reuniones nuevo y asegurarse de que el complemento adecuado está presente en Outlook? Tenga en cuenta que TeamsUpgradePolicy no controla la participación en la reunión. Los usuarios siempre pueden *unirse a* cualquier reunión, ya sea un Skype para la reunión de negocios o a una reunión de los equipos.
- *La experiencia del cliente*: ¿qué funcionalidad está disponible en los equipos y Skype para cliente empresarial? ¿Pueden que los usuarios inician las llamadas y chats en los equipos, Skype para la empresa o ambos? ¿Es que la experiencia de los equipos & canales disponibles?  

Para obtener más detalles sobre el comportamiento de enrutamiento y presencia basada en el modo, vea [coexistencia con Skype para la empresa](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

Sin embargo, desde una perspectiva de experiencia, de modo más simplemente se puede describir como definición de la experiencia de:
- *Conversaciones y llamar a*: ¿qué cliente usa un usuario?
- *Programación de reuniones*: ¿los usuarios programar reuniones nuevo como los equipos o Skype para reuniones de negocios?
- *Disponibilidad de la funcionalidad de colaboración en el cliente de los equipos*. ¿Es una función de canales de & de los equipos y los archivos disponibles mientras los usuarios aún tienen Skype para la empresa?

Los modos se enumeran a continuación.
</br>
</br>

|Modo|Llamadas y conversaciones|Programación de reunión<sup>1</sup>|Los equipos & canales|Caso de uso|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Requiere home en Skype para profesionales en línea*|Microsoft Teams|Microsoft Teams|Sí|El estado final del que se está actualizando. También el valor predeterminado para los inquilinos nuevo con <500 puestos.|
|Islas|cualquiera de los dos|cualquiera de los dos|Sí|Configuración predeterminada. Permite que un único usuario evaluar a ambos clientes en paralelo. Charlas y las llamadas se pueden colocar en cualquier cliente, por lo que los usuarios siempre deben ejecutar a ambos clientes.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Empresarial|Microsoft Teams|Sí|"Reuniones primera". Principalmente para las organizaciones locales para beneficiarse de la funcionalidad de reunión de los equipos, si aún no están listos para mover la llamada a la nube.|
|SfBWithTeamsCollab|Skype Empresarial|Skype Empresarial|Sí|Punto de partida alternativa para las organizaciones complejas que necesitan un control administrativo estricta.|
|SfBOnly|Skype Empresarial|Skype Empresarial|No hay<sup>3</sup>|Especializados escenario para organizaciones con estrictos requisitos alrededor de control de datos. Los equipos sólo se utiliza para participar en reuniones programadas por otros usuarios.|
||||||

</br>
</br>

**Notas:**

<sup>1</sup> la posibilidad de unirse a una reunión existente (si programado en los equipos o en Skype para la empresa) no se regirá por el modo. De forma predeterminada, los usuarios pueden unirse a cualquier reunión que hayan sido invitados a.

<sup>2</sup> de forma predeterminada, al asignar TeamsOnly o SfbWithTeamsCollabAndMeetings a un usuario individual, cualquier Skype existente para las reuniones de negocio programadas por ese usuario para el futuro se convierten a las reuniones de los equipos. Si lo desea, puede dejar salir estas reuniones como Skype para reuniones de negocios ya sea especificando `-MigrateMeetingsToTeams $false` concesión TeamsUpgradePolicy o anulando la selección de la casilla de verificación en el portal de administración de equipos.   Tenga en cuenta que la capacidad de convertir las reuniones de Skype para la empresa a los equipos no es la que estará disponible cuando concesión TeamsUpgradePolicy en todo el inquilino. 

<sup>3</sup> en la actualidad, los equipos no tienen la capacidad para deshabilitar la funcionalidad de los equipos y canales de manera permanecerá habilitado por ahora.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: administración de la migración y coexistencia

TeamsUpgradePolicy expone dos propiedades claves: modo y NotifySfbUsers. 
</br>
</br>

|Parámetro|Tipo|Valores permitidos</br>(valor predeterminado en cursiva)|Descripción|
|---|---|---|---|
|Modo|Enum|*Islas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indica el modo en que se debe ejecutar en el cliente.|
|NotifySfbUsers|Booleano|*False* o true|Indica si se debe mostrar una pancarta en la Skype para clientes empresariales que informa al usuario que los equipos pronto reemplazará Skype para la empresa. Esto no puede ser true si el modo = TeamsOnly.|
|||||

Los equipos proporciona todas las instancias pertinentes de TeamsUpgradePolicy a través de directivas integradas, como de solo lectura. Por lo tanto, sólo obtener y Grant cmdlets están disponibles. Las instancias de integrada se enumeran a continuación.
</br>
</br>

|Identity |Modo|NotifySfbUsers|
|---|---|---|
|Islas|Islas|False|
|IslandsWithNotify|Islas|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Global</br>*Valor predeterminado*|Islas|False|
||||

Estas instancias de directiva pueden concederse a usuarios individuales o en todo el inquilino. Por ejemplo:
- Para actualizar un usuario ($SipAddress) a los equipos, conceder la instancia de "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para actualizar al inquilino todo, omite el parámetro identity desde el comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Consideraciones sobre la federación

Federación desde los equipos a otro usuario usar Skype para la empresa requiere que el usuario de los equipos se hospedado en línea en Skype para la empresa. Finalmente, los equipos de los usuarios alojados en Skype para empresarial local podrán federarse con los equipos sólo a los usuarios.

TeamsUpgradePolicy controla el enrutamiento de llamadas y chats federados entrantes. Comportamiento de enrutamiento federada es el mismo que el mismo arrendatario escenarios, *excepto en el modo de islas*.  Cuando los destinatarios se encuentran en modo de islas: 
- Si el destinatario está en un *inquilino federada*, land charlas y las llamadas iniciadas desde los equipos en SfB.
- Si el destinatario está en el *mismo arrendatario*, land charlas y las llamadas iniciadas desde los equipos en los equipos.
- Charlas y las llamadas iniciadas desde SfB siempre land en Skype para la empresa.

Para obtener más detalles, vea [coexistencia con Skype para la empresa](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>El usuario de los equipos cliente experiencia al usar los modos de SfB
Cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), todos los chats entrantes y las llamadas se enrutan a Skype del usuario para clientes empresariales. Para evitar confusiones al usuario final y garantizar el enrutamiento correcto, llamadas y conversaciones funcionalidad en el cliente de los equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los Skype para los modos de negocio. De forma similar, programar reuniones en los equipos está deshabilitado de forma explícita cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y explícitamente habilitado cuando un usuario se encuentra en el modo de SfBWithTeamsCollabAndMeetings. La funcionalidad para deshabilitar automáticamente conversaciones y llamar a la funcionalidad, así como habilitar o deshabilitar la programación basada en el modo de la reunión es ahora generalmente disponible. Para obtener información detallada sobre la nueva funcionalidad, vea [experiencia de los equipos cliente y conformidad a los modos de coexistencia](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Antes de la entrega de la ejecución automática de los equipos y los canales, los modos de SfbOnly y SfBWithTeamsCollab comportan del mismo.



## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>Se ha retirado TeamsInteropPolicy y modo heredado 

TeamsInteropPolicy se ha reemplazado por TeamsUpgradePolicy. Se han actualizado todos los componentes que anteriormente garantizada TeamsInteropPolicy para respetar TeamsUpgradePolicy en su lugar. Microsoft había introducido previamente el modo "Heredado" en TeamsUpgradePolicy para facilitar la transición de TeamsInteropPolicy a TeamsUpgradePolicy. En modo heredado, los componentes de enrutamiento que entiende TeamsUpgradePolicy sería volver a TeamsInteropPolicy. Enrutamiento ahora es totalmente compatible con TeamsUpgradePolicy. Ya no se admite el modo heredado y ya no es posible conceder modo heredado.


## <a name="detailed-mode-descriptions"></a>Descripciones de modo detallado
</br>
</br>

|Modo|Explicación|
|---|---|
|**Islas**</br>(valor predeterminado)|Un usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Puede iniciar chats y llamadas de VoIP en ambos Skype para profesionales o los equipos cliente. Nota: Los usuarios con Skype para la empresa hospedados local no se puede iniciar desde los equipos ponerse en contacto con otro Skype para usuarios de empresa, independientemente del modo del destinatario.<li>Recibe chats & que VoIP llamadas iniciadas en Skype para la empresa por otro usuario en su Skype para clientes empresariales.<li>Recibe chats & VoIP llamadas iniciadas en los equipos por otro usuario en su cliente de los equipos si están en el *mismo arrendatario*.<li>Recibe chats & VoIP llamadas iniciadas en los equipos por otro usuario en su Skype para clientes empresariales si están en un *inquilino federado*. <li>Tiene funcionalidad de RTC, tal y como se indica a continuación:<ul><li>Si el usuario está hospedado en Skype para empresarial local, las llamadas RTC se inició y reciben en Skype para la empresa.<li>Si el usuario está hospedado en línea, el usuario tiene el sistema de teléfono, cuyo caso el usuario:<ul><li>Inicia y recibe llamadas de RTC en los equipos si el usuario está configurado para el enrutamiento directo<li>Inicia y recibe llamadas de RTC en Skype para la empresa si el usuario tiene un Plan de llamar a MS o se conecta a la red RTC a través de cualquier Skype para Business Edition de conector en la nube o una implementación local de Skype para Business Server (voz híbrida)</ul></ul><li>Puede programar reuniones en los equipos o Skype para la empresa (y verá ambas plug-ins de forma predeterminada).<li>Se pueden unir a cualquier Skype para profesionales o los equipos de reunión; la reunión se abrirá en el cliente respectivo.</ul>|
|**SfBOnly**|Un usuario ejecuta sólo Skype para la empresa. Este usuario:</br><ul><li>Puede iniciar chats y únicamente a las llamadas de Skype para la empresa.<li>Recibe cualquier llamada en su Skype para clientes empresariales, independientemente de donde se inicia, a menos que el iniciador es un usuario de los equipos con Skype para la empresa hospedados local. * <li>Puede programar sólo Skype para reuniones de negocios, pero se pueden unir a Skype para las reuniones de negocios o los equipos. </br> *Modo de uso de islas con usuarios locales no se recomienda en combinación con otros usuarios en el modo de SfBOnly. Si un usuario de los equipos con Skype para la empresa hospedado local inicia una llamada o chat a un usuario SfBOnly, el usuario SfBOnly no es accesible y recibe una llamada perdida email.*|
|**SfBWithTeamsCollab**|Un usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Tiene la funcionalidad de un usuario en el modo de SfBOnly.<li>Ha habilitado los equipos sólo para colaboración en grupo (canales); programación de chat, llamada o reunión están deshabilitadas.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:<ul><li>Tiene el chat y la funcionalidad de llamada de usuario en el modo de SfBOnly.<li>Tiene los equipos habilitados para la colaboración en grupo (canales: incluye las conversaciones del canal); Chat y llamar al método están deshabilitadas.<li>Puede programar reuniones de los equipos sólo, pero se pueden unir a Skype para las reuniones de negocios o los equipos.</ul>|
|**TeamsOnly**</br>(requiere SfB Online principal)|Un usuario ejecuta sólo los equipos. Este usuario:<ul><li>Recibe cualquier chats y llamadas en su cliente de los equipos, independientemente de donde se inició.<li>Puede iniciar chats y únicamente a las llamadas de los equipos.<li>Puede programar reuniones sólo en los equipos, pero se pueden unir a Skype para las reuniones de negocios o los equipos.<li>Puede seguir usando Skype para teléfonos IP empresarial.</ul> |
|||




## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Uso del servicio de migración de reunión (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
