---
title: Coexistencia con Microsoft Teams y Skype Empresarial
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualizar de Skype Empresarial a Teams- Coexistencia
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0690af8226f3f992dcc12f68c6135c953eb043f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533617"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coexistencia con Teams y Skype Empresarial

Este artículo resume el comportamiento que puede experimentar al ejecutar clientes de Teams y Skype Empresarial en la misma organización, independientemente del modo y el método de actualización usado:

- [Reuniones](#meetings)
- [Interoperabilidad](#interoperability)
- [Conversaciones de Teams- Interoperabilidad frente a hilos nativos](#teams-conversations---interop-versus-native-threads)
- [Presence](#presence)
- [Federación](#federation)
- [Contactos](#contacts)



## <a name="meetings"></a>Reuniones

Independientemente de su modo, los usuarios siempre pueden unirse a cualquier tipo de reunión a la que estén invitados, ya sea Skype Empresarial o Teams.  Sin embargo, los usuarios deben unirse a la reunión con un cliente correspondiente que coincida con el tipo de reunión:

- Si se trata de una reunión de Teams, todos los participantes (ya sean usuarios de TeamsOnly, Islas o Skype Empresarial) usan el cliente de Teams para unirse a la reunión. Si Teams no está instalado, se dirigirá al usuario a la web al intentar unirse a una reunión.

- Si la reunión es una reunión de Skype Empresarial, todos los participantes (ya sean usuarios de TeamsOnly, Islas o Skype Empresarial) usan el cliente de Skype Empresarial para unirse a la reunión. Si el cliente de Skype Empresarial no está instalado, se dirigirá al usuario a la web para unirse a través de la aplicación Reunión de Skype.

Al organizar reuniones, el tipo de reunión que se programa se basa en el modo del organizador, como se muestra en la tabla siguiente:

| Modo de organizador    |      Comportamiento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas las reuniones programadas en Teams. El complemento de Skype Empresarial no está disponible en Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas las reuniones programadas en Skype Empresarial. El complemento de Teams no está disponible en Outlook. | 
| Aplicaciones aisladas | De forma predeterminada, las reuniones se pueden programar en Skype Empresarial o en Teams. Ambos complementos están disponibles en Outlook. Sin embargo, opcionalmente, puede exigir que los usuarios de las Islas programen siempre reuniones en Teams al asignarles una instancia de TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams.| 


## <a name="interoperability"></a>Interoperabilidad

Teams admite la interoperabilidad ("interoperabilidad") con Skype Empresarial en determinados escenarios. La comunicación de interoperabilidad hace referencia a un chat o llamada entre un usuario de Skype Empresarial y un usuario de Teams.  La comunicación de interoperabilidad solo es posible entre dos usuarios; no se admiten chats o llamadas entre varios usuarios ni agregar usuarios adicionales.

Cuando se cumple cada una de las condiciones siguientes, se crea un chat interoperabilidad o una llamada entre dos usuarios:

- Un usuario está usando Teams y el otro está usando Skype Empresarial.

- El modo del destinatario de la comunicación inicial NO es Islas (de lo contrario, la comunicación llegaría al mismo cliente) si ambos usuarios se encuentran en la misma organización. En los escenarios federados, el usuario que envía usa Teams y el destinatario no está en el modo TeamsOnly. 

- El usuario de Teams NO tiene también una cuenta de Skype Empresarial que se encuentra en local. 

Dentro de la comunicación interoperabilidad, el chat es de texto sin formato. Además, el uso compartido de archivos y la pantalla compartida no son posibles *en el chat interoperabilidad propiamente dicho.* Sin embargo, los usuarios en una conversación interoperabilidad pueden conseguir fácilmente el uso compartido de archivos y/o de pantalla mediante la creación de una reunión a petición, desde el chat interoperabilidad, tal y como se describe a continuación:

- Si el usuario de Teams intenta compartir su pantalla, se crea automáticamente una reunión de Teams a petición y se envía un vínculo de invitación a la reunión al cliente del usuario de Skype Empresarial. Al hacer clic en el vínculo, el usuario de Skype Empresarial abrirá Teams y se unirá a la reunión. Ambos usuarios se encuentran ahora en una reunión de Teams y pueden compartirlos según sea necesario.

- Si el usuario de Skype Empresarial usa un cliente de 2018 o posterior e intenta compartir contenido, se crea automáticamente una reunión a petición de Skype Empresarial y se envía un vínculo de invitación a la reunión al cliente del usuario de Teams. Al hacer clic en el vínculo, el usuario de Teams intentará unirse a la reunión de Skype Empresarial. Si el usuario de Teams tiene instalado el cliente de Skype Empresarial, se abrirá y se le pedirá al usuario que inicie sesión (si aún no ha iniciado sesión).  Si el usuario de Teams no tiene instalado el cliente de Skype Empresarial, se le pedirá que use la versión web. Una vez que ambos usuarios han iniciado sesión, se encuentran en una reunión de Skype Empresarial y pueden compartirlos según sea necesario.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversaciones de Teams: interoperabilidad frente a hilos nativos

Como las comunicaciones de interoperabilidad no admiten todas las características de la conversación nativa de Teams, el cliente de Teams mantiene conversaciones independientes para la comunicación de Teams a Teams y Teams a Skype Empresarial. Estas conversaciones se representan de forma diferente en la interfaz de usuario: Las conversaciones de interoperabilidad se pueden diferenciar de una conversación normal de Teams nativa mediante:

- Falta de controles para texto enriquecido, uso compartido de archivos y pantalla, incapacidad de agregar usuarios.
- Una modificación del icono del usuario de destino, que muestra una "S" para Skype Empresarial.

Estas diferencias se muestran en las capturas de pantalla siguientes:

Una conversación de Teams a Teams nativa con la prueba G3 del usuario

![Diagrama que muestra una conversación nativa de Teams a Teams](media/teams-upgrade-native-thread.png)

Una conversación interoperabilidad con la misma prueba G3 del usuario

![Diagrama que muestra una conversación entre equipos y equipos interoperabilidad](media/teams-upgrade-interop-thread.png)

Una vez que se crea una conversación, el tipo nunca cambia. Una vez creada, un subproceso de interoperabilidad en Teams siempre se enruta al cliente de Skype Empresarial del usuario de destino. Una conversación nativa siempre se dirigirá al cliente de Teams del usuario de destino.  Si cambia el modo de un usuario destinatario, las conversaciones de Teams existentes con ese usuario ya no funcionarán y se mostrará una nota en ese chat con un vínculo para iniciar una nueva conversación nativa, tal y como se muestra en la siguiente captura de pantalla.


![Diagrama que muestra un chat con un usuario actualizado de Skype Empresarial](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Presence

La presencia de un usuario determinado se basa en la actividad del usuario en el servicio a través del cliente. A continuación, se publica la presencia para que otros usuarios la vean.  Skype Empresarial y Teams son servicios independientes con clientes independientes, por lo que cada servicio tiene su propio estado de presencia para un usuario.   También hay sincronización entre los servicios de presencia en Teams y en Skype Empresarial Online.  Esto permite que un servicio publique potencialmente la presencia del usuario desde el otro servicio, si es necesario. 

El comportamiento de publicación de presencia se basa en el modo del usuario. Hay tres casos básicos:

- Si un usuario se encuentra en modo TeamsOnly, todos los demás usuarios verán la presencia de Teams para ese usuario, independientemente del cliente que usen.

- Si un usuario se encuentra en cualquiera de los modos de Skype Empresarial, todos los demás usuarios verán la presencia de Skype Empresarial para ese usuario, independientemente del cliente que usen.

- Si un usuario se encuentra en modo Islas, la presencia publicada en Skype Empresarial y Teams es independiente, por lo que la presencia que se muestra a los usuarios de la misma organización dependerá del cliente del otro usuario. Los usuarios de organizaciones federadas verán la presencia de ese usuario en función de su actividad de Skype Empresarial, ya que el tráfico federado a un usuario en modo Islas cae en Skype Empresarial.

Por ejemplo, supongamos que el usuario A está en el modo Islas. Si el usuario A está activo en Teams pero no ha iniciado sesión en Skype Empresarial, otros usuarios verían al Usuario A como activo desde su cliente de Teams, pero en su cliente de Skype Empresarial verían al Usuario A como desconectado. Esto se debe al diseño, ya que no se puede llegar al usuario A si no está ejecutando el cliente. 


## <a name="federation"></a>Federación

La federación de Teams a otro usuario que usa Skype Empresarial requiere que el usuario de Teams esté conectado en Skype Empresarial. TeamsUpgradePolicy controla el enrutamiento de las llamadas y chats federados entrantes. El comportamiento de enrutamiento federado es el mismo que para los escenarios de espacio empresarial, excepto en el modo "aplicaciones aisladas". Cuando los destinatarios están en modo Aplicaciones aisladas:

- Los chats y llamadas iniciados desde Teams se inician en Skype Empresarial si el destinatario se encuentra en un inquilino federado.
- Chats y llamadas iniciadas desde Teams llegan a Teams si el destinatario está en el mismo espacio empresarial.
- Los chats y llamadas iniciados desde Skype Empresarial siempre se des fijon en Skype Empresarial.

Un chat federado puede ser un hilo nativo o un hilo de interoperabilidad. Vea [Conversaciones de Teams ---interop-versus-native-threads.](#teams-conversations---interop-versus-native-threads)

- Si el receptor y el remitente se encuentran en el modo de actualización de TeamsOnly, la conversación será una experiencia de chat nativa que incluye todas las capacidades avanzadas de mensajería y llamadas. Para obtener más información, lea [La experiencia de chat nativa para usuarios externos (federados) en Teams.](native-chat-for-external-users.md) 

- Si alguno de los participantes de la conversación NO está en el modo de actualización de TeamsOnly, la conversación sigue siendo una experiencia interoperabilidad con mensajes de solo texto. La interfaz de usuario expone chats federados de forma similar a los hilos de interoperabilidad del mismo espacio empresarial, excepto que hay una nota que indica que el usuario es externo.

Para obtener más información, consulte [Administrar el acceso externo en Microsoft Teams](manage-external-access.md) y la experiencia de chat nativa para usuarios externos [(federados) en Teams.](native-chat-for-external-users.md)

## <a name="contacts"></a>Contactos

Teams y Skype Empresarial tienen listas de contactos independientes. Esto significa que las adiciones, la eliminación y las modificaciones realizadas en un sistema no se sincronizan con el otro sistema. Sin embargo, los contactos de Skype Empresarial se copian automáticamente en Teams cuando se produce cualquiera de los dos eventos específicos: 

- Para cualquier usuario de Skype Empresarial Online, la primera vez que inicie sesión en Teams, los contactos de Skype Empresarial se copiarán en Teams.  Este comportamiento no está disponible para los usuarios con una cuenta local en Skype Empresarial Server.  

- Después de actualizar un usuario a TeamsOnly (a través de la asignación de TeamsUpgradePolicy o a través de Move-CsUser -MoveToTeams), la próxima vez que un usuario inicie sesión en Teams, los contactos existentes en Skype Empresarial se combinarán con los contactos existentes que ya existen en Teams. Este comportamiento ocurre independientemente de que la cuenta de Skype Empresarial del usuario esté en local o en línea. 

En ambos casos, la transferencia de contactos de Skype Empresarial a Teams es asíncrona, por lo que pueden transfirse unos minutos antes de que los contactos aparezcan en Teams. Los dos eventos anteriores son los que desencadenan la copia.  

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

