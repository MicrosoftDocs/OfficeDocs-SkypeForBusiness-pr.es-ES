---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a7071cf6adbfa423e4c0fa12ac21a5bc777268
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940741"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Métodos &mdash; de actualización para administradores de ti

En este artículo se describen los métodos de actualización para migrar a teams. Este artículo es el segundo de varios que describen los conceptos de actualización y la implementación para administradores de ti.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- **Métodos de actualización** (este artículo)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementación de la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones sobre la red telefónica pública conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, los artículos siguientes describen los conceptos de actualización importantes y los comportamientos de coexistencia:

- [Coexistencia de Teams y Skype empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia: referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Métodos de actualización

Existen dos métodos para actualizar una organización existente con Skype empresarial (ya sea en línea o local) a teams: método de funciones superpuestas y el método de funciones SELECT.  Este artículo le ayuda a elegir el método adecuado para su organización, ya que describe ambos métodos y presenta los pros y los inconvenientes de cada uno. 

- [Método de funciones superpuestas (con el modo Islas)](#overlapping-capabilities-method-using-islands-mode)

   Los usuarios de una organización existente de Skype empresarial se presentan a Teams para que puedan usar ambos clientes durante una fase de transición. Durante este período, la mayoría de las funciones de Teams (pero no todas) están disponibles para ellos. El modo de esta configuración se conoce como Islas y este es el modo predeterminado para cualquier organización existente con Skype Empresarial. Una vez que la organización está lista, el administrador mueve a los usuarios al modo TeamsOnly.

- [Seleccione el método de capacidades (con uno o varios de los modos de Skype empresarial)](#select-capabilities-method-using-skype-for-business-modes)

   El administrador administra la transición (de Skype empresarial a teams) del chat, las llamadas y la funcionalidad de programación de reuniones para los usuarios de su organización.  Cada una de estas funciones está disponible en Skype Empresarial o en Teams, pero no en ambas aplicaciones. Los administradores usan TeamsUpgradePolicy para controlar cuándo una funcionalidad pasa a Teams para los usuarios. Los usuarios que todavía no están en el modo TeamsOnly continúan usando Skype Empresarial para chat y llamadas, y los dos conjuntos de usuarios pueden comunicar entre sí mediante la funcionalidad de interoperabilidad. Los administradores gestionan la transición mediante la migración progresiva de más usuarios al modo TeamsOnly.  

Después de comprender y elegir el método de actualización, puede obtener información sobre las [herramientas para administrar la actualización de su organización a teams](upgrade-to-teams-on-prem-tools.md).

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de funciones superpuestas (con el modo Islas)

Con el método de funciones superpuestas, los usuarios pueden usar tanto equipos como clientes de Skype Empresarial para chat, llamadas VoIP y reuniones. Este estado se denomina "islas" porque el tráfico de comunicaciones de Skype empresarial y Teams sigue siendo independiente (incluso para el mismo usuario) y los dos clientes diferentes nunca se comunican entre sí (para los usuarios de la misma organización). Por ejemplo, supongamos que el usuario del destinatario A está en modo islas:

- La comunicación iniciada desde el cliente de Skype Empresarial de otro usuario siempre llegará al cliente de Skype Empresarial del Usuario A.

- La comunicación iniciada desde el cliente de Teams de otro usuario siempre se pondrá al cliente de equipos del usuario A, *si el otro usuario se encuentra en la misma organización*. 

- La comunicación iniciada desde el cliente de Teams de otro usuario siempre estará en el cliente de Skype empresarial del usuario A, *si el otro usuario se encuentra en una organización federada*.

El modo islas es el modo predeterminado de TeamsUpgradePolicy para cualquier organización existente que aún no haya actualizado a TeamsOnly. Cuando asigna una licencia de Microsoft 365 o de Office 365, se asignan licencias de equipo y de Skype empresarial online de forma predeterminada. (Esto es cierto incluso si el usuario está alojado en local en Skype empresarial Server. Si el usuario se ha alojado en local o en línea, deje habilitada la licencia de Skype empresarial online, porque actualmente es necesaria para la funcionalidad de Teams completa. De hecho, si no ha tomado ningún paso para cambiar la configuración predeterminada, es posible que ya tenga un uso significativo de los equipos de su organización.  Este es uno de los beneficios del enfoque de funcionalidades superpuestas. Permite una adopción rápida y controlada por el usuario final dentro de una organización.

Para que este método funcione de forma eficaz, es necesario que todos los usuarios ejecuten ambos clientes al mismo tiempo. Los chats y llamadas entrantes desde la organización a un usuario en el modo Islas pueden llegar al cliente de Skype Empresarial o al de Teams, circunstancia esta que no está bajo el control del destinatario. Si el remitente y el destinatario están en la misma organización, dependen del cliente que use el remitente para iniciar la comunicación. Si el remitente y el destinatario están en distintas organizaciones, las llamadas entrantes y chats a un usuario en modo Islas siempre se encuentran en el cliente de Skype Empresarial.  

Por ejemplo, si un destinatario de modo islas ejecuta Skype empresarial pero no equipos, y alguien de la misma organización lo envía mensajes de Teams, el destinatario del modo islas no verá el mensaje (pero al final recibirá un mensaje de correo electrónico que indica que han perdido un mensaje en Teams). De manera similar, si un usuario está ejecutando Teams pero no es Skype Empresarial y alguien le envía un mensaje desde Skype Empresarial, el usuario no verá este chat.  Recibirán un mensaje de correo electrónico en el que se indica que había un mensaje perdido. El comportamiento en cada uno de estos casos es similar para las llamadas. Si los usuarios no ejecutan ambos clientes, se pueden producir situaciones frustrantes.

Cuando el usuario A está en modo islas, la presencia del usuario A tal y como lo ven otros usuarios en Teams y en Skype empresarial es independiente:

- Los otros usuarios que utilicen Teams verán la presencia en función de la actividad del Usuario A en Teams. 
- Los otros usuarios que utilicen Skype Empresarial verán la presencia en función de la actividad del Usuario A en Skype Empresarial. 

Esto significa que los otros usuarios pueden ver diferentes estados de presencia para el Usuario A en función del cliente que utilicen. Para obtener más información, consulte [Presencia](upgrade-to-teams-on-prem-coexistence.md#presence).

Una vez que esté listo para actualizar a los usuarios al modo TeamsOnly, puede actualizar los usuarios de forma individual o puede actualizar todo el inquilino a la vez con la Directiva para todo el inquilino. Una vez que un usuario se actualiza al modo TeamsOnly, este recibe todas las conversaciones y llamadas entrantes en Teams. (Tenga en cuenta que la migración de reuniones de Skype empresarial a reuniones de Teams solo se desencadena cuando se aplica TeamsUpgradePolicy a usuarios individuales, no por espacio empresarial. Consulte [migración de reuniones](upgrade-to-teams-on-prem-tools.md#meeting-migration) para obtener más información.)

Sin embargo, los destinatarios no actualizados en modo Islas pueden seguir recibiendo chats y llamadas de un usuario TeamsOnly en los clientes de Skype Empresarial o de Teams.  Esto se debe a que el cliente de Teams mantiene hilos de conversación independientes para las comunicaciones Teams-Teams y Teams-Skype Empresarial, incluso para el mismo usuario.  (Consulte [conversaciones de Teams: interoperabilidad frente a subprocesos nativos](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)).  Por ejemplo, supongamos que el usuario A de las islas usa Teams para enviar un mensaje a TeamsOnly usuario B. Cuando el usuario B responda a esa conversación, la comunicación se situará en el cliente de equipos del usuario A. Supongamos que el usuario A usa su cliente de Skype empresarial para enviar un mensaje a TeamsOnly usuario B. el usuario B recibirá la conversación en Teams, pero será una conversación independiente en el cliente de equipos del usuario B en comparación con la otra conversación. Si el usuario B responde a esta conversación con el usuario A, se colocará en el cliente de Skype empresarial del usuario A. 

En la tabla siguiente se resume la experiencia de Teams para los modos Islas y TeamsOnly:  

| Experiencia de Teams | En modo Islas | En modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats y llamadas entrantes recibidos en:|  Teams o Skype Empresarial | Teams |
| Llamadas RTC recibidas en: | Skype Empresarial <br>(El uso de la función RTC en equipos no es compatible con el modo Islas).    | Teams |   
 |Presencia  | La presencia en Skype Empresarial y en Teams es independiente. Los usuarios pueden ver diferentes estados para el mismo usuario en modo Islas en función del cliente que utilicen. | La presencia está basada únicamente en la actividad del usuario en Teams. El resto de usuarios, independientemente del cliente que usen, verán esta presencia. | 
 | Programación de reuniones   | De forma predeterminada, los usuarios pueden programar reuniones en Teams o Skype empresarial. Se mostrarán ambos complementos en Outlook. |   Los usuarios solo pueden programar reuniones en Teams. En Outlook, solo está disponible el complemento Teams. | 

En la tabla siguiente se resumen las ventajas e inconvenientes de usar el método de funciones superpuestas para migrar su organización a Teams.

| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Permite una rápida adopción en la organización.| Existe un potencial de confusión para el usuario final debido a que existen dos clientes con funcionalidades similares pero interfaces de usuario diferentes. Además, no tienen control sobre el cliente al que llegan los mensajes de chat o llamadas entrantes. |
| Permite a los usuarios aprender y familiarizarse con Teams y seguir teniendo acceso completo a Skype Empresarial. | Existe un potencial de insatisfacción para el usuario final debido a la pérdida de mensajes si el usuario no ejecuta los dos clientes. Los usuarios pueden quejarse de que no reciben mensajes.|
| Mínimo esfuerzo de administración para empezar a trabajar en Teams. | Puede ser desafiante "salir del modo islas" y pasar al modo TeamsOnly si no todos los miembros de la organización usan equipos, especialmente si no todos los usuarios están activos en Teams. Por ejemplo, una vez que un subconjunto de usuarios se actualiza al modo TeamsOnly, los usuarios solo se enviarán en Teams. Para el resto de la población en el modo islas, esos mensajes siempre estarán en el equipo. Pero si algunos de esos rellenados no se ejecutan en Teams, percibirán estos mensajes como perdidos. |
|  | Cuando se usan equipos, los usuarios que tienen una cuenta local en Skype empresarial Server no admiten la compatibilidad con la interoperabilidad o la Federación.  Esto puede crear confusión si tiene una combinación de usuarios de islas, algunas personas que se encuentran en Skype empresarial online y otras en Skype empresarial local.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Seleccionar el método de funcionalidades (con modos de Skype Empresarial)

Es posible que algunas organizaciones prefieran proporcionar a los usuarios finales una experiencia más predecible y sencilla a medida que su organización pase de Skype empresarial a equipos. En este modelo, los administradores de ti usan uno de los modos de Skype empresarial en TeamsUpgradePolicy para designar de forma explícita qué usuarios permanecen en Skype empresarial antes de migrar al modo TeamsOnly. Puesto que están listos para desplazar a los usuarios seleccionados al modo TeamsOnly, el administrador actualiza el modo de que esos usuarios TeamsOnly. A medida que progresa la implementación, se transfieren cada vez más usuarios de Skype empresarial a modo TeamsOnly.  Durante esta transición:

- Los usuarios que siguen en Skype Empresarial reciben todas las conversaciones y llamadas entrantes en el cliente de Skype Empresarial, independientemente de si la comunicación proviene del cliente de Teams o de Skype Empresarial del otro usuario. Además, para estos usuarios de Skype empresarial, la funcionalidad de llamadas y chats en el cliente de equipos están deshabilitadas para ayudar a evitar la confusión del usuario final y garantizar el enrutamiento adecuado. 

- Los usuarios en modo TeamsOnly reciben todas las conversaciones y las llamadas entrantes en el cliente de su equipo, independientemente de dónde se originó la comunicación: Teams, Skype empresarial o cualquier tipo de usuario federado. 

A diferencia del método islas, en el método de selección de funciones, los usuarios de Skype empresarial y de TeamsOnly pueden comunicarse entre sí. La comunicación entre un usuario de Skype Empresarial y un usuario de Teams se conoce como interoperabilidad (o «interop»). La comunicación interoperativa es posible en una base de uno a uno para conversaciones y llamadas entre usuarios de Skype empresarial y otros usuarios de Teams; sin embargo, es posible que algunas funcionalidades avanzadas no estén disponibles. (Consulte [interoperabilidad](upgrade-to-teams-on-prem-coexistence.md#interoperability)). Además, los usuarios invitados siempre pueden unirse a una reunión de Skype empresarial o de Teams, pero deben usar un cliente que se corresponda con el tipo de reunión. Para obtener más información, consulte [Reuniones](upgrade-to-teams-on-prem-coexistence.md#meetings).

Como los usuarios de una transición de funciones de selección no suelen estar en modo islas, la presencia de un usuario es coherente, independientemente del cliente que use el otro usuario. Si el usuario está en uno de los modos de Skype Empresarial, el resto de usuarios verán la presencia en función de la actividad de este usuario en Skype Empresarial. De forma similar, si un usuario está en modo TeamsOnly, el resto de usuarios verán la presencia en función de la actividad de este usuario en Teams. Para obtener más información, consulte [Presencia](upgrade-to-teams-on-prem-coexistence.md#presence).

Para una organización que aún no ha empezado a usar Teams, el administrador debe cambiar el modo de todo el inquilino de islas a SfbWithTeamsCollab. (En el caso de organizaciones que ya tienen algunos usos de Teams, el administrador debe tener a los usuarios "abuelo" activos en Teams para asegurarse de que este cambio no se aplique a ellos. Para obtener más información, vea [un método de selección de funciones para una organización que ya está usando el modo islas](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Cuando el modo cambia de islas a SfbWithTeamsCollab, los usuarios que nunca hayan usado Teams no verán ninguna diferencia en el modo en que usan Skype empresarial. Sin embargo, si el usuario empieza a usar Teams, solo estará expuesto a funcionalidades como Teams, canales y archivos. El chat, las llamadas y la programación de reuniones no estarán disponibles en Teams, puesto que el administrador ha designado (por ahora) Skype Empresarial como el cliente deseado para estas funciones.  

Nota: cuando el usuario A cambia de islas a uno de los modos de Skype empresarial, el cliente de Teams de cualquier otro usuario que se comunique con el usuario A debe saber que el modo del usuario a ha cambiado para que pueda enrutar la comunicación al cliente a adecuado para el usuario A.  Para los usuarios que ya hayan establecido chats nativos entre equipos con el usuario A, pueden tardar hasta 36 horas en que los clientes de los equipos de estos otros usuarios sean conscientes del cambio de modo de islas a cualquier modo de Skype empresarial.   Por el contrario, otros clientes detectan cambios en el modo de TeamsOnly de un usuario existente en un plazo de 2 horas.

Cuando los administradores estén listos, podrán pasar de una vez el chat, las llamadas y la programación de reuniones de un usuario determinado a Teams actualizando el modo del usuario a TeamsOnly.  

Como alternativa, el administrador de puede mover primero la programación de reuniones a Teams, dejando que el chat y las llamadas funcionen en Skype Empresarial mediante el modo SfBWithTeamsCollabAndMeetings. Este modo permite que las organizaciones pasen a los equipos de las reuniones, si aún no están listos para pasar al modo TeamsOnly (normalmente porque es posible que se necesite más tiempo para migrar la funcionalidad de RTC existentes). Este escenario transitorio se denomina [Reuniones primero](meetings-first.md).

En la tabla siguiente se resumen las ventajas e inconvenientes de usar los modos de Skype Empresarial como paso transitorio hacia el modo TeamsOnly.


| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Direccionamiento predecible para el usuario final.  Todas las llamadas y chats llegan a Skype Empresarial o a Teams (pero no a ambos), en función de la selección del administrador.  | Las conversaciones de interoperabilidad no son compatibles con el texto enriquecido, el uso compartido de archivos y el uso compartido de pantalla.  Esto se puede llevar a cabo con las reuniones a petición, pero no es tan fácil.  |
| Elimine la confusión entre usuarios finales porque una determinada función solo está disponible en un cliente.  | Los usuarios no pueden probar ambos clientes en paralelo para el mismo conjunto de funciones. Esto puede ser especialmente un factor si los usuarios perciben que el cambio de Skype empresarial a teams es un cambio de paradigma importante. |
| Permite una introducción incremental de Teams.  |  | |
| El administrador tiene el control total de la transición de Skype empresarial a teams. |  | | 
| Permite a una organización usar Teams para reuniones, incluso si todavía no está lista para cambiar plenamente al modo TeamsOnly. |  | |
| La presencia de un usuario determinado es la que ven el resto de usuarios, independientemente del cliente que utilicen.  |  | |

## <a name="summary-of-upgrade-methods"></a>Resumen de los métodos de actualización

En la tabla siguiente se resumen los métodos de actualización:

| Funciones superpuestas (con el modo Islas)     |      Seleccionar capacidades (con los modos de Skype empresarial) |
| :------------------ | :---------------- |
| Antes de actualizar a TeamsOnly, los usuarios deben ejecutar ambos clientes de forma simultánea, ya que los chats y llamadas entrantes pueden dirigirse a cualquiera de los dos clientes.   | El chat y las llamadas llegan a un solo cliente, en función del modo del destinatario. Los usuarios no actualizados pueden ejecutar ambos clientes, pero no hay ningún solapamiento funcional (las llamadas y el chat no están disponibles en Teams).  Los administradores también pueden controlar si los usuarios programan reuniones en Teams o Skype empresarial.   |
| Los usuarios pueden usar Skype empresarial y Teams en paralelo para obtener la misma funcionalidad.   | Permite a los administradores introducir una nueva funcionalidad de Teams para los usuarios finales (equipos y canales), sin proporcionar la misma funcionalidad que también existe en Skype empresarial.   |
|La interoperabilidad entre Skype Empresarial y Teams no existe mientras ambos usuarios se encuentren en modo Islas. Una vez que se actualizan algunos usuarios a TeamsOnly, es posible que se produzca una conversación interoperativa entre los usuarios y otros usuarios que aún se encuentren en modo islas. Sin embargo, el usuario de las islas podría optar por usar Teams y evitar la conversación de interoperabilidad. | La interoperabilidad es necesaria para la comunicación entre los usuarios de Skype Empresarial y Teams.   |


## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

