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
description: Obtenga información sobre cómo Teams usa flujos de Office 365 en varias topologías, así como flujos de equipo únicos que se usan para la comunicación multimedia punto a punto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27a2c68483c3d54cb3f3572bbed3a06a53ccc67e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059214"
---
# <a name="microsoft-teams-call-flows"></a>Flujos de llamadas de Microsoft Teams

> [!TIP]
> Vea esta sesión para obtener información sobre cómo Teams aprovecha su red y cómo planear una conectividad de red óptima: [Planificación de red de Teams.](https://aka.ms/teams-networking)

## <a name="overview"></a>Información general

En este artículo se describe cómo Teams usa Flujos de llamadas de Microsoft 365 u Office 365 en varias topologías. Además, describe flujos únicos de Teams que se usan para la comunicación multimedia punto a punto. En el documento se describen estos flujos, su finalidad y su origen y finalización en la red. Para los fines de este artículo, suponga lo siguiente:

- El cliente local usa Flow X para comunicarse con el servicio de Microsoft 365 u Office 365 en la nube. Procede de la red de clientes y termina como punto de conexión en Microsoft 365 u Office 365.

- El cliente local usa el flujo Y para comunicarse con un servicio en Internet en el que Microsoft 365 u Office 365 tienen una dependencia. Se origina a partir de la red del cliente y termina como un punto de conexión en Internet.

En este artículo se trata la siguiente información:

- **Fondo**. Proporciona información de fondo, como redes que los flujos pueden atravesar, tipos de tráfico, instrucciones de conectividad de la red de clientes a puntos de conexión de servicio de Microsoft 365 u Office 365, interoperabilidad con componentes de terceros y principios que usa Teams para seleccionar flujos multimedia.

- **La llamada fluye en varias topologías.** Ilustra el uso de flujos de llamadas en varias topologías. Para cada topología, la sección enumera todos los flujos admitidos e ilustra cómo se usan estos flujos en varios casos de uso. Para cada caso de uso, describe la secuencia y selección de flujos mediante un diagrama de flujo.

- **Teams con optimización de Ruta rápida.** Describe cómo se usan estos flujos cuando express route se implementa para la optimización, ilustrado con una topología simple.

## <a name="background"></a>Información general

### <a name="network-segments"></a>Segmentos de red

**Red de clientes**. Este es el segmento de red que controla y administra. Esto incluye todas las conexiones de clientes dentro de las oficinas de clientes, ya sean cableadas o inalámbricas, conexiones entre edificios de oficinas, conexiones a centros de datos locales y sus conexiones a proveedores de Internet, Express Route o cualquier otro emparejamiento privado.

Normalmente, una red de clientes tiene varios perímetros de red con firewalls o servidores proxy, que aplican las directivas de seguridad de su organización y que solo permiten cierto tráfico de red que haya configurado y configurado. Dado que administra esta red, tiene control directo sobre el rendimiento de la red y le recomendamos que complete evaluaciones de red para validar el rendimiento tanto dentro de los sitios de la red como desde su red a la red de Microsoft 365 u Office 365.

**Internet**. Este es el segmento de red que forma parte de la red general que usarán los usuarios que se conecten a Microsoft 365 u Office 365 desde fuera de la red de clientes. También lo usa algún tráfico desde la red de clientes a Microsoft 365 u Office 365.

**Red privada visitada o invitada.** Este es el segmento de red fuera de su red de clientes, pero no en internet público, que los usuarios y sus invitados pueden visitar (por ejemplo, una red privada doméstica o una red privada empresarial, que no implementa Teams, donde pueden residir sus usuarios y sus clientes que interactúan con los servicios de Teams).

> [!NOTE]
> La conectividad a Microsoft 365 u Office 365 también se aplica a estas redes.

**Microsoft 365 u Office 365**. Este es el segmento de red compatible con los servicios de Microsoft 365 u Office 365. Se distribuye en todo el mundo con bordes cercanos a la red de clientes en la mayoría de las ubicaciones. Entre las funciones se incluyen Retransmisión de transporte, servidor de conferencias y Procesador multimedia.

**Ruta rápida (opcional).** Este es el segmento de red que forma parte de la red general que le dará una conexión privada dedicada a la red de Microsoft 365 u Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfico

**Multimedia en tiempo real**. Datos encapsulados dentro del Protocolo de transporte en tiempo real (RTP) que admite cargas de trabajo de audio, vídeo y uso compartido de pantalla. En general, el tráfico multimedia es altamente sensible a la latencia, por lo que le gustaría que este tráfico tomara la ruta más directa posible y usar UDP frente a TCP como protocolo de capa de transporte, que es el mejor transporte para medios interactivos en tiempo real desde una perspectiva de calidad. (Tenga en cuenta que, como último recurso, los medios pueden usar TCP/IP y también se pueden túneles dentro del protocolo HTTP, pero no se recomienda debido a malas implicaciones de calidad). El flujo RTP se protege con SRTP, en el que solo se cifra la carga.

**Señalización**. El vínculo de comunicación entre el cliente y el servidor u otros clientes que se usan para controlar actividades (por ejemplo, cuando se inicia una llamada) y entregar mensajes instantáneos. La mayoría del tráfico de señalización usa las interfaces REST basadas en HTTPS, aunque en algunos escenarios (por ejemplo, la conexión entre Microsoft 365 u Office 365 y un controlador de borde de sesión) usa el protocolo SIP. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede causar interrupciones del servicio o tiempos de espera de llamadas si la latencia entre los puntos de conexión supera varios segundos.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Conectividad a Microsoft 365 u Office 365

Teams requiere [conectividad a Internet.](/office365/enterprise/assessing-network-connectivity) Las direcciones URL y los intervalos de direcciones IP de punto de conexión de Teams se muestran en direcciones URL e [intervalos de direcciones IP de Office 365.](/office365/enterprise/urls-and-ip-address-ranges) (Tenga en cuenta que se requiere conectividad abierta a los puertos TCP 80 y 443 y a los puertos UDP 3478 a 3481). Además, Teams tiene una dependencia de Skype Empresarial Online, que también debe estar conectada a Internet.

La conectividad de flujos multimedia de Teams se implementa mediante procedimientos estándar de establecimiento de conectividad interactiva (ICE) de IETF.

### <a name="interoperability-restrictions"></a>Restricciones de interoperabilidad

**Retransmisión multimedia de terceros**. Un flujo multimedia de Teams (es decir, donde uno de los puntos de conexión multimedia es Teams) solo puede atravesar retransmisión multimedia nativa de Teams o Skype Empresarial. La interoperabilidad con un relé multimedia de terceros no es compatible. (Tenga en cuenta que un SBC de terceros en el límite con RTC debe finalizar la transmisión RTP/RTCP, protegerse con SRTP y no retransmitirla al siguiente salto).

**Servidores proxy SIP de terceros**. Un cuadro de diálogo SIP de señalización de Teams con un SBC de terceros o una puerta de enlace puede atravesar Teams o servidores proxy SIP nativos de Skype Empresarial. No se admite la interoperabilidad con un proxy SIP de terceros.

**B2BUA (o SBC)** de terceros . Un SBC de terceros finaliza un flujo multimedia de Teams hacia y desde la RTC. Sin embargo, no se admite la interoperabilidad con un SBC de terceros dentro de la red de Teams (donde un SBC de terceros media dos puntos de conexión de Teams o Skype Empresarial).

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologías que no se recomiendan con Microsoft Teams

**Red VPN**. No se recomienda para el tráfico multimedia (o el flujo 2'). El cliente VPN debe usar el túnel dividido y enrutar el tráfico multimedia de Teams como cualquier usuario externo que no sea VPN, tal y como se especifica en Habilitar medios de Lync para omitir [un túnel VPN.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)

> [!NOTE]
> Aunque el título indica Lync, también se aplica a Teams.

**Formadores de paquetes**. No se recomienda ningún tipo de snipper de paquetes, inspección de paquetes o dispositivos de formador de paquetes para el tráfico multimedia de Teams y puede degradar significativamente la calidad.

### <a name="principles"></a>Principios

Hay cuatro principios generales que le ayudan a comprender los flujos de llamadas de Microsoft Teams:

- Microsoft 365 u Office 365 hospedan una conferencia de Microsoft Teams en la misma región donde se unió el primer participante. (Tenga en cuenta que si hay excepciones a esta regla en algunas topologías, se describirán en este documento e ilustrarán con un flujo de llamada adecuado).

- Un punto de conexión multimedia de Teams en Microsoft 365 u Office 365 se usa en función de las necesidades de procesamiento multimedia y no en función del tipo de llamada. (Por ejemplo, una llamada punto a punto puede usar un punto de conexión multimedia en la nube para procesar medios para la transcripción o grabación, mientras que una conferencia con dos participantes puede no usar ningún punto de conexión multimedia en la nube). Sin embargo, la mayoría de las conferencias usarán un punto de conexión multimedia para fines de combinación y enrutamiento, asignado donde se hospeda la conferencia. El tráfico multimedia enviado desde un cliente al punto de conexión multimedia se puede enrutar directamente o usar una retransmisión de transporte en Microsoft 365 u Office 365 si es necesario debido a las restricciones del firewall de red del cliente.

- El tráfico multimedia para las llamadas punto a punto toma la ruta más directa disponible, suponiendo que la llamada no requiere un punto de conexión multimedia en la nube (vea el principio anterior). La ruta preferida es directa al punto remoto (cliente), pero si esa ruta no está disponible, una o más retransmisiones de transporte retransmitirán el tráfico. Se recomienda que el tráfico multimedia no transversa los servidores como los formadores de paquetes, los servidores VPN, entre otros, ya que esto afectará a la calidad de los medios.

- El tráfico de señalización siempre va al servidor más cercano al usuario.

Para obtener más información sobre los detalles de la ruta de acceso multimedia que se elige, vea Comprender los flujos de medios en [Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).

## <a name="call-flows-in-various-topologies"></a>Flujos de llamadas en varias topologías

### <a name="teams-topology"></a>Topología de Teams

Esta topología la usan los clientes que aprovechan los servicios de Teams desde la nube sin ninguna implementación local, como Skype Empresarial Server o Enrutamiento directo del sistema telefónico. Además, la interfaz de Microsoft 365 u Office 365 se realiza a través de Internet sin Azure Express Route.

[![Figura 01 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1: topología de Teams*

Ten en cuenta que:

- La dirección de las flechas del diagrama anterior refleja la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros empresariales. En el caso de UDP para medios, los primeros paquetes pueden fluir en la dirección inversa, pero estos paquetes pueden bloquearse hasta que fluyan los paquetes en la otra dirección.
- Teams se implementa en paralelo con Skype Empresarial Online, por lo que los clientes se muestran como "Usuario de Teams/SFB".

Encontrará más información sobre las siguientes topologías opcionales más adelante en el artículo:

- La implementación local de Skype Empresarial se describe en **topología híbrida de Teams.**
- Enrutamiento directo del sistema telefónico (para conectividad RTC) se describe en **Teams con topología de enrutamiento directo.**
- Ruta rápida se describe en **Teams con optimización de Ruta rápida.**

**Descripciones de flujo:**

- **Flujo 2:** representa un flujo iniciado por un usuario de la red de clientes a Internet como parte de la experiencia de Teams del usuario. Algunos ejemplos de estos flujos son DNS y medios de punto a punto.
- **Flujo 2':** representa un flujo iniciado por un usuario remoto de Teams móvil, con VPN a la red del cliente.
- **Flujo 3:** representa un flujo iniciado por un usuario remoto de Teams móvil a puntos de conexión de Microsoft 365 u Office 365/Teams.
- **Flujo 4:** representa un flujo iniciado por un usuario en la red de clientes a puntos de conexión de Microsoft 365 u Office 365/Teams.
- **Flujo 5:** representa un flujo multimedia punto a punto entre un usuario de Teams y otro usuario de Teams o Skype Empresarial dentro de la red de clientes.
- **Flujo 6:** representa un flujo multimedia punto a punto entre un usuario móvil remoto de Teams y otro usuario remoto de Teams móviles o skype empresarial a través de Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: uno a uno

Las llamadas uno a uno usan un modelo común en el que el autor de la llamada obtendrá un conjunto de candidatos compuesto por direcciones IP o puertos, incluidos los candidatos locales, de retransmisión y reflexivos (dirección IP pública del cliente, como lo ven los retransmisión). El autor de la llamada envía estos candidatos a la parte llamada; la parte llamada también obtiene un conjunto similar de candidatos y los envía al autor de la llamada. Los mensajes de comprobación de conectividad de ATURD se usan para buscar qué rutas multimedia de autor de llamada o de fiesta funcionan y se selecciona la mejor ruta de trabajo. Los medios (es decir, paquetes RTP/RTCP protegidos con SRTP) se envían después con el par de candidatos seleccionado. La retransmisión de transporte se implementa como parte de Microsoft 365 y Office 365.

Si los candidatos de dirección IP/puerto local o los candidatos reflexivos tienen conectividad, se seleccionará la ruta directa entre los clientes (o mediante un NAT) para los medios. Si los clientes están ambos en la red de clientes, se debe seleccionar la ruta de acceso directa. Esto requiere conectividad UDP directa dentro de la red del cliente. Si los clientes son usuarios en la nube nómadas, en función del NAT/firewall, los medios pueden usar la conectividad directa.

Si un cliente es interno en la red de clientes y un cliente es externo (por ejemplo, un usuario de la nube móvil), es poco probable que la conectividad directa entre los candidatos locales o reflexivos funcione. En este caso, una opción es usar uno de los candidatos de retransmisión de transporte de cualquiera de los clientes (por ejemplo, el cliente interno obtuvo un candidato de retransmisión de la retransmisión de transporte en Microsoft 365 u Office 365; el cliente externo debe poder enviar paquetes de STUN/RTP/RTCP a la retransmisión de transporte). Otra opción es el cliente interno que envía al candidato de retransmisión obtenido por el cliente de nube móvil. Tenga en cuenta que, aunque la conectividad UDP para medios es muy recomendable, tcp es compatible.

**Pasos de alto nivel:**

1. El usuario A de Teams resuelve el nombre de dominio url (DNS) con el flujo 2.
1. El usuario A de Teams asigna un puerto de retransmisión multimedia en Teams Transport Relay con el flujo 4.
1. El usuario A de Teams envía "invitación" con los candidatos del ICE mediante el flujo 4 a Microsoft 365 u Office 365.
1. Microsoft 365 u Office 365 envía notificaciones al usuario B de Teams mediante el flujo 4.
1. El usuario B de Teams asigna un puerto de retransmisión multimedia en Teams Transport Relay con el flujo 4.
1. El usuario B de Teams envía "respuesta" con los candidatos de ICE mediante el flujo 4, que se reenvía al usuario de Teams A con el flujo 4.
1. El usuario A de Teams y el usuario B de Teams invocan pruebas de conectividad ICE y se selecciona la mejor ruta de acceso multimedia disponible (vea diagramas a continuación para varios casos de uso).
1. Los usuarios de Teams envían telemetría a Microsoft 365 u Office 365 con el flujo 4.

**Dentro de la red de clientes:**

[![Figura 02 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figura 2: Dentro de la red de clientes*

En el paso 7, se selecciona el flujo de medios punto a punto 5.

Los medios son bidireccionales. La dirección del flujo 5 indica que un lado inicia la comunicación desde una perspectiva de conectividad, coherente con todos los flujos de este documento. En este caso, no importa qué dirección se usa porque ambos puntos de conexión están dentro de la red del cliente.

**Red de cliente a usuario externo (multimedia retransmitido por Teams Transport Relay):**

[![Figura 03 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3: Red de cliente a usuario externo (medios retransmitido por Teams Transport Relay)*

En el paso 7, se selecciona el flujo 4, de la red de clientes a Microsoft 365 u Office 365, y el flujo 3, del usuario remoto de Teams móvil a Microsoft 365 u Office 365. Estos flujos se retransmiten mediante Teams Transport Relay en Microsoft 365 u Office 365.

Los medios son bidireccionales, donde la dirección indica qué lado inicia la comunicación desde una perspectiva de conectividad. En este caso, estos flujos se usan para señalización y medios, con diferentes protocolos de transporte y direcciones.

**Red de cliente a usuario externo (medios directos):**

[![Figura 04 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4: Red de cliente a usuario externo (medios directos)*

En el paso 7, se selecciona el flujo 2, desde la red de clientes a Internet (el punto del cliente).

- Los medios directos con usuarios móviles remotos (no retransmitido a través de Microsoft 365 u Office 365) son opcionales. En otras palabras, el cliente puede bloquear esta ruta para exigir una ruta de acceso multimedia a través de Retransmisión de transporte en Microsoft 365 u Office 365.

- Los medios son bidireccionales. La dirección del flujo 2 para el usuario móvil remoto indica que un lado inicia la comunicación desde una perspectiva de conectividad.

**Usuario de VPN a usuario interno (retransmisión multimedia por Teams Transport Relay)**

[![Figura 05 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figura 5: usuario VPN a usuario interno (medios retransmitido por Teams Transport Relay)*

La señalización entre la RED VPN a la red del cliente está usando el flujo 2'. La señalización entre la red de clientes y Microsoft 365 u Office 365 está usando el flujo 4. Sin embargo, los medios omiten la VPN y se enruta con los flujos 3 y 4 a través de la retransmisión multimedia de Teams en Microsoft 365 u Office 365.

**Usuario de VPN a usuario interno (medios directos)**

[![Figura 06 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6: usuario DE VPN a usuario interno (medios directos)*

La señalización entre la RED VPN a la red del cliente está usando el flujo 2'. La señalización entre la red de clientes y Microsoft 365 u Office 365 está usando el flujo 4. Sin embargo, los medios omiten la VPN y se enruta mediante el flujo 2 desde la red de clientes a Internet.

Los medios son bidireccionales. La dirección del flujo 2 para el usuario móvil remoto indica que un lado inicia la comunicación desde una perspectiva de conectividad.

**Usuario de VPN a usuario externo (medios directos)**

[![Flujo de llamadas de Microsoft Teams Figura 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7: usuario DE VPN a usuario externo (medios directos)*

La señalización entre el usuario VPN a la red del cliente es usar el flujo 2' y usar el flujo 4 a Microsoft 365 u Office 365. Sin embargo, los medios omiten la VPN y se enruta con el flujo 6.

Los medios son bidireccionales. La dirección del flujo 6 para el usuario móvil remoto indica que un lado inicia la comunicación desde una perspectiva de conectividad.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Caso de uso: Teams to PSTN through Microsoft 365 u Office 365 Trunk

Microsoft 365 y Office 365 tienen un sistema telefónico que permite realizar y recibir llamadas desde la red telefónica conmutada (RTC). Si el tronco RTC está conectado con el Plan de llamadas del sistema telefónico, no hay requisitos de conectividad especiales para este caso de uso. (Si desea conectar su propio tronco RTC local a Microsoft 365 u Office 365, puede usar enrutamiento directo del sistema telefónico).

[![Figura 08 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8: Teams to PSTN through Office 365 Trunk*

#### <a name="use-case-teams-meeting"></a>Caso de uso: reunión de Teams

El servidor de conferencias de uso compartido de audio/vídeo/pantalla (VBSS) forma parte de Microsoft 365 y Office 365. Tiene una dirección IP pública que debe ser accesible desde la red del cliente y debe ser accesible desde un cliente de nube nómada. Cada cliente o punto de conexión debe poder conectarse al servidor de conferencias.

Los clientes internos obtendrán candidatos locales, reflexivos y de retransmisión del mismo modo que se describe para las llamadas uno a uno. Los clientes enviarán estos candidatos al servidor de conferencias en una invitación. El servidor de conferencias no usa una retransmisión, ya que tiene una dirección IP accesible públicamente, por lo que responde con su candidato de dirección IP local. El cliente y el servidor de conferencia comprobarán la conectividad de la misma manera que se describe para las llamadas uno a uno.

Ten en cuenta que:

- Los clientes de Teams no pueden unirse a reuniones de Skype Empresarial y los clientes de Skype Empresarial no pueden unirse a reuniones de Teams.

- Un usuario RTC opcionalmente "Marca IN" o es "Marcado HACIA FUERA", según el aprovisionamiento de llamadas RTC o conferencias del organizador de la reunión.

- Un usuario invitado o un usuario cliente pueden unirse desde una red privada de invitados, que está protegida con FW/NAT con reglas estrictas.

[![Figura 09 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9: Reunión de Teams*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso de uso: Federación con Skype Empresarial local

**Multimedia retransmitido por Teams Transport Relay en Microsoft 365 u Office 365**

[![Figura 10 Flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10: Retransmisión multimedia por Teams Transport Relay en Office 365*

Ten en cuenta que:

- La federación es, por definición, una comunicación entre dos inquilinos. En este caso, el inquilino A, que usa Teams, se federa con el inquilino B, que usa Skype Empresarial local. Si el inquilino B también usa Microsoft 365 u Office 365, el cliente de Skype Empresarial habría usado el flujo 3 para conectarse con Microsoft 365 u Office 365.

- La señalización y los medios desde el cliente federado de Skype Empresarial a Skype Empresarial Server local están fuera del ámbito de este documento. Sin embargo, se ilustra aquí para mayor claridad.

- La señalización entre Teams y Skype Empresarial está puenteada por una puerta de enlace.

- Los medios en este caso son retransmitido por Teams Transport Relay a la red de clientes y al cliente remoto de Skype Empresarial mediante el flujo 4.

**Retransmisión multimedia por Skype Empresarial Media Relay en inquilino federado**

[![Figura 11 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figura 11: Medios retransmitido por Skype Empresarial Media Relay en inquilino federado*

Ten en cuenta que:

- La señalización y los medios desde el cliente federado de Skype Empresarial a un Skype Empresarial Server local está fuera del ámbito de este documento. Sin embargo, se ilustra aquí para mayor claridad.

- La señalización entre Teams y Skype Empresarial está puenteada por una puerta de enlace.

- Los medios en este caso son retransmitido por Skype Empresarial Local Media Relay a la red de clientes mediante el flujo 2. (Tenga en cuenta que el tráfico desde el usuario de Teams al Retransmisión multimedia remota en la red de clientes federados se bloqueará inicialmente por la Retransmisión multimedia hasta que el tráfico en la dirección inversa empiece a fluir. Sin embargo, el flujo bidireccional abrirá la conectividad en ambas direcciones).

**Directo (punto a punto)**

[![Figura 12 Flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12: Directa (punto a punto)*

### <a name="teams-hybrid-topology"></a>Topología híbrida de Teams

Esta topología incluye Teams con una implementación local de Skype Empresarial.

[![Figura 13 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13: topología híbrida de Teams*

- La dirección de las flechas del diagrama anterior refleja la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros empresariales. En el caso de UDP para medios, los primeros paquetes pueden fluir en la dirección inversa, pero estos paquetes pueden bloquearse hasta que fluyan los paquetes en la otra dirección.

- Teams se implementa en paralelo con Skype Empresarial Online, por lo que los clientes se muestran como "Usuario de Teams/SFB".

Flujo adicional (en la parte superior de la topología de Teams):

- **Flujo 5A:** representa un flujo multimedia punto a punto entre un usuario de Teams dentro de la red de clientes y un retransmisión multimedia local de Skype Empresarial en el perímetro de red del cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: Teams to Skype Empresarial uno a uno

**Híbrido dentro de la red de clientes**

[![Figura 14 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figura 14: híbrido dentro de la red de clientes*

La señalización entre Teams y Skype Empresarial está puenteada por una puerta de enlace. Sin embargo, los medios se enruta directamente de punto a punto dentro de la red de clientes mediante el flujo 5.

**Red híbrida de clientes con usuario externo de Skype Empresarial, retransmitido por Microsoft 365 u Office 365**

[![Figura 15 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15: Red híbrida de clientes con usuario externo de Skype Empresarial, retransmitido por Office 365*

Ten en cuenta que:

- La señalización y los medios desde el cliente de Skype Empresarial a un Skype Empresarial Server local está fuera del ámbito de este documento. Sin embargo, se ilustra aquí para mayor claridad.

- La señalización entre Teams y Skype Empresarial está puenteada por una puerta de enlace.

- Los medios se retransmiten a través de Teams Transport Relay a la red de clientes a través del flujo 4.

**Red híbrida de clientes con usuario externo de Skype Empresarial, retransmitido por edge local**

[![Figura 16 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16: Red híbrida de clientes con usuario externo de Skype Empresarial, retransmitido por edge local*

Ten en cuenta que:

- La señalización y los medios desde el cliente de Skype Empresarial a un Skype Empresarial Server local está fuera del ámbito de este documento. Sin embargo, se ilustra aquí para mayor claridad.

- La señalización está puenteada por una puerta de enlace.

- El retransmisión multimedia de Skype Empresarial se retransmite dentro de Skype Empresarial local edge al usuario de Teams dentro de la red de clientes con el flujo multimedia 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams con topología de enrutamiento directo de sistema telefónico

Esta topología incluye Teams con enrutamiento directo del sistema telefónico.

Enrutamiento directo le permite usar un proveedor de servicios de red telefónica conmutada (RTC) de terceros emparejando un dispositivo de hardware de controlador de borde de sesión (SBC) local compatible con Microsoft 365 u Office 365 y, después, conectando el tronco de telefonía a ese dispositivo.

Para admitir este escenario, el cliente debe implementar un SBC certificado para enrutamiento directo de uno de los partners certificados de Microsoft. El SBC debe configurarse según lo recomendado por el proveedor y ser enrutable desde Microsoft 365 u Office 365 para el tráfico UDP directo. Los medios pueden fluir directamente desde Teams o el cliente de Skype Empresarial al SBC (omitiendo la puerta de enlace de Teams) o atravesar la puerta de enlace de Teams. La conectividad con el SBC, cuando el tronco está configurado para omitir la puerta de enlace de Teams, se basa en ICE, donde SBC admite ICE-Lite, mientras que el punto de conexión multimedia de Teams/Skype Empresarial admite el formulario completo de ICE.

[![Figura 17 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Figura 17: topología de enrutamiento directo de teams con sistema telefónico

Ten en cuenta que:

- La dirección de las flechas del diagrama anterior refleja la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros empresariales. En el caso de UDP para medios, los primeros paquetes pueden fluir en la dirección inversa, pero estos paquetes pueden bloquearse hasta que fluyan los paquetes en la otra dirección.

- Teams se implementa en paralelo con Skype Empresarial Online, por lo que los clientes se muestran como "Usuario de Teams/SFB".

Flujos adicionales (en la parte superior de la topología en línea de Teams):

- **Flujo 4':** representa un flujo de Microsoft 365 u Office 365 a la red de clientes, que se usa para establecer una conexión entre el servidor multimedia de Teams en la nube con el SBC local.
- **Flujo 5B:** representa un flujo multimedia entre el usuario de Teams dentro de la red de clientes con el SBC de enrutamiento directo en modo de omisión.
- **Flujo 5C:** representa un flujo multimedia entre el SBC de enrutamiento directo a otro SBC de enrutamiento directo en un modo de omisión de llamada de la función de direccionamiento directo.

**Usuario interno con enrutamiento directo (retransmisión multimedia por Teams Transport Relay)**

[![Figura 18 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figura 18: Usuario interno con enrutamiento directo (retransmisión multimedia por Teams Transport Relay)*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365.

- La señalización y los medios desde el SBC a Microsoft 365 u Office 365 y viceversa usan el flujo 4 y/o el flujo 4'.

- La señalización y los medios desde el cliente dentro de la red de clientes a Microsoft 365 u Office 365 usan el flujo 4.

**Usuario remoto con enrutamiento directo (los medios se enruta a través de un servidor multimedia (MP))**

[![Figura 19 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figura 19: Usuario remoto con enrutamiento directo (los medios se enruta a través de un servidor multimedia (MP))*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365.

- La señalización y los medios desde el SBC a Microsoft 365 u Office 365 y viceversa usan el flujo 4 y/o el flujo 4'.

- La señalización y los medios desde el cliente en Internet a Microsoft 365 u Office 365 usan el flujo 3.

**Enrutamiento directo interno del usuario (omisión de medios)**

[![Figura 20 Flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20: Enrutamiento directo del usuario interno (omisión de medios)*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365.

- La señalización de SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 y/o el flujo 4'.

- La señalización desde el cliente dentro de la red de clientes a Microsoft 365 u Office 365 usan el flujo 4.

- Los medios desde el cliente dentro de la red de clientes a SBC dentro de la red de clientes usan el flujo 5B.

**Usuario remoto con enrutamiento directo (desvío de medios retransmitido por Teams Transport Relay)**

[![Figura 21 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21: Usuario remoto con enrutamiento directo (desvío de medios retransmitido por Teams Transport Relay)*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365 e Internet.

- La señalización desde el SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 y/o el flujo 4'.

- La señalización desde el cliente en Internet a Microsoft 365 u Office 365 usa el flujo 3.

- Los medios desde el cliente en Internet hasta el SBC dentro de la red de clientes usan los flujos 3 y 4, retransmitido por Teams Transport Relay.

**Enrutamiento directo del usuario remoto (desvío de medios directo)**

[![Figura 22 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22: Enrutamiento directo del usuario remoto (desvío directo de medios)*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365 e Internet.

- La señalización desde el SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 y/o el flujo 4'.

- La señalización desde el cliente en Internet a Microsoft 365 u Office 365 usa el flujo 3.

- Los medios desde el cliente en Internet hasta el SBC dentro de la red de clientes usan el flujo 2.

**Enrutamiento directo (omisión de medios): llamada de la horquilla RTC (debido al desvío o transferencia de llamadas)**

[![Figura 23 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figura 23 - Enrutamiento directo (desvío de medios) - Llamada de la horquilla RTC (debido a desvío de llamadas/transferencia)*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365.

- La señalización desde el SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 y/o el flujo 4'.

- El cliente está fuera del bucle de señalización y multimedia después de que la llamada se desanclar de RTC a RTC.

- Los medios de la instancia A de SBC dentro de la red de clientes a la instancia B de SBC dentro de la red de clientes (donde, A y B pueden ser la misma instancia) usa el flujo 5C.

**Enrutamiento directo (medios a través de Microsoft 365 u Office 365): llamada de la horquilla RTC en dos inquilinos**

[![Figura 24 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Figura 24: Enrutamiento directo (medios a través de Microsoft 365 u Office 365): llamada de la horquilla RTC en dos inquilinos*

Ten en cuenta que:

- El SBC debe tener una dirección IP pública que sea enrutable desde Microsoft 365 u Office 365.

- La señalización desde el SBC a Microsoft 365 u Office 365 y viceversa usa el flujo 4 y/o el flujo 4'.

- El cliente está fuera del bucle de señalización y multimedia después de que la llamada se desanclar de RTC a RTC.

- Los medios de la instancia A de SBC dentro de la red de cliente X a la instancia B de SBC deben retransmitirse a través de Microsoft 365 u Office 365 Media Server y no pueden usar el modo de omisión.

## <a name="teams-with-express-route-optimization"></a>Teams con optimización de Ruta rápida

[![Figura 25 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25: Teams con optimización de Ruta rápida*

En el caso de que Ruta rápida esté justificado e implementado, los flujos de Teams se podrían volver a enrutar del flujo 4 al flujo 1 y del flujo 4' al flujo 1'. Sin embargo, la aplicación teams tiene una dependencia difícil de otros flujos de Microsoft 365 u Office 365 a través de Internet mediante los flujos 4 y 4'; por lo tanto, estos flujos no deben bloquearse.

Tenga en cuenta que el tráfico perimetral híbrido de Skype Empresarial se enruta a Internet y no a Express Route para comunicarse con usuarios externos y federar con otros inquilinos.

Para evitar flujos asimétricos, el redireccionamiento debe estar en ambas direcciones. En otras palabras, una dirección dentro de la red de clientes es enrutable a través de Internet o Express Route, en función de la optimización, pero no a través de ambos.


**Red de cliente a usuario externo (multimedia retransmitido por Teams Transport Relay):**

[![Figura 26 flujos de llamadas de Microsoft Teams Online](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26: Red de cliente a usuario externo (medios retransmitido por Teams Transport Relay)*

**Pasos de alto nivel:**

1. El usuario de Teams dentro de la red de clientes resuelve el nombre de dominio URL (DNS) con flow2.
1. El usuario de Teams dentro de la red de clientes asigna un puerto de retransmisión multimedia en Teams Transport Relay con el flujo 1.
1. El usuario de Teams dentro de la red de clientes envía "invitación" con los candidatos del ICE mediante el flujo 1 a Microsoft 365 u Office 365.
1. Microsoft 365 u Office 365 envía notificaciones al usuario externo de Teams mediante el flujo 3.
1. El usuario externo de Teams asigna un puerto de retransmisión multimedia en Teams Transport Relay con el flujo 3.
1. El usuario externo de Teams envía "respuesta" con los candidatos de ICE mediante el flujo 3, que se reenvía al usuario de Teams A con el flujo 1.
1. El usuario A de Teams y el usuario B de Teams invocan pruebas de conectividad de ICE y seleccionan los flujos 1 y 3, que se retransmiten por Teams Transport Relay.
1. Los usuarios de Teams envían telemetría a Microsoft 365 u Office 365 mediante los flujos 1 y 3.

> [!NOTE]
> El flujo 4 debe estar habilitado para admitir dependencias de la aplicación teams en otros microservicios que ordene el flujo 4.
