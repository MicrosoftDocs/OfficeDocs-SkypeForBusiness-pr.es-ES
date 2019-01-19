---
title: Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Instrucciones para la administración de la transición a los equipos de Skype para la empresa
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7cbce74cdc06a2f37f628dd32f6f36356c1ad27a
ms.sourcegitcommit: 708e691b00f490da45d8d7f1d6594be29f45023b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "29354503"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial

> [!Tip] 
> Vea la sesión siguiente para obtener más información acerca de la [interoperabilidad y coexistencia](https://aka.ms/teams-upgrade-coexistence-interop)

Como una organización con Skype para la empresa comienza a adoptar los equipos, los administradores pueden administrar la experiencia del usuario en su organización con el concepto de "modo", que es una propiedad de TeamsUpgradePolicy de coexistencia. Con modo, los administradores administrar la interoperabilidad y migración como administran la transición de Skype para la empresa a los equipos.  Modo de un usuario determina en qué cliente están programados en chats entrantes y las llamadas land, así como en qué las nuevas reuniones del servicio (los equipos o Skype para la empresa). En el futuro, modo también se usará para definir el comportamiento de los equipos cliente en términos de qué funcionalidad estará disponible. 


## <a name="fundamental-concepts"></a>Conceptos fundamentales

1.  *Interoperabilidad* : 1 a 1 la comunicación entre un Lync/Skype para usuarios de empresa y un usuario de los equipos.

2.  *Federación* : comunicación entre los usuarios de diferentes inquilinos.

3.  Todos los equipos de los usuarios tienen un Skype subyacente para cuenta de negocio que sea "alojados" ya sea en línea o local:
    - Los usuarios ya está usando Skype para profesionales Online usar su cuenta en línea existente.
    - Los usuarios que ya está usando Skype para profesionales y Lync local usar su cuenta local existente.
    - Los usuarios para los que no se puede detectar un Skype existente para la cuenta de empresa tendrán un Skype para cuenta en línea de negocio que se aprovisionan automáticamente cuando se crea el usuario de los equipos. No se requiere ningún Skype para licencia empresarial.

4.  Si tiene una implementación local de cualquier Skype para empresariales o de Lync y desea que los usuarios para que los usuarios de los equipos, debe como mínimo asegurarse de que Azure Connect AD está sincronizando el msRTCSIP-DeploymentLocator de atributo en AAD, por lo que los equipos y Skype para la empresa Online detecta correctamente su entorno local. Además, para mover los usuarios al modo de sólo los equipos (es decir, un usuario de actualización), *primero debe configurar Skype para modo híbrido de negocio*. Para obtener más detalles, vea [Configurar Azure AD conectar para Skype para profesionales y los equipos](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilidad entre los equipos y Skype para usuarios profesionales sólo es posible *Si el usuario de los equipos está hospedado en línea en Skype para la empresa*. El destinatario Skype para usuario empresarial puede estar alojado ya sea local (y requiere la configuración de Skype para entornos híbridos de negocio) o en línea. Los usuarios que están hospedados en Skype para empresarial local pueden usar los equipos en modo de islas (definido más adelante en este documento), pero que no se pueden usar los equipos a la interoperabilidad o federar con otros usuarios que utilizan Skype para la empresa.  

6.  Comportamiento de actualización e interoperabilidad se determina en función de modo de coexistencia de un usuario, que se administra por TeamsUpgradePolicy. TeamsInteropPolicy ya no está pagado y otorgar el modo = heredados ya no está permitido. 

7.  Actualización de un usuario para el modo de TeamsOnly garantiza que todos los chats entrantes y las llamadas se siempre colocará en cliente de los equipos del usuario, independientemente del cliente orignated desde. Estos usuarios también va a programar todas las nuevas reuniones en los equipos. Para estar en modo de TeamsOnly, un usuario debe estar alojado en línea en Skype para la empresa. Este proceso es necesario para garantizar la interoperabilidad, la federación y la administración completa del usuario de los equipos. Para actualizar un usuario a TeamsOnly: r. Si el usuario está hospedado en Skype para la empresa en línea (o nunca tenía cualquier cuenta de Skype), concederles TeamsUpgradePolicy con el modo = TeamsOnly utilizando la instancia de "UpgradeToTeams" con PowerShell, o use el centro de administración de equipos para seleccionar la Modo de TeamsOnly.
    B. Si el usuario es alojarse en local, use `Move-CsUser` desde el local herramientas admin al primer movimiento al usuario Skype para profesionales en línea. Hay 2 opciones al mover usuarios de local:  
      - Si tiene Skype para Business Server 2019 o CU8 de Skype para Business Server 2015, puede especificar el `-MoveToTeams` cambiar en `Move-CsUser` para mover el usuario directamente a los equipos. Esta opción también migrar las reuniones del usuario a los equipos (aunque por ahora, la migración de la reunión sólo es funcional para los clientes TAP). 
       - En caso contrario, después de `Move-CsUser` completa, asignar el modo de TeamsOnly a ese usuario con PowerShell o el centro de administración de equipos.  
     Para obtener más información, vea [mover usuarios entre local y la nube](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Para obtener más detalles sobre la migración de la reunión, vea [utilizar el servicio de migración de reunión (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


8.  Para usar las características del sistema de teléfono de los equipos con los equipos, los usuarios deben ser en modo de TeamsOnly (es decir, alojados en Skype para profesionales en línea y actualizar a los equipos), y se debe configurar para el sistema telefónico de Microsoft [Enrutamiento directo](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (que le permite usar el sistema telefónico con su propio troncos SIP y SBC) o disponer de un Plan de llamada de 365 de Office.   

9.  Programación de reuniones de los equipos con las conferencias de Audio (marcado o llamada de salida a través de RTC) actualmente sólo está disponible para los usuarios que están hospedados en Skype para profesionales en línea. Soporte técnico para los usuarios de los equipos con un Skype local para la cuenta de empresa está en puntee dos veces en.


## <a name="coexistence-modes"></a>Modos de coexistencia

Interoperabilidad y migración se administran en función de "modo de coexistencia" con TeamsUpgradePolicy. Determina el modo de un usuario:

- *¿Enrutamiento entrante*: en qué hacer de cliente (los equipos o Skype para la empresa) entrante charlas y llama a land? 
- *Programación de la reunión*: el servicio que se usa para programar reuniones nuevo y asegurarse de que el complemento adecuado está presente en Outlook. Tenga en cuenta que TeamsUpgradePolicy no controla la participación en la reunión. Los usuarios siempre pueden *unirse a* cualquier reunión, ya sea un Skype para la reunión de negocios o a una reunión de los equipos.
- *La experiencia del cliente*: ¿qué funcionalidad está disponible en los equipos y Skype para cliente empresarial? Esto se implementa para el modo TeamsOnly. Soporte para otros modos de está planificado para el futuro. 

Los modos se enumeran a continuación. SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings le permitirá uso mixto de ambos clientes, pero con ninguna funcionalidad superpuesta. Modo de islas permite el uso de ambos clientes, pero con funcionalidad de superpuestas. Por ejemplo, en el modo de islas, un usuario puede iniciar una charla en ambos Skype para empresariales o de los equipos, pero en SfBWithTeamsCollab, pueden sólo chat de Skype para la empresa (aunque pueden participar en las conversaciones del canal de los equipos). Tenga en cuenta que el expeirence de cliente para los modos de SfB todavía no es totalmente funcional.  
</br>
</br>

|Modo|Comportamiento de enrutamiento|Programación de reuniones|Experiencia del cliente|
|---|---|---|---|
|Islas|VOIP entrante llama y charlas land en el mismo cliente como autor, excepto si el destinatario está asociado y en modo de islas, en cuyo caso en que se encuentran en SfB.<sup>1</sup>|Both|Los usuarios finales puede iniciar las llamadas y chats desde cualquier cliente y puede programar reuniones desde cualquier cliente.|
|SfBOnly|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Skype para la empresa solo|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa sólo y sólo programar Skype para reuniones de negocios. (AÚN NO SE APLICAN)|
|SfBWithTeamsCollab<sup>2</sup>|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Skype para la empresa solo|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa sólo y sólo programar Skype para reuniones de negocios. También pueden utilizar canales en los equipos. (AÚN NO SE APLICAN)|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Sólo los equipos|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa únicamente y sólo programación reuniones de los equipos. Pueden participar en las conversaciones del canal de los equipos. (AÚN NO SE APLICAN)|
|TeamsOnly|Charlas y las llamadas entrantes se enrutan a los equipos|Sólo los equipos|Los usuarios finales pueden iniciar llamadas y chats sólo desde los equipos. Skype para la empresa sólo está disponible para participar en reuniones.|
|||||

**Notas:**

<sup>1</sup> para obtener información detallada en RTC de llamada, consulte la tabla al final de este documento.

<sup>2</sup> SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings aún no están expuestos en la experiencia de usuario de administración porque se comportan actualmente diferente que el modo de SfBOnly, excepto para controlar los complementos de Outlook. Una vez que se entrega la experiencia del cliente, estos modos estará disponibles en el Portal de administración. 

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

Federación desde los equipos a otro usuario usar Skype para la empresa requiere que el usuario de los equipos se hospedado en línea en Skype para la empresa. Finalmente, los equipos de los usuarios alojados en Skype para empresarial local podrán federar con otros usuarios de los equipos.

TeamsUpgradePolicy controla el enrutamiento de llamadas y chats federados entrantes. Comportamiento de enrutamiento federada es el mismo que el mismo arrendatario escenarios, *excepto en el modo de islas*.  Cuando los destinatarios se encuentran en modo de islas: 
- Si el destinatario está en un *inquilino federada*, land charlas y las llamadas iniciadas desde los equipos en SfB.
- Si el destinatario está en el *mismo arrendatario*, land charlas y las llamadas iniciadas desde los equipos en los equipos.
- Charlas y las llamadas iniciadas desde SfB siempre land en SfB.


## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>El usuario de cliente previsto experiencia en los equipos al usar los modos de SfB

Cuando los usuarios están en cualquiera de los Skype para los modos de negocio (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), *llamadas y conversaciones funcionalidad en la aplicación de los equipos está pensada para ser deshabilitado*, pero actualmente no aún no lo está. De forma similar, cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, *programar reuniones en los equipos está pensada para ser deshabilitado*, pero actualmente no es. Se prevé una solución para proporcionar automáticamente esta experiencia.

Hasta que se entrega esta solución, los administradores pueden aplicar la experiencia del cliente previsto del modo TeamsUpgradePolicy mediante la configuración manual de los valores de TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy. Además, al usar `Grant-CsTeamsUpgradePolicy` en PowerShell, el cmdlet comprobará automáticamente la configuración de los valores correspondientes en TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy a determmine si son compatibles con estas opciones de configuración el modo especificado. Si alguna no están configurado correctamente, la concesión se realizará correctamente pero se proporcionará una advertencia que indica los valores de configuración no están configurados correctamente. El administrador debe actualizar posteriormente las directivas indicadas para proporcionar una experiencia de usuario final compatible en los equipos. Si el administrador decide no realizar ninguna acción como consecuencia de la advertencia, los usuarios aún tener acceso a conversaciones, llamar o funciones de programación en los equipos según los valores de TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy, de la reunión lo que puede conllevar una experiencia de usuario final confusa.

### <a name="expected-values-of-workload-policy-settings-per-mode"></a>Valores esperados de configuración de directiva de carga de trabajo por modo
La tabla muestra la configuración de directiva que se comprueba cuando se concede TeamsUpgradeMode. En el futuro, la intención es para que el modo SfBOnly también desactivar canales en los equipos; Sin embargo, actualmente no hay ninguna opción que permite que la característica de canales en los equipos que va a deshabilitar.


|**Modalidad (aplicación)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Llamadas|TeamsCallingPolicy.AllowPrivateCalling|
|Programación de reuniones|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

El mostrar a continuación se muestra, de un modo determinado, los valores esperados de estas opciones:

|Modo|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islas|Habilitado|Habilitado|Habilitado|Habilitado|
|SfBWithTeamsCollabAndMeetings|Deshabilitado|Deshabilitado|Habilitado|Habilitado|
|SfBWithTeamsCollab o SfBOnly|Deshabilitado|Deshabilitado|Deshabilitado|Deshabilitado|
||||||


Si se detecta cualquier otra combinación de estas opciones de configuración durante Grant-CsTeamsUpgradePolicy, la concesión se realizará correctamente, pero se mostrará una advertencia que indica la configuración específica que no cumplen el comportamiento esperado. Temporalmente, el administrador debe habilitar o deshabilitar la carga de trabajo a través de la directiva de carga de trabajo principal.  Una vez implementada la aplicación automática en función de TeamsUpgradePolicy, se actualizarán las advertencias de PowerShell para informar al administrador de que la experiencia del cliente se aplicará automáticamente. En ese caso, los valores de TeamsMessagingPolicy, TeamsCallingPolicy y TeamsMeetingPolicy permanecen inalterados – pero la experiencia del cliente previsto se exigirán según TeamsUpgradePolicy.

A continuación es un ejemplo del aspecto que podría tener la advertencia de PowerShell:


`PS C:\Users\janedoe> Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab
WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.
PS C:\Users\janedoe>`


Antes de la entrega de la aplicación automática de comportamiento de los clientes se ha descrito anteriormente, cada uno de los modos de SfB se comportan básicamente el mismo. Los modos de SfBOnly, SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings son todos los idénticos en cómo se enrutan charlas y las llamadas entrantes. La única diferencia, por ahora, es en si están habilitados los complementos de Outlook para los equipos y Skype para la empresa. Hasta que se entrega la experiencia de cliente diferenciados, sólo 1 de los modos de SfB está habilitada en el Portal de administración. Pero todos los modos están disponibles en PowerShell.


## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy y modo heredado que se retiran 

TeamsInteropPolicy se ha reemplazado por TeamsUpgradePolicy. Se han actualizado todos los componentes que anteriormente garantizada TeamsInteropPolicy para respetar TeamsUpgradePolicy en su lugar.  Microsoft había introducido previamente el modo "Heredado" en TeamsUpgradePolicy para facilitar la transición de TeamsInteropPolicy a TeamsUpgradePolicy. En modo heredado, los componentes de enrutamiento que entiende TeamsUpgradePolicy sería volver a TeamsInteropPolicy. Enrutamiento ahora es totalmente compatible con TeamsUpgradePolicy y ya no se admite el modo heredado. *Los clientes que usen el modo heredado deben actualizar su configuración de TeamsUpgradePolicy utilizar uno de los otros modos.* 


### <a name="action-required-for-organizations-that-are-using-modelegacy-andor-teamsinteroppolicy"></a>Acción necesaria para las organizaciones que usan el modo de = heredado o TeamsInteropPolicy
Los clientes que usen el modo = Legacy en TeamsUpgradePolicy (instancia de directiva = NoUpgrade o directiva de instancia = NotifyForTeams) debe actualizar su configuración para utilizar una directiva con un modo que no sea heredada.  Además, los clientes que usen TeamsInteropPolicy deben quitar las asignaciones de esta directiva ya que ya no se utiliza el sistema.  Tenga en cuenta que es que ya no es posible conceder modo heredado. 

Acciones necesarias:
 - Los clientes que usen TeamsInteropPolicy con los usuarios que son *no* en modo heredado: la directiva no tiene ningún efecto y del se recomienda quitar cualquier usuario Redistribuir asignaciones y usar sólo la directiva global con valores predeterminados.
 - Los clientes que usen el modo heredado con el enrutamiento de TeamsInteropPolicy a SfB (DisallowOverrideCallingSfbChatSfb): estas organizaciones deben cambiar para utilizar uno de los modos de SfB (SfBOnly, SfBWithTeamsCollab, SfbWithTeamsCollabAndMeetings) en TeamsUpgradePolicy. Desde una perspectiva de enrutamiento, cualquiera de estos modos se comporta lo mismo que usar el modo heredado con el enrutamiento de TeamsInteropPolicy a SfB.
  - Los clientes que usen el modo heredado con el enrutamiento de TeamsInteropPolicy a los equipos (DisallowOverrideCallingTeamsChatTeams): estas organizaciones deben cambiar a modo de TeamsOnly.  Desde una perspectiva de enrutamiento se trata de tener el mismo. Sin embargo, una diferencia es que los usuarios en el modo sólo los equipos ya no podrán iniciar las charlas y las llamadas ni programar reuniones en Skype para la empresa. Sin embargo todavía puede unirse a cualquier Skype para la reunión de negocios.


 **Microsoft solicita que los clientes quitar todo el uso de modo heredado por el 15 de noviembre de 2018.** En algún momento después de que, Microsoft va a quitar instancias de TeamsUpgradePolicy con el modo = heredado.</br> 


## <a name="detailed-mode-descriptions"></a>Descripciones de modo detallado
</br>
</br>

|Modo|Explicación (includeding planeado la experiencia del cliente)|
|---|---|
|**Islas**</br>(valor predeterminado)|Un usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Puede iniciar chats y llamadas de VOIP en ambos Skype para profesionales o los equipos cliente. Nota: Los usuarios con Skype para la empresa hospedados local no se puede iniciar desde los equipos ponerse en contacto con otro Skype para usuarios de empresa.<li>Recibe chats & VOIP llamadas iniciadas en Skype para la empresa por otro usuario en su Skype para clientes empresariales.<li>Recibe chats & VOIP llamadas iniciadas en los equipos por otro usuario en su cliente de los equipos si están en el *mismo arrendatario*.<li>Recibe chats & VOIP llamadas iniciadas en los equipos por otro usuario en su Skype para clientes empresariales si están en un *inquilino federado*. <li>Tiene funcionalidad de RTC, tal y como se indica a continuación:<ul><li>Si el usuario está hospedado en Skype para empresarial local, las llamadas RTC se inició y reciben en Skype para la empresa.<li>Si el usuario está hospedado en línea, el usuario tiene el sistema de teléfono, cuyo caso el usuario:<ul><li>Inicia y recibe llamadas de RTC en los equipos si el usuario está configurado para el enrutamiento directo<li>Inicia y recibe llamadas de RTC en Skype para la empresa si el usuario tiene un Plan de llamar a MS o se conecta a la red RTC a través de cualquier Skype para Business Edition de conector en la nube o una implementación local de Skype para Business Server (voz híbrida)</ul></ul><li>Puede programar reuniones en los equipos o Skype para la empresa (y verá ambas plug-ins de forma predeterminada).<li>Se pueden unir a cualquier Skype para profesionales o los equipos de reunión; la reunión se abrirá en el cliente respectivo.</ul>|
|**SfBOnly**|Un usuario ejecuta sólo Skype para la empresa. Este usuario:</br><ul><li>Puede iniciar chats y únicamente a las llamadas de Skype para la empresa.<li>Recibe cualquier llamada en su Skype para clientes empresariales, independientemente de donde se inicia, a menos que el iniciador es un usuario de los equipos con Skype para la empresa hospedados local. * <li>Puede programar sólo Skype para reuniones de negocios, pero se pueden unir a Skype para las reuniones de negocios o los equipos. </br> *Modo de uso de islas con usuarios locales no se recomienda en combinación con otros usuarios en el modo de SfBOnly. Si un usuario de los equipos con Skype para la empresa hospedado local inicia una llamada o chat a un usuario SfBOnly, el usuario SfBOnly no es accesible y recibe una llamada perdida email.*|
|**SfBWithTeamsCollab**|Un usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Tiene la funcionalidad de un usuario en el modo de SfBOnly.<li>Ha habilitado los equipos sólo para colaboración en grupo (canales); programación de chat, llamada o reunión están deshabilitadas.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:<ul><li>Tiene el chat y la funcionalidad de llamada de usuario en el modo de SfBOnly.<li>Tiene los equipos habilitados para la colaboración en grupo (canales: incluye las conversaciones del canal); Chat y llamar al método están deshabilitadas.<li>Puede programar reuniones de los equipos sólo, pero se pueden unir a Skype para las reuniones de negocios o los equipos.</ul>|
|**TeamsOnly**</br>(requiere SfB Online principal)|Un usuario ejecuta sólo los equipos. Este usuario:<ul><li>Recibe cualquier chats y llamadas en su cliente de los equipos, independientemente de donde se inició.<li>Puede iniciar chats y únicamente a las llamadas de los equipos.<li>Puede programar reuniones sólo en los equipos, pero se pueden unir a Skype para las reuniones de negocios o los equipos.<li>Puede seguir usando Skype para teléfonos IP empresarial.</ul> |
|||




## <a name="related-topics"></a>Temas relacionados

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Nueva CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
