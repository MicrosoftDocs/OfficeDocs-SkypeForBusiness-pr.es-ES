---
title: Coexistencia con Skype Empresarial
author: jambirk
ms.author: francoid
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: Este documento describe el comportamiento de chat, el enrutamiento de llamadas y presencia entre los usuarios de los equipos y Skype para la empresa, en el inquilino y federado, en función de los modos de TeamsUpgrade asignados. Incluye optimizaciones de enrutamiento, comportamiento de presencia, así como el cambio del modo de TeamsUpgrade predeterminado de *heredado* a *Islas* y la retirada inminente de *heredado*.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67c2e403511c3329d37fa3712bc8f559dcc16c38
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29743000"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

Coexistencia y la interoperabilidad entre Skype para clientes empresariales y de los equipos y los usuarios se define mediante los modos de TeamsUpgrade, que se describen en la [migración e instrucciones de interoperabilidad para las organizaciones que utilizan los equipos junto con Skype para la empresa](migration-interop-guidance-for-teams-with-skype.md).

Cualquier usuario determinado siempre se asignará un modo TeamsUpgrade, ya sea de forma predeterminada o explícitamente por el administrador. El valor predeterminado es *Islas*. Los usuarios actualizados a los equipos tienen el modo de *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*y *SfBWithTeamsCollabAndMeetings* también son modos posibles.

> [!NOTE]
> Modo *heredado* ha quedado obsoleto; los usuarios que estaban en modo *heredado* se convirtieron en modo de *Islas* .

## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo de TeamsUpgrade del destinatario es clave para determinar el comportamiento de chats, las llamadas y presencia tanto dentro de un inquilino en inquilinos federados.

Si el remitente está usando los equipos, las decisiones de enrutamiento se realizan al crear una nueva secuencia de conversación. Subprocesos de conversación existentes en los equipos de conservan siempre el método de enrutamiento determinado cuando se creó el subproceso: los equipos admite subprocesos persistentes.

 Métodos de enrutamiento de subproceso son:  

- *nativo* para equipos de una conversación de los equipos en el inquilino
- *interoperabilidad* para un equipos Skype para conversación empresarial en inquilino
- *federados* para mantener una conversación federado en inquilinos

Los parámetros que determinan el método de enrutamiento de subproceso son:

- El modo de TeamsUpgrade del destinatario
- El cliente utilizado por el remitente
- Si la conversación es nueva o forma parte de un tema existente
- Si la conversación está en el inquilino o federados
- Si es posible la conversación
    - Interoperabilidad *de inquilino* requiere que el inquilino es puro en línea o Skype para entornos híbridos de negocio. Los inquilinos puramente local no pueden tener en el inquilino interoperabilidad.
    - *Federación entre inquilino* siempre requiere Skype adecuado para la configuración de federación de negocio, así como la configuración de federación de los equipos adecuado desde tanto los inquilinos. No es necesario de puede ser inquilino Skype para entornos híbridos de negocio.
    - Si el Skype para cuenta de empresa que el autor es in situ hospedado, que el usuario no puede usar al cliente de los equipos para la interoperabilidad en el inquilino o para la federación. Que el usuario sólo puede usar el Skype para cliente empresarial para la interoperabilidad y la federación.
    - Los equipos para la comunicación de los equipos siempre es posible en el inquilino.

> [!NOTE]
> Actualmente, todas la federación implica a los equipos aprovecha la Skype para canalización de federación de negocio, así como los equipos – Skype para la interoperabilidad de negocio. Tenemos previsto equipos nativos – federación de los equipos. El presente documento se actualizará tras el lanzamiento de federación nativa.

# <a name="chat-and-call-routing"></a>Chat y el enrutamiento de llamadas

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>El enrutamiento para el nuevo chats o las llamadas en inquilino 

Las tablas siguientes capturan el enrutamiento de llamadas y conversaciones en inquilino y son válidas para las nuevas llamadas o charlas que no se han iniciado desde un subproceso ya existente. Describe qué cliente recibirá una nueva llamada o chat, si se ha originado por un usuario de la izquierda, para un usuario de destinatario en el inquilino de la derecha.

Los mensajes enviados a los usuarios de TeamsOnly siempre se enrutarán a los equipos. Los mensajes enviados a SfB\* a los usuarios siempre enrutará a Skype para la empresa, si la conversación es posible tal y como se ha descrito anteriormente. Los mensajes enviados a los usuarios de islas enrutará siempre al mismo cliente desde el que se enviaron.

Las tablas siguientes mostrar qué cliente en un modo determinado recibirán una llamada desde el originador (tres columnas más a la izquierda), dependiendo del modo del originador, cliente elegido, y donde se hospeda su Skype para cliente empresarial (en prem o en línea).

En las tablas siguientes: 
- **SfB\* ** representa cualquiera de los siguientes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Texto en cursiva* resalta una conversación de interoperabilidad.

- **No es posible** representa una situación en la que la conversación o llamada no es posible. El autor debe usar Skype para la empresa en su lugar en estos casos. Se trata de uno de los motivos por preceptivos de Microsoft a los clientes híbrida on-prem son utilizar un modo que no sea de islas (normalmente, SfBWithTeamsCollab) como el punto de partida de su viaje por la actualización a los equipos.

**Tabla 1a: chat nuevo en el inquilino o enrutamiento a un destinatario de modo de islas de llamadas**

| <br/><br/> Modo | Autor <br/><br/> Cliente | <br/><br/> SfB&nbsp;hospedados | | Destinatario <br/><br/> Islas  |
|--- |--- |--- |--- |--- |
| Islas | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| En línea<br/> En línea<br/> En prem<br/>En prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> En prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Microsoft Teams| Online<br/>|&boxv;<br/>|Microsoft Teams|
| | | | | |

**Tabla 1b: chat nuevo en el inquilino o llamada de enrutamiento a un destinatario de un SfB\* modo**

| <br/><br/> Modo   | Autor <br/><br/> Cliente | <br/><br/> SfB&nbsp;hospedados | |   Destinatario <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Islas |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |En línea<br/> En línea<br/> En prem<br/> En prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype for Business<br/> **No es posible** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> En prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Microsoft Teams| Online<br/>|&boxv;<br/> |  *Skype Empresarial* <br/>| 
| | | | | |

**Tabla 1c: chat nuevo en el inquilino o enrutamiento a un destinatario de modo TeamsOnly de llamadas**

| <br/><br/> Modo   | Autor <br/><br/> Cliente | <br/><br/> SfB&nbsp;hospedados | |   Destinatario <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Islas   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|En línea<br/> En línea<br/> En prem<br/> En prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Microsoft Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> En prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Microsoft Teams | Online |  &boxv; |Microsoft Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>Federados de enrutamiento para llamadas o charlas nuevo
  
Las tablas siguientes capturan el enrutamiento de llamadas federadas y chats y son válidas para las nuevas llamadas o charlas. Se describe qué cliente recibirá una nueva llamada o chat, si se ha originado por un usuario de la izquierda, para un usuario federado de destino en la derecha.

En resumen, si la conversación es posible tal y como se ha descrito anteriormente, los mensajes enviados a los usuarios de TeamsOnly se colocarán siempre en los equipos; los mensajes enviados a SfB\* a los usuarios siempre se colocarán en Skype para la empresa; los mensajes enviados a los usuarios de islas siempre se colocarán en Skype para la empresa con independencia del cliente desde el que se enviaron. Enrutamiento de federados charlas y las llamadas difiere en el inquilino enrutamiento en que los usuarios de islas siempre recibirán una comunicación federada de Skype para la empresa.

Esto es debido a que no podemos asumir que una federada Skype para socio comercial ya usa los equipos si están en modo de islas. Islas es el modo predeterminado, sin embargo, no podemos asumir todos los usuarios de islas ejecutan los equipos. Enrutamiento de Skype para la empresa se Asegúrese de que ninguna comunicación a un usuario de islas se produce un error. Si se redirige a los equipos, que la comunicación se pudo perdida si el destino no utilizó los equipos. Enrutamiento de Skype para la empresa garantiza que siempre se recibirá el mensaje.  

> [!NOTE]
> La implementación actual de la federación de los equipos se basa en Skype para la federación de negocio, por lo tanto, aprovecha la infraestructura de interoperabilidad (lo que requiere el inquilino que el autor puede ser puro en línea o Skype para entornos híbridos de negocio) y proporciona un conjunto reducido de capacidades en comparación con un subproceso nativo. Esperamos que proporcione a los equipos nativos para la federación los equipos en el futuro, momento en el que el subproceso se nativo y proporcionar la funcionalidad completa de las.

Las tablas siguientes describen qué cliente recibe una llamada desde el originador (tres columnas más a la izquierda), dependiendo del modo del originador, elegida de cliente, y donde se hospeda su Skype para cliente empresarial (en prem o en línea).

**Tabla 2a: federados chat nueva o a un destinatario de islas el enrutamiento de llamadas**

| <br/><br/>Modo   | Autor<br/><br/> Cliente| <br/><br/>SfB hospedados| | Destinatario<br/><br/> Islas |
|--- |--- |--- |--- |--- |
| Islas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |En línea<br/> En línea<br/> En prem<br/> En prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype for Business <br/> **No es posible**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> En prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Microsoft Teams |Online| &boxv;|*Skype Empresarial* |
|  | | | | 

**Tabla 2b: federados chat nuevo o el enrutamiento de llamadas a un destinatario de un SfB\* modo**

| <br/><br/>Modo   | Autor<br/><br/> Cliente| <br/><br/>SfB hospedados| |  Destinatario<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Islas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|En línea<br/> En línea<br/> En prem<br/> En prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Empresarial* <br/> Skype for Business <br/> **No es posible** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> En prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Microsoft Teams|Online |&boxv; |*Skype Empresarial*  |
|  | | | | |

**Tabla 2c: federados chat nueva o a un destinatario de modo TeamsOnly el enrutamiento de llamadas**

| <br/><br/>Modo | Autor<br/><br/> Cliente| <br/><br/>SfB hospedados| |  Destinatario<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Islas  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|En línea<br/> En línea<br/> En prem<br/> En prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Microsoft Teams <br/>*Teams* <br/>**No es posible** <br/>*Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> En prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Microsoft Teams |Online |&boxv; |Microsoft Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Charlas y llama desde subprocesos ya existentes

### <a name="from-teams"></a>Desde los equipos

Las llamadas o charlas iniciado desde una ya existente se van a enrutar un subproceso persistente en los equipos de la misma manera que ese subproceso, si dicha opción enrutamiento sigue estando disponible.

Si el subproceso persistente ya existente en los equipos era un subproceso nativo (es decir, se enruta a los equipos), mensajes de chat adicionales y las llamadas de ese subproceso se pasará a los equipos. Si era un subproceso de interoperabilidad (es decir, se enruta al Skype para la empresa), las llamadas y mensajes de chat adicionales se vaya a Skype para la empresa (nuevo suponemos que el enrutamiento de las opciones está disponible).

> [!NOTE]
> Es posible que los subprocesos ya existentes en los equipos para que dejen de ser enrutables, por ejemplo, cuando el subproceso era un subproceso de interoperabilidad a un usuario que se actualice ahora a los equipos. Desde que se creó como un subproceso de interoperabilidad, el subproceso podría enrutar a Skype para la empresa, pero que el usuario ya no puede usar Skype para la empresa para chat y llamar al método. En ese caso, el subproceso se deshabilitará y no permita efectuar la comunicación.

### <a name="from-skype-for-business"></a>De Skype para la empresa

Skype para subprocesos de negocio no se conservan más allá del tiempo de espera de sesión SIP de 10 minutos. En la misma manera que el subproceso se enrutarán charlas y las llamadas de un subproceso existente en Skype para la empresa antes de la expiración de la sesión SIP. Las llamadas y conversaciones de un tema existente en Skype para la empresa más allá del tiempo de espera de sesión SIP se enrutarán a Skype de la parte remota para la empresa, independientemente del cliente que el subproceso original proviene del lado de la otra parte.

## <a name="availability"></a>Disponibilidad

Los comportamientos de en el inquilino y federados descritos anteriormente están disponibles, con las siguientes limitaciones:

- Los asistentes externos cuyos inquilinos residen en una implementación de GoLocal o geografía diferentes no verán mensajería instantánea conversaciones mientras está en una reunión "federada"
- No se admite la interoperabilidad entre Multitenant O365 y nubes soberanos y federación

# <a name="presence"></a>Presencia

Cuando haya una situación donde algunos de los usuarios usan al cliente de los equipos y otros usuarios sigue utilizando la Skype para clientes empresariales, puede que tenga un número de usuarios que están utilizando a ambos clientes. Desea continuar Estados de presencia a se comparte con todos los usuarios sin tener en cuenta qué cliente tiene un usuario individual. Cuando esto se comparte en toda la organización, los usuarios pueden determinar mejor si es adecuado iniciar una charla o realizar una llamada.

Por ejemplo, si un originador chat o llamada debe land en Skype del destino para clientes empresariales, es el Skype para la presencia del cliente de negocio que se debe mostrar al autor de la. Si debe abrir en el cliente de los equipos de destino, es presencia del cliente de los equipos que debe mostrarse.

Para saber qué comportamiento cabe esperar, necesita comprender que la presencia se comparte en función de modo de coexistencia de un usuario:

* Si un usuario está en modo de TeamsOnly, a continuación, cualquier otro usuario (ya sea en los equipos o Skype para la empresa) vea el estado de presencia de ese usuario TeamsOnly los equipos
* Si un usuario se encuentra en cualquiera de los SfB\* modos (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings) y, a continuación, cualquier otro usuario (ya sea en los equipos o Skype para la empresa) verán que SfB\* Skype del usuario para la presencia de negocio
* Si un usuario se encuentra en islas (o heredados) modo, la presencia en los equipos y la presencia de Skype para la empresa son independientes (los valores no necesitan coincidir con) y otros usuarios verán uno o la presencia de otra del usuario islas, dependiendo de si está en el mismo arrendatario o en un federat inquilino ED y que utilicen el cliente
    * Desde los equipos, cualquier otro usuario con el mismo inquilino verá la presencia de los equipos del usuario Islas; Esto se alinea con la tabla de enrutamiento en inquilino anterior
    * Desde los equipos, cualquier otro usuario en un inquilino federado verán Skype del usuario islas de presencia de negocio; Esto se alinea con la tabla de enrutamiento federada anterior
    * De Skype para la empresa, cualquier otro usuario verán Skype del usuario islas de presencia de negocio (tanto en el inquilino y federado); Esto se alinea con las tablas de enrutamiento anteriores

> [!NOTE]
> Se trata de un cambio reciente de la implementación anterior (denominado presencia unificada) que se mostró una presencia combinada, agregado de los equipos y Skype el destino para los clientes empresariales. Ese enfoque anterior resultado para ser confusa para los usuarios, ya que con frecuencia daría lugar de mostrar en presencia exacta, es decir, un usuario no está accesible, aunque su presencia les mostramos en línea.

## <a name="in-tenant-presence"></a>Presencia en el inquilino

Los mensajes enviados a los usuarios de TeamsOnly siempre se colocarán en los equipos. Los mensajes enviados a SfB\* a los usuarios siempre se colocarán en Skype para la empresa, si la conversación es posible tal y como se ha descrito anteriormente. Los mensajes enviados a los usuarios de islas siempre se colocarán en el cliente desde el que se han se originó.

La tabla describen la presencia de Publisher que se verán por un monitor, según el modo del Editor y el cliente del Monitor (para un nuevo subproceso).

**Tabla 3: en inquilino presencia (nuevo subproceso)**

|Monitor <br/><br/>Cliente| |<br/><br/>Islas |Publisher <br/><br/>SfB\* |<br/>Sólo los equipos|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Microsoft Teams|
|Microsoft Teams |&boxv; |Microsoft Teams |Skype for Business |Microsoft Teams |
| | | | |

## <a name="federated-presence"></a>Presencia federada

Presencia federado se basa en la posibilidad de acceso federado que se muestra en la tabla 2.

En la tabla siguiente se describe la presencia de Publisher que se verán por un monitor, según el modo del Editor y el cliente del Monitor (para un nuevo subproceso). En la práctica, el cliente del monitor no hace ninguna diferencia de federación en esta etapa.

**Tabla 4: federada presencia (nuevo subproceso)**

|Monitor <br/><br/> Cliente | |<br/><br/> Islas  |Publisher <br/><br/> SfB\* |<br/><br/> Sólo los equipos |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Microsoft Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Microsoft Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Presencia en subprocesos ya existentes

Con el fin de alinear la presencia y el alcance de los subprocesos ya existentes, presencia del destino expuesto en que el subproceso necesita se alinea con el enrutamiento de la secuencia, se supone que el enrutamiento es posible.

En particular, si un destinatario previamente tenía un subproceso persistente conversación interoperabilidad con se ha actualizado a los equipos, que el subproceso ya no reflejarán presencia preciso y ya no estará enrutable. Debe iniciar un nuevo subproceso.

## <a name="related-links"></a>Vínculos relacionados

[Vídeo: Administrar la coexistencia y la interoperabilidad entre los equipos y SfB](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)