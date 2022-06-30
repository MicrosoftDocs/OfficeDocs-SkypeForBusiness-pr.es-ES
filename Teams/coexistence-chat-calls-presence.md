---
title: Coexistencia con Skype Empresarial
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Comportamiento de coexistencia entre & Skype Empresarial de Teams, incluidos parámetros de enrutamiento, enrutamiento de llamadas & de chat, chats & llamadas de subprocesos preexistedos & presencia.
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562399"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistencia con Skype Empresarial

La coexistencia y la interoperabilidad entre Skype Empresarial y los clientes de Teams se controlan mediante modos de coexistencia. Para obtener más información, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams junto con Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md). Después de la retirada de Skype Empresarial Online el 31 de julio de 2021, los usuarios alojados en la nube siempre son usuarios de TeamsOnly. Ya no es posible asignar un modo de coexistencia distinto de TeamsOnly a un usuario en línea. Los modos de coexistencia distintos de TeamsOnly solo son relevantes para las organizaciones con implementaciones locales de Skype Empresarial Server o Lync Server 2013. En este artículo, cualquier referencia a "Skype Empresarial Server" también se aplica a Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Determinar el modo de coexistencia de un usuario
Todos los usuarios de organizaciones que no tengan ninguna implementación local de Skype Empresarial Server son del modo TeamsOnly y el modo efectivo del inquilino también es TeamsOnly. Esto se puede confirmar consultando la propiedad TeamsUpgradeEffectiveMode del inquilino o del usuario que usa Teams PowerShell.   Antes de la retirada de Skype Empresarial Online el 31 de julio de 2021, las organizaciones tenían la posibilidad de cambiar el modo de coexistencia para el usuario o el inquilino. Esto ya no es posible excepto para las organizaciones con una implementación local de Skype Empresarial Server, que no debe tener el modo de inquilino de TeamsOnly. Puede confirmar que el modo de coexistencia ya no se puede cambiar si TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" en el usuario o en el espacio empresarial.  (TeamsUpgradePolicyIsReadOnly en cualquier usuario tendrá el mismo valor que el valor del inquilino).  


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

En una organización con una implementación local de Skype Empresarial Server, la directiva global de inquilinos para TeamsUpgradePolicy puede tener cualquier modo *distinto de TeamsOnly*. Los modos permitidos son: *SfBOnly*, *SfBWithTeamsCollab* y *SfBWithTeamsCollabAndMeetings*. También se puede asignar directamente a los usuarios una instancia de TeamsUpgradePolicy, que sustituiría a la directiva global del inquilino.  Los usuarios alojados en la nube deben ser TeamsOnly y los usuarios locales deben ser cualquier modo distinto de TeamsOnly.  Si un usuario no tiene asignada una instancia de TeamsUpgradePolicy, el usuario recibe el valor de la directiva global del inquilino. 

## <a name="routing-parameters"></a>Parámetros de enrutamiento

El modo de coexistencia del destinatario determina el comportamiento de los chats, las llamadas y la presencia, tanto dentro de un inquilino como entre inquilinos federados. Si el remitente usa Teams, la decisión de enrutamiento se toma al crear una nueva conversación. Una vez creado un subproceso de conversación, su enrutamiento no cambia y conserva el método de enrutamiento determinado cuando se creó el subproceso.

Los métodos de enrutamiento de subprocesos son:

- *nativa* de una conversación de Teams a Teams en el espacio empresarial
- *interoperabilidad* para que un equipo Skype Empresarial conversación en el inquilino
- *federado nativo* para una conversación federada entre inquilinos cuando ambos usuarios tienen el modo TeamsOnly. 
- *interoperabilidad federada* para una conversación federada entre inquilinos que se basa en la interoperabilidad entre Skype Empresarial y Teams.

> [!NOTE]
> - Las conversaciones nativas, ya sean en el mismo espacio empresarial o en escenarios federados, se producen cuando el receptor y el remitente tienen el modo TeamsOnly. La conversación será una experiencia de chat nativa, que incluye todas las capacidades de llamada y mensajería enriquecidas. Para obtener más información, lea [Experiencia de chat nativa para usuarios externos (federados) en Teams](native-chat-for-external-users.md). 
> - Si alguno de los participantes de la conversación NO tiene el modo TeamsOnly, la conversación es una experiencia de interoperabilidad con mensajes de solo texto.
> - Las comunicaciones federadas entre usuarios de TeamsOnly en nubes multiinquilino y entornos de nube especiales (por ejemplo, nubes gubernamentales) aparecerán como chats federados de interoperabilidad.


Al crear una nueva conversación, los factores que determinan cómo se enruta el subproceso son:

- El modo de coexistencia del destinatario
- El cliente usado por el remitente
- Si la conversación está en el espacio empresarial o federado
- Si la conversación es posible. Si un usuario tiene una cuenta de Skype Empresarial local, ese usuario no puede usar el cliente de Teams para interoperabilidad en espacios empresariales ni para federación. Ese usuario solo puede usar el cliente de Skype Empresarial para la interoperabilidad y la federación. Tenga en cuenta que la comunicación entre Equipos y Teams siempre es posible en el espacio empresarial.

## <a name="chat-and-call-routing"></a>Enrutamiento de llamadas y chat
Las tablas siguientes muestran qué cliente en un modo determinado recibirá una llamada del originador (tres columnas situadas más a la izquierda). El experto que recibe la llamada depende del modo del originador, el cliente elegido y el lugar donde se aloja la cuenta de Skype Empresarial (local o en línea).

En las tablas siguientes:

- **Skype Empresarial** _ representa cualquiera de los modos siguientes: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *El texto en cursiva* resalta una conversación de interoperabilidad.
- **No es posible** representa una situación en la que el chat o la llamada no es posible. El creador debe usar Skype Empresarial en su lugar en estos casos. Esta es una de las razones por las que la guía prescriptiva de Microsoft para los clientes locales e híbridos es usar un modo que no sea Islas (normalmente SfBWithTeamsCollab) como punto de partida para su recorrido de actualización a Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Enrutamiento en el espacio empresarial para nuevos chats o llamadas

Las tablas siguientes capturan el enrutamiento de llamadas y chats dentro del espacio empresarial, y son válidas para llamadas o chats nuevos que no se inician desde una conversación preexistente. Aquí se describe qué cliente recibirá una nueva llamada o chat, si es originado por un usuario a la izquierda, a un usuario destinatario en el espacio empresarial a la derecha.  Los mensajes enviados a TeamsLos usuarios de TeamsOnly siempre se redirigirán a Teams. Los mensajes enviados a Skype Empresarial usuarios siempre se redirigirán a Skype Empresarial. Los mensajes enviados a los usuarios de las Islas siempre se redirigirán al mismo cliente desde el que se enviaron.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabla 1a: enrutamiento de llamadas o chats nuevos en el espacio empresarial a un destinatario del modo Desenlazamiento de Teams

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>&nbsp;Skype Empresarial homed|<br><br>Ruta: >|TeamsOnly Destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;|Teams <br> *Teams*|
|Skype Empresarial | Skype Empresarial | Local|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabla 1b: enrutamiento de llamadas o chats nuevos en el espacio empresarial a un destinatario del modo islas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>&nbsp;Skype Empresarial homed|<br><br>Ruta: >|Destinatario de islas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Aplicaciones aisladas| Teams <br> Skype Empresarial|Local<br>Local|&boxv;<br>&boxv;| Teams <br> Skype Empresarial|
|Skype Empresarial |Skype Empresarial | Local|&boxv;| Skype Empresarial|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabla 1c: enrutamiento de llamadas o chats nuevos en el espacio empresarial a un destinatario en un modo Skype Empresarial

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>&nbsp;Skype Empresarial homed|<br><br>Ruta: >|Skype Empresarial destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype Empresarial*|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;| **No es posible** <br> Skype Empresarial|
|Skype Empresarial | Skype Empresarial| Local|&boxv;| Skype Empresarial|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Enrutamiento federado para nuevos chats o llamadas

Las tablas siguientes capturan el enrutamiento de llamadas y chats federados y son válidas para llamadas o chats nuevos. Describen qué cliente recibirá una nueva llamada o chat, si lo ha originado un usuario a la izquierda, a un usuario de destino federado a la derecha. En resumen, si la conversación es posible como se describió anteriormente, los mensajes enviados a TeamsOnly los usuarios siempre llegarán a Teams; Los mensajes enviados a Skype Empresarial modo los usuarios siempre llegarán a Skype Empresarial; los mensajes enviados a los usuarios de las Islas siempre llegarán a Skype Empresarial independientemente del cliente desde el que se enviaron. 

El enrutamiento para los chats federados y las llamadas difiere del enrutamiento en el inquilino en que los usuarios de las Islas siempre recibirán una comunicación federada en Skype Empresarial. Esto se debe a que es posible que el partner federado todavía no esté usando Teams. El enrutamiento a Skype Empresarial para cualquier receta del modo islas garantiza que siempre se reciban mensajes.  El enrutamiento a Teams podría provocar que se perdiese la comunicación si el destinatario no usa Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabla 2a: nuevo chat federado o enrutamiento de llamadas a un destinatario del modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial alojado|<br><br>Ruta: >|TeamsOnly Destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Aplicaciones aisladas|Teams <br> Skype Empresarial|Local <br> Local|&boxv;<br>&boxv;|**No es posible** <br> *Teams*|
|Skype Empresarial |Skype Empresarial|Local|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabla 2b: nuevo chat federado o enrutamiento de llamadas a un destinatario de islas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial alojado|<br><br>Ruta: >|Destinatario de islas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype Empresarial*|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;| **No es posible** <br> Skype Empresarial|
|Skype Empresarial |Skype Empresarial| Local|&boxv;| Skype Empresarial|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabla 2c: enrutamiento de llamadas o chats nuevos federados a un destinatario en un modo Skype Empresarial

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype Empresarial alojado|<br><br>Ruta: >|Skype Empresarial destinatario|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype Empresarial*|
|Aplicaciones aisladas|Teams <br> Skype Empresarial| Local <br> Local|&boxv;<br>&boxv;|**No es posible** <br> Skype Empresarial|
|Skype Empresarial |Skype Empresarial|Local|&boxv;<br>&boxv;|Skype Empresarial|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats y llamadas de hilos preexistedos

### <a name="from-teams"></a>Desde Teams

Las llamadas o chats iniciados desde una conversación preexistente en Teams se enrutan de la misma manera que esa conversación. Si la conversación preexistente en Teams era una conversación nativa (es decir, enrutada a Teams), los mensajes de chat adicionales y las llamadas de esa conversación se enviarán a Teams. Si se trataba de una conversación de interoperabilidad (es decir, enrutada a Skype Empresarial), los mensajes de chat y las llamadas adicionales irán a Skype Empresarial (suponiendo que haya opciones de enrutamiento disponibles).

> [!NOTE]
> Es posible que los subprocesos preexistentes en Teams ya no sean enrutables, como cuando el subproceso era un subproceso de interoperabilidad para un usuario que desde entonces se ha actualizado a Teams. Dado que se creó como un subproceso de interoperabilidad, el subproceso se enrutaría a Skype Empresarial, pero ese usuario ya no puede usar Skype Empresarial para chatear y llamar. En ese caso, la conversación se deshabilitará y no permitirá más comunicación.

### <a name="from-skype-for-business"></a>Desde Skype Empresarial

Skype Empresarial subprocesos no persisten más allá del tiempo de espera de la sesión SIP de 10 minutos. Los chats y las llamadas de un subproceso existente en Skype Empresarial antes de la expiración de la sesión SIP se enrutarán de la misma manera que el subproceso. Las llamadas y chats de un subproceso existente en Skype Empresarial más allá del tiempo de espera de la sesión SIP se redirigirán al Skype Empresarial del usuario remoto, independientemente del cliente del que provenía el subproceso original del lado de la otra parte.

## <a name="presence"></a>Presence

En situaciones en las que algunos usuarios usan el cliente de Teams y otros usan el cliente de Skype Empresarial, es posible que algunos de estos usuarios usen ambos clientes. Es importante comprender que la presencia se publica en función del modo de coexistencia de un usuario. Por ejemplo, si la llamada o el chat de un autor debe llegar al cliente Skype Empresarial del destino, la presencia del cliente de Skype Empresarial debe mostrarse al creador. Si se posiciona en el cliente de Teams del destino, es la presencia del cliente de Teams la que se debe mostrar.

La presencia se comparte en función del modo de coexistencia de un usuario como se describe a continuación:

- Si un usuario está en modo TeamsOnly, cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá la presencia de Teams del usuario de Teams
- Si un usuario se encuentra en cualquiera de los modos Skype Empresarial (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), cualquier otro usuario (ya sea en Teams o Skype Empresarial) verá que Skype Empresarial presencia Skype Empresarial usuario
- Si un usuario está en modo Islas, la presencia en Teams y la presencia en Skype Empresarial son independientes (los valores no necesitan coincidir) y otros usuarios verán una u otra presencia del usuario de las Islas, dependiendo de si están en el mismo inquilino o en un inquilino federado y qué cliente usan
  - Desde Teams, cualquier otro usuario del mismo inquilino verá la presencia de Teams del usuario de las Islas; esto está alineado con la tabla de enrutamiento en el espacio empresarial anterior
  - Desde Teams, cualquier otro usuario de un inquilino federado verá la presencia Skype Empresarial del usuario de las Islas; esto está alineado con la tabla de enrutamiento federada anterior
  - Desde Skype Empresarial, cualquier otro usuario verá la presencia Skype Empresarial del usuario de las Islas (tanto en el inquilino como federado); esto está alineado con las tablas de enrutamiento anteriores

### <a name="in-tenant-presence"></a>Presencia en el espacio empresarial

Los mensajes enviados a TeamsLos usuarios de TeamsOnly siempre llegarán a Teams. Los mensajes enviados a Skype Empresarial modo los usuarios siempre estarán en Skype Empresarial, si la conversación es posible como se describió anteriormente. Los mensajes enviados a los usuarios de las Islas siempre llegarán al cliente desde el que se originaron.

En la tabla se describe la presencia de Publisher que verá un watcher, en función del modo del editor y del cliente del editor (para un subproceso nuevo).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabla 3: presencia en el espacio empresarial (nuevo subproceso)

<br>

|Observador<br><br>Cliente|<br><br>Ruta: >|<br><br>Aplicaciones aisladas|Publisher<br><br>Skype Empresarial|<br>Solo Teams|
|---|:---:|---|---|---|
|Skype Empresarial|&boxv;|Skype Empresarial|Skype Empresarial|Teams|
|Teams|&boxv;|Teams|Skype Empresarial|Teams|
|||||

### <a name="federated-presence"></a>Presencia federada

La presencia federada se basa en la accesibilidad federada que se muestra en la tabla 2.  En la tabla siguiente se describe la presencia de Publisher que verá un watcher, en función del modo del editor y del cliente del editor (para un subproceso nuevo). En la práctica, el cliente del Watcher no hace ninguna diferencia en la federación en esta etapa.

#### <a name="table-4-federated-presence-new-thread"></a>Tabla 4: presencia federada (nuevo subproceso)

<br>

|Observador<br><br>Cliente|<br><br>Ruta: >|<br><br>Aplicaciones aisladas|Publisher<br><br>Skype Empresarial|<br><br>Solo Teams|
|---|:---:|---|---|---|
|Skype Empresarial|&boxv;|Skype Empresarial|Skype Empresarial|Teams|
|Teams|&boxv;|Skype Empresarial|Skype Empresarial|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presencia en subprocesos preexisteros

Para alinear la presencia y el alcance en subprocesos preexistentes, la presencia del destino expuesta en ese subproceso debe alinearse con el enrutamiento del subproceso, suponiendo que el enrutamiento sea posible.  En particular, si un destinatario con el que tenía una conversación de interoperabilidad persistente se actualizó a Teams, ese subproceso ya no reflejará la presencia precisa y dejará de ser enrutable. Debe iniciar una nueva conversación.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federación e interoperabilidad con Office 365 operados por 21Vianet

La federación y la interoperabilidad entre Office 365 multiinquilino y Office 365 operados por 21Vianet son compatibles cuando los usuarios Office 365 multiempresa están en modo Solo teams. En este caso, Skype Empresarial usuarios en línea de Office 365 operados por 21Vianet podrán comunicarse con usuarios de Teams solo en Office 365 multiempresa a través de chats y llamadas. En la tabla siguiente se muestran los escenarios admitidos en esta configuración:
 
|Escenario|Origen|Destinatario|¿Compatible?|
|---|---|---|---|
|Presence|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí<br>Sí|
|Chat|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí (solo 1:1)<br>Sí(solo 1:1)|
|Llamadas de audio|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí (solo 1:1)<br>Sí (solo 1:1)|
|Videollamadas|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams|Sí (solo 1:1)<br>Sí (solo 1:1)|
|Uso compartido de la pantalla|Teams <br> Skype Empresarial <br> | Skype Empresarial <br> Teams |Sí (a través de una reunión de Teams promocionada)<br>Sí (a través de una reunión Skype Empresarial promocionada)|
|||||


## <a name="related-links"></a>Vínculos relacionados
[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Administrar la coexistencia y la interoperabilidad entre Skype Empresarial y Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
