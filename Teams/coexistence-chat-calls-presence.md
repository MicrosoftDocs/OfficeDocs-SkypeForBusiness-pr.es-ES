---
title: Coexistencia con Skype Empresarial
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Coexistencia entre Teams & Skype Empresarial, incluidos parámetros de enrutamiento, enrutamiento de llamadas & chat, chats & llamadas desde conversaciones preexistentes, & presencia.
ms.openlocfilehash: 9dd2baa717466b0f414168356256b6d78ce33f6a
ms.sourcegitcommit: e5e60079cf9d62627de6b26dd4badd353bcc190c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48661352"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

La coexistencia y la interoperabilidad entre los clientes y usuarios de Skype Empresarial y Teams se define en los modos TeamsUpgrade, que se describen en la guía de migración e interoperabilidad para las organizaciones que usan Teams junto con [Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md)

A un usuario determinado se le asignará siempre un modo TeamsUpgrade, ya sea de forma predeterminada o explícita por el administrador. El valor predeterminado es *Islas.* Los usuarios actualizados a Teams tienen el *modo de TeamsOnly.* *SfBOnly,* *SfBWithTeamsCollab* y *SfBWithTeamsCollabAndMeetings* también son posibles modos.


## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo de cambio a Teams del destinatario es clave para determinar el comportamiento de los chats, las llamadas y la presencia, tanto en un inquilino como en todos los inquilinos federados.

Si el remitente usa Teams, la decisión de enrutamiento se toma al crear un nuevo hilo de conversación. Los hilos de conversación existentes en Teams siempre conservan el método de enrutamiento que se determina cuando se creó el hilo: Teams admite conversaciones persistentes.

 Los métodos de enrutamiento de subprocesos son:  

- *nativo* de una conversación de Teams a Teams en el espacio empresarial
- *interoperabilidad* de una conversación de Teams a Skype Empresarial en el inquilino
- *federado para* una conversación federada entre inquilinos

Los parámetros que determinan el método de enrutamiento de hilos son:

- El modo TeamsUpgrade del destinatario
- El cliente que ha usado el remitente
- Si la conversación es nueva o parte de un hilo existente
- Si la conversación es dentro del inquilino o federado
- Si la conversación es posible
    - *La interoperabilidad dentro* del espacio empresarial requiere que el espacio empresarial sea en línea puros o una implementación híbrida de Skype Empresarial. Los inquilinos locales puramente no pueden tener interoperabilidad dentro del espacio empresarial.
    - *La federación entre inquilinos* siempre requiere una configuración de federación de Skype Empresarial correcta, así como una configuración de federación de Teams adecuada de ambos inquilinos. Skype Empresarial híbrido no es necesario para ninguno de los inquilinos.
    - Si la cuenta de Skype Empresarial del creador está local, ese usuario no podrá usar el cliente de Teams para interoperabilidad en el espacio empresarial ni para federación. Ese usuario solo puede usar el cliente de Skype Empresarial para interoperabilidad y federación.
    - La comunicación entre equipos de Teams siempre es posible dentro del espacio empresarial.

> [!NOTE]
> Si el receptor y el remitente se encuentran en el modo de actualización de TeamsOnly, la conversación será una experiencia de chat nativa que incluye todas las capacidades avanzadas de mensajería y llamadas. Para obtener más información, lea [La experiencia de chat nativa para usuarios externos (federados) en Teams.](native-chat-for-external-users.md) Si alguno de los participantes de la conversación NO está en el modo de actualización de TeamsOnly, la conversación sigue siendo una experiencia interoperabilidad con mensajes de solo texto.

## <a name="chat-and-call-routing"></a>Enrutamiento de llamadas y chats

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Enrutamiento en el espacio empresarial para nuevos chats o llamadas 

Las tablas siguientes capturan el enrutamiento de llamadas y chats dentro del espacio empresarial, y son válidas para llamadas o chats nuevos que no se inician desde una conversación ya existente. Aquí se describe qué cliente recibirá una nueva llamada o chat, si es originado por un usuario a la izquierda, a un usuario destinatario en el inquilino a la derecha.

Los mensajes enviados a los usuarios de TeamsOnly siempre se enruta a Teams. Los mensajes enviados a usuarios de SfB siempre se enruta a Skype Empresarial, si la conversación \* es posible como se describió anteriormente. Los mensajes enviados a los usuarios de las Islas siempre se enruta al mismo cliente desde el que se enviaron.

Las tablas siguientes muestran qué cliente en un modo determinado recibirá una llamada del autor (tres columnas situadas más a la izquierda), según el modo del autor, el cliente elegido y dónde se encuentra el cliente de Skype Empresarial (local o en línea).

En las tablas siguientes: 
- **SfB \** _ representa cualquiera de los siguientes modos: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *El texto en cursiva* resalta una conversación de interoperabilidad.

- **No es** posible representa una situación en la que el chat o la llamada no es posible. El creador debe usar Skype Empresarial en su lugar en estos casos. Este es uno de los motivos por los que la guía prescriptiva de Microsoft para los clientes locales/híbridos es usar un modo que no sea Islas (normalmente SfBWithTeamsCollab) como punto de partida de su viaje de actualización a Teams.

**Tabla 1a: nuevo chat en el espacio empresarial o enrutamiento de llamadas a un destinatario del modo islas**

| <br/><br/> Modo | Creador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Route-->| Destinatario <br/><br/> Aplicaciones aisladas  |
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas | Microsoft Teams <br/> Skype Empresarial<br/> Microsoft Teams<br/> Skype Empresarial| En línea<br/> En línea<br/> On-prem<br/>On-prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype Empresarial<br/> Microsoft Teams<br/> Skype Empresarial|
|SfB\* <br/> | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv;|Skype Empresarial<br/>Skype Empresarial<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabla 1b: nuevo chat en el espacio empresarial o enrutamiento de llamadas a un destinatario en modo \* SfB**

| <br/><br/> Modo   | Creador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Route--> |   Destinatario <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Aplicaciones aisladas |Microsoft Teams<br/>Skype Empresarial<br/>Microsoft Teams <br/>Skype Empresarial  |En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial<br/> **No posible** <br/>Skype Empresarial<br/> |
|SfB\* <br/> | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv; |  Skype Empresarial<br/>Skype Empresarial<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype Empresarial* <br/>| 
| | | | | |

**Tabla 1c: nuevo chat en el espacio empresarial o enrutamiento de llamadas a un destinatario de modo TeamsOnly**

| <br/><br/> Modo   | Creador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Route-->|   Destinatario <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Aplicaciones aisladas   |Microsoft Teams<br/>Skype Empresarial<br/>Microsoft Teams <br/>Skype Empresarial<br/>|En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> On-prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Enrutamiento federado para nuevos chats o llamadas
  
Las tablas siguientes capturan el enrutamiento de llamadas y chats federados, y son válidas para las nuevas llamadas o chats. Describen qué cliente recibirá una nueva llamada o chat, si es originado por un usuario a la izquierda, a un usuario de destino federado a la derecha.

En resumen, si la conversación es posible como se describió anteriormente, los mensajes enviados a los usuarios de TeamsOnly siempre llegarán a Teams; Los mensajes enviados a usuarios de SfB siempre llegarán a Skype Empresarial; los mensajes enviados a los usuarios de las Islas siempre llegarán a Skype Empresarial independientemente del cliente desde el que se \* enviaron. El enrutamiento para chats federados y llamadas difiere del enrutamiento dentro del inquilino en que los usuarios de las Islas siempre recibirán una comunicación federada en Skype Empresarial.

Esto se debe a que no podemos suponer que un partner federado de Skype Empresarial ya usa Teams si se encuentra en el modo Islas. Las islas son el modo predeterminado, pero no podemos suponer que todos los usuarios de las islas ejecutan Teams. Al enrutar a Skype Empresarial, garantizamos que no se produce un error en la comunicación con un usuario de las Islas. Si se enrutó a Teams, se podría perder esa comunicación si el destino no usa Teams. El enrutamiento a Skype Empresarial garantiza que siempre se recibirá el mensaje.  

> [!NOTE]
> La implementación actual de la federación de Teams se basa en la federación de Skype Empresarial, por lo que aprovecha la infraestructura de interoperabilidad (que requiere que el inquilino del creador sea en línea puros o skype empresarial híbrido) y proporciona un conjunto reducido de capacidades en comparación con un hilo nativo. Esperamos proporcionar Teams nativo a la federación de Teams en el futuro, momento en el que la conversación será nativa y proporcionará funcionalidades completas.

En las tablas siguientes se describe qué cliente recibirá una llamada del autor (tres columnas situadas más a la izquierda), según el modo del autor, el cliente elegido y dónde se encuentra el cliente de Skype Empresarial (local o en línea).

**Tabla 2a: Enrutamiento de llamadas o chats nuevos federados a un destinatario de las islas**

| <br/><br/>Modo   | Creador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Route--> | Destinatario<br/><br/> Aplicaciones aisladas |
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas |Microsoft Teams<br/>Skype Empresarial <br/>Microsoft Teams <br/>Skype Empresarial  |En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial <br/> **No posible**   <br/> Skype Empresarial |
| SfB\* |Skype Empresarial <br/>Skype Empresarial |Online<br/> On-prem<br/> | &boxv;<br/>&boxv;|Skype Empresarial <br/>Skype Empresarial |
| TeamsOnly |Teams |Online| &boxv;|*Skype Empresarial* |
|  | | | | 

**Tabla 2b: enrutamiento de llamadas o chat nuevo federado a un destinatario en modo \* SfB**

| <br/><br/>Modo   | Creador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Route-->|  Destinatario<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas |Microsoft Teams<br/>Skype Empresarial <br/>Microsoft Teams <br/>Skype Empresarial <br/>|En línea<br/> En línea<br/> On-prem<br/> On-prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial <br/> **No posible** <br/>Skype Empresarial <br/> |  
| SfB\* |Skype Empresarial <br/>Skype Empresarial  |Online<br/> On-prem<br/>  |&boxv;<br/>&boxv; | Skype Empresarial <br/>Skype Empresarial  |
| TeamsOnly | Teams|Online |&boxv; |*Skype Empresarial*  |
|  | | | | |

**Tabla 2c: nuevo chat federado o enrutamiento de llamadas a un destinatario de modo TeamsOnly**

| <br/><br/>Modo | Creador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Route-->|  Destinatario<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas  |Microsoft Teams<br/>Skype Empresarial <br/>Microsoft Teams <br/>Skype Empresarial <br/>|En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**No posible** <br/>*Teams* |
| SfB\* |Skype Empresarial <br/>Skype Empresarial  | Online<br/> On-prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats y llamadas de conversaciones preexistentes

### <a name="from-teams"></a>Desde Teams

Las llamadas o chats iniciados desde un hilo persistente existente en Teams se enruta de la misma manera que esa conversación, si esa opción de enrutamiento sigue estando disponible.

Si el hilo persistente existente en Teams era una conversación nativa (es decir, enrutada a Teams), otros mensajes de chat y llamadas de esa conversación irán a Teams. Si se trataba de un subproceso de interoperabilidad (es decir, enrutado a Skype Empresarial), las llamadas y mensajes de chat adicionales irán a Skype Empresarial (siempre que las opciones de enrutamiento estén disponibles).

> [!NOTE]
> Es posible que los subprocesos existentes en Teams ya no sean enrutables, como cuando la conversación era un hilo de interoperabilidad con un usuario que ahora se ha actualizado a Teams. Puesto que se creó como un subproceso de interoperabilidad, la conversación se enruta a Skype Empresarial, pero ese usuario ya no puede usar Skype Empresarial para chatear y llamar. En ese caso, la conversación se deshabilitará y no permitirá una comunicación posterior.

### <a name="from-skype-for-business"></a>Desde Skype Empresarial

Los hilos de Skype Empresarial no se conservan más allá de los 10 minutos. El tiempo de espera de la sesión SIP es superior a 10 minutos. Los chats y llamadas de un hilo existente en Skype Empresarial antes de que expire la sesión SIP se enruta de la misma manera que la conversación. Las llamadas y chats de un hilo existente en Skype Empresarial más allá del tiempo de espera de la sesión SIP se enruta al Skype Empresarial del usuario remoto, independientemente del cliente del que provenía el hilo original del otro usuario.

### <a name="availability"></a>Disponibilidad

Están disponibles tanto los comportamientos federados como dentro del espacio empresarial descritos anteriormente, con las siguientes limitaciones:

- Los asistentes externos cuyos inquilinos residen en una implementación de GoLocal diferente o en una ubicación geográfica no verán el chat de mensajería instantánea en una reunión "federada"
- No se admiten la federación ni la interoperabilidad entre O365 multitenant y las nubes sovereign

## <a name="presence"></a>Presence

Si tiene una situación en la que algunos de los usuarios usan el cliente de Teams y otros usan el cliente de Skype Empresarial, es posible que tenga varios usuarios que usan ambos clientes. Desea que los estados de presencia se compartan con todos los usuarios sin tener en cuenta el cliente que tiene un usuario individual. Cuando esto se comparte en toda la organización, los usuarios pueden determinar mejor si es apropiado iniciar un chat o realizar una llamada.

Por ejemplo, si el chat o la llamada de un autor debe llegar al cliente de Skype Empresarial del destino, la presencia del cliente de Skype Empresarial es lo que debe mostrarse al autor. Si debe llegar al cliente de Teams del destino, entonces es la presencia del cliente de Teams la que debe mostrarse.

Para saber qué comportamiento esperar, debe comprender que la presencia se comparte en función del modo de coexistencia de un usuario:

* Si un usuario está en modo TeamsOnly, cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá la presencia de Teams del usuario de Teams
* Si un usuario se encuentra en cualquiera de los modos SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), cualquier otro usuario (tanto en Teams como en Skype Empresarial) verá la presencia del usuario de SfB en Skype Empresarial. \*
* Si un usuario está en modo Islas (o heredado), la presencia en Teams y la presencia en Skype Empresarial son independientes (los valores no coinciden) y otros usuarios verán una o la otra presencia del usuario de las Islas, dependiendo de si se encuentran en el mismo inquilino o en un inquilino federado y qué cliente usan.
    * Desde Teams, cualquier otro usuario del mismo inquilino verá la presencia de Teams del usuario de las Islas; esto está alineado con la tabla de enrutamiento del espacio empresarial anterior
    * Desde Teams, cualquier otro usuario de un inquilino federado verá la presencia de Skype Empresarial del usuario de las Islas; está alineado con la tabla de enrutamiento federada anterior
    * Desde Skype Empresarial, cualquier otro usuario verá la presencia de Skype Empresarial del usuario de las Islas (tanto in-tenant como federado); esto está alineado con las tablas de enrutamiento anteriores


### <a name="in-tenant-presence"></a>Presencia en el espacio empresarial

Los mensajes enviados a los usuarios de TeamsOnly siempre llegarán a Teams. Los mensajes enviados a usuarios de SfB siempre llegarán a Skype Empresarial, si la conversación es posible \* tal y como se ha descrito anteriormente. Los mensajes enviados a los usuarios de las Islas siempre llegarán al cliente del que se han originado.

En la tabla se describe la presencia de Publisher que verá un watcher, según el modo del editor y el cliente del watcher (para un nuevo hilo).

**Tabla 3: presencia dentro del espacio empresarial (nueva conversación)**

|Watcher <br/><br/>Cliente|<br/><br/>Route--> |<br/><br/>Aplicaciones aisladas |Publisher <br/><br/>SfB\* |<br/>Solo equipos|
|--- |--- |--- |--- |---|
|Skype Empresarial |&boxv;|Skype Empresarial | Skype Empresarial | Teams|
|Teams |&boxv; |Microsoft Teams |Skype Empresarial |Teams |
| | | | |

### <a name="federated-presence"></a>Presencia federada

La presencia federada se basa en la capacidad de acceso federada que se muestra en la tabla 2.

En la tabla siguiente se describe la presencia de Publisher que verá un watcher, según el modo del editor y el cliente del watcher (para un nuevo subproceso). En la práctica, el cliente del Watcher no tiene diferencias en la federación en esta fase.

**Tabla 4: presencia federada (nueva conversación)**

|Watcher <br/><br/> Cliente |<br/><br/>Route-->|<br/><br/> Aplicaciones aisladas  |Publisher <br/><br/> SfB\* |<br/><br/> Solo equipos |
|--- |--- |--- |--- |---|
|Skype Empresarial |&boxv; |Skype Empresarial  | Skype Empresarial  | Teams  |
|Microsoft Teams | &boxv;|Skype Empresarial |Skype Empresarial |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presencia en conversaciones existentes

Para alinear la presencia y el alcance en los subprocesos existentes, la presencia del destino expuesta en ese subproceso debe alinearse con el enrutamiento de la conversación, suponiendo que el enrutamiento es posible.

En particular, si un destinatario al que previamente tenía una conversación de interoperabilidad persistente con se actualizó a Teams, esa conversación ya no reflejará la presencia precisa y ya no se enrutable. Debería iniciar una nueva conversación.

## <a name="related-links"></a>Vínculos relacionados
[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Vídeo: Administrar coexistencia e interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
