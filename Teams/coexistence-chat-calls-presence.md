---
title: Coexistencia con Skype Empresarial
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Comportamiento de coexistencia entre Teams & Skype Empresarial, incluidos los parámetros de enrutamiento, el & de llamadas, los chats & llamadas de subprocesos preexistentes, & presencia.
ms.openlocfilehash: 5c32e99ad7cd74966cc7d8f22bd19a2520249b85
ms.sourcegitcommit: a5b80ad33b4ee9505ea2be1a37f5ec2d8bf5ba76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2021
ms.locfileid: "61042371"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

La coexistencia y la interoperabilidad entre Skype Empresarial y Teams clientes se controlan mediante modos de coexistencia. Para obtener más información, vea Instrucciones de migración e [interoperabilidad](migration-interop-guidance-for-teams-with-skype.md)para organizaciones que usan Teams junto con Skype Empresarial . Después de la retirada de Skype Empresarial Online el 31 de julio de 2021, los usuarios que se encuentran en la nube siempre son usuarios de TeamsOnly. Ya no es posible asignar un modo de coexistencia distinto de TeamsOnly a un usuario en línea. Los modos de coexistencia distintos de TeamsOnly solo son relevantes para las organizaciones con implementaciones locales de Skype Empresarial Server o Lync Server 2013. En este artículo, cualquier referencia a "Skype Empresarial Server" también se aplica a Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Determinar el modo de coexistencia de un usuario
Todos los usuarios de organizaciones sin ninguna implementación local de Skype Empresarial Server están en modo TeamsOnly y el modo efectivo del inquilino también es TeamsOnly. Esto se puede confirmar si mira la propiedad TeamsUpgradeEffectiveMode en el inquilino o el usuario que usa Teams PowerShell.   Antes de la retirada de Skype Empresarial Online el 31 de julio de 2021, las organizaciones tenían la capacidad de cambiar el modo de coexistencia para el usuario o el inquilino. Esto ya no es posible excepto para las organizaciones con una implementación local de Skype Empresarial Server, que no debe tener el modo de todo el espacio empresarial de TeamsOnly. Puede confirmar que el modo de coexistencia ya no se puede cambiar si TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" en el usuario o en el espacio empresarial.  (TeamsUpgradePolicyIsReadOnly en cualquier usuario tendrá el mismo valor que el valor del inquilino).  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

En una organización con una implementación local de Skype Empresarial Server, la directiva global de inquilino para TeamsUpgradePolicy puede tener cualquier modo distinto *de TeamsOnly.* Los modos permitidos son: *SfBOnly*, *SfBWithTeamsCollab* y *SfBWithTeamsCollabAndMeetings*. A los usuarios también se les puede asignar directamente una instancia de TeamsUpgradePolicy, que reemplazaría la directiva global del inquilino.  Los usuarios que se aloen en la nube deben ser TeamsOnly y los usuarios que se aloen localmente deben ser cualquier otro modo que no sea TeamsOnly.  Si a un usuario no se le asigna una instancia de TeamsUpgradePolicy, el usuario recibe el valor de la directiva global del inquilino. 

## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo de coexistencia del destinatario determina el comportamiento de los chats, las llamadas y la presencia, tanto dentro de un inquilino como entre inquilinos federados. Si el remitente usa Teams, la decisión de enrutamiento se toma al crear un nuevo hilo de conversación. Una vez creada una conversación, el enrutamiento no cambia y conserva el método de enrutamiento determinado cuando se creó la conversación.

Los métodos de enrutamiento de subprocesos son:

- *nativo* para un Teams para Teams conversación en el espacio empresarial
- *interoperabilidad* para un Teams para Skype Empresarial conversación en el espacio empresarial
- *nativo federado para* una conversación federada entre inquilinos cuando ambos usuarios tienen el modo TeamsOnly. 
- *interoperabilidad federada* para una conversación federada entre inquilinos que depende de la interoperabilidad entre Skype Empresarial y Teams.

> [!NOTE]
> - Las conversaciones nativas, ya sea en el mismo espacio empresarial o en escenarios federados, se producen cuando tanto el receptor como el remitente tienen el modo TeamsOnly. La conversación será una experiencia de chat nativa, que incluye todas las funciones enriquecciones de mensajería y llamadas. Para obtener más información, lea [Experiencia de chat nativa para usuarios externos (federados) en Teams](native-chat-for-external-users.md). 
> - Si alguno de los participantes de la conversación NO tiene el modo TeamsOnly, la conversación es una experiencia de interoperabilidad con mensajes de solo texto.
> - Comunicaciones federadas entre los usuarios de TeamsOnly en nubes multiempresa y entornos de nube especiales (por ejemplo, nubes gubernamentales) aparecerán como chats federados de interoperabilidad.


Al crear una nueva conversación, los factores que determinan cómo se enruta la conversación son:

- El modo de coexistencia del destinatario
- El cliente usado por el remitente
- Si la conversación está en el inquilino o federada
- Si la conversación es posible. Si un usuario tiene una cuenta Skype Empresarial local, ese usuario no puede usar el cliente de Teams para interoperabilidad en el espacio empresarial o para federación. Ese usuario solo puede usar el Skype Empresarial para interoperabilidad y federación. Tenga en cuenta que Teams Teams comunicación siempre es posible en el espacio empresarial.

## <a name="chat-and-call-routing"></a>Enrutamiento de llamadas y chats
Las tablas siguientes muestran qué cliente en un modo determinado recibirá una llamada del originador (tres columnas situadas a la izquierda). Qué cient recibe la llamada depende del modo del autor, del cliente elegido y de dónde se encuentra la cuenta de Skype Empresarial (local o en línea).

En las tablas siguientes:

- **Skype Empresarial** _ representa cualquiera de los modos siguientes: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *El texto en* cursiva resalta una conversación de interoperabilidad.
- **No es** posible representa una situación en la que el chat o la llamada no es posible. El creador debe usar Skype Empresarial en estos casos. Este es uno de los motivos por los que las instrucciones prescriptivas de Microsoft para los clientes locales e híbridos es usar un modo distinto de islas (normalmente SfBWithTeamsCollab) como punto de partida para su viaje de actualización a Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Enrutamiento en el espacio empresarial para nuevos chats o llamadas

Las tablas siguientes capturan el enrutamiento de llamadas y chats en el espacio empresarial, y son válidas para las nuevas llamadas o chats que no se inician desde una conversación existente previamente. Describe qué cliente recibirá una nueva llamada o chat, si es originado por un usuario de la izquierda, a un usuario destinatario en el inquilino de la derecha.  Los mensajes enviados a TeamsOnly los usuarios siempre se dirigirán a Teams. Los mensajes enviados Skype Empresarial usuarios siempre se dirigirán a Skype Empresarial. Los mensajes enviados a los usuarios de islas siempre se dirigirán al mismo cliente desde el que se enviaron.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabla 1a: nuevo chat o enrutamiento de llamadas en el espacio empresarial a un destinatario de modo de TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial &nbsp; hogar|<br><br>Ruta: >|TeamsOnly Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;|Teams <br> *Teams*|
|Skype Empresarial | Skype Empresarial | Local|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabla 1b: nuevo chat o enrutamiento de llamadas en el inquilino a un destinatario del modo islas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial &nbsp; hogar|<br><br>Ruta: >|Destinatario de islas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Aplicaciones aisladas| Teams <br> Skype Empresarial|Local<br>Local|&boxv;<br>&boxv;| Teams <br> Skype Empresarial|
|Skype Empresarial |Skype Empresarial | Local|&boxv;| Skype Empresarial|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabla 1c: nuevo chat o enrutamiento de llamadas en el espacio empresarial a un destinatario en un Skype Empresarial local

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial &nbsp; hogar|<br><br>Ruta: >|Skype Empresarial destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype Empresarial*|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;| **No es posible** <br> Skype Empresarial|
|Skype Empresarial | Skype Empresarial| Local|&boxv;| Skype Empresarial|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Enrutamiento federado para nuevos chats o llamadas

Las tablas siguientes capturan el enrutamiento de llamadas y chats federados, y son válidas para nuevas llamadas o chats. Describen qué cliente recibirá una nueva llamada o chat, si es originado por un usuario de la izquierda, a un usuario de destino federado a la derecha. En resumen, si la conversación es posible como se ha descrito anteriormente, los mensajes enviados a TeamsOnly los usuarios siempre llegarán Teams; los mensajes enviados Skype Empresarial los usuarios en modo Skype Empresarial siempre llegarán Skype Empresarial; los mensajes enviados a los usuarios de las Islas siempre llegarán Skype Empresarial  independientemente del cliente desde el que se enviaron. 

El enrutamiento para chats y llamadas federados difiere del enrutamiento en el espacio empresarial en que los usuarios de las islas siempre recibirán una comunicación federada en Skype Empresarial. Esto se debe a que es posible que el partner federado aún no esté usando Teams. El enrutamiento a Skype Empresarial para cualquier receta de modo de islas garantiza que los mensajes siempre se reciban.  El enrutamiento a Teams posiblemente podría provocar la falta de comunicación si el destinatario no usa Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabla 2a: enrutamiento de llamadas o chats nuevos federados a un destinatario del modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial hogar|<br><br>Ruta: >|TeamsOnly Recipient|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Aplicaciones aisladas|Teams <br> Skype Empresarial|Local <br> Local|&boxv;<br>&boxv;|**No es posible** <br> *Teams*|
|Skype Empresarial |Skype Empresarial|Local|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabla 2b: enrutamiento de llamadas o chats nuevos federados a un destinatario de islas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial hogar|<br><br>Ruta: >|Destinatario de islas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype Empresarial*|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;| **No es posible** <br> Skype Empresarial|
|Skype Empresarial |Skype Empresarial| Local|&boxv;| Skype Empresarial|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabla 2c: nuevo chat federado o enrutamiento de llamadas a un destinatario en un Skype Empresarial usuario

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial hogar|<br><br>Ruta: >|Skype Empresarial destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype Empresarial*|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;|**No es posible** <br> Skype Empresarial|
|Skype Empresarial |Skype Empresarial|Local|&boxv;<br>&boxv;|Skype Empresarial|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats y llamadas de hilos preexistentes

### <a name="from-teams"></a>Desde Teams

Las llamadas o chats iniciados desde un hilo de conversación existente en Teams se enruta de la misma manera que esa conversación. Si el hilo preexistido en Teams era un hilo nativo (es decir, se enrutó a Teams), los mensajes de chat adicionales y las llamadas de esa conversación irán a Teams. Si se trataba de un hilo de interoperabilidad (es decir, se enrutó a Skype Empresarial), los mensajes de chat y las llamadas adicionales irán a Skype Empresarial (suponiendo que las opciones de enrutamiento estén disponibles).

> [!NOTE]
> Es posible que los subprocesos existentes en Teams ya no sean enrutables, como cuando el hilo era un hilo de interoperabilidad para un usuario que desde entonces se ha actualizado a Teams. Puesto que se creó como un hilo de interoperabilidad, el hilo se enrutaría a Skype Empresarial, pero ese usuario ya no puede usar Skype Empresarial chat y llamadas. En ese caso, la conversación se deshabilitará y no permitirá más comunicaciones.

### <a name="from-skype-for-business"></a>Desde Skype Empresarial

Skype Empresarial hilos no persisten más allá del tiempo de espera de sesión SIP de 10 minutos. Los chats y las llamadas de un hilo existente en Skype Empresarial antes de la expiración de la sesión SIP se enrutarán de la misma manera que la conversación. Las llamadas y chats de un hilo existente en Skype Empresarial más allá del tiempo de espera de la sesión SIP se enrutarán al Skype Empresarial del usuario remoto, independientemente del cliente del que provenía el hilo original del otro usuario.

## <a name="presence"></a>Presence

En situaciones en las que algunos usuarios usan el cliente Teams y otros usan el cliente Skype Empresarial, es posible que algunos de estos usuarios estén usando ambos clientes. Es importante comprender que la presencia se publica en función del modo de coexistencia de un usuario. Por ejemplo, si el chat o la llamada de un originador debe llegar al cliente de Skype Empresarial del destino, es la presencia del cliente Skype Empresarial la que debe mostrarse al autor. Si debe llegar al cliente Teams destino, es la presencia Teams cliente que debe mostrarse.

La presencia se comparte en función del modo de coexistencia de un usuario como se describe a continuación:

- Si un usuario está en el modo TeamsOnly, cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá que TeamsOnly Teams presencia
- Si un usuario está en cualquiera de los modos Skype Empresarial (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá que Skype Empresarial presencia del usuario Skype Empresarial
- Si un usuario está en modo Islas, la presencia en Teams y la presencia en Skype Empresarial son independientes (los valores no tienen por qué coincidir) y otros usuarios verán una u otra presencia del usuario de las Islas, dependiendo de si están en el mismo inquilino o en un inquilino federado y el cliente que usan.
  - Desde Teams, cualquier otro usuario dentro del mismo inquilino verá la presencia Teams del usuario de las Islas; esto está alineado con la tabla de enrutamiento del espacio empresarial anterior
  - Desde Teams, cualquier otro usuario de un inquilino federado verá la presencia del usuario de Skype Empresarial islas; esto está alineado con la tabla de enrutamiento federada anterior
  - Desde Skype Empresarial, cualquier otro usuario verá la presencia de Skype Empresarial del usuario de las Islas (tanto en el inquilino como federado); esto está alineado con las tablas de enrutamiento anteriores

### <a name="in-tenant-presence"></a>Presencia en el inquilino

Los mensajes enviados a TeamsOnly los usuarios siempre llegarán a Teams. Los mensajes enviados Skype Empresarial los usuarios en modo de Skype Empresarial, si la conversación es posible como se describe anteriormente. Los mensajes enviados a los usuarios de las Islas siempre llegarán al cliente desde el que se originaron.

En la tabla se describe la presencia del Publisher que verá un watcher, dependiendo del modo del Publisher y del cliente del Watcher (para una nueva conversación).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabla 3: presencia en el espacio empresarial (nueva conversación)

<br>

|Watcher<br><br>Cliente|<br><br>Ruta: >|<br><br>Aplicaciones aisladas|Publisher<br><br>Skype Empresarial|<br>Teams solo para Teams|
|---|:---:|---|---|---|
|Skype Empresarial|&boxv;|Skype Empresarial|Skype Empresarial|Teams|
|Teams|&boxv;|Teams|Skype Empresarial|Teams|
|||||

### <a name="federated-presence"></a>Presencia federada

La presencia federada se basa en la capacidad de acceso federada que se muestra en la tabla 2.  En la tabla siguiente se describe la presencia del Publisher que verá un watcher, dependiendo del modo del Publisher y del cliente del Watcher (para una nueva conversación). En la práctica, el cliente del Vigilante no marca ninguna diferencia en la federación en esta fase.

#### <a name="table-4-federated-presence-new-thread"></a>Tabla 4: presencia federada (nueva conversación)

<br>

|Watcher<br><br>Cliente|<br><br>Ruta: >|<br><br>Aplicaciones aisladas|Publisher<br><br>Skype Empresarial|<br><br>Teams solo para Teams|
|---|:---:|---|---|---|
|Skype Empresarial|&boxv;|Skype Empresarial|Skype Empresarial|Teams|
|Teams|&boxv;|Skype Empresarial|Skype Empresarial|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presencia en hilos preexistedos

Para alinear la presencia y la capacidad de alcance en los hilos preexistedos, la presencia del destino expuesta en esa conversación debe alinearse con el enrutamiento de la conversación, suponiendo que el enrutamiento sea posible.  En particular, si un destinatario con el que tenía anteriormente una conversación de interoperabilidad persistente se actualizó a Teams, esa conversación ya no reflejará la presencia precisa y ya no será enrutable. Debe iniciar una nueva conversación.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federación e interoperabilidad con Office 365 21Vianet

La federación y la interoperabilidad entre Office 365 multiinquilino y Office 365 que opera 21Vianet son compatibles cuando los usuarios de Office 365 multiinquilino están en modo Teams único. En este escenario, los usuarios de Skype Empresarial Online en Office 365 operados por 21Vianet podrán comunicarse con Teams Solo los usuarios de Office 365 a través de chats y llamadas. En la tabla siguiente se muestran los escenarios admitidos en esta configuración:
 
|Escenario|Origen|Destinatario|¿Compatible?|
|---|---|---|---|
|Presence|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí<br>Sí|
|Chat|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí (solo 1:1)<br>Sí(solo 1:1)|
|Llamadas de audio|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí (solo 1:1)<br>Sí (solo 1:1)|
|Videollamadas|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí (solo 1:1)<br>Sí (solo 1:1)|
|Uso compartido de pantalla|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams |Sí (a través de una reunión Teams promoción)<br>Sí (a través de una reunión Skype Empresarial promoción)|
|||||


## <a name="related-links"></a>Vínculos relacionados
[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Administrar la coexistencia y la interoperabilidad entre Skype Empresarial y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
