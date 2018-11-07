---
title: Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Instrucciones para la administración de la transición a los equipos de Skype para la empresa
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff664c630f5c8da8e3f63700d018b40ab9f0ef70
ms.sourcegitcommit: 75e0c9e186dc167bad01f5b17ec9de8a682ee007
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2018
ms.locfileid: "26005516"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa

Interoperabilidad y migración se administran mediante "el modo coexistencia" según lo determinado por TeamsUpgradePolicy. Selección del modo de usuario regula ambos enrutamiento de llamadas entrantes y chats y si el usuario programa las reuniones en los equipos o Skype para la empresa.  Muy pronto, junto con las próxima TeamsAppPermissionsPolicy, modo también regirá en el cliente que el usuario puede iniciar charlas y las llamadas. 

Como anteriormente anunciado en abril de 2018, se va a retirar TeamsInteropPolicy. Su funcionalidad se ha consolidado en TeamsUpgradePolicy y ya no es necesario configurar TeamsInteropPolicy. No se admite a menos que TeamsUpgradePolicy tenga modo = heredado.  Ahora que la compatibilidad de TeamsUpgradePolicy está completa, *los clientes deben actualizar sus configuraciones para usar un modo que no sea heredada*. Concesión de instancias de TeamsUpgradePolicy con el modo = heredado ahora se bloquea de forma predeterminada.

## <a name="fundamental-concepts"></a>Conceptos fundamentales

1.  *Interoperabilidad* : 1 a 1 la comunicación entre un Lync/Skype para usuarios de empresa y un usuario de los equipos.

2.  *Federación* : comunicación entre los usuarios de diferentes inquilinos.

3.  Todos los equipos de los usuarios tienen un Skype subyacente para cuenta de negocio que sea "alojados" ya sea en línea o local:
    - Los usuarios ya está usando Skype para profesionales Online usar su cuenta en línea existente.
    - Los usuarios que ya está usando Skype para profesionales y Lync local usar su cuenta local existente.
    - Los usuarios para los que no se puede detectar un Skype existente para la cuenta de empresa tendrán un Skype para cuenta en línea de negocio que se aprovisionan automáticamente cuando se crea el usuario de los equipos. No se requiere ningún Skype para licencia empresarial.

4.  Si tiene una implementación local de cualquier Skype para empresariales o de Lync y desea que los usuarios para que los usuarios de los equipos, debe como mínimo asegurarse de que Azure Connect AD está sincronizando el msRTCSIP-DeploymentLocator de atributo en AAD, por lo que los equipos y Skype para la empresa Online detecta correctamente su entorno local. Además, para mover los usuarios al modo de sólo los equipos (es decir, un usuario de actualización), *debe configurar Skype para modo híbrido de negocio*. Para obtener más detalles, vea [Configurar Azure AD conectar para Skype para profesionales y los equipos](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interoperabilidad entre los equipos y Skype para usuarios profesionales sólo es posible *Si el usuario de los equipos está hospedado en línea en Skype para la empresa*. El destinatario Skype para usuario empresarial puede estar alojado ya sea local (y requiere la configuración de Skype para entornos híbridos de negocio) o en línea. Los usuarios que están hospedados en Skype para empresarial local pueden usar los equipos en modo de islas (definido más adelante en este documento), pero que no se pueden usar los equipos a la interoperabilidad o federar con otros usuarios que utilizan Skype para la empresa.  

6.  Para actualizar un usuario a los equipos (es decir, conceder TeamsUpgradePolicy con el modo = TeamsOnly), el usuario debe estar alojado en línea en Skype para la empresa. Este proceso es necesario para garantizar la interoperabilidad, la federación y la administración completa del usuario de los equipos. Para actualizar los usuarios que se encuentran ubicados en local, use `Move-CsUser` desde el local herramientas admin al primer movimiento al usuario Skype para empresarial en línea:

    - Si tiene Skype para Business Server 2019 o CU8 de Skype para Business Server 2015, especifique la `-MoveToTeams` cambiar en `Move-CsUser` para mover el usuario directamente a los equipos.
    - En caso contrario, después de `Move-CsUser` completa, asignar el modo de TeamsOnly a ese usuario con PowerShell o el centro de administración de equipos. 

7.  La directiva de núcleo para la administración de actualización y la interoperabilidad es TeamsUpgradePolicy. TeamsInteropPolicy ya no se respetan excepto cuando se utiliza el modo TeamsUpgradePolicy = heredados y los clientes que usen el modo = heredado debe actualizar su configuración de TeamsUpgradePolicy para usar un modo diferente.  Modo de concesión = heredado ahora se bloquea de forma predeterminada, aunque los administradores pueden reemplazar este nombre utilizando `-Force` por el momento. Finalmente, el `-Force` modificador será conceder y se ha quitado el modo = heredado no será posible. 

8.  Para usar las características del sistema de teléfono de los equipos con los equipos, los usuarios deben ser en modo de TeamsOnly (es decir, alojados en Skype para profesionales en línea y actualizar a los equipos), y se debe configurar para el sistema telefónico de Microsoft [Enrutamiento directo](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (que le permite usar el sistema telefónico con su propio troncos SIP y SBC) o disponer de un Plan de llamada de 365 de Office.   

9.  Programación de reuniones de los equipos con las conferencias de Audio (marcado o llamada de salida a través de RTC) actualmente sólo está disponible para los usuarios que están hospedados en Skype para profesionales en línea. Soporte técnico para los usuarios de los equipos con un Skype local para la cuenta de empresa está en puntee dos veces en.


## <a name="coexistence-modes"></a>Modos de coexistencia

Interoperabilidad y migración se administran en función de "modo de coexistencia" con TeamsUpgradePolicy. Determina el modo de un usuario:

- *¿Enrutamiento entrante*: en qué hacer de cliente (los equipos o Skype para la empresa) entrante charlas y llama a land? 
- *Programación de la reunión*: el servicio que se usa para programar reuniones nuevo y asegurarse de que el complemento adecuado está presente en Outlook. Tenga en cuenta que TeamsUpgradePolicy no controla la participación en la reunión. Los usuarios siempre pueden *unirse a* cualquier reunión, ya sea un Skype para la reunión de negocios o a una reunión de los equipos.
- *La experiencia del cliente*: ¿qué funcionalidad está disponible en los equipos y Skype para cliente empresarial? Esto se implementa para el modo TeamsOnly. Compatibilidad con los otros modos depende de la TeamsAppPermissionsPolicy próxima. Cuando esta nueva directiva está en su lugar, TeamsUpgradePolicy tiene una dependencia en él para asegurarse de que los equipos está configurado correctamente para el modo deseado.

Los modos de planeada se enumeran a continuación. SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings le permitirá uso mixto de ambos clientes, pero con ninguna funcionalidad superpuesta. Modo de islas permite el uso de ambos clientes, pero con funcionalidad de superpuestas. Por ejemplo, en el modo de islas, un usuario puede iniciar una charla en ambos Skype para empresariales o de los equipos, pero en SfBWithTeamsCollab, solo puede chat de Skype para la empresa. Tenga en cuenta que no todos los modos aún están completamente disponibles.  
</br>
</br>

|Modo|Comportamiento de enrutamiento|Programación de reuniones|Experiencia del cliente|
|---|---|---|---|
|Islas|VOIP entrante llama y charlas land en el mismo cliente como autor, excepto si el destinatario está asociado y en modo de islas, en cuyo caso en que se encuentran en SfB.<sup>1</sup>|Both|Los usuarios finales puede iniciar las llamadas y chats desde cualquier cliente y puede programar reuniones desde cualquier cliente.|
|SfBOnly|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Skype para la empresa solo|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa sólo y sólo programar Skype para reuniones de negocios. (AÚN NO SE APLICAN)|
|SfBWithTeamsCollab<sup>2</sup>|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Skype para la empresa solo|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa sólo y sólo programar Skype para reuniones de negocios. También pueden utilizar canales en los equipos. (AÚN NO SE APLICAN)|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Sólo los equipos|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa únicamente y sólo programación reuniones de los equipos. También pueden utilizar canales en los equipos. (AÚN NO SE APLICAN)|
|TeamsOnly|Charlas y las llamadas entrantes se enrutan a los equipos|Sólo los equipos|Los usuarios finales pueden iniciar llamadas y chats sólo desde los equipos. Skype para la empresa sólo está disponible para participar en reuniones.|
|Heredado</br>*En desuso*|El enrutamiento se basa en TeamsInteropPolicy|Ningún impacto|Ningún impacto. Esto era un modo temporal que facilita la transición de TeamsInteropPolicy a TeamsUpgradePolicy. TeamsUpgradePolicy es totalmente compatible para *los clientes deberían actualizar sus configuraciones para los modos que no sean heredados.*  Concesión de modo heredado ahora se bloquea de forma predeterminada. |
|||||

**Notas:**

<sup>1</sup> para obtener información detallada en RTC de llamada, consulte la tabla al final de este documento.

<sup>2</sup> SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings aún no están expuestos en la experiencia de usuario de administración porque actualmente comportan no diferente al modo de SfBOnly. Una vez que se entrega la experiencia del cliente, estos modos estará disponibles. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: administración de la migración y coexistencia

TeamsUpgradePolicy expone tres propiedades. Las propiedades principales son modo y NotifySfbUsers. Acción es un parámetro heredado y es totalmente redundante con la combinación de modo y NotifySfbUsers.
</br>
</br>

|Parámetro|Tipo|Valores permitidos</br>(valor predeterminado en cursiva)|Descripción|
|---|---|---|---|
|Modo|Enum|*Islas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>Heredado|Indica el modo en que se debe ejecutar en el cliente. Si el modo = Legacy, componentes de consumo de esta directiva se revertirán a teniendo en cuenta y TeamsInteropPolicy. TeamsUpgradePolicy ahora es totalmente compatible y los clientes deben actualizar sus modos de uso de las configuraciones que no sean heredados.|
|NotifySfbUsers|Booleano|*False* o true|Indica si se debe mostrar una pancarta en la Skype para clientes empresariales que informa al usuario que los equipos pronto reemplazará Skype para la empresa. Esto no puede ser true si el modo = TeamsOnly.|
|Acción</br>*En desuso*|Enum|*Ninguno*, notificar, actualización|Éste es un parámetro heredado que finalmente se quitará, porque es redundante con la combinación de modo y NotifySfbUsers. |
|||||

Los equipos proporciona todas las instancias pertinentes de TeamsUpgradePolicy a través de directivas integradas, como de solo lectura. Por lo tanto, sólo obtener y Grant cmdlets están disponibles. Las instancias de integrada se enumeran a continuación.
</br>
</br>

|Identity |Modo|NotifySfbUsers|Acción|Comentarios|
|---|---|---|---|---|
|Islas|Islas|False|Ninguno||
|IslandsWithNotify|Islas|True|Notificar a||
|SfBOnly|SfBOnly|False|Ninguno|Por ahora, este modo de forma eficaz es el mismo que el cliente preferido de configuración = SfB. En el futuro esperamos que esto restringe las funciones de los equipos.|
|SfBOnlyWithNotify|SfBOnly|True|Notificar a|Por ahora, este modo de forma eficaz es el mismo que el cliente preferido de configuración = SfB. En el futuro esperamos que esto restringe las funciones de los equipos.|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|Ninguno|Este modo no existe en la capa de PowerShell pero no se expone todavía en la experiencia de usuario de administración. Desde una perspectiva de enrutamiento, es el mismo que el modo SfBOnly. Cuando TeamsAppPolicy está disponible, esto solo permitirá canales en aplicación de los equipos.|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|Notificar a|Este modo no existe en la capa de PowerShell pero no se expone todavía en la experiencia de usuario de administración. Desde una perspectiva de enrutamiento, es el mismo que el modo SfBOnly. Cuando TeamsAppPolicy está disponible, esto solo permitirá canales en aplicación de los equipos.|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|Ninguno|Este modo no existe en la capa de PowerShell pero no se expone todavía en la experiencia de usuario de administración. Desde una perspectiva de enrutamiento, es el mismo que el modo SfBOnly. Cuando TeamsAppPolicy está disponible, esto le permitirá canales y programación en los equipos de reuniones.|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|Notificar a|Este modo no existe en la capa de PowerShell pero no se expone todavía en la experiencia de usuario de administración. Desde una perspectiva de enrutamiento, es el mismo que el modo SfBOnly. Cuando TeamsAppPolicy está disponible, esto le permitirá canales y programación en los equipos de reuniones.|
|UpgradeToTeams|TeamsOnly|False|Upgrade|Utilice este modo para actualizar a los usuarios a los equipos y para evitar que chat, llamadas y programar reuniones en Skype para la empresa.|
|Global|Islas|False|Ninguno|El es la directiva predeterminada.|
|NoUpgrade|Heredado|False|Ninguno|Esta instancia se retirarse pronto.|
|NotifyForTeams|Heredado|True|Notificar a|Esta instancia se retirarse pronto.|
||||||

Estas instancias de directiva pueden concederse a usuarios individuales o en todo el inquilino. Por ejemplo:
- Para actualizar un usuario ($SipAddress) a los equipos, conceder la instancia de "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para actualizar al inquilino todo, omite el parámetro identity desde el comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy y modo heredado que se retiran 

Como se describió anteriormente, TeamsInteropPolicy ha sido reemplazada por TeamsUpgradePolicy. Se han actualizado todos los componentes que anteriormente garantizada TeamsInteropPolicy para respetar TeamsUpgradePolicy en su lugar. 

Microsoft introdujo previamente el modo "Heredado" en TeamsUpgradePolicy para facilitar la transición de TeamsInteropPolicy a TeamsUpgradePolicy. En modo heredado, los componentes de enrutamiento que entiende TeamsUpgradePolicy sería volver a TeamsInteropPolicy. Enrutamiento ahora es totalmente compatible con TeamsUpgradePolicy y no es necesario usar el modo heredado. *Los clientes que usen el modo heredado deben actualizar su configuración de TeamsUpgradePolicy utilizar uno de los otros modos.* 

Los clientes que usen aún modo heredado un recordatorio para que sólo las tres instancias específicas de TeamsInteropPolicy enumerados a continuación son compatibles. En cada caso, el valor de CallingDefaultClient coincide con el valor de ChatDefaultClient y AllowEndUserClientOverride siempre es false. 
</br>
</br>
**Admite instancias de TeamsInteropPolicy cuando se usa el modo TeamsUpgradePolicy = heredado**
</br>
</br>

|Identity |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|False|Valor predeterminado|Valor predeterminado|
|`DisallowOverrideCallingSfbChatSfb`|False|Sfb|Sfb|
|`DisallowOverrideCallingTeamsChatTeams`|False|Microsoft Teams|Microsoft Teams|
|||||

Use la siguiente sintaxis de cmdlet, donde $policy es uno de los valores anteriores de identidad:`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>Consideraciones sobre la federación

Federación desde los equipos a otro usuario usar Skype para la empresa requiere que el usuario de los equipos se hospedado en línea en Skype para la empresa. Finalmente, los equipos de los usuarios alojados en Skype para empresarial local podrán federar con otros usuarios de los equipos.

TeamsUpgradePolicy controla el enrutamiento de llamadas y chats federados entrantes. Comportamiento de enrutamiento federada es el mismo que el mismo arrendatario escenarios, *excepto en el modo de islas*.  Cuando los destinatarios se encuentran en modo de islas: 
- Si el destinatario está en un *inquilino federada*, land charlas y las llamadas iniciadas desde los equipos en SfB.
- Si el destinatario está en el *mismo arrendatario*, land charlas y las llamadas iniciadas desde los equipos en los equipos.
- Charlas y las llamadas iniciadas desde SfB siempre land en SfB.


## <a name="completing-the-transition-to-mode-management"></a>Completar la transición a la administración de modo

Más adelante en este año, planes de Microsoft introducir un nuevo tipo de directiva, TeamsAppPermissionsPolicy, para controlar qué partes de cliente de los equipos están habilitadas (por ejemplo, mensajería instantánea, las reuniones, Chat, canales). Cuando se convierte en la nueva directiva para habilitar o deshabilitar las cargas de trabajo en los equipos disponible, TeamsUpgradePolicy se actualizará para que cuando un administrador intenta conceder una instancia de TeamsUpgradePolicy a un usuario, primero se comprueba para asegurarse de que TeamsAppPolicy está correctamente configurado para el modo deseado. En caso contrario, se producirá un error de la concesión con un error que explica cómo en primer lugar se debe establecer la directiva de otra. 

Hasta que TeamsAppPolicy pasa a estar disponible, TeamsUpgradePolicy esencialmente regula el enrutamiento de llamadas y chats, así como la programación de reuniones (tal y como se expone a través de complementos de Outlook). Debido a que el comportamiento de los clientes de los equipos no está aún en su lugar, no todos los modos están habilitados en el Portal moderno. Desde una perspectiva de enrutamiento, los modos de SfBOnly, SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings son idénticos. 

## <a name="action-required-for-organizations-that-were-using-teamsinteroppolicy"></a>Acción necesaria para las organizaciones que estaban usando TeamsInteropPolicy

Los clientes siguen usando TeamsInteropPolicy: 
1. Asegúrese de que los usuarios con TeamsInteropPolicy se asignan solo uno de estos tres instancias integradas, qué CallingDefaultClient = ChatDefaultClient y para qué AllowEndUserClientOverride = false. Estas instancias son:
   </br>
   </br>

   |Identity |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|False|Valor predeterminado|Valor predeterminado|
   |`DisallowOverrideCallingSfbChatSfb`|False|Sfb|Sfb|
   |`DisallowOverrideCallingTeamsChatTeams`|False|Microsoft Teams|Microsoft Teams|
   |||||

    Use la siguiente sintaxis de cmdlet, donde $policy es uno de los valores anteriores de identidad:

    `Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

    **Microsoft solicita que los clientes actualizan sus directivas por 30 de junio de 2018.** En algún momento después de, Microsoft va a quitar de las otras instancias de TeamsInteropPolicy.</br> 
    ***Las organizaciones que no se actualizan a una de estas instancias finalmente tendrán sus usuarios que se actualiza automáticamente a una de estas instancias. Se obviamente preferir que los clientes hacen esto, por lo que puede elegir lo que es mejor para sus usuarios.***

2. Si personaliza la directiva global integrada, deshacer esta operación. La directiva global debe tener los siguientes valores:
   </br>
   </br>

    |Parámetro|Valor|
    |---|---|
    |`AllowEndUserClientOverride`|False|
    |`CallingDefaultClient`|Valor predeterminado|
    |`ChatDefaultClient`|Valor predeterminado|
    |||

    Si alguno de los valores es distinta de la anterior, ejecute el siguiente procedimiento para quitar cualquier personalizaciones específicas del inquilino:

    `Grant-CsTeamsInteropPolicy -PolicyName $null`




## <a name="action-required-for-organizations-that-are-using-modelegacy"></a>Acción necesaria para las organizaciones que usan el modo de = heredado

Los clientes que usen el modo = Legacy en TeamsUpgradePolicy (instancia de directiva = NoUpgrade o directiva de instancia = NotifyForTeams) debe actualizar su configuración para utilizar una directiva con un modo que no sea heredada. 

 **Microsoft solicita que los clientes quitar todo el uso de modo heredado por el 15 de noviembre de 2018.** En algún momento después de que, Microsoft va a quitar instancias de TeamsUpgradePolicy con el modo = heredado.</br> 


## <a name="detailed-mode-descriptions"></a>Descripciones de modo detallado
</br>
</br>

|Modo|Explicación|
|---|---|
|**Islas**</br>(valor predeterminado)|Un solo usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Puede iniciar chats y llamadas de VOIP en ambos Skype para profesionales o los equipos cliente. Nota: Los usuarios con Skype para la empresa hospedados local no se puede iniciar desde los equipos ponerse en contacto con otro Skype para usuarios de empresa.<li>Recibe las llamadas VOIP iniciadas en Skype para la empresa por otro usuario en su Skype para clientes empresariales y chats.<li>Recibe llamadas VOIP iniciadas en los equipos por otro usuario en su cliente de los equipos si están en el *mismo arrendatario*y chats.<li>Recibe las llamadas VOIP iniciadas en los equipos por otro usuario en su Skype para cliente de negocio si están en un *inquilino federado*y chats. <li>Tiene funcionalidad de RTC, tal y como se indica a continuación:<ul><li>Si el usuario está hospedado en Skype para empresarial local, las llamadas RTC se inició y reciben en Skype para la empresa.<li>Si el usuario está hospedado en línea, el usuario tiene el sistema de teléfono, cuyo caso el usuario:<ul><li>Inicia y recibe llamadas de RTC en los equipos si el usuario está configurado para el enrutamiento directo<li>Inicia y recibe llamadas de RTC en Skype para la empresa si el usuario tiene un Plan de llamar a MS o se conecta a la red RTC a través de cualquier Skype para Business Edition de conector en la nube o una implementación local de Skype para Business Server (voz híbrida)</ul></ul><li>Puede programar reuniones en los equipos o Skype para la empresa (y verá ambas plug-ins de forma predeterminada).<li>Se pueden unir a cualquier Skype para profesionales o los equipos de reunión; la reunión se abrirá en el cliente respectivo.</ul>|
|**SfBOnly**|Un solo usuario ejecuta sólo Skype para la empresa. Este usuario:</br><ul><li>Puede iniciar chats y únicamente a las llamadas de Skype para la empresa.<li>Recibe cualquier llamada en su Skype para clientes empresariales, independientemente de donde se inicia, a menos que el iniciador es un usuario de los equipos con Skype para la empresa hospedados local. * <li>Puede programar sólo Skype para reuniones de negocios, pero se pueden unir a Skype para las reuniones de negocios o los equipos. </br> *Modo de uso de islas con usuarios locales no se recomienda en combinación con otros usuarios en el modo de SfBOnly. Si un usuario de los equipos con Skype para la empresa hospedado local inicia una llamada o chat a un usuario SfBOnly, el usuario SfBOnly no es accesible y recibe una llamada perdida email.*|
|**SfBWithTeamsCollab**|Un solo usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Tiene la funcionalidad de un usuario en el modo de SfBOnly.<li>Ha habilitado los equipos sólo para colaboración en grupo (canales); programación de chat, llamada o reunión están deshabilitadas.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un solo usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:<ul><li>Tiene el chat y la funcionalidad de llamada de usuario en el modo de SfBOnly.<li>Ha habilitado los equipos para la colaboración en grupo (canales); Chat y llamar al método están deshabilitadas.<li>Puede programar reuniones de los equipos sólo, pero se pueden unir a Skype para las reuniones de negocios o los equipos.</ul>|
|**TeamsOnly**</br>(requiere SfB Online principal)|Un solo usuario ejecuta sólo los equipos. Este usuario:<ul><li>Recibe cualquier chats y llamadas en su cliente de los equipos, independientemente de donde se inició.<li>Puede iniciar chats y únicamente a las llamadas de los equipos.<li>Puede programar reuniones sólo en los equipos, pero se pueden unir a Skype para las reuniones de negocios o los equipos.<li>Puede seguir usando Skype para teléfonos IP empresarial.</ul> |
|**Heredado**</br>(obsoleto)|Este modo se usó durante la transición de TeamsInteropPolicy a TeamsUpgradePolicy para garantizar una experiencia coherente como software implantado los cambios. Este modo ya no se necesita ahora que TeamsUpgradePolicy es totalmente compatible. Los clientes que usen el modo = heredado debe actualizar su configuración para usar en de los otros modos.|
|||




## <a name="related-topics"></a>Temas relacionados

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[GRANT CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[Remove-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Nueva CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
