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
description: Comportamiento de coexistencia entre Teams & Skype Empresarial, incluidos parámetros de enrutamiento, enrutamiento de llamadas & chat, chats & llamadas desde subprocesos preexistentes, & presencia.
ms.openlocfilehash: 603356df5e6f5006ea67f6a84141acf1347c1235
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122344"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

La coexistencia e interoperabilidad entre clientes y usuarios de Skype Empresarial y Teams se define mediante los modos TeamsUpgrade, que se describen en Las instrucciones de migración e interoperabilidad para las organizaciones que usan Teams junto con [Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md)

A cualquier usuario determinado siempre se le asignará un modo TeamsUpgrade, ya sea de forma predeterminada o explícita por el administrador. El valor predeterminado es *Islas.* Los usuarios actualizados a Teams tienen el modo *de TeamsOnly.* *SfBOnly*, *SfBWithTeamsCollab* y *SfBWithTeamsCollabAndMeetings* también son modos posibles.


## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo TeamsUpgrade del destinatario es clave para determinar el comportamiento de los chats, las llamadas y la presencia, tanto dentro de un inquilino como en todos los inquilinos federados.

Si el remitente usa Teams, la decisión de enrutamiento se toma al crear una nueva conversación. Los hilos de conversación existentes en Teams siempre conservan el método de enrutamiento determinado cuando se creó el hilo: Teams admite los hilos persistentes.

 Los métodos de enrutamiento de subprocesos son:  

- *nativa* para una conversación de Teams a Teams en el espacio empresarial
- *interoperabilidad* de una conversación de Teams a Skype Empresarial en el inquilino
- *federado para* una conversación federada entre inquilinos

Los parámetros que determinan el método de enrutamiento de hilos son:

- El modo TeamsUpgrade del destinatario
- El cliente usado por el remitente
- Si la conversación es nueva o parte de un hilo existente
- Si la conversación está en el inquilino o federada
- Si la conversación es posible
    - *La interoperabilidad en el* espacio empresarial requiere que el inquilino sea puro en línea o híbrido de Skype Empresarial. Los inquilinos puramente locales no pueden tener interoperabilidad en el espacio empresarial.
    - *La federación entre inquilinos* siempre requiere una configuración de federación de Skype Empresarial adecuada, así como una configuración de federación de Teams adecuada de ambos inquilinos. Skype Empresarial híbrido no es necesario para ninguno de los inquilinos.
    - Si la cuenta de Skype Empresarial del originador se encuentra en el entorno local, ese usuario no puede usar el cliente de Teams para la interoperabilidad en el espacio empresarial o para la federación. Ese usuario solo puede usar el cliente de Skype Empresarial para la interoperabilidad y la federación.
    - La comunicación de Teams a Teams siempre es posible en el espacio empresarial.

> [!NOTE]
> Si el receptor y el remitente están en modo de actualización de TeamsOnly, la conversación será una experiencia de chat nativa que incluye todas las funciones enriquecciones de mensajería y llamadas. Para obtener más información, lea [Experiencia de chat nativa para usuarios externos (federados) en Teams.](native-chat-for-external-users.md) Si alguno de los participantes de la conversación NO está en el modo de actualización de TeamsOnly, la conversación seguirá siendo una experiencia de interoperabilidad con mensajes de solo texto.

## <a name="chat-and-call-routing"></a>Enrutamiento de llamadas y chats

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Enrutamiento en el espacio empresarial para nuevos chats o llamadas 

Las tablas siguientes capturan el enrutamiento de llamadas y chats en el espacio empresarial, y son válidas para las nuevas llamadas o chats que no se inician desde una conversación existente previamente. Describe qué cliente recibirá una nueva llamada o chat, si es originado por un usuario de la izquierda, a un usuario destinatario en el inquilino de la derecha.

Los mensajes enviados a TeamsOnly los usuarios siempre se dirigirán a Teams. Los mensajes enviados a los usuarios de SfB siempre se dirigirán a Skype Empresarial, si la conversación es posible como \* se describe anteriormente. Los mensajes enviados a los usuarios de islas siempre se dirigirán al mismo cliente desde el que se enviaron.

En las tablas siguientes se muestra qué cliente en un modo determinado recibirá una llamada del autor (tres columnas situadas a la izquierda), según el modo del autor, el cliente elegido y el lugar donde se encuentra su cliente de Skype Empresarial (local o en línea).

En las tablas siguientes: 
- **SfB \** _ representa cualquiera de los modos siguientes: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *El texto en* cursiva resalta una conversación de interoperabilidad.

- **No es** posible representa una situación en la que el chat o la llamada no es posible. El autor debe usar Skype Empresarial en su lugar en estos casos. Esta es una de las razones por las que las instrucciones prescriptivas de Microsoft para los clientes locales e híbridos es usar un modo distinto de islas (normalmente SfBWithTeamsCollab) como punto de partida de su viaje de actualización a Teams.

**Tabla 1a: nuevo chat o enrutamiento de llamadas en el inquilino a un destinatario del modo islas**

| <br/><br/> Modo | Originador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Ruta: >| Destinatario <br/><br/> Aplicaciones aisladas  |
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas | Microsoft Teams <br/> Skype Empresarial<br/> Microsoft Teams<br/> Skype Empresarial| En línea<br/> En línea<br/> On-prem<br/>On-prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype Empresarial<br/> Microsoft Teams<br/> Skype Empresarial|
|SfB\* <br/> | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv;|Skype Empresarial<br/>Skype Empresarial<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabla 1b: nuevo chat o enrutamiento de llamadas en el espacio empresarial a un destinatario en modo \* SfB**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Ruta: > |   Destinatario <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Aplicaciones aisladas |Microsoft Teams<br/>Skype Empresarial<br/>Microsoft Teams <br/>Skype Empresarial  |En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial<br/> **No es posible** <br/>Skype Empresarial<br/> |
|SfB\* <br/> | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv; |  Skype Empresarial<br/>Skype Empresarial<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype Empresarial* <br/>| 
| | | | | |

**Tabla 1c: nuevo chat o enrutamiento de llamadas en el espacio empresarial a un destinatario de modo de TeamsOnly**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Ruta: >|   Destinatario <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Aplicaciones aisladas   |Microsoft Teams<br/>Skype Empresarial<br/>Microsoft Teams <br/>Skype Empresarial<br/>|En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> On-prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Enrutamiento federado para nuevos chats o llamadas
  
Las tablas siguientes capturan el enrutamiento de llamadas y chats federados, y son válidas para nuevas llamadas o chats. Describen qué cliente recibirá una nueva llamada o chat, si es originado por un usuario de la izquierda, a un usuario de destino federado a la derecha.

En resumen, si la conversación es posible como se describe anteriormente, los mensajes enviados a TeamsOnly los usuarios siempre llegarán a Teams; Los mensajes enviados a los usuarios de SfB siempre llegarán a Skype Empresarial; los mensajes enviados a los usuarios de las islas siempre llegarán a Skype Empresarial independientemente del cliente desde el que \* se enviaron. El enrutamiento para chats y llamadas federados difiere del enrutamiento en el espacio empresarial en que los usuarios de las islas siempre recibirán una comunicación federada en Skype Empresarial.

Esto se debe a que no podemos suponer que un partner federado de Skype Empresarial ya usa Teams si están en modo Islas. Islas es el modo predeterminado, pero no podemos suponer que todos los usuarios de las islas ejecuten Teams. Al enrutar a Skype Empresarial nos aseguramos de que no se produce ningún error en la comunicación con un usuario de islas. Si se enrutó a Teams, se podría perder esa comunicación si el destino no usa Teams. El enrutamiento a Skype Empresarial garantiza que el mensaje siempre se recibirá.  

> [!NOTE]
> La implementación actual de la federación de Teams se basa en la federación de Skype Empresarial, por lo que aprovecha la infraestructura de interoperabilidad (que requiere que el inquilino del autor sea puro en línea o híbrido de Skype Empresarial) y proporciona un conjunto reducido de capacidades en comparación con un hilo nativo. Esperamos proporcionar Teams nativos a la federación de Teams en el futuro, momento en el que el hilo será nativo y proporcionará funcionalidades completas.

En las tablas siguientes se describe qué cliente recibirá una llamada del autor (tres columnas situadas a la izquierda), según el modo del autor, el cliente elegido y el lugar donde se encuentra su cliente de Skype Empresarial (local o en línea).

**Tabla 2a: nuevo chat federado o enrutamiento de llamadas a un destinatario de islas**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Ruta: > | Destinatario<br/><br/> Aplicaciones aisladas |
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas |Microsoft Teams<br/>Skype Empresarial <br/>Microsoft Teams <br/>Skype Empresarial  |En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial <br/> **No es posible**   <br/> Skype Empresarial |
| SfB\* |Skype Empresarial <br/>Skype Empresarial |Online<br/> On-prem<br/> | &boxv;<br/>&boxv;|Skype Empresarial <br/>Skype Empresarial |
| TeamsOnly |Teams |Online| &boxv;|*Skype Empresarial* |
|  | | | | 

**Tabla 2b: nuevo chat federado o enrutamiento de llamadas a un destinatario en modo \* SfB**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Ruta: >|  Destinatario<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas |Microsoft Teams<br/>Skype Empresarial <br/>Microsoft Teams <br/>Skype Empresarial <br/>|En línea<br/> En línea<br/> On-prem<br/> On-prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial <br/> **No es posible** <br/>Skype Empresarial <br/> |  
| SfB\* |Skype Empresarial <br/>Skype Empresarial  |Online<br/> On-prem<br/>  |&boxv;<br/>&boxv; | Skype Empresarial <br/>Skype Empresarial  |
| TeamsOnly | Teams|Online |&boxv; |*Skype Empresarial*  |
|  | | | | |

**Tabla 2c: enrutamiento de llamadas o chats nuevos federados a un destinatario del modo TeamsOnly**

| <br/><br/>Modo | Originador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Ruta: >|  Destinatario<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Aplicaciones aisladas  |Microsoft Teams<br/>Skype Empresarial <br/>Microsoft Teams <br/>Skype Empresarial <br/>|En línea<br/> En línea<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**No es posible** <br/>*Teams* |
| SfB\* |Skype Empresarial <br/>Skype Empresarial  | Online<br/> On-prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats y llamadas de hilos preexistentes

### <a name="from-teams"></a>Desde Teams

Las llamadas o chats iniciados desde una conversación persistente preexistente en Teams se enrutarán de la misma manera que esa conversación, si esa opción de enrutamiento sigue estando disponible.

Si la conversación persistente preexistente en Teams era una conversación nativa (por ejemplo, se enrutó a Teams), los mensajes de chat adicionales y las llamadas de esa conversación irán a Teams. Si se trataba de un hilo de interoperabilidad (es decir, se enrutó a Skype Empresarial), los mensajes de chat y las llamadas adicionales irán a Skype Empresarial (siempre que las opciones de enrutamiento estén disponibles).

> [!NOTE]
> Es posible que los subprocesos existentes en Teams ya no sean enrutables, como cuando el hilo era un hilo de interoperabilidad para un usuario que ahora se actualiza a Teams. Puesto que se creó como un hilo de interoperabilidad, el hilo se enrutaría a Skype Empresarial, pero ese usuario ya no puede usar Skype Empresarial para chatear y llamar. En ese caso, la conversación se deshabilitará y no permitirá más comunicaciones.

### <a name="from-skype-for-business"></a>Desde Skype Empresarial

Los hilos de Skype Empresarial no se conservan más allá del tiempo de espera de la sesión SIP de 10 minutos. Los chats y las llamadas desde un hilo existente en Skype Empresarial antes de expirar la sesión SIP se enrutarán de la misma manera que el hilo. Las llamadas y chats de una conversación existente en Skype Empresarial más allá del tiempo de espera de la sesión SIP se enrutarán al Skype Empresarial del usuario remoto, independientemente del cliente del que provenía el hilo original del otro usuario.

### <a name="availability"></a>Disponibilidad

Están disponibles tanto los comportamientos dentro del espacio empresarial como los federados descritos anteriormente, con las siguientes limitaciones:

- Los asistentes externos cuyos inquilinos residen en una implementación o geografía de GoLocal diferente no verán el chat de mensajería instantánea mientras están en una reunión "federada".
- La federación y la interoperabilidad entre O365 Multitenant y Nubes soberanas no son compatibles

## <a name="presence"></a>Presence

Cuando tiene una situación en la que algunos de sus usuarios usan el cliente de Teams y otros siguen usando el cliente de Skype Empresarial, es posible que tenga un número de usuarios que usan ambos clientes. Aún quiere que los estados de presencia se compartan con todos los usuarios sin tener en cuenta el cliente que tiene un usuario individual. Cuando esto se comparte en toda la organización, los usuarios pueden determinar mejor si es apropiado iniciar un chat o realizar una llamada.

Por ejemplo, si el chat o la llamada de un originador deben llegar al cliente de Skype Empresarial del destino, es la presencia del cliente de Skype Empresarial la que debe mostrarse al originador. Si debe llegar al cliente de Teams del destino, es la presencia del cliente de Teams la que debe mostrarse.

Para saber qué comportamiento esperar, deberá comprender que la presencia se comparte en función del modo de coexistencia de un usuario:

* Si un usuario está en modo TeamsOnly, cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá la presencia de Teams Del usuario de TeamsOnly
* Si un usuario está en cualquiera de los modos SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá la presencia de skype empresarial del usuario de SfB \*
* Si un usuario está en modo Islas (o Heredado), la presencia en Teams y la presencia en Skype Empresarial son independientes (los valores no tienen por qué coincidir) y otros usuarios verán una u otra presencia del usuario de las Islas, dependiendo de si están en el mismo inquilino o en un inquilino federado y el cliente que usan.
    * Desde Teams, cualquier otro usuario del mismo inquilino verá la presencia de Teams del usuario de las Islas; esto está alineado con la tabla de enrutamiento en el espacio empresarial anterior
    * Desde Teams, cualquier otro usuario de un inquilino federado verá la presencia de Skype Empresarial del usuario de las Islas; esto está alineado con la tabla de enrutamiento federada anterior
    * Desde Skype Empresarial, cualquier otro usuario verá la presencia de Skype Empresarial del usuario de las Islas (tanto en el inquilino como federado); esto está alineado con las tablas de enrutamiento anteriores


### <a name="in-tenant-presence"></a>Presencia en el inquilino

Los mensajes enviados a TeamsOnly los usuarios siempre llegarán a Teams. Los mensajes enviados a usuarios de SfB siempre llegarán a Skype Empresarial, si la conversación es posible como \* se describe anteriormente. Los mensajes enviados a los usuarios de las Islas siempre llegarán al cliente desde el que se originaron.

En la tabla se describe la presencia del Editor que verá un vigilante, dependiendo del modo del Editor y del cliente del Watcher (para un nuevo hilo).

**Tabla 3: presencia en el espacio empresarial (nueva conversación)**

|Watcher <br/><br/>Cliente|<br/><br/>Ruta: > |<br/><br/>Aplicaciones aisladas |Publisher <br/><br/>SfB\* |<br/>Solo en Teams|
|--- |--- |--- |--- |---|
|Skype Empresarial |&boxv;|Skype Empresarial | Skype Empresarial | Teams|
|Teams |&boxv; |Microsoft Teams |Skype Empresarial |Teams |
| | | | |

### <a name="federated-presence"></a>Presencia federada

La presencia federada se basa en la capacidad de acceso federada que se muestra en la tabla 2.

En la tabla siguiente se describe la presencia del Editor que verá un vigilante, dependiendo del modo del Editor y del cliente del Watcher (para un nuevo hilo). En la práctica, el cliente del Vigilante no marca ninguna diferencia en la federación en esta fase.

**Tabla 4: presencia federada (nueva conversación)**

|Watcher <br/><br/> Cliente |<br/><br/>Ruta: >|<br/><br/> Aplicaciones aisladas  |Publisher <br/><br/> SfB\* |<br/><br/> Solo en Teams |
|--- |--- |--- |--- |---|
|Skype Empresarial |&boxv; |Skype Empresarial  | Skype Empresarial  | Teams  |
|Microsoft Teams | &boxv;|Skype Empresarial |Skype Empresarial |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presencia en hilos preexistedos

Para alinear la presencia y la capacidad de alcance en los hilos preexistedos, la presencia del destino expuesta en esa conversación debe alinearse con el enrutamiento de la conversación, suponiendo que el enrutamiento sea posible.

En particular, si un destinatario con el que tenía anteriormente una conversación de interoperabilidad persistente con se actualizó a Teams, esa conversación ya no reflejará la presencia precisa y ya no será enrutable. Debe iniciar una nueva conversación.

## <a name="related-links"></a>Vínculos relacionados
[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Administrar la coexistencia y la interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)