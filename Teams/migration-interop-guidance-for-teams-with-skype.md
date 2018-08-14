---
title: Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Instrucciones para la administración de la transición a los equipos de Skype para la empresa
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f97554c0e03ae1e337d2c4b77e472edebab453e
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246667"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa

En abril de 2018, Microsoft aclarar su orientación para migrar a los equipos de Skype para empresas y cómo estos dos clientes pueden coexistir para un usuario determinado. En ese momento, se ha anunciado cambios planeados para simplificar la administración y aumentar la satisfacción del usuario final. Desde entonces, Microsoft ha proporcionado una actualización para la experiencia de usuario de administración coherente con dicho plan. Las instrucciones de este documento reflejan esos cambios.

Como se ha anunciado anteriormente, TeamsInteropPolicy se deben retirarse (dirigido para el fin de T3) y su funcionalidad se consolidan en TeamsUpgradePolicy. Interoperabilidad y migración se administrarán utilizando "modo de coexistencia" según lo determinado por TeamsUpgradePolicy, que ahora está disponible. Selección del modo de usuario tendrán prioridad ambos enrutamiento de charlas y las llamadas entrantes y en el cliente que el usuario puede iniciar charlas y las llamadas o programar reuniones. Mientras se deben retirarse TeamsInteropPolicy, aún debe establecerse en paralelo con TeamsUpgradePolicy durante el phaseout.  

Como parte de este esfuerzo, Microsoft ha actualizado recientemente el "Microsoft equipos & Skype para profesionales centro de administración" (también conocido como Portal moderno) para reflejar el nuevo modelo de administración en función de los modos de coexistencia. En Portal moderno, configurar TeamsUpgradePolicy realizarán ahora automáticamente también establezca TeamsInteropPolicy en valor coherente, por lo que TeamsInteropPolicy ya no se expone en la interfaz de usuario. *Sin embargo, los administradores con PowerShell aún deben establecer TeamsUpgradePolicy tanto TeamsInteropPolicy juntos para garantizar el enrutamiento correcto.* Una vez finalizada la transición a TeamsUpgradePolicy, ya no será necesario establecer también TeamsInteropPolicy.
</br>
</br>
|**Administración de interoperabilidad y migración**|**Portal moderno**|**PowerShell**|
|----|----|----|----|
|Hasta septiembre de 2018 (fechas está sujeta a cambios)|Usar TeamsUpgradePolicy|Use TeamsUpgradePolicy y TeamsInteropPolicy |
|Registrar septiembre de 2018 (fechas está sujeta a cambios)|Usar TeamsUpgradePolicy|Usar TeamsUpgradePolicy solamente; TeamsInteropPolicy en desuso|
|||||

Para tener en cuenta para la introducción de modos de coexistencia y la retirada pendiente de TeamsInteropPolicy, Microsoft proporciona ahora esta guía para que los clientes que usen los equipos en la actualidad puedan administrar la transición.

## <a name="in-this-article"></a>En este artículo

- [Conceptos fundamentales](#fundamental-concepts)
- [Modos de coexistencia](#coexistence-modes)
- [TeamsUpgradePolicy: administración de la migración y coexistencia](#teamsupgradepolicy-managing-migration-and-co-existence)
- [TeamsInteropPolicy retirarse](#teamsinteroppolicy-to-be-retired)
- [Completar la transición a la administración de modo](#completing-the-transition-to-mode-management)
- [Acción necesaria para las organizaciones que ya se han utilizado TeamsInteropPolicy](#action-required-for-organizations-that-have-already-used-teamsinteroppolicy)   
- [Descripciones de modo detallado](#detailed-mode-descriptions) 
- [Resumen de los cambios de funcionalidad planeada para simplificar la coexistencia y migración](#summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration) 
- [Problemas conocidos](#known-issues)

## <a name="fundamental-concepts"></a>Conceptos fundamentales

1.  *Interoperabilidad* : 1 a 1 la comunicación entre un Lync/Skype para usuarios de empresa y un usuario de los equipos.

2.  *Federación* : comunicación entre los usuarios de diferentes inquilinos.

3.  Todos los equipos de los usuarios tienen un Skype subyacente para cuenta de negocio que sea "alojados" ya sea en línea o local:
    - Los usuarios ya está usando Skype para profesionales Online usar su cuenta en línea existente.
    - Los usuarios que ya está usando Skype para profesionales y Lync local usar su cuenta local existente.
    - Los usuarios para los que no se puede detectar un Skype existente para la cuenta de empresa tendrán un Skype para cuenta en línea de negocio que se aprovisionan automáticamente cuando se crea el usuario de los equipos. No se requiere ningún Skype para licencia empresarial.

4.  Si tiene una implementación local de cualquier Skype para empresariales o de Lync y desea que los usuarios para que los usuarios de los equipos, debe como mínimo asegurarse de que Azure Connect AD está sincronizando el msRTCSIP-DeploymentLocator de atributo en AAD, por lo que los equipos y Skype para la empresa Online detecta correctamente su entorno local. Además, para mover los usuarios al modo de sólo los equipos (es decir, un usuario de actualización), *debe configurar Skype para modo híbrido de negocio*.

5.  Interoperabilidad entre los equipos y Skype para usuarios profesionales sólo es posible *Si el usuario de los equipos está hospedado en línea en Skype para la empresa*. El Skype para usuario empresarial puede estar alojado ya sea local (y requiere la configuración de Skype para entornos híbridos de negocio) o en línea. Los usuarios que están hospedados en Skype para empresarial local pueden usar los equipos en modo de islas (definido más adelante en este documento), pero que no se pueden usar los equipos a la interoperabilidad o federar con otros usuarios que utilizan Skype para la empresa.  

6.  Para actualizar un usuario a los equipos (es decir, conceder TeamsUpgradePolicy con el modo = TeamsOnly), el usuario debe estar alojado en línea en Skype para la empresa. Este proceso es necesario para garantizar la interoperabilidad, la federación y la administración completa del usuario de los equipos. Para actualizar los usuarios que se encuentran ubicados en local, use `Move-CsUser` desde el local herramientas admin al primer movimiento al usuario Skype para profesionales en línea. A continuación, conceder TeamsUpgradePolicy y TeamsInteropPolicy para el usuario en línea o usar Portal moderno para asignar el modo de TeamsOnly.

7.  Las directivas de núcleo para la administración de actualización y la interoperabilidad son TeamsUpgradePolicy y TeamsInteropPolicy.  Sin embargo, TeamsInteropPolicy es en el proceso que se retira y toda la funcionalidad de será reemplazada por TeamsUpgradePolicy. Hasta que se complete la transición, los clientes deben establecer TeamsUpgradePolicy y TeamsInteropPolicy coherentemente (como se describe [posterior](#important) en este documento) para garantizar el funcionamiento correcto, o usar el nuevo Portal moderno, que hace esto automáticamente.

8.  Para usar las características del sistema de teléfono de los equipos, los usuarios deben ser en modo de TeamsOnly (es decir, alojados en Skype para profesionales en línea y actualizar a los equipos), y se debe configurar para Microsoft teléfono del sistema enrutamiento directo (que le permite usar el sistema telefónico con su propios SIP troncos y SBC) o disponer de un Plan de llamada de 365 de Office. Enrutamiento directo está [disponible para el público](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) a partir del 28 de junio de 2018.  

9.  Programación de reuniones de los equipos con las conferencias de Audio (marcado o llamada de salida a través de RTC) actualmente sólo está disponible para los usuarios que están hospedados en Skype para profesionales en línea. Soporte técnico para los usuarios de los equipos con un Skype local para la cuenta de empresa es planeado.

10. El enrutamiento de mensajes para las organizaciones que aún no se ha habilitado para el servicio de presencia unificada (UPS) no respeta TeamsInteropPolicy (ChatDefaultClient) o TeamsUpgradePolicy (modo). Implantación de SAI (UPS) finaliza a través de las próximas semanas, se respetan TeamsInteropPolicy o TeamsUpgradePolicy. TeamsUpgradePolicy finalmente sólo tendrá en cuenta.

## <a name="coexistence-modes"></a>Modos de coexistencia

Para simplificar la administración y aumentar la satisfacción del usuario final, interoperabilidad y migración ahora se administran en función de "modo de coexistencia" con TeamsUpgradePolicy. Determina el modo de un usuario:

- *¿Enrutamiento entrante* : en qué hacer de cliente (los equipos o Skype para la empresa) entrante charlas y llama a land? Esta funcionalidad reemplaza a lo que anteriormente se ha controlado por TeamsInteropPolicy. TeamsInteropPolicy se deben retirarse una vez finalizada la transición. ***Durante la transición, TeamsUpgradePolicy y TeamsInteropPolicy se deben establecer de manera coordinada, tal como se describe en la siguiente sección***.
- *¿Programación de la reunión* : el servicio que se usa para programar reuniones nuevo y asegurarse de que el complemento adecuado está presente en Outlook? Compatibilidad de complementos de Outlook se espera que se implemente en las próximas semanas. Tenga en cuenta que TeamsUpgradePolicy no controla la participación en la reunión. Los usuarios siempre pueden *unirse a* cualquier reunión, ya sea un Skype para la reunión de negocios o a una reunión de los equipos.
- *La experiencia del cliente* : ¿qué funcionalidad está disponible en los equipos y Skype para cliente empresarial? Esto se implementa para el modo TeamsOnly. Compatibilidad con los otros modos depende de la TeamsAppPolicy próxima. Cuando esta nueva directiva está en su lugar, TeamsUpgradePolicy tiene una dependencia en él para asegurarse de que los equipos está configurado correctamente para el modo deseado.

Los modos de planeada se enumeran a continuación. SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings le permitirá uso mixto de ambos clientes, pero con ninguna funcionalidad superpuesta. Modo de islas permite el uso de ambos clientes, pero con funcionalidad de superpuestas. Por ejemplo, en el modo de islas, un usuario puede iniciar una charla en ambos Skype para empresariales o de los equipos, pero en SfBWithTeamsCollab, solo puede chat de Skype para la empresa. Tenga en cuenta que no todos los modos aún están disponibles.  
</br>
</br>
|Modo|Comportamiento de enrutamiento|Programación de reuniones|Experiencia del cliente|
|---|---|---|---|
|Islas|VOIP entrante llama y charlas land en el mismo cliente como autor<sup>1</sup>|Ambos|Los usuarios finales puede iniciar las llamadas y chats desde cualquier cliente y puede programar reuniones desde cualquier cliente.|
|SfBOnly|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Skype para la empresa solo|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa sólo y sólo programar Skype para reuniones de negocios. (AÚN NO SE APLICAN)|
|SfBWithTeamsCollab<sup>2</sup>|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Skype para la empresa solo|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa sólo y sólo programar Skype para reuniones de negocios. También pueden utilizar canales en los equipos. (AÚN NO SE APLICAN)|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|Charlas y las llamadas entrantes se enrutan a Skype para la empresa|Sólo los equipos|Los usuarios finales pueden iniciar llamadas y conversaciones de Skype para la empresa únicamente y sólo programación reuniones de los equipos. También pueden utilizar canales en los equipos. (AÚN NO SE APLICAN)|
|TeamsOnly|Charlas y las llamadas entrantes se enrutan a los equipos|Sólo los equipos|Los usuarios finales pueden iniciar llamadas y chats sólo desde los equipos. Skype para la empresa sólo está disponible para participar en reuniones.|
|Heredado|El enrutamiento se basa en TeamsInteropPolicy|Ningún impacto|Ningún impacto. Este un modo temporal para facilitar la transición de TeamsInteropPolicy a TeamsUpgradePolicy. Una vez finalizada la transición, este modo se quitará. |
|||||

**Notas:**

<sup>1</sup> para obtener información detallada en RTC de llamada, consulte la tabla al final de este documento.

<sup>2</sup> SfBWithTeamsCollab no está todavía expuesta en la experiencia de usuario de administración debido a que se comporta actualmente diferente que el modo de SfBOnly. Cuando se entrega la experiencia del cliente, este modo estará disponible.

<sup>3</sup> SfBWithTeamsCollabAndMeetings aún no está disponible. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: administración de la migración y coexistencia

TeamsUpgradePolicy ahora expone tres propiedades. Las propiedades principales son modo y NotifySfbUsers. Acción es un parámetro heredado y es totalmente redundante con la combinación de modo y NotifySfbUsers.
</br>
</br>
|Parámetro|Tipo|Valores permitidos</br>(valor predeterminado en cursiva)|Descripción|
|---|---|---|---|
|Modo|Enum|*Islas*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>Heredado|Indica el modo en que se debe ejecutar en el cliente. Si el modo = Legacy, componentes de consumo de esta directiva se revertirán a teniendo en cuenta y TeamsInteropPolicy. Esto es para facilitar la transición al nuevo esquema de como componentes que anteriormente garantizada TeamsInteropPolicy se actualizan para respetar TeamsUpgradePolicy.</br>Modo = TeamsOnly es el equivalente de acción = actualización.|
|NotifySfbUsers|Booleano|*False* o true|Indica si se debe mostrar una pancarta en la Skype para clientes empresariales que informa al usuario que los equipos pronto reemplazará Skype para la empresa. Esto no puede ser true si el modo = TeamsOnly. Esto equivale a la acción = Notify.|
|Acción|Enum|*Ninguno*, notificar, actualización|Éste es un parámetro heredado que finalmente se quitará, porque es redundante con la combinación de modo y NotifySfbUsers. |
|||||

Los equipos proporciona todas las instancias pertinentes de TeamsUpgradePolicy a través de directivas integradas, como de solo lectura. Por lo tanto, sólo obtener y Grant cmdlets están disponibles. Las instancias de integrada se enumeran a continuación.
</br>
</br>
|Identity |Modo|NotifySfbUsers|Acción|Comentarios|
|---|---|---|---|---|
|Islas|Islas|Falso|Ninguna||
|IslandsWithNotify|Islas|Verdadero|Notificar a||
|SfBOnly|SfBOnly|Falso|Ninguna|Por ahora, este modo de forma eficaz es el mismo que el cliente preferido de configuración = SfB. En el futuro esperamos que esto restringe las funciones de los equipos.|
|SfBOnlyWithNotify|SfBOnly|Verdadero|Notificar a|Por ahora, este modo de forma eficaz es el mismo que el cliente preferido de configuración = SfB. En el futuro esperamos que esto restringe las funciones de los equipos.|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Falso|Ninguna|Este modo no existe en la capa de PowerShell pero no se expone todavía en la experiencia de usuario de administración. Desde una perspectiva de enrutamiento, es el mismo que el modo SfBOnly. Cuando TeamsAppPolicy está disponible, esto solo permitirá canales en aplicación de los equipos.|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Verdadero|Notificar a|Este modo no existe en la capa de PowerShell pero no se expone todavía en la experiencia de usuario de administración. Desde una perspectiva de enrutamiento, es el mismo que el modo SfBOnly. Cuando TeamsAppPolicy está disponible, esto solo permitirá canales en aplicación de los equipos.|
|UpgradeToTeams|TeamsOnly|Falso|Upgrade|Utilice este modo para actualizar a los usuarios a los equipos y para evitar que chat, llamadas y programar reuniones en Skype para la empresa.|
|Global|Heredado|Falso|Ninguna|El modo de finalmente se actualizarán a islas.|
|NoUpgrade|Heredado|Falso|Ninguna|Finalmente se retirarse esta instancia.|
|NotifyForTeams|Heredado|Verdadero|Notificar a|Finalmente se retirarse esta instancia.|
||||||

Estas instancias de directiva pueden concederse a usuarios individuales o en todo el inquilino. Por ejemplo:
- Para actualizar un usuario ($SipAddress) a los equipos, conceder la instancia de "UpgradeToTeams":</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Para actualizar al inquilino todo, omite el parámetro identity desde el comando grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

### <a name="important"></a>¡IMPORTANTE!
Son los componentes que anteriormente garantizada TeamsInteropPolicy se está actualizando para respetar TeamsUpgradePolicy. Durante la transición, la administración de estas dos directivas debe coordinarse tal como se especifica a continuación. Tenga en cuenta que la actualización reciente Portal moderno concede automáticamente ambas de estas directivas correctamente cuando se selecciona un modo de coexistencia.
</br>
</br>
|Si concede a una instancia de TeamsUpgradePolicy</br>con este valor de modo...|... A continuación, conceder esta instancia de TeamsInteropPolicy|
|---|---|
|Islas|`DisallowOverrideCallingDefaultChatDefault`|
|SfBOnly, SfBWithTeamsCollab,</br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
|||

## <a name="teamsinteroppolicy-to-be-retired"></a>TeamsInteropPolicy retirarse 

Como se describió anteriormente, TeamsInteropPolicy se reemplazará por TeamsUpgradePolicy. Hasta que se complete esta transición, se admiten sólo las tres instancias específicas de TeamsInteropPolicy enumerados a continuación. En cada caso, el valor de CallingDefaultClient coincide con el valor de ChatDefaultClient y AllowEndUserClientOverride siempre es false. 
</br>
</br>
**Instancias compatibles de TeamsInteropPolicy antes de la retirada**
|Identity |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|Falso|Predeterminado|Predeterminado|
|`DisallowOverrideCallingSfbChatSfb`|Falso|Sfb|Sfb|
|`DisallowOverrideCallingTeamsChatTeams`|Falso|Microsoft Teams|Microsoft Teams|
|||||

Use la siguiente sintaxis de cmdlet, donde $policy es uno de los valores anteriores de identidad:`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>Consideraciones sobre la federación

Federación desde los equipos a otro usuario usar Skype para la empresa requiere que el usuario de los equipos se hospedado en línea en Skype para la empresa. La federación es en piloto y progresivamente se encuentre disponible. Si la organización requiere la federación, no se debería actualizar hasta que la compatibilidad de federación está en su lugar. Finalmente, los equipos de los usuarios alojados en Skype para empresarial local podrán federar con otros usuarios de los equipos.

Una vez habilitada la compatibilidad con la federación, TeamsUpgradePolicy (junto con TeamsInteropPolicy durante la transición) regula el enrutamiento de llamadas y chats federados entrantes. Para facilitar la otras organizaciones iniciar comunicaciones federadas con los usuarios de su organización, se recomienda elegir un modo que enruta específicamente cualquiera a Skype empresarial o los equipos, en lugar de islas.
</br>
|Para enrutar las llamadas y chats a...|Conceder una instancia de TeamsUpgradePolicy</br> con uno de estos modos|Y conceder a esta instancia de TeamsInteropPolicy|
|---|---|---|
|Skype Empresarial|SfBOnly, SfBWithTeamsCollab, </br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|Microsoft Teams|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
||||

## <a name="completing-the-transition-to-mode-management"></a>Completar la transición a la administración de modo

Más adelante en este año, planes de Microsoft introducir un nuevo tipo de directiva, TeamsAppPolicy, para controlar qué partes de cliente de los equipos están habilitadas (por ejemplo, mensajería instantánea, las reuniones, Chat, canales). Cuando se convierte en la nueva directiva para habilitar o deshabilitar las cargas de trabajo en los equipos disponible, TeamsUpgradePolicy se actualizará para que cuando un administrador intenta conceder una instancia de TeamsUpgradePolicy a un usuario, primero se comprueba para asegurarse de que TeamsAppPolicy está correctamente configurado para el modo deseado. En caso contrario, se producirá un error de la concesión con un error que explica cómo en primer lugar se debe establecer la directiva de otra. 

Hasta que TeamsAppPolicy pasa a estar disponible, TeamsUpgradePolicy esencialmente regula el enrutamiento de llamadas y chats, así como la programación de reuniones (tal y como se expone a través de complementos de Outlook). Debido a que el comportamiento de los clientes de los equipos no está aún en su lugar, no todos los modos están habilitados en el Portal moderno. Desde una perspectiva de enrutamiento, los modos de SfBOnly, SfBWithTeamsCollab y SfBWithTeamsCollabAndMeetings son idénticos. 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>Acción necesaria para las organizaciones que ya se han utilizado TeamsInteropPolicy

Para prepararse para estos cambios en próximos, los clientes deben hacer lo siguiente:

1. Asegúrese de que los usuarios con TeamsInteropPolicy se asignan solo uno de estos tres instancias integradas, qué CallingDefaultClient = ChatDefaultClient y para qué AllowEndUserClientOverride = false. Estas instancias son:
</br>
</br>
   |Identity |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|Falso|Predeterminado|Predeterminado|
   |`DisallowOverrideCallingSfbChatSfb`|Falso|Sfb|Sfb|
   |`DisallowOverrideCallingTeamsChatTeams`|Falso|Microsoft Teams|Microsoft Teams|
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
    |`AllowEndUserClientOverride`|Falso|
    |`CallingDefaultClient`|Predeterminado|
    |`ChatDefaultClient`|Predeterminado|
    |||

    Si alguno de los valores es distinta de la anterior, ejecute el siguiente procedimiento para quitar cualquier personalizaciones específicas del inquilino:

    `Grant-CsTeamsInteropPolicy -PolicyName $null`

## <a name="detailed-mode-descriptions"></a>Descripciones de modo detallado
</br>
</br>

|Modo|Explicación|
|---|---|
|**Islas**|Un solo usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Puede iniciar chats y llamadas de VOIP en ambos Skype para profesionales o los equipos cliente. Nota: Los usuarios con Skype para la empresa hospedados local no se puede iniciar desde los equipos ponerse en contacto con otro Skype para usuarios de empresa.<li>Recibe las llamadas VOIP iniciadas en Skype para la empresa por otro usuario en su Skype para clientes empresariales y chats.<li>Recibe VOIP las llamadas iniciadas en los equipos por otro usuario en su cliente de los equipos.<li>Recibe chats iniciadas en los equipos por otro usuario:<ul><li>Skype para la empresa proporciona el destinatario es hospedado en línea y nunca iniciado sesión en los equipos<li>Equipos en los demás casos.</ul><li>Tiene funcionalidad de RTC, tal y como se indica a continuación:<ul><li>Si el usuario está hospedado en Skype para empresarial local, las llamadas RTC se inició y reciben en Skype para la empresa.<li>Si el usuario está hospedado en línea, el usuario tiene el sistema de teléfono, cuyo caso el usuario:<ul><li>Inicia y recibe llamadas de RTC en los equipos si el usuario está configurado para el enrutamiento directo<li>Inicia y recibe llamadas de RTC en Skype para la empresa si el usuario tiene un Plan de llamar a MS o se conecta a la red RTC a través de cualquier Skype para Business Edition de conector en la nube o una implementación local de Skype para Business Server (voz híbrida)</ul></ul><li>Puede programar reuniones en los equipos o Skype para la empresa (y verá ambas plug-ins de forma predeterminada).<li>Se pueden unir a cualquier Skype para profesionales o los equipos de reunión; la reunión se abrirá en el cliente respectivo.</ul>|
|**SfBOnly**|Un solo usuario ejecuta sólo Skype para la empresa. Este usuario:</br><ul><li>Puede iniciar chats y únicamente a las llamadas de Skype para la empresa.<li>Recibe cualquier llamada en su Skype para clientes empresariales, independientemente de donde se inicia, a menos que el iniciador es un usuario de los equipos con Skype para la empresa hospedados local. * <li>Puede programar sólo Skype para reuniones de negocios, pero se pueden unir a Skype para las reuniones de negocios o los equipos. </br> *Modo de uso de islas con usuarios locales no se recomienda en combinación con otros usuarios en el modo de SfBOnly. Si un usuario de los equipos con Skype para la empresa hospedado local inicia una llamada o chat a un usuario SfBOnly, el usuario SfBOnly no es accesible y recibe una llamada perdida email.*|
|**SfBWithTeamsCollab**|Un solo usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:</br><ul><li>Tiene la funcionalidad de un usuario en el modo de SfBOnly.<li>Ha habilitado los equipos sólo para colaboración en grupo (canales); programación de chat, llamada o reunión están deshabilitadas.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(planeado)|Un solo usuario ejecuta ambos Skype para profesionales y los equipos de lado. Este usuario:<ul><li>Tiene el chat y la funcionalidad de llamada de usuario en el modo de SfBOnly.<li>Ha habilitado los equipos para la colaboración en grupo (canales); Chat y llamar al método están deshabilitadas.<li>Puede programar reuniones de los equipos sólo, pero se pueden unir a Skype para las reuniones de negocios o los equipos.</ul>|
|**TeamsOnly**</br>(requiere SfB Online principal)|Un solo usuario ejecuta sólo los equipos. Este usuario:<ul><li>Recibe cualquier chats y llamadas en su cliente de los equipos, independientemente de donde se inició.<li>Puede iniciar chats y únicamente a las llamadas de los equipos.<li>Puede programar reuniones sólo en los equipos, pero se pueden unir a Skype para las reuniones de negocios o los equipos.<li>Puede seguir usando Skype para teléfonos IP empresarial.</ul> |
|**Heredado**</br>(valor predeterminado)|Este modo se usa durante la transición mientras se retire TeamsInteropPolicy. Los diferentes componentes del sistema se actualizarán para usar TeamsUpgradePolicy en momentos diferentes. Durante esta transición, los usuarios con este modo seguirá respetar el valor TeamsInteropPolicy existente. Esto permite una experiencia de usuario coherente, aunque los diferentes componentes en el servicio se actualizan en momentos diferentes.|
|||

## <a name="summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration"></a>Resumen de los cambios de funcionalidad planeada para simplificar la coexistencia y migración

En función de seguro comentarios de clientes TAP y otros primeros usuarios, Microsoft ha anunciado cambios planeados en abril para simplificar la administración y aumentar la satisfacción del usuario final como las organizaciones migración de Skype para la empresa a los equipos. Estos cambios ofrecerán una experiencia de usuario final más predecible y simplificada, con un modelo de directiva simplificada para la administración de actualización e interoperabilidad. Los cambios que se describe a continuación se implementarán de forma incremental durante los próximos meses. En un nivel alto, existen cuatro cambios funcionales planeados, que se describen a continuación.
</br>
</br>
**CAMBIAR #1: No hay más superpuestas modalidades cuando se establece cliente preferido**
|||
|---|---|
|**TOMA DE DECISIONES**|*Cuando el cliente preferido de un usuario se establece en "Equipos" o "Sfb"*, una determinado modalidad (mensajería instantánea, programación, al llamar a la reunión) sólo estarán disponibles y admitidos en un cliente (los equipos o Skype para la empresa) para ese usuario. (*Cliente preferido* hace referencia a los parámetros DefaultChatClient y DefaultCallingClient en TeamsInteropPolicy.) Solo cuando el cliente preferido se establece en "Predeterminado" (en el futuro se conoce como "Modo de islas") realizarán una modalidad determinada se disponibles y admitidos en ambos clientes. |
|**FUNDAMENTO**|Los comentarios constantes que hemos recibido son que los usuarios se puede confundir por una razón u otra al intentar utilizar a ambos clientes con superpuestos modalidades. Es difícil predecir y comprender por qué mensajes y llamadas de tierra en un cliente frente a otro, y presencia puede ser imprecisos o engañosos.|
|**ESTADO**|Esto es compatible con el modo = TeamsOnly. Compatibilidad con los otros modos estará disponible en los próximos meses. |
|||

**CAMBIAR #2: Unificar a cliente preferido para mensajería y llamar al método**
|||
|---|---|
|**TOMA DE DECISIONES**|Microsoft unificar la administración de cliente preferido para mensajería instantánea y llamar al método. En concreto, DefaultChatClient y DefaultCallingClient deben tener el mismo valor - ambos predeterminado (Islas), tanto en los equipos o en ambos Skype para la empresa.  |
|**FUNDAMENTO**|Si estos no están alineados, presencia en algunos casos será engañosos y confusa. Además, iniciar una llamada desde una conversación existente podría ser confusa debido a que la llamada podría llegar en un cliente distinto a la conversación existente. |
|**ESTADO**|Este cambio se ha implementado en el nivel de directiva mediante TeamsUpgradePolicy, así como en la administración de la experiencia de usuario (portal moderno). Sin embargo, la transición aún no está completa, por lo que los clientes también deben establecer TeamsInteropPolicy. Los clientes sólo deben establecer una de las tres instancias compatibles de TeamsInteropPolicy, que son: DisallowOverrideCallingTeamsChatTeams, DisallowOverrideCallingDefaultChatDefault, DisallowOverrideCallingSfbChatSfb|
|||

**CAMBIAR #3: Sin más usuarios finales opciones de cliente preferido**
|||
|---|---|
|**TOMA DE DECISIONES**|Los usuarios finales ya no tendrá una opción de cliente preferido. (AllowEndUserClientOverride en TeamsInteropPolicy se debe establecer en false). El cliente preferido se basará en modo, que está establecido por el administrador.|
|**FUNDAMENTO**|Análisis de datos de uso se muestra que casi ningún usuario configurar esto. Eliminar esta opción simplifica los escenarios de administración y departamento de soporte técnico y reduce la complejidad de ingeniería. Por último, si el usuario final elegir a un cliente preferido diferente de lo que el administrador haya configurado para enrutamiento de voz en una organización con Enterprise Voice, esto provocaría una experiencia de usuario final confusa debido a que el resultado sería VOIP y las llamadas de RTC de destino en diferentes clientes.|
|**ESTADO**|Este cambio se ha implementado en el nivel de directiva mediante TeamsUpgradePolicy, así como en la administración de la experiencia de usuario (Portal moderno). Sin embargo, la transición aún no se ha completado, por lo que los clientes que usen cmdlets también deben establecer TeamsInteropPolicy en una de las tres instancias compatibles de TeamsInteropPolicy, todos los cuales no permitir invalidación.|
|||

**CAMBIAR #4: Administración basada en cliente "modo"**
|||
|---|---|
|**TOMA DE DECISIONES**|Microsoft introduce el concepto de "modo" para administrar el comportamiento de los clientes como expandidas usar Skype para la empresa de inicio a adoptar los equipos. Los administradores pueden establecer el modo de por usuario y el modo de un usuario unidad qué funcionalidad está disponible en el cliente, así como en las llamadas y chats land. Los administradores a administrar esto a través de la TeamsUpgradePolicy revisada, que se ha actualizado para admitir el modo. Finalmente se en desuso en TeamsInteropPolicy y se elimina, una vez que se han actualizado todos los componentes para leer de TeamsUpgradePolicy.|
|**FUNDAMENTO**|Para simplificar la administración y aumentar la satisfacción del usuario final, interoperabilidad y migración se administrarán utilizando "modo de coexistencia" con TeamsUpgradePolicy. Selección del modo de usuario tendrán prioridad de enrutamiento de charlas y las llamadas entrantes y, en el cliente que el usuario puede iniciar charlas y las llamadas o programar reuniones. Consolidación de TeamsUpgradePolicy y TeamsInteropPolicy también evita que los errores de configuración que podrían dar como resultado si estas dos directivas no se han establecido de forma coherente. |
|**ESTADO**|Ahora, puntee en clientes ver tres modos en el UX. Admin Tal y como se admiten para cambiar #1 territorios, modos adicionales estarán disponibles. Modo de SfBOnly actualmente impide que los usuarios el uso de los equipos, pero lo hará en el futuro. |
|||

## <a name="known-issues"></a>Problemas conocidos

- Al crear nuevas conversaciones en los equipos, chats no respetan aún TeamsUpgradePolicy o TeamsInteropPolicy del usuario de destino. Se prevé una corrección.
- Al crear nuevas conversaciones en Skype para la empresa, chats no aún respetan TeamsUpgradePolicy o TeamsInteropPolicy si la organización todavía no está habilitada para la interoperabilidad de mensajería y SAI (UPS).

## <a name="related-topics"></a>See also

[Get-CsTeamsInteropPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[GRANT CsTeamsInteropPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[Remove-CsTeamsInteropPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[GRANT CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Nueva CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
