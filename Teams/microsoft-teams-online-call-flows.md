---
title: Flujos de llamadas de Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Obtenga información sobre cómo Teams usa los flujos de Office 365 en diversas topologías, así como los flujos de equipo únicos usados para la comunicación multimedia punto a punto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13bd0479436963402124e7edea049bcc250d3515
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638669"
---
# <a name="microsoft-teams-call-flows"></a>Flujos de llamadas de Microsoft Teams

> [!TIP]
> Vea esta sesión para obtener información sobre cómo Teams aprovecha su red y cómo planear la conectividad de red óptima: planificación de la [red de Teams](https://aka.ms/teams-networking).

## <a name="overview"></a>Información general

En este artículo se describe cómo se usan los flujos de llamada de Microsoft 365 o de Office 365 en diversas topologías. Además, describe los flujos de equipos únicos que se usan para la comunicación multimedia punto a punto. El documento describe estos flujos, su propósito, así como su origen y terminación en la red. Para los fines de este artículo, supongamos lo siguiente:

- Flow X lo usa el cliente local para comunicarse con el servicio Microsoft 365 u Office 365 en la nube. Se origina desde la red del cliente y termina como un punto final en Microsoft 365 u Office 365.

- El flujo Y lo usa el cliente local para comunicarse con un servicio en Internet en el que Microsoft 365 u Office 365 tiene una dependencia. Se origina desde la red del cliente y termina como un extremo en Internet.

En este artículo se describe la siguiente información:

- **Fondo**. Proporciona información básica como redes que los flujos pueden atravesar, tipos de tráfico, guía de conectividad de la red del cliente a Microsoft 365 u Office 365 puntos de conexión de servicio, interoperabilidad con componentes de terceros y principios usados por Teams para seleccionar flujos de medios.

- **Flujos de llamadas en varias topologías**. Muestra el uso de los flujos de llamadas en varias topologías. Para cada topología, en la sección se enumeran todos los flujos compatibles y se muestra cómo se usan estos flujos en varios casos de uso. Para cada caso de uso, describe la secuencia y la selección de flujos usando un diagrama de flujo.

- **Teams con optimización de expressroute**. Describe cómo se usan estos flujos cuando se implementa Expressroute para la optimización, que se muestra con una topología simple.

## <a name="background"></a>Información general

### <a name="network-segments"></a>Segmentos de red

**Red de clientes**. Este es el segmento de red que controla y administra. Esto incluye todas las conexiones de los clientes dentro de las oficinas de los clientes, ya sea por cable o inalámbricas, conexiones entre los edificios de oficinas, conexiones a centros de trabajo locales y sus conexiones a proveedores de Internet, Expressroute o a cualquier otro emparejamiento privado.

Por lo general, una red de clientes tiene varios perímetros de red con firewalls o servidores proxy, que aplican las directivas de seguridad de su organización y que solo permiten un determinado tráfico de red que usted ha configurado y configurado. Como usted administra esta red, tiene control directo sobre el rendimiento de la red y le recomendamos que complete las evaluaciones de red para validar el rendimiento dentro de los sitios de su red y de su red con la red de Microsoft 365 u Office 365.

**Internet**. Este es el segmento de red que forma parte de su red general que usarán los usuarios que se conectan a Microsoft 365 u Office 365 desde fuera de la red del cliente. También lo usa el tráfico de la red del cliente a Microsoft 365 u Office 365.

**Redes privadas o invitados visitados**. Este es el segmento de red fuera de la red de clientes, pero no en la Internet pública, que los usuarios y sus invitados puedan visitar (por ejemplo, una red privada local o una red privada empresarial) que no implemente equipos en los que puedan residir los usuarios y los clientes que interactúan con los servicios de Teams.

> [!NOTE]
> La conectividad a Microsoft 365 u Office 365 también es aplicable a estas redes.

**Microsoft 365 u Office 365**. Este es el segmento de red compatible con Microsoft 365 u Office 365 Services. Se distribuye por todo el mundo con bordes cercanos a la red del cliente en la mayoría de las ubicaciones. Las funciones incluyen retransmisión de transporte, servidor de conferencia y procesador de medios.

Expressroute **(opcional)**. Este es el segmento de red que forma parte de su red general que le proporcionará una conexión privada y dedicada a la red de Microsoft 365 u Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfico

**Medios en tiempo real**. Datos encapsulados en el protocolo de transporte en tiempo real (RTP) que admite las cargas de trabajo de audio, vídeo y pantalla compartida. En general, el tráfico multimedia es sensible a la latencia, por lo que le gustaría que este tráfico tomara la ruta más directa posible y usar UDP en comparación con TCP como protocolo de la capa de transporte, que es el mejor transporte de medios de tiempo interactivo en tiempo real desde una perspectiva de calidad. (Tenga en cuenta que, como último recurso, los elementos multimedia pueden usar TCP/IP y también pueden estar tunelizados dentro del protocolo HTTP, pero no se recomienda debido a consecuencias de calidad erróneas). El flujo RTP se asegura mediante SRTP, en la que solo se cifra la carga.

**Señalización**. El vínculo de comunicación entre el cliente y el servidor, u otros clientes que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y enviar mensajes instantáneos. La mayoría de las señales de tráfico usan las interfaces de REST basadas en HTTPS, aunque en algunos escenarios (por ejemplo, la conexión entre Microsoft 365 u Office 365 y un controlador de borde de sesión) usa el protocolo SIP. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede provocar interrupciones de servicio o tiempos de espera de llamadas si la latencia entre los puntos de conexión supera varios segundos.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Conectividad con Microsoft 365 u Office 365

Teams requiere [conectividad a Internet](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity). Las direcciones URL y los intervalos de direcciones IP de los terminales se enumeran en [Office 365 direcciones URL e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). (Tenga en cuenta que se requiere conectividad abierta a los puertos TCP 80 y 443, y a los puertos UDP 3478 a 3481). Además, Teams tiene una dependencia en Skype empresarial online, que también debe estar conectado a Internet.

Equipos de equipos multimedia la conectividad se implementa con procedimientos estándar del tipo de conectividad interactiva de IETF (ICE).

### <a name="interoperability-restrictions"></a>Restricciones de interoperabilidad

**Retransmisiones multimedia de terceros**. Un flujo de medios de Teams (es decir, cuando uno de los puntos de conexión multimedia es Teams) puede atravesar solo los equipos o las retransmisiones multimedia nativas de Skype empresarial. No se admite la interoperabilidad con retransmisiones multimedia de terceros. (Tenga en cuenta que un SBC de terceros en el límite con RTC debe finalizar la secuencia RTP/RTCP, protegerse con SRTP y no retransmitirla al siguiente salto).

**Servidores proxy SIP de terceros**. Un cuadro de diálogo de la señalización de equipos con un SBC o una puerta de enlace de terceros puede atravesar equipos o proxies SIP nativos de Skype empresarial. No se admite la interoperabilidad con un proxy SIP de terceros.

**B2BUA (o SBC) de terceros**. Un SBC de terceros termina un flujo de medios de equipos hacia y desde la RTC. Sin embargo, no se admite la interoperabilidad con un SBC de terceros dentro de la red de equipos (donde un SBC de terceros corrige dos equipos o puntos de conexión de Skype empresarial).

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologías que no se recomiendan con Microsoft Teams

**Red VPN**. No se recomienda para el tráfico de medios (o el flujo 2 '). El cliente VPN debe usar la división VPN y el tráfico de medios de enrutamiento, como cualquier otro usuario externo que no sea de VPN, como se especifica en [Habilitar el medio de Lync para eludir un túnel VPN](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).

> [!NOTE]
> Aunque el título indica Lync, también se aplica a los equipos.

**Formadores de paquetes**. Cualquier tipo de snippers de paquetes, la inspección de paquetes o los dispositivos de forma de paquetes no son recomendables y puede degradar significativamente la calidad.

### <a name="principles"></a>Principios

Hay cuatro principios generales que le ayudan a comprender los flujos de llamadas para Microsoft Teams:

- Una conferencia de Microsoft Teams está hospedada en Microsoft 365 u Office 365 en la misma región en la que se unió el primer participante. (Tenga en cuenta que si hay excepciones a esta regla en algunas topologías, se describen en este documento y se muestra un flujo de llamada adecuado).

- Se usa un extremo de Team media en Microsoft 365 u Office 365 según las necesidades de procesamiento de contenido multimedia y no según el tipo de llamada. (Por ejemplo, una llamada punto a punto puede usar un extremo de medios en la nube para procesar medios para transcripción o grabación, mientras que una conferencia con dos participantes no puede usar ningún extremo multimedia en la nube). Sin embargo, la mayoría de las conferencias usarán un extremo de medios para la mezcla y enrutamiento, asignados donde se hospeda la Conferencia. El tráfico multimedia enviado desde un cliente al extremo de medios se puede enrutar directamente o usar una retransmisión de transporte en Microsoft 365 u Office 365 si es necesario debido a restricciones de Firewall de red del cliente.

- El tráfico de medios para las llamadas de punto a punto toma la ruta más directa disponible, suponiendo que la llamada no impone un extremo de medios en la nube (vea el principio anterior). La ruta preferida es directa al interlocutor remoto (cliente), pero si esa ruta no está disponible, una o más retransmisiones de transporte retransmitirán el tráfico. Se recomienda que el tráfico multimedia no sea un servidor transversal, como formadores de paquetes, servidores VPN, etc., ya que esto afectará la calidad de los medios.

- El tráfico de señalización siempre va al servidor más cercano.

Para obtener más información sobre los detalles de la ruta de medios seleccionada, consulte [Descripción de los flujos multimedia en Microsoft Teams-BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).

## <a name="call-flows-in-various-topologies"></a>Flujos de llamadas en varias topologías

### <a name="teams-topology"></a>Topología de Teams

Esta topología la usan los clientes que aprovechan los servicios de Teams de la nube sin ninguna implementación local, como el enrutamiento directo de Skype empresarial Server o el sistema telefónico. Además, la interfaz para Microsoft 365 u Office 365 se realiza a través de Internet sin la ruta de Azure Express.

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1: topología de Teams*

Tenga en cuenta lo siguiente:

- La dirección de las flechas en el diagrama anterior reflejan la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para medios, los primeros paquetes pueden fluir en dirección contraria, pero estos paquetes se pueden bloquear hasta que se transmitan paquetes de la otra dirección.
- Teams se implementa en paralelo con Skype empresarial online, por lo que los clientes se muestran como "Teams/SFB user".

Puede encontrar más información sobre las siguientes topologías opcionales más adelante en este artículo:

- La implementación local de Skype empresarial se describe en la **topología híbrida de Teams**.
- El enrutamiento directo de sistema telefónico (para conectividad RTC) se describe en **Teams con topología de enrutamiento directo**.
- Expressroute se describe en **Teams with Express Route Optimization**.

**Descripciones de flujos**:

- **Flow 2** : representa un flujo Iniciado por un usuario en la red del cliente a través de Internet como parte de la experiencia de los equipos de los usuarios. Algunos ejemplos de estos flujos son medios DNS y de par a par.
- **Flow 2 '** : representa un flujo Iniciado por un usuario remoto de equipos móviles, con VPN a la red del cliente.
- **Flujo 3** : representa un flujo Iniciado por un usuario de equipos móviles remotos a Microsoft 365 o a puntos de conexión de Office 365/Teams.
- **Flow 4** : representa un flujo Iniciado por un usuario en la red del cliente a Microsoft 365 o a los puntos de conexión de Office 365/Teams.
- **Flujo 5** : representa un flujo de medios de par a par entre un usuario de Teams y otros equipos o usuarios de Skype empresarial dentro de la red de clientes.
- **Flujo 6** : representa un flujo de medios de punto a punto entre un usuario de equipos móviles remotos y otros equipos móviles remotos o un usuario de Skype empresarial a través de Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: uno a uno

Las llamadas uno a uno usan un modelo común en el que la persona que llama obtendrá un conjunto de candidatos que consta de direcciones IP y puertos, incluidos los candidatos local, de retransmisión y reflexivo (dirección IP pública del cliente como lo ven los candidatos de retransmisión). La persona que llama envía estos candidatos a la persona a la que se llama; la persona a la que llama también obtiene un conjunto similar de candidatos y los envía a la persona que llama. Los mensajes de comprobación de conectividad de STUN se usan para averiguar qué llamador o qué rutas multimedia funcionan y se selecciona la mejor ruta de trabajo. Los medios (es decir, los paquetes RTP/RTCP protegidos con SRTP) se envían a continuación con el par de candidatos seleccionado. La retransmisión de transporte se implementa como parte de Microsoft 365 y Office 365.

Si la dirección IP local y los candidatos al puerto o los candidatos devueltos tienen conectividad, entonces la ruta directa entre los clientes (o el uso de un NAT) se seleccionará para los medios. Si los clientes están en la red del cliente, se debe seleccionar la ruta directa. Esto requiere conectividad UDP directa dentro de la red del cliente. Si los clientes son ambos usuarios de la nube Nomadic, según el NAT o el firewall, es posible que los medios usen conectividad directa.

Si un cliente es interno en la red del cliente y un cliente es externo (por ejemplo, un usuario móvil de la nube), es improbable que la conectividad directa entre los candidatos reforzables o locales funcione. En este caso, una opción es usar uno de los candidatos de retransmisión de transporte desde cualquier cliente (por ejemplo, el cliente interno obtenido a un candidato de retransmisión de la transmisión de transporte en Microsoft 365 u Office 365; el cliente externo debe poder enviar paquetes STUN/RTP/RTCP a la retransmisión de transporte). Otra opción es que el cliente interno envíe al candidato de retransmisión obtenido por el cliente de nube móvil. Tenga en cuenta que, aunque se recomienda encarecidamente la conectividad UDP para medios, TCP es compatible.

**Pasos de alto nivel**:

1. El usuario de Teams A resuelve el nombre de dominio (DNS) de la dirección URL con el flujo 2.
1. El usuario de Teams A asigna un puerto de retransmisión de multimedia en Team Relay de transporte usando Flow 4.
1. El usuario A de Teams A envía una "invitación" con candidatos de hielo usando el flujo 4 a Microsoft 365 u Office 365.
1. Microsoft 365 u Office 365 envía una notificación a los equipos que el usuario B usa en Flow 4.
1. Teams el usuario B asigna un puerto de retransmisión de multimedia en Team retransmisión de transporte con Flow 4.
1. Los equipos que el usuario B envía "respuesta" con candidatos de hielo con el flujo 4, que se reenvía al usuario de Teams a través de Flow 4.
1. Teams el usuario A y los equipos del usuario B invocan pruebas de conectividad de ICE y se selecciona la mejor ruta de medios disponible (vea los diagramas siguientes para los distintos casos de uso).
1. Los usuarios de Teams envían telemetría a Microsoft 365 u Office 365 con Flow 4.

**Dentro de la red del cliente:**

[![Flujos de llamadas en línea de Microsoft Teams, figura 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Ilustración 2: dentro de la red del cliente*

En el paso 7, se selecciona flujo de medios de punto a punto 5.

Los medios son bidireccionales. La dirección del flujo 5 indica que un lado inicia la comunicación desde un punto de vista de la conectividad, coherente con todos los flujos de este documento. En este caso, no importa qué dirección se use porque ambos puntos de conexión se encuentran dentro de la red del cliente.

**Red de clientes para usuarios externos (medios retransmitidos por la retransmisión de transporte de Teams):**

[![Flujos de llamada de Microsoft Teams online, Ilustración 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3: red de clientes para usuarios externos (medios retransmitidos por la retransmisión de transporte de Teams)*

En el paso 7, flujo 4, de la red del cliente a Microsoft 365 u Office 365, y el flujo 3, del usuario de equipos móviles remotos a Microsoft 365 u Office 365, está seleccionado. Estos flujos se retransmiten a través de Teams transporte de retransmisión dentro de Microsoft 365 u Office 365.

Los medios son bidireccionales, donde dirección indica qué lado inicia la comunicación desde una perspectiva de conectividad. En este caso, estos flujos se usan para la señalización y los medios con diferentes protocolos de transporte y direcciones.

**Red de clientes para usuarios externos (medios directos):**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4: red de clientes para usuarios externos (medios directos)*

En el paso 7, está seleccionado flujo 2, desde la red del cliente hasta Internet (es decir, el interlocutor del cliente).

- Los medios directos con usuarios móviles remotos (no retransmitidos mediante Microsoft 365 u Office 365) son opcionales. En otras palabras, el cliente puede bloquear este camino para exigir una ruta de medios a través del transmisor de transporte en Microsoft 365 u Office 365.

- Los medios son bidireccionales. La dirección del flujo 2 a un usuario móvil remoto indica que un lado inicia la comunicación desde un punto de vista de la conectividad.

**Usuario de VPN para usuarios internos (medios retransmitidos por la retransmisión de transporte de Teams)**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Ilustración 5: usuario de VPN para usuarios internos (medios retransmitidos por la retransmisión de transporte de Teams)*

La señalización entre la red privada para la red del cliente está usando el flujo 2. La señalización entre la red del cliente y Microsoft 365 u Office 365 está usando el flujo 4. Sin embargo, los elementos multimedia omiten la red privada virtual y se enrutan mediante los flujos 3 y 4 a teams media Relay en Microsoft 365 u Office 365.

**Usuario de VPN para usuarios internos (medios directos)**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6: usuario de VPN para usuarios internos (medios directos)*

La señalización entre la red privada para la red del cliente está usando el flujo 2. La señalización entre la red del cliente y Microsoft 365 u Office 365 está usando el flujo 4. Sin embargo, los elementos multimedia omiten la VPN y se enrutan mediante el flujo 2 desde la red del cliente a Internet.

Los medios son bidireccionales. La dirección del flujo 2 al usuario móvil remoto indica que un lado inicia la comunicación desde un punto de vista de la conectividad.

**Usuario de VPN a usuarios externos (medios directos)**

[![Flujos de llamada de Microsoft Teams, Ilustración 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7: usuario de VPN a usuarios externos (medios directos)*

La señalización entre el usuario de VPN y la red del cliente está usando el flujo 2 y usa el flujo 4 a Microsoft 365 u Office 365. Sin embargo, los elementos multimedia omiten VPN y se enrutan mediante el flujo 6.

Los medios son bidireccionales. La dirección del flujo 6 al usuario móvil remoto indica que un lado inicia la comunicación desde un punto de vista de la conectividad.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Caso de uso: equipos a RTC a través de Microsoft 365 u Office 365 troncal

Microsoft 365 y Office 365 tienen un sistema telefónico que permite realizar y recibir llamadas de la red de telefonía pública conmutada (RTC). Si el tronco de RTC se conecta mediante el plan de llamadas de sistema telefónico, no hay ningún requisito especial de conectividad para este caso de uso. (Si desea conectar su propio tronco local de RTC a Microsoft 365 u Office 365, puede usar el enrutamiento directo del sistema telefónico).

[![Flujos de llamada de Microsoft Teams online, figura 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8: Teams to PSTN mediante Office 365 trunk*

#### <a name="use-case-teams-meeting"></a>Caso de uso: reunión de Teams

El servidor de conferencia audio/vídeo/pantalla compartida (VBSS) es parte de Microsoft 365 y Office 365. Tiene una dirección IP pública que debe ser accesible desde la red del cliente y debe ser alcanzable desde un cliente de Nomadic Cloud. Cada cliente/extremo debe poder conectarse al servidor de conferencia.

Los clientes internos obtendrán candidatos locales, reflexivos y de retransmisión, de la misma manera que lo describen las llamadas de uno a uno. Los clientes enviarán estos candidatos al servidor de conferencia en una invitación. El servidor de conferencia no usa una retransmisión porque tiene una dirección IP accesible públicamente, por lo que responde con su candidato de dirección IP local. El cliente y el servidor de conferencia verificarán la conectividad de la misma forma que se describe para las llamadas de uno a uno.

Tenga en cuenta lo siguiente:

- Los clientes de Teams no pueden unirse a reuniones de Skype empresarial y los clientes de Skype empresarial no pueden unirse a reuniones de Teams.

- Un usuario de la RTC, opcionalmente, "marca" o está "marcado", según las llamadas RTC de la reunión o el aprovisionamiento de conferencias.

- Un usuario invitado o un usuario del cliente se pueden unir desde una red privada de invitado, que está protegida con el FW/NAT con reglas estrictas.

[![Flujos de llamadas en línea de Microsoft Teams ilustración 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9: reunión de Teams*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso de uso: Federación con Skype empresarial local

**Multimedia retransmitida por Teams transmisión de transporte en Microsoft 365 u Office 365**

[![Flujos de llamadas en línea de Microsoft Teams, figura 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10: medios retransmitidos por el transporte de Teams en Office 365*

Tenga en cuenta lo siguiente:

- La Federación es, por definición, una comunicación entre dos inquilinos. En este caso, el inquilino A, que usa Teams, federates con el inquilino B, que usa Skype empresarial local. Si el inquilino B también está usando Microsoft 365 u Office 365, el cliente de Skype empresarial habría usado el flujo 3 para conectarse con Microsoft 365 u Office 365.

- La señalización y los medios del cliente de Skype empresarial federado a Skype empresarial Server local está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- La señalización entre equipos y Skype empresarial está unida por un Gateway.

- En este caso, los medios se retransmiten a través de Teams transporte a la red del cliente y el cliente remoto de Skype empresarial con Flow 4.

**Multimedia retransmitida por la retransmisión multimedia de Skype empresarial en el inquilino federado**

[![Flujos de llamadas en línea de Microsoft Teams, ilustración 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Ilustración 11: multimedia retransmitida por la retransmisión de multimedia de Skype empresarial en un inquilino federado*

Tenga en cuenta lo siguiente:

- La señalización y los medios del cliente de Skype empresarial federado para un servidor local de Skype empresarial está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- La señalización entre equipos y Skype empresarial está unida por un Gateway.

- En este caso, los medios son retransmitidos por la retransmisión de multimedia local de Skype empresarial a la red del cliente mediante el flujo 2. (Tenga en cuenta que el transmisor de transmisión multimedia bloqueará el tráfico de los usuarios de Teams a través de la red de clientes federados, hasta que el tráfico en la dirección inversa comience a fluir. Sin embargo, el flujo bidireccional abrirá la conectividad en ambas direcciones.)

**Directo (de punto a punto)**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Ilustración 12: directo (de punto a punto)*

### <a name="teams-hybrid-topology"></a>Topología híbrida de Teams

Esta topología incluye equipos con una implementación local de Skype empresarial.

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13: topología híbrida de Teams*

- La dirección de las flechas en el diagrama anterior reflejan la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para medios, los primeros paquetes pueden fluir en dirección contraria, pero estos paquetes se pueden bloquear hasta que se transmitan paquetes de la otra dirección.

- Teams se implementa en paralelo con Skype empresarial online, por lo que los clientes se muestran como "Teams/SFB user".

Flujo adicional (en la parte superior de la topología de Teams):

- **Flow 5A** : representa un flujo de medios de par a par entre un usuario de Teams dentro de la red del cliente y una retransmisión multimedia local de Skype empresarial en el perímetro de la red del cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: equipos para Skype empresarial uno a uno

**Híbrido dentro de la red del cliente**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Ilustración 14: híbrida dentro de la red de clientes*

La señalización entre equipos y Skype empresarial está unida por un Gateway. Sin embargo, los medios se enrutan directamente de punto a punto dentro de la red del cliente usando el flujo 5.

**Red de clientes híbridos con usuario externo de Skype empresarial: retransmitida por Microsoft 365 u Office 365**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15: red de clientes híbridas con usuario externo de Skype para empresas retransmitida por Office 365*

Tenga en cuenta lo siguiente:

- La señalización y los medios del cliente de Skype empresarial para un servidor local de Skype empresarial está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- La señalización entre equipos y Skype empresarial está unida por un Gateway.

- Los medios se retransmiten a través de Teams transporte a la red del cliente a través de Flow 4.

**Red de clientes híbrida con usuario externo de Skype empresarial: retransmitida por un borde local**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16: red de clientes híbridas con usuario externo de Skype para empresas retransmitida por un borde local*

Tenga en cuenta lo siguiente:

- La señalización y los medios del cliente de Skype empresarial para un servidor local de Skype empresarial está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- La señalización está unida por una puerta de enlace.

- Los medios son retransmitidos por el servicio de transmisión de multimedia de Skype empresarial dentro de la periferia local de Skype empresarial a los usuarios de la red del cliente que usan el flujo de medios 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Equipos con topología de enrutamiento directo de sistema telefónico

Esta topología incluye equipos con enrutamiento directo de sistema telefónico.

El enrutamiento directo le permite usar un proveedor de servicios de red telefónica de telefonía conmutada (RTC) de terceros al emparejar un dispositivo de hardware de controlador de borde de sesión local (SBC) de propiedad de cliente de terceros admitido a Microsoft 365 u Office 365 y, a continuación, conectar el tronco de telefonía a ese dispositivo.

Para admitir este escenario, el cliente debe implementar un SBC certificado para el enrutamiento directo desde uno de los socios certificados de Microsoft. La SBC debe estar configurada como recomendada por el proveedor y ser enrutable desde Microsoft 365 u Office 365 para el tráfico UDP directo. Los medios pueden transmitirse directamente desde Teams o el cliente de Skype empresarial a SBC (eludiendo la puerta de enlace de Teams) o atravesar la puerta de enlace de Teams. La conectividad con SBC, cuando el tronco está configurado para evitar la puerta de enlace de Teams, se basa en ICE, donde SBC admite ICE-Lite, mientras que el extremo de los equipos/Skype para empresas admite la forma completa de ICE.

[![Flujos de llamada de Microsoft Teams online, Ilustración 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* Figura 17-equipos con topología de enrutamiento directo de sistema telefónico

Tenga en cuenta lo siguiente:

- La dirección de las flechas en el diagrama anterior reflejan la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para medios, los primeros paquetes pueden fluir en dirección contraria, pero estos paquetes se pueden bloquear hasta que se transmitan paquetes de la otra dirección.

- Teams se implementa en paralelo con Skype empresarial online, por lo que los clientes se muestran como "Teams/SFB user".

Flujos adicionales (en la parte superior de la topología de Teams online):

- **Flow 4 '** : representa un flujo de Microsoft 365 u Office 365 a la red del cliente, que se usa para establecer una conexión entre el servidor de equipos multimedia de la nube con la SBC en local.
- **Flujo 5B** : representa un flujo de medios entre el usuario de Teams dentro de la red del cliente con el SBC de enrutamiento directo en el modo de omisión.
- **Flujo 5C** : representa un flujo de medios entre el SBC de enrutamiento directo a otro SBC de enrutamiento directo en un modo de omisión de llamada de Hairpin RTC.

**Usuario interno con enrutamiento directo (medios retransmitidos por la retransmisión de transporte de Teams)**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Ilustración 18: usuario interno con enrutamiento directo (multimedia retransmitida por la retransmisión de transporte de Teams)*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365.

- La señalización y los medios de SBC a Microsoft 365 u Office 365 y viceversa usan el flujo 4 o el flujo 4.

- Señalización y medios desde el cliente dentro de la red del cliente a Microsoft 365 u Office 365 usar Flow 4.

**Usuario remoto con enrutamiento directo (los medios se enrutan a través de un servidor multimedia (MP))**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Ilustración 19: usuario remoto con enrutamiento directo (los medios se dirige a través de un servidor multimedia (MP))*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365.

- La señalización y los medios de SBC a Microsoft 365 u Office 365 y viceversa usan el flujo 4 o el flujo 4.

- Las señales y los medios del cliente en Internet a Microsoft 365 u Office 365 usan el flujo 3.

**Enrutamiento directo de usuario interno (omisión de medios)**

[![Flujos de llamadas en línea de Microsoft Teams, figura 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20: enrutamiento directo de usuario interno (omisión de medios)*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365.

- La señalización de SBC a Microsoft 365 u Office 365 y viceversa usan el flujo 4 o el flujo 4.

- La señalización desde el cliente dentro de la red del cliente a Microsoft 365 u Office 365 usar Flow 4.

- Los medios desde el cliente dentro de la red del cliente hasta SBC dentro de la red del cliente usan el flujo 5B.

**Usuario remoto con enrutamiento directo (omisión de medios retransmitida por Teams retransmisión de transporte)**

[![Flujos de llamadas en línea de Microsoft Teams, ilustración 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21: usuario remoto con enrutamiento directo (omisión de medios transmitida por Teams retransmisión de transporte)*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365 y a través de Internet.

- La señalización de SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 o el flujo 4.

- La señalización del cliente en Internet a Microsoft 365 u Office 365 usa el flujo 3.

- Los medios del cliente en Internet a la SBC dentro de la red del cliente usan los flujos 3 y 4, retransmitidos por la retransmisión de transporte de Teams.

**Enrutamiento directo de usuario remoto (dirección por omisión de medios)**

[![Flujos de llamada de Microsoft Teams online, figura 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22: enrutamiento directo de usuario remoto (medios bypass directos)*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365 e Internet.

- La señalización de SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 o el flujo 4.

- La señalización del cliente en Internet a Microsoft 365 u Office 365 usa el flujo 3.

- Los medios del cliente en Internet a la SBC dentro de la red del cliente usan el flujo 2.

**Enrutamiento directo (omisión de medios): llamada RTC Hairpin (debido a la transferencia o a la transferencia de llamadas)**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figura 23: enrutamiento directo (omisión de medios)-llamada RTC Hairpin (debido a la transferencia de llamadas/transferencias)*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365.

- La señalización de SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 o el flujo 4.

- El cliente está fuera de la señalización y el bucle de medios después de que la llamada se hairpinned de la RTC a la RTC.

- Los elementos multimedia de la instancia de SBC a dentro de la red del cliente a la instancia de SBC B dentro de la red del cliente (donde, A y B pueden ser la misma instancia) usa el flujo 5C.

**Enrutamiento directo (multimedia a través de Microsoft 365 u Office 365): llamada RTC Hairpin en dos espacios empresariales**

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Ilustración 24: enrutamiento directo (multimedia a través de Microsoft 365 u Office 365): llamada RTC Hairpin en dos espacios empresariales*

Tenga en cuenta lo siguiente:

- La SBC debe tener una dirección IP pública que se pueda enrutar desde Microsoft 365 u Office 365.

- La señalización de SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 o el flujo 4.

- El cliente está fuera de la señalización y el bucle de medios después de que la llamada se hairpinned de la RTC a la RTC.

- Los elementos multimedia de la instancia de SBC a dentro de la instancia de Network X a SBC B deben retransmitirse a través de Microsoft 365 o de Office 365 Media Server, y no pueden usar el modo de omisión.

## <a name="teams-with-express-route-optimization"></a>Teams con optimización de Expressroute

[![Flujos de llamadas en línea de Microsoft Teams, Ilustración 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25-equipos con optimización de Expressroute*

En el caso de que expressroute esté justificado e implementado, los flujos de equipos podrían ser redirigidos desde el flujo 4 al flujo 1 y desde el flujo 4 hasta el flujo 1. Sin embargo, la aplicación de Teams tiene una dependencia fuerte en otros flujos de Microsoft 365 u Office 365 a través de Internet con los flujos 4 y 4. por lo tanto, estos flujos no se deben bloquear.

Tenga en cuenta que el tráfico perimetral de Skype empresarial híbrido se enruta a Internet y no se expresa para comunicarse con usuarios externos y federar a otros inquilinos.

Para evitar flujos asimétricos, el redireccionamiento debe estar en ambas direcciones. En otras palabras, una dirección dentro de la red del cliente se puede enrutar a través de Internet o expressroute, en función de la optimización, pero no de ambos.


**Red de clientes para usuarios externos (medios retransmitidos por la retransmisión de transporte de Teams):**

[![Flujos de llamadas en línea de Microsoft Teams, ilustración 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26: red de clientes para usuarios externos (medios retransmitidos por la retransmisión de transporte de Teams)*

**Pasos de alto nivel:**

1. Los usuarios de Teams de la red de clientes resuelven el nombre de dominio (DNS) mediante Flow2.
1. Los usuarios de Teams de la red del cliente asignan un puerto de retransmisión de multimedia en Teams transporte de transporte usando el flujo 1.
1. El usuario de Teams de la red del cliente envía "invitar" a los candidatos de hielo mediante el flujo 1 a Microsoft 365 u Office 365.
1. Microsoft 365 u Office 365 envía una notificación al usuario de equipos externos que usa el flujo 3.
1. Teams el usuario externo asigna un puerto de retransmisión de multimedia en Team retransmisión de transporte con Flow 3.
1. El usuario externo de Teams envía "respuesta" a los candidatos de hielo mediante el flujo 3, que se reenvía al usuario de Teams a través de Flow 1.
1. Teams usuario A y Teams usuario B invocan pruebas de conectividad de ICE y selecciona los flujos 1 y 3, que se retransmiten a través de la retransmisión de transporte de Teams.
1. Los usuarios de Teams envían telemetría a Microsoft 365 u Office 365 con los flujos 1 y 3.

> [!NOTE]
> El flujo 4 debe estar habilitado para admitir dependencias de aplicaciones de Teams en otros microservicios que contengan el flujo 4.
