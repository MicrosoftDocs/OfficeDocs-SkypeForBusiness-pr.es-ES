---
title: Coexistencia con Skype Empresarial
author: kenwith
ms.author: kenwith
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
description: Este documento describe el comportamiento de la conversación, el enrutamiento de llamadas y la presencia entre los usuarios de Teams y Skype empresarial, tanto en el inquilino como en el federado, en función de los modos de TeamsUpgrade asignados. Incluye optimizaciones de enrutamiento, comportamiento de presencia, así como el cambio de modo de TeamsUpgrade predeterminado de *heredado* a *islas* y la jubilación inminente de la *herencia*.
ms.openlocfilehash: 3af54bdfecc7843fbbc095ca0d0cebb91732e648
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515867"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

La coexistencia y la interoperabilidad entre Skype empresarial y los clientes de equipos se definen en los modos de TeamsUpgrade, que se describen en [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).

A cualquier usuario determinado siempre se le asignará un modo TeamsUpgrade, ya sea de forma predeterminada o explícita por el administrador. El valor predeterminado es *islas*. Los usuarios que se actualizan a teams tienen el modo de *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*y *SfBWithTeamsCollabAndMeetings* también son posibles modos.


## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo TeamsUpgrade del destinatario es clave para determinar el comportamiento de los chats, las llamadas y la presencia, tanto dentro de un espacio empresarial como en los inquilinos federados.

Si el remitente usa Teams, la decisión de enrutamiento se realiza al crear una conversación nueva. Los subprocesos de conversación existentes en Teams siempre conservan el método de enrutamiento determinado cuando se creó el subproceso: Teams es compatible con subprocesos persistentes.

 Los métodos de enrutamiento de subprocesos son:  

- *nativo* para un equipo para una conversación de equipos en el inquilino
- *interoperabilidad* de equipos para conversaciones de Skype empresarial en el inquilino
- *federado* para una conversación federada entre espacios empresariales

Los parámetros que determinan el método de enrutamiento de subprocesos son:

- El modo TeamsUpgrade del destinatario
- El cliente usado por el remitente
- Si la conversación es nueva o parte de un subproceso existente
- Si la conversación es de inquilinos o federados
- Si la conversación es posible
    - La interoperabilidad *dentro del inquilino* requiere que el inquilino sea en línea o en un entorno híbrido de Skype empresarial. Los inquilinos puramente locales no pueden tener interoperabilidad entre inquilinos.
    - *La Federación entre inquilinos* siempre requiere una configuración de Federación adecuada de Skype empresarial, así como una configuración de Federación de equipos adecuados de ambos inquilinos. Skype empresarial híbrido no es necesario para ningún inquilino.
    - Si la cuenta de Skype empresarial del creador está hospedada en local, ese usuario no puede usar el cliente de Teams para la interoperabilidad en el inquilino o para la Federación. Ese usuario solo puede usar el cliente de Skype empresarial para la interoperabilidad y la Federación.
    - La comunicación entre equipos siempre es posible en el inquilino.

> [!NOTE]
> En la actualidad, toda Federación que incluye equipos aprovecha la canalización de Federación de Skype empresarial, así como los equipos, la interoperabilidad de Skype empresarial. Planeamos equipos nativos: Federación de equipos. El presente documento se actualizará al liberar la Federación nativa.

# <a name="chat-and-call-routing"></a>Enrutamiento de llamadas y chats

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Enrutamiento en el inquilino para nuevos chats o llamadas 

Las tablas siguientes capturan el enrutamiento de llamadas y chats en inquilino y son válidos para llamadas nuevas o chats que no se inician desde un subproceso ya existente. Describe qué cliente recibirá una nueva llamada o un chat, si ha sido originado por un usuario de la izquierda, para un usuario de ese inquilino a la derecha.

Los mensajes enviados a los usuarios de TeamsOnly siempre se enrutarán a teams. Los mensajes enviados a\* los usuarios de SfB siempre se dirigirán a Skype empresarial, si la conversación es posible según se describe anteriormente. Los mensajes enviados a los usuarios de las islas siempre se enrutarán al mismo cliente desde el que fueron enviados.

En las tablas siguientes se muestra qué cliente de un modo determinado recibirá una llamada del originador (tres columnas del extremo izquierdo), según el modo del creador, el cliente elegido y la ubicación de su cliente de Skype empresarial (local o en línea).

En las siguientes tablas: 
- **SfB\* ** representa cualquiera de los siguientes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- El *texto en cursiva* resalta una conversación interoperativa.

- **No es posible** representa una situación en la que no es posible la conversación o la llamada. En su lugar, el creador debe usar Skype empresarial en estos casos. Esta es una de las razones por las que la orientación prescriptiva de Microsoft para clientes locales o híbridos es usar un modo distinto de islas (generalmente SfBWithTeamsCollab) como punto de partida de la actualización del viaje a teams.

**Tabla 1A: nueva conversación en el inquilino o enrutamiento de llamadas a un destinatario de modo islas**

| <br/><br/> Multimodo | Autor <br/><br/> Cliente | <br/><br/> SfB&nbsp; | | Remite <br/><br/> Logra  |
|--- |--- |--- |--- |--- |
| Logra | Microsoft Teams <br/> Skype Empresarial<br/> Microsoft Teams<br/> Skype Empresarial| En línea<br/> En línea<br/> Local<br/>Local| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype Empresarial<br/> Microsoft Teams<br/> Skype Empresarial|
|SfB\* <br/> | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> Local<br/> |&boxv;<br/>&boxv;|Skype Empresarial<br/>Skype Empresarial<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabla 1B: nueva conversación en el inquilino o enrutamiento de llamadas a un destinatario en modo\* SfB**

| <br/><br/> Multimodo   | Autor <br/><br/> Cliente | <br/><br/> SfB&nbsp; | |   Remite <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Logra |Microsoft Teams<br/>Skype Empresarial<br/>Microsoft Teams <br/>Skype Empresarial  |En línea<br/> En línea<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial<br/> **No es posible** <br/>Skype Empresarial<br/> |
|SfB\* <br/> | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> Local<br/> |&boxv;<br/>&boxv; |  Skype Empresarial<br/>Skype Empresarial<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype Empresarial* <br/>| 
| | | | | |

**Tabla 1C: nueva conversación en el inquilino o enrutamiento de llamadas a destinatarios en modo TeamsOnly**

| <br/><br/> Multimodo   | Autor <br/><br/> Cliente | <br/><br/> SfB&nbsp; | |   Remite <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Logra   |Teams<br/>Skype Empresarial<br/>Teams <br/>Skype Empresarial<br/>|En línea<br/> En línea<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype Empresarial<br/>Skype Empresarial<br/> | Online<br/> Local<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>Enrutamiento federado para nuevos chats o llamadas
  
Las tablas siguientes capturan el enrutamiento de llamadas federadas y chats, y son válidas para nuevas llamadas o chats. Describen qué cliente recibirá una nueva llamada o un chat, si ha sido originado por un usuario de la izquierda, a un usuario de destino federado a la derecha.

En Resumen, si la conversación es posible según se describe anteriormente, los mensajes enviados a los usuarios de TeamsOnly siempre estarán en el equipo. los mensajes enviados a\* los usuarios de SfB siempre estarán en Skype para empresas; los mensajes enviados a los usuarios de las islas siempre estarán en Skype para empresas, independientemente del cliente desde el que se enviaron. El enrutamiento de chats y llamadas federadas difiere del enrutamiento de inquilino en que los usuarios de las islas siempre recibirán una comunicación federada en Skype empresarial.

Esto se debe a que no se puede suponer que un socio federado de Skype empresarial ya usa Teams si está en modo islas. Islas es el modo predeterminado, pero no podemos asumir que todos los usuarios de las islas ejecutan Teams. Al enrutar a Skype empresarial, garantizamos que no se produzcan errores de comunicación con un usuario de islas. Si se enrutan a Teams, esa comunicación podría perderse si el destino no utilizase Teams. El enrutamiento a Skype empresarial siempre garantiza que el mensaje se recibirá.  

> [!NOTE]
> La implementación actual de la Federación de equipos se basa en la Federación de Skype empresarial, por lo que se aprovecha la infraestructura de interoperabilidad (que requiere que el inquilino del originador sea en línea o en un entorno híbrido de Skype empresarial) y proporciona una se ha reducido el conjunto de funciones en comparación con un subproceso nativo. Esperamos proporcionar equipos nativos a la Federación de equipos en el futuro, momento en el que el hilo será nativo y ofrecerá todas las funciones.

Las tablas siguientes describen qué cliente recibirá una llamada de su originador (tres columnas del extremo izquierdo), según el modo del creador, el cliente elegido y la ubicación de su cliente de Skype empresarial (local o en línea).

**Tabla 2A: nueva conversación o enrutamiento de llamadas a un destinatario de islas**

| <br/><br/>Multimodo   | Autor<br/><br/> Cliente| <br/><br/>SfB| | Remite<br/><br/> Logra |
|--- |--- |--- |--- |--- |
| Logra |Teams<br/>Skype Empresarial <br/>Teams <br/>Skype Empresarial  |En línea<br/> En línea<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial <br/> **No es posible**   <br/> Skype Empresarial |
| SfB\* |Skype Empresarial <br/>Skype Empresarial |Online<br/> Local<br/> | &boxv;<br/>&boxv;|Skype Empresarial <br/>Skype Empresarial |
| TeamsOnly |Teams |Online| &boxv;|*Skype Empresarial* |
|  | | | | 

**Tabla 2B: nueva conversación o enrutamiento de llamadas a un destinatario en modo SfB\***

| <br/><br/>Multimodo   | Autor<br/><br/> Cliente| <br/><br/>SfB| |  Remite<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Logra |Teams<br/>Skype Empresarial <br/>Teams <br/>Skype Empresarial <br/>|En línea<br/> En línea<br/> Local<br/> Local<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype Empresarial <br/> **No es posible** <br/>Skype Empresarial <br/> |  
| SfB\* |Skype Empresarial <br/>Skype Empresarial  |Online<br/> Local<br/>  |&boxv;<br/>&boxv; | Skype Empresarial <br/>Skype Empresarial  |
| TeamsOnly | Teams|Online |&boxv; |*Skype Empresarial*  |
|  | | | | |

**Tabla 2C: nueva conversación federada o enrutamiento de llamadas a destinatarios en modo TeamsOnly**

| <br/><br/>Multimodo | Autor<br/><br/> Cliente| <br/><br/>SfB| |  Remite<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Logra  |Teams<br/>Skype Empresarial <br/>Teams <br/>Skype Empresarial <br/>|En línea<br/> En línea<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**No es posible** <br/>*Teams* |
| SfB\* |Skype Empresarial <br/>Skype Empresarial  | Online<br/> Local| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats y llamadas de conversaciones preexistentes

### <a name="from-teams"></a>Desde Teams

Las llamadas o conversaciones iniciadas desde un subproceso persistente preexistente en Teams se redirigirán de la misma manera que ese subproceso, si esa opción de enrutamiento aún está disponible.

Si el subproceso persistente preexistente de Teams era un subproceso nativo (es decir, enrutado a teams), los mensajes de chat adicionales y las llamadas de ese subproceso Irán a teams. Si se trataba de un subproceso de interoperabilidad (por ejemplo, enrutado a Skype empresarial), los mensajes de chat y las llamadas adicionales se enviarán a Skype empresarial (siempre que estén disponibles las opciones de enrutamiento).

> [!NOTE]
> Es posible que los subprocesos predeterminados de Teams dejen de ser enrutables, como cuando el subproceso era un subproceso de interoperabilidad para un usuario que se ha actualizado a teams. Puesto que se creó como un subproceso de interoperabilidad, el subproceso se dirigirá a Skype empresarial, pero ese usuario ya no podrá usar Skype empresarial para conversaciones y llamadas. En ese caso, el subproceso se deshabilitará y no permitirá ninguna comunicación adicional.

### <a name="from-skype-for-business"></a>Desde Skype empresarial

Los subprocesos de Skype empresarial no persisten más allá del tiempo de espera de sesión SIP de 10 minutos. Los chats y las llamadas desde un subproceso existente en Skype empresarial antes del vencimiento de la sesión SIP se redirigirán de la misma manera que el hilo. Las llamadas y los chats de un subproceso existente en Skype empresarial más allá del tiempo de espera de la sesión SIP se enrutarán a la Skype empresarial de la parte remota, independientemente del cliente del que provenga la conversación original.

## <a name="availability"></a>Disponibilidad

Los comportamientos en el inquilino y en el inquilino descritos anteriormente están disponibles, con las siguientes limitaciones:

- Los asistentes externos cuyos inquilinos residen en una implementación o geografía diferente de GoLocal no verán la conversación de mensajes instantáneos en una reunión "federada".
- No se admite la Federación y la interoperabilidad entre O365 y nubes soberanos multiinquilino.

# <a name="presence"></a>Presence

Cuando tiene una situación en la que algunos de los usuarios usan el cliente de Teams y otros siguen usando el cliente de Skype empresarial, es posible que tenga un número de usuarios que están usando ambos clientes. Aún quiere que los Estados de presencia se compartan con todos los usuarios sin tener en cuenta qué cliente tiene un usuario individual. Cuando se comparte en toda la organización, los usuarios pueden determinar mejor si es adecuado iniciar una conversación o hacer una llamada.

Por ejemplo, si la conversación o la llamada de un creador se deben colocar en el cliente de Skype empresarial de destino, la presencia del cliente de Skype empresarial debe mostrarse al autor. Si se debe colocar en el cliente de Teams de destino, se debe mostrar la presencia del cliente de Teams.

Para saber qué comportamiento esperar, necesitará comprender que la presencia se comparte en función del modo de coexistencia del usuario:

* Si un usuario está en modo TeamsOnly, cualquier otro usuario (ya sea en Teams o en Skype empresarial) verá la presencia de Teams de TeamsOnly de usuario.
* Si un usuario se encuentra en cualquiera de los\* modos SfB (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), cualquier otro usuario (ya sea en Teams o Skype empresarial) verá la presencia\* de SfB de usuario de Skype empresarial.
* Si un usuario está en modo islas (o heredadas), la presencia en Teams y la presencia de Skype empresarial son independientes (no es necesario que los valores coincidan) y otros usuarios verán una o la otra presencia del usuario de las islas, en función de si se encuentran en el mismo inquilino o en un federat Ed y el cliente que usan
    * En Teams, cualquier otro usuario dentro del mismo inquilino verá la presencia de equipos del usuario de islas; Esto se alinea con la tabla de enrutamiento en el inquilino anterior
    * En Teams, cualquier otro usuario de un inquilino federado verá la presencia de Skype empresarial por parte del usuario de las islas; Esto se ha alineado con la tabla de enrutamiento federado anterior
    * Desde Skype empresarial, cualquier otro usuario verá la presencia de Skype empresarial del usuario de islas (tanto en el inquilino como en el servicio federado). Esto se ha alineado con las tablas de enrutamiento anteriores


## <a name="in-tenant-presence"></a>Presencia en el inquilino

Los mensajes enviados a los usuarios de TeamsOnly siempre estarán en el equipo. Los mensajes enviados a\* los usuarios de SfB siempre estarán en Skype para empresas, si la conversación es posible según se describe anteriormente. Los mensajes enviados a los usuarios de las islas siempre se encontrarán en el cliente desde el que se han originado.

En la tabla se describe la presencia del editor que verá un monitor, según el modo del editor y el cliente del observador (para un nuevo hilo).

**Tabla 3: presencia en el inquilino (nuevo subproceso)**

|Monitor <br/><br/>Cliente| |<br/><br/>Logra |Publisher <br/><br/>SfB\* |<br/>Solo equipos|
|--- |--- |--- |--- |---|
|Skype Empresarial |&boxv;|Skype Empresarial | Skype Empresarial | Teams|
|Microsoft Teams |&boxv; |Microsoft Teams |Skype Empresarial |Teams |
| | | | |

## <a name="federated-presence"></a>Presencia federada

La presencia federada se basa en la disponibilidad federada que se muestra en la tabla 2.

En la tabla siguiente se describe la presencia del editor que verá un monitor, según el modo del editor y el cliente del observador (para un nuevo subproceso). En la práctica, el cliente del monitor no hace ninguna diferencia en la Federación en este momento.

**Tabla 4: presencia federada (nuevo hilo)**

|Monitor <br/><br/> Cliente | |<br/><br/> Logra  |Publisher <br/><br/> SfB\* |<br/><br/> Solo equipos |
|--- |--- |--- |--- |---|
|Skype Empresarial |&boxv; |Skype Empresarial  | Skype Empresarial  | Teams  |
|Microsoft Teams | &boxv;|Skype Empresarial |Skype Empresarial |Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Presencia en subprocesos preexistentes

Para alinear la presencia y la disponibilidad en subprocesos ya existentes, la presencia de destino expuesta en ese subproceso debe estar alineada con el enrutamiento del subproceso, siempre que sea posible el enrutamiento.

En particular, si un destinatario tenía un subproceso de conversación de interoperabilidad persistente con el que se actualizó a Teams, ese subproceso ya no reflejará la presencia exacta y ya no podrá ser enrutable. Debes iniciar un nuevo hilo.

## <a name="related-links"></a>Vínculos relacionados
[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Vídeo: administrar la coexistencia y la interoperabilidad entre SfB y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
