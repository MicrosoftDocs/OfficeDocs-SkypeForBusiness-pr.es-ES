---
title: Coexistencia con Skype para la empresa
author: jambirk
ms.author: francoid
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: Este documento describe el comportamiento de chat, el enrutamiento de llamadas y presencia entre los usuarios de los equipos y Skype para la empresa, en el inquilino y federado, en función de los modos de TeamsUpgrade asignados. Incluye optimizaciones de enrutamiento, comportamiento de presencia, así como el cambio del modo de TeamsUpgrade predeterminado de *heredado* a *Islas* y la retirada inminente de *heredado*.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5014dd842daf9c08b2ab22abfc405586273cf47
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2018
ms.locfileid: "26216067"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype para la empresa

Coexistencia y la interoperabilidad entre Skype para la empresa y los equipos se define mediante los modos de TeamsUpgrade, que se describen en la [migración e instrucciones de interoperabilidad para las organizaciones con equipos junto con Skype para la empresa](migration-interop-guidance-for-teams-with-skype.md).

Cualquier usuario determinado siempre se asignará un modo TeamsUpgrade, ya sea de forma predeterminada o explícitamente por el administrador. El valor predeterminado es *Islas*. Los usuarios actualizados a los equipos tienen el modo de *TeamsOnly*.

> [!NOTE]
> Modo *heredado* ha quedado obsoleto; los usuarios que permanezca en modo *heredado* se convertirá al modo de *Islas* después del 15 de noviembre de 2018.

## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo de TeamsUpgrade del destinatario es clave para determinar el comportamiento de chats, las llamadas y presencia tanto dentro de un inquilino en inquilinos federados.

Si el remitente está usando los equipos, las decisiones de enrutamiento se realizan al crear una nueva secuencia de conversación. Subprocesos de conversación existentes en los equipos de conservan siempre el método de enrutamiento determinado cuando se creó el subproceso. Los equipos admite subprocesos persistentes.

 Métodos de enrutamiento de subproceso son:  
* *nativo* para equipos de una conversación de los equipos en el inquilino
* *interoperabilidad* para un equipos Skype para conversación empresarial en inquilino
* para mantener una conversación federado en inquilinos, *federados* .

Los parámetros que determinan el método de enrutamiento de subproceso son:
* El modo de TeamsUpgrade del destinatario
* El cliente utilizado por el remitente
* Si la conversación es nueva o forma parte de un tema existente
* Si la conversación está en el inquilino o federados
* Si es posible la conversación
    * Interoperabilidad de inquilinos y la federación de los equipos requiere que inquilino del autor de la es cualquiera puro en línea o Skype para entornos híbridos de negocio. No pueden tener los inquilinos puramente in situ en inquilino interoperabilidad o la federación para los equipos.
    * Si el Skype para cuenta de empresa que el autor es in situ hospedado, que el usuario no puede usar al cliente de los equipos para la interoperabilidad en el inquilino y para la federación. Que el usuario debe usar en su lugar el Skype para cliente empresarial para la interoperabilidad y la federación.
    * Los equipos para la comunicación de los equipos siempre es posible en el inquilino.

# <a name="chat-and-call-routing"></a>Chat y el enrutamiento de llamadas

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>El enrutamiento para el nuevo chats o las llamadas en inquilino 

La tabla siguiente recoge práctica actual de chat en el inquilino y el enrutamiento de llamadas. Esta tabla es válida para las llamadas nuevas o charlas que no se han iniciado desde un subproceso existente ya existente. Describe qué cliente se enrutará una nueva llamada (o chat), si se ha originado por un usuario de la izquierda, para un usuario de destino en el inquilino de la derecha.

Los mensajes enviados a los usuarios de TeamsOnly siempre se colocarán en los equipos. Los mensajes enviados a usuarios de SfB siempre se colocarán en Skype para la empresa, si la conversación es posible tal y como se ha descrito anteriormente. Los mensajes enviados a los usuarios de islas siempre se colocarán en el cliente desde el que se han se originó.

**Tabla 1: chat nuevo en el inquilino o enrutamiento de llamadas**

| <br/> Modo   | Desde&nbsp;autor <br/> Cliente | <br/> SfB&nbsp;hospedados | | <br/> Islas  | Para&nbsp;destino <br/> SfB\*   | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |--- |
| Islas <br/>Islas <br/>Islas <br/>Islas<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Microsoft Teams<br/>SfB <br/>Microsoft Teams <br/>SfB <br/>SfB <br/>SfB <br/>Microsoft Teams|En línea<br/> En línea<br/> En prem<br/> En prem<br/> Online<br/> En prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>|Microsoft Teams <br/> SfB <br/> Microsoft Teams <br/> SfB <br/>  SfB <br/> SfB <br/> Microsoft Teams | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>*SfB* <br/>  | Microsoft Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams* <br/> *Microsoft Teams*  <br/>*Microsoft Teams* <br/>Microsoft Teams <br/> |
|  | | | | | | |

En la tabla, SfB * representa cualquiera de los siguientes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Texto en cursiva* en la tabla indica una conversación de interoperabilidad.

**Negrita** en la tabla representa una situación en la que la conversación o llamada no es posible. Que es debido a que la infraestructura de interoperabilidad sólo está disponible en línea y requiere la Skype para la cuenta de la empresa asociada con la cuenta de los equipos para que sea una cuenta en línea. El autor debe usar Skype para la empresa en su lugar en estos casos. Se trata de uno de los motivos por preceptivos de Microsoft a los clientes híbrida on-prem son de usar otro modo que Islas (normalmente, *SfBWithTeamsCollab*) como el punto de partida de su viaje por la actualización a los equipos.

## <a name="federated-routing-for-new-chats-or-calls"></a>Federados de enrutamiento para llamadas o charlas nuevo
  
La tabla siguiente recoge recomendados federadas actuales de enrutamiento de llamadas (y chat). Esta tabla es válida para las llamadas nuevas o charlas. Describe qué cliente se enrutará una nueva llamada (o chat), si se ha originado por un usuario de la izquierda, para un usuario federado de destino en la derecha.

En resumen, si la conversación es posible tal y como se ha descrito anteriormente, los mensajes enviados a los usuarios de TeamsOnly se colocarán siempre en los equipos; los mensajes enviados a usuarios de SfB siempre se colocarán en Skype para la empresa; los mensajes enviados a los usuarios de islas siempre se colocarán en Skype para la empresa con independencia del cliente desde el que se han se originó. Enrutamiento de federados charlas y las llamadas difiere en el inquilino enrutamiento en que los usuarios de islas siempre recibirán una comunicación federada de Skype para la empresa.

La razón de este último punto es que no podemos asumir que una federada Skype para socio comercial ya usa los equipos si están en modo de islas. Islas es el modo predeterminado, sin embargo, no podemos asumir todos los usuarios de islas ejecutan los equipos. Enrutamiento de Skype para la empresa se Asegúrese de que ninguna comunicación a un usuario de islas se produce un error. Si se redirige a los equipos, que la comunicación se pudo perdida si el destino no utilizó los equipos. Enrutamiento de Skype para la empresa garantiza que siempre se recibirá el mensaje.  

> [!NOTE]
> La implementación actual de la federación de los equipos se basa en Skype para la federación de negocio, por lo tanto, aprovecha la infraestructura de interoperabilidad (lo que requiere el inquilino que el autor puede ser puro en línea o SfB híbrido) y proporciona un conjunto reducido de capacidades en comparación con un subproceso nativo. Esperamos que proporcione a los equipos nativos para la federación los equipos en el futuro, momento en el que el subproceso se nativo y proporcionar la funcionalidad completa de las.

**Tabla 2: chat nuevo federado o el enrutamiento de llamadas**

| <br/>Modo   | De autor<br/> Cliente| <br/>SfB hospedados| | <br/> Islas | En el destino<br/> SfB\* | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |---|
| Islas <br/>Islas <br/>Islas <br/>Islas<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Microsoft Teams<br/>SfB <br/>Microsoft Teams <br/>SfB <br/>SfB <br/>SfB <br/>Microsoft Teams|En línea<br/> En línea<br/> En prem<br/> En prem<br/> Online<br/> En prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/> | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/>  | Microsoft Teams <br/>Microsoft Teams <br/>**NA** <br/>*Los equipos <br/>equipos <br/>los equipos* <br/>Microsoft Teams <br/> |
|  | | | | | |

En la tabla, SfB * representa cualquiera de los siguientes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Texto en cursiva* resalta una conversación de interoperabilidad.

**Negrita** representa una situación en la que la conversación o llamada no es posible. El autor debe usar Skype para la empresa en su lugar en estos casos. Se trata de uno de los motivos por preceptivos de Microsoft a los clientes híbrida on-prem son de usar otro modo que Islas (normalmente, SfBWithTeamsCollab) como el punto de partida de su viaje por la actualización a los equipos.

## <a name="chats-and-calls-from-pre-existing-threads"></a>Charlas y llama desde subprocesos ya existentes

### <a name="from-teams"></a>Desde los equipos

Las llamadas o charlas iniciado desde una ya existente se van a enrutar un subproceso persistente en los equipos de la misma manera que ese subproceso, si dicha opción enrutamiento sigue estando disponible. 

Si el subproceso persistente ya existente en los equipos era un subproceso nativo (es decir, se enruta a los equipos), mensajes de chat adicionales y las llamadas de ese subproceso se pasará a los equipos. Si era un subproceso de interoperabilidad (es decir, se enruta al Skype para la empresa), las llamadas y mensajes de chat adicionales se vaya a Skype para la empresa (nuevo suponemos que el enrutamiento de las opciones está disponible).

> [!NOTE]
> Subprocesos ya existentes en los equipos pueden no ser enrutables. Esto puede ocurrir por ejemplo si el subproceso era un subproceso de interoperabilidad a un usuario que se actualice ahora a los equipos. Dado que es un subproceso de interoperabilidad, el subproceso podría enrutar a Skype para la empresa pero que el usuario ya no puede usar Skype para la empresa para chat y llamar al método. En ese caso, el subproceso se deshabilitará y no permita efectuar la comunicación.

### <a name="from-skype-for-business"></a>De Skype para la empresa

Skype para la empresa no tiene persistencia de subproceso más allá del tiempo de espera de sesión SIP (10 minutos). En la misma manera que el subproceso se enrutarán charlas y las llamadas de un subproceso existente en Skype para la empresa antes de la expiración de la sesión SIP. Las llamadas y conversaciones de un tema existente en Skype para la empresa más allá del tiempo de espera de sesión SIP se enrutarán a Skype de la parte remota para la empresa, independientemente del cliente que el subproceso original proviene del lado de la otra parte.

## <a name="availability"></a>Disponibilidad

El comportamiento de inquilino descrito anteriormente está disponible en la producción actual.

El comportamiento federado descrito anteriormente principalmente está disponible en la producción actual. Los siguientes elementos aún se van a implantar y sólo están disponibles para los inquilinos en los primeros usuarios: 
* Federación con un inquilino local con visibilidad de presencia
* Para mostrar de los contactos federados migrados en la lista de contactos de los equipos cliente
* Posibilidad de usar la dirección URI del SIP o SMTP para detectar un contacto asociado externo.

Implantación para estos tiene disponibilidad comenzada y general se espera antes de fin de noviembre de 2018.

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

|Monitor <br/>Cliente| |<br/>Islas |Publisher <br/>SfB\* |<br/>Sólo los equipos|
|--- |--- |--- |--- |---|
|SfB <br/> Microsoft Teams|&boxv;<br/>&boxv;<br/> |SfB <br/>Microsoft Teams | SfB <br/>SfB | Microsoft Teams  <br/> Microsoft Teams |
| | | | |

## <a name="federated-presence"></a>Presencia federada

Presencia federado se basa en la posibilidad de acceso federado que se muestra en la tabla 2.

En la tabla siguiente se describe la presencia de Publisher que se verán por un monitor, según el modo del Editor y el cliente del Monitor (para un nuevo subproceso). En la práctica, el cliente del monitor no hace ninguna diferencia de federación en esta etapa.

**Tabla 4: federada presencia (nuevo subproceso)**

|Monitor <br/> Cliente | |<br/> Islas  |Publisher <br/> SfB\* |<br/> Sólo los equipos  |
|--- |--- |--- |--- |---|
|SfB <br/> Microsoft Teams|&boxv;<br/>&boxv; |SfB <br/> SfB | SfB <br/> SfB | Microsoft Teams <br/> Microsoft Teams |
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Presencia en subprocesos ya existentes

Con el fin de alinear la presencia y el alcance de los subprocesos ya existentes, presencia del destino expuesto en que el subproceso necesita se alinea con el enrutamiento de la secuencia, se supone que el enrutamiento es posible.

En particular, si un destinatario previamente tenía un subproceso persistente conversación interoperabilidad con se posteriormente actualice a los equipos, que el subproceso ya no reflejarán presencia preciso y ya no estará enrutable. Debe iniciar un nuevo subproceso.
