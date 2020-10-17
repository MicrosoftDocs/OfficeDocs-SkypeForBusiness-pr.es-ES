---
title: Coexistencia con Microsoft Teams y Skype empresarial
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 'Actualizar de Skype empresarial a equipos: coexistencia'
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
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coexistencia con Teams y Skype empresarial

En este artículo se resume el comportamiento que se puede experimentar al ejecutar tanto los equipos como los clientes de Skype empresarial en la misma organización, independientemente del modo y el método de actualización que se use:

- [Reuniones](#meetings)
- [Interoperabilidad](#interoperability)
- [Conversaciones de Teams: interoperabilidad frente a subprocesos nativos](#teams-conversations---interop-versus-native-threads)
- [Presence](#presence)
- [Federación](#federation)
- [Contactos](#contacts)



## <a name="meetings"></a>Reuniones

Independientemente de su modo, los usuarios siempre pueden unirse a cualquier tipo de reunión a la que se les invite, ya sea Skype empresarial o Teams.  Sin embargo, los usuarios deben unirse a la reunión con un cliente correspondiente que coincida con el tipo de reunión:

- Si la reunión es una reunión de Teams, todos los participantes (ya sean TeamsOnly, Islas o usuarios de Skype empresarial) usan el cliente de Teams para unirse a la reunión. Si Teams no está instalado, se dirigirá al usuario a la web, al intentar unirse a una reunión.

- Si la reunión es una reunión de Skype empresarial, todos los participantes (ya sean TeamsOnly, Islas o usuarios de Skype empresarial) usan el cliente de Skype empresarial para unirse a la reunión. Si el cliente de Skype empresarial no está instalado, se dirigirá al usuario a la web para unirse a través de la aplicación de reunión de Skype.

Al organizar reuniones, el tipo de reunión que se programa se basa en el modo de organizador, como se muestra en la tabla siguiente:

| Modo del organizador    |      Comportamiento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas las reuniones programadas en Teams. El complemento de Skype empresarial no está disponible en Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas las reuniones programadas en Skype empresarial. El complemento de Teams no está disponible en Outlook. | 
| Aplicaciones aisladas | De forma predeterminada, las reuniones se pueden programar en Skype empresarial o en Teams. Ambos complementos están disponibles en Outlook. Sin embargo, opcionalmente, puede requerir que los usuarios de islas programen siempre reuniones en Teams asignándoles una instancia de TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode = Teams.| 


## <a name="interoperability"></a>Interoperabilidad

Teams es compatible con la interoperabilidad ("interoperabilidad") con Skype empresarial en algunos escenarios. La comunicación interoperativa hace referencia a una conversación o una llamada entre un usuario de Skype empresarial y un usuario de Teams.  La comunicación de interoperabilidad solo es posible entre dos usuarios; no es posible hacer llamadas y chats de varios participantes ni agregar usuarios adicionales.

Se crea un chat o una llamada entre dos usuarios cuando se cumple cada una de las siguientes condiciones:

- Un usuario está usando Teams y el otro está usando Skype empresarial.

- El modo del receptor de la comunicación inicial no es islas (de lo contrario, la comunicación se situaría en el mismo cliente) si ambos usuarios están en la misma organización. En los escenarios federados, el usuario que envía está usando Teams y el destinatario no está en modo TeamsOnly. 

- El usuario de los equipos no tiene una cuenta de Skype empresarial doméstica local. 

Dentro de la comunicación de interoperabilidad, chat solo es texto sin formato. Además, el uso compartido de archivos y la pantalla compartida no son posibles *en el chat de interoperabilidad propiamente*dicho. Sin embargo, los usuarios de una conversación de interoperabilidad pueden lograr fácilmente el uso compartido de archivos y/o pantalla mediante la creación de una reunión a petición, desde dentro de la conversación interoperativa, como se describe a continuación:

- Si el usuario de Teams intenta compartir su pantalla, se crea automáticamente una reunión de equipos a petición y se envía un vínculo de invitación a la reunión al cliente del usuario de Skype empresarial. Al hacer clic en el vínculo, el usuario de Skype empresarial abrirá Teams y se unirá a la reunión. Ambos usuarios están ahora en una reunión de Teams y pueden compartir según sea necesario.

- Si el usuario de Skype empresarial está usando un cliente de 2018 o posterior e intenta compartir cualquier contenido, se crea automáticamente una reunión a petición de Skype empresarial y se envía un vínculo de invitación a la reunión al cliente del usuario de Teams. Al hacer clic en el vínculo, el usuario de Teams intentará unirse a la reunión de Skype empresarial. Si el usuario de Teams tiene instalado el cliente de Skype empresarial, se abrirá y se solicitará que el usuario inicie sesión (si aún no lo ha hecho).  Si el usuario de Teams no tiene instalado el cliente de Skype empresarial, se le pedirá que use la versión Web. Una vez que los dos usuarios han iniciado sesión, están en una reunión de Skype empresarial y pueden compartirlo según sea necesario.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversaciones de Teams: interoperabilidad frente a subprocesos nativos

Dado que las comunicaciones interoperativas no admiten todas las características de la conversación de equipos nativos, el cliente de Teams mantiene hilos de conversaciones independientes para la comunicación entre equipos y equipos entre usuarios de Skype empresarial. Estas conversaciones se representan de forma diferente en la interfaz de usuario: los subprocesos de interoperabilidad se pueden diferenciar de un subproceso de equipo nativo normal por:

- Ausencia de controles para texto enriquecido, uso compartido de archivos/pantallas, incapacidad para agregar usuarios.
- Una modificación en el icono del usuario de destino, en la que se muestra una "S" para Skype empresarial.

Estas diferencias se muestran en las siguientes capturas de pantallas:

Una conversación de equipos nativos a equipos con la prueba G3 de usuario

![Diagrama que muestra una conversación entre equipos nativo](media/teams-upgrade-native-thread.png)

Una conversación de interoperabilidad con la misma prueba G3 de usuario

![Diagrama que muestra una conversación interoperativa entre equipos](media/teams-upgrade-interop-thread.png)

Una vez que se crea una conversación, su tipo nunca cambia. Una vez creado, un subproceso de interoperabilidad de Teams siempre se enrutará al cliente de Skype empresarial del usuario de destino. Un subproceso nativo siempre se enrutará al cliente de equipos del usuario de destino.  Si cambia el modo de un usuario de un destinatario, los subprocesos existentes de Teams a ese usuario dejarán de funcionar y aparecerá una nota en la conversación con un vínculo para iniciar una nueva conversación nativa, tal y como se muestra en la siguiente captura de pantalla.


![Diagrama que muestra una conversación con un usuario de Skype empresarial actualizado](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Presence

La presencia de un usuario determinado se basa en la actividad del usuario en el servicio a través del cliente. A continuación, se publica la presencia de otros usuarios para verlo.  Skype empresarial y Teams son servicios independientes con clientes independientes, de modo que cada servicio tiene su propio estado de presencia para un usuario.   También existe una sincronización entre los servicios de presencia en Teams y Skype empresarial online.  Esto permite que un servicio publique potencialmente la presencia del usuario desde el otro servicio, si es necesario. 

El comportamiento de la publicación de presencia se basa en el modo del usuario. Hay tres casos básicos:

- Si un usuario está en modo TeamsOnly, todos los demás usuarios verán la presencia de Teams para ese usuario, independientemente del cliente que usen.

- Si un usuario se encuentra en cualquiera de los modos de Skype empresarial, todos los demás usuarios verán la presencia de Skype empresarial para ese usuario, independientemente del cliente que usen.

- Si un usuario está en modo islas, la presencia Publicada en Skype empresarial y Teams es independiente, por lo que la presencia que se muestra a los usuarios dentro de la misma organización dependerá del cliente del otro usuario. Los usuarios de organizaciones federadas verán la presencia de ese usuario en función de su actividad de Skype empresarial, ya que el tráfico federado hacia un usuario del modo islas aterriza en Skype empresarial.

Por ejemplo, supongamos que el usuario A está en modo islas. Si el usuario A está activo en Teams pero no ha iniciado sesión en Skype empresarial, otros usuarios verían el usuario A como activo en el cliente de su equipo, pero en su cliente de Skype empresarial, verían el usuario A como desconectado. Esto se debe a su diseño, ya que no se puede comunicar con el usuario A si no ejecuta el cliente. 


## <a name="federation"></a>Federación

La Federación de equipos a otro usuario con Skype empresarial requiere que el usuario de Teams se conecte en línea en Skype empresarial. TeamsUpgradePolicy controla el enrutamiento de las llamadas y chats federados entrantes. El comportamiento de enrutamiento federado es el mismo que para los escenarios de espacio empresarial, excepto en el modo "aplicaciones aisladas". Cuando los destinatarios están en modo Aplicaciones aisladas:

- Chats y llamadas iniciadas desde la tierra de un equipo en Skype empresarial si el destinatario se encuentra en un inquilino federado.
- Chats y llamadas iniciadas desde Teams llegan a Teams si el destinatario está en el mismo espacio empresarial.
- Los chats y las llamadas iniciadas desde Skype empresarial siempre se encuentran en Skype empresarial.

Un chat federado puede ser un subproceso nativo o un subproceso de interoperabilidad. Vea [conversaciones de teams---interoperabilidad frente a subprocesos nativos](#teams-conversations---interop-versus-native-threads).

- Si el receptor y el remitente están en modo de actualización de TeamsOnly, la conversación será una experiencia de chat nativa que incluye todas las capacidades enriquecidas de mensajería y llamada. Para obtener más información, lea [experiencia de chats nativos para usuarios externos (federados) en Teams](native-chat-for-external-users.md). 

- Si alguno de los participantes de la conversación no está en el modo de actualización de TeamsOnly, la conversación seguirá siendo una experiencia de interoperabilidad con los mensajes de solo texto. La interfaz de usuario expone los chats federados de manera similar a los mismos subprocesos de interoperabilidad de inquilino, excepto que hay una nota que indica que el usuario es externo.

Para obtener más información, vea [administrar el acceso externo en Microsoft Teams](manage-external-access.md) y la [experiencia de chat nativa para usuarios externos (federados) en Teams](native-chat-for-external-users.md).

## <a name="contacts"></a>Contactos

Teams y Skype empresarial tienen listas distintas de contactos. Esto significa que las adiciones, la eliminación y las modificaciones de los contactos realizados en un sistema no se sincronizan con el otro sistema. Sin embargo, los contactos de Skype empresarial se copian automáticamente en Teams cuando se produce una de las dos sucesos específicos: 

- Para cualquier usuario de Skype empresarial online, la primera vez que inicie sesión en Teams, los contactos de Skype empresarial se copiarán en Teams.  Este comportamiento no está disponible para los usuarios con una cuenta local en Skype empresarial Server.  

- Después de que un usuario se actualice a TeamsOnly (mediante la asignación de TeamsUpgradePolicy o a través de Move-CsUser-MoveToTeams), la próxima vez que un usuario inicie sesión en Teams, los contactos existentes en Skype empresarial se combinarán con los existentes que ya estén en Teams. Este comportamiento se produce si la cuenta de Skype empresarial del usuario está hospedada en local o en línea. 

En ambos casos, la transferencia de contactos de Skype empresarial a teams es asincrónica, por lo que puede transcurrir unos minutos antes de que los contactos aparezcan en Teams. Los dos eventos anteriores son lo que desencadena la copia.  

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

