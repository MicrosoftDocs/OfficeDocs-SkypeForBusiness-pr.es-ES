---
title: Flujos de llamadas de Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: Describe cómo los equipos utiliza flujos de Office 365 en varias topologías.
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 856793c99fc02fb016383d0b6f8411c386d78886
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2019
ms.locfileid: "31828940"
---
# <a name="microsoft-teams-call-flows"></a>Flujos de llamadas de Microsoft Teams

> [!Tip]
> Vea la sesión siguiente para obtener información sobre cómo los equipos aprovecha la red y cómo planear la conectividad de red óptima: [Planeación de los equipos de red](https://aka.ms/teams-networking)

## <a name="overview"></a>Información general
Este artículo describe cómo llamar usos de los equipos Office 365 a flujos en varias topologías. Además, describe únicos flujos de los equipos que se usan para la comunicación de punto a punto medio. El documento describen estos flujos, su propósito y su origen y la terminación de la red. Para los propósitos de este artículo, se supone lo siguiente:

- Flujo de X se usa en el cliente de Office 365 local para comunicarse con el servicio de Office 365 en la nube. Se origina desde la red del cliente y finaliza como un extremo en Office 365.

- Flujo Y se usa en el cliente de Office 365 local para comunicarse con un servicio en Internet que Office 365 tiene una dependencia en. Se origina desde la red del cliente y finaliza como un extremo en Internet.

El artículo contiene las secciones siguientes:

- **Fondo** - proporciona información de fondo, como las redes que pueden atravesar flujos de Office 365, tipo de tráfico, la orientación de la conectividad de la red del cliente a los extremos de servicio de Office 365, la interoperabilidad con componentes de terceros, y principios que se usan por parte de equipos para seleccionar los flujos de medios.

- **Llamar a flujos en varias topologías** - ilustra el uso de flujos de llamadas en varias topologías. Para cada topología, la sección enumera todos los flujos de compatibles e ilustra cómo se usan estos flujos a través de varios casos de uso. Para cada caso de uso, describen la secuencia y selección de flujos de a través de un diagrama de flujo. 

- **Los equipos con la optimización de la ruta de Express** - describe cómo estos flujos se usan cuando se implementa ruta Express para la optimización, se muestra a través de una topología simple.

## <a name="background"></a>Información general
### <a name="network-segments"></a>Segmentos de red
**Red del cliente**: éste es el segmento de red que puede controla y administrar. Esto incluye todas las conexiones de cliente dentro de las oficinas de atención al cliente, ya sea por cable o inalámbrica, entre edificios de oficinas, en centros de datos locales y las conexiones a proveedores de Internet, ruta de Express o cualquier otro interconexión privada. 

Normalmente, una red de cliente tiene varias perímetros de red con servidores de seguridad o servidores proxy, que aplicar directivas de seguridad de la organización, y que sólo permiten determinado el tráfico de red que ha configurado y configurado. Debido a que administrar esta red, tienen un control directo sobre el rendimiento de la red y se recomienda complete las evaluaciones de red para validar el rendimiento tanto dentro de los sitios en la red y desde la red a la red de Office 365. 

**Internet**: éste es el segmento de red que forma parte de la red general que se usará por los usuarios que se conectan a Office 365 desde fuera de la red del cliente. También se usa por parte del tráfico de la red del cliente a Office 365. 

**Red privada visitado/invitado**: éste es el segmento de red fuera de la red del cliente, pero no en Internet pública, que es posible que visite los usuarios o sus invitados. Por ejemplo, principal red privada o una red privada de Enterprise, que no distribuye los equipos, donde es posible que residen los usuarios o sus clientes que interactúan con los servicios de los equipos.

>**Nota**: también es aplicable a estas redes de conectividad a Office 365.

**Office 365**: éste es el segmento de red que admita servicios de Office 365. Se distribuye en todo el mundo con bordes cerca de la red del cliente en la mayoría de las ubicaciones. Funciones que se mencionan en este documento incluyen retransmisión de transporte, servidor de conferencia y procesador de medios. 

**Ruta de Express (opcional)**: éste es el segmento de red que forma parte de la red general que le proporcionará una conexión privada y dedicada a la red de Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfico

**Multimedia en tiempo real**: datos que se encapsulan en RTP (Protocolo de transporte en tiempo real) que admite audio, vídeo y uso compartido de las cargas de trabajo de pantalla. En general, el tráfico de medios es altamente latencia confidencial, por lo que sería conveniente este tráfico para tomar la ruta más directa posible y usar UDP frente a TCP como protocolo de capa de transporte, que es el transporte recomendado para medios interactivos en tiempo real desde una perspectiva de calidad . (Nota: como último recurso, pueden usar TCP/IP y también un túnel dentro del protocolo HTTP de medios, pero no se recomienda debido a las implicaciones de mala calidad.) Flujo RTP se protege mediante SRTP, en la que se cifra sólo la carga.

**Señalización**: el vínculo de comunicación entre el cliente y servidor u otros clientes que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y entregar los mensajes instantáneos. El tráfico de señales más utiliza las interfaces REST basada en HTTPS, aunque en algunos casos (por ejemplo, la conexión entre Office 365 y un controlador de borde de sesión) usa el protocolo SIP. Es importante comprender que este tráfico es mucho menos sensible a la latencia pero puede provocar interrupciones de servicio o tiempos de espera de llamadas si la latencia entre los extremos supera varios segundos. 

### <a name="connectivity-to-office-365"></a>Conectividad a Office 365

Los equipos requieren [conectividad a Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Direcciones URL de extremo y los intervalos de direcciones de IP de los equipos se enumeran en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). (Nota: abra la conectividad con los puertos TCP 80 y 443 y, a los puertos UDP 3478 a través de 3481 es necesario.) Además, los equipos tiene una dependencia en Skype para profesionales en línea, que también debe estar conectado a Internet.

Conectividad de flujos de medios de los equipos se implementa mediante procedimientos estándar de IETF ICE (establecimiento interactivo de conectividad).

### <a name="interoperability-restrictions"></a>Restricciones de interoperabilidad
**Medios de terceros retransmite**: los equipos de un flujo de medios (es decir, uno de los extremos de medios es equipos) puede atravesar sólo los equipos o Skype para retransmisiones de medios nativo de negocio. No se admite la interoperabilidad con una retransmisión de medios de terceros. (Nota: un tercero SBC en el límite con RTC debe terminar secuencias RTP/RTCP, protegida a través de SRTP y no se transmita al próximo salto.)

**Los servidores proxy SIP de terceros fabricantes**: A los equipos de señalización SIP diálogo con un tercero SBC o puerta de enlace puede atravesar los equipos o Skype para servidores proxy SIP nativos de negocio. No se admite la interoperabilidad con un servidor proxy SIP de terceros.

**B2BUA de terceros (es decir, SBC)**: los equipos de un flujo de medios de/a la RTC se termina por terceros SBC. Sin embargo, interoperabilidad con un tercero SBC dentro de la red de los equipos (es decir, un tercero SBC actúa de mediador en dos equipos/Skype para los extremos de negocio) no se admite.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologías que no se recomiendan con Microsoft Teams

**Red VPN**: no se recomienda para el tráfico de medios (es decir, flujo 2'). El cliente VPN debe utilizar dividido VPN y enrutar el tráfico de medios al igual que cualquier usuario externo que no sean de VPN, como se especifica en https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.

>**Nota**: aunque el título es Lync, es aplicable a los equipos así como.

**Formadores de paquete**: cualquier tipo de snippers de paquetes, inspección de paquetes o dispositivos de Modelador de paquetes no se recomiendan y puede degradar la calidad de forma significativa. 

### <a name="principles"></a>Principios de
Hay cuatro principios generales que le ayudarán a comprender los flujos de llamadas para Microsoft Teams:
 
1.  Una conferencia de Microsoft Teams está hospedada en Office 365 en la misma región donde se unió la primera participante. (Nota: si habrá excepciones a esta regla en algunas topologías, a continuación, se que se describen en este documento y se muestra en un flujo de llamada apropiada.)

2.  Los equipos de un extremo de medios en Office 365 se usa en función de las necesidades de procesamiento de medios y no según el tipo de llamada. (Por ejemplo, una llamada punto a punto puede usar un extremo de medios en la nube para procesar el medio para transcripción o grabar, mientras una conferencia con dos participantes no puede usar cualquier extremo de medios en la nube.) Sin embargo, la mayoría de las conferencias usará un extremo de medios para mezclar y enrutamiento, asignado donde se hospeda la conferencia. El tráfico de medios enviado desde un cliente al extremo de medios se pueden enrutar directamente o utilizar una retransmisión de transporte en Office 365, si es necesario debido a restricciones de firewall de red de cliente. 

3.  El tráfico de medios para las llamadas de punto a punto toman la ruta más directa que está disponible, suponiendo que la llamada no exigir la aplicación de un extremo de medios en la nube (vea #2 anterior). La ruta preferida es directa al interlocutor remoto (cliente), pero si esa ruta no está disponible, uno o más retransmisiones de transporte se retransmitir el tráfico. Se recomienda que el tráfico de medios será servidores no transversales como formadores de paquetes, servidores VPN y así sucesivamente, ya que esto afectará a la calidad de los medios.

4.  El tráfico de señales siempre va al servidor más cercano al usuario. 

Para obtener más información acerca de los detalles en la ruta de acceso de medios que se ha elegido, consulte https://www.youtube.com/watch?v=1tmHMIlAQdo.

## <a name="call-flows-in-various-topologies"></a>Flujos de llamadas en varias topologías
### <a name="teams-topology"></a>Topología de los equipos
Esta topología se usa en los clientes que aprovechan los servicios de los equipos de la nube sin cualquier implementación local, como Skype para Business Server o enrutamiento directo de teléfono del sistema. Además, la interfaz a Office 365 se realiza a través de Internet sin ruta Express de Azure. 

[![Figura 01 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*La figura 1: topología de los equipos*

Tenga en cuenta:

- La dirección de las flechas en el diagrama anterior reflejar la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para los medios, es posible que flujo de la primera paquetes en la dirección inversa, pero estos paquetes se pueden bloquear hasta que se fluyan de paquetes en la otra dirección.
- Los equipos se implementa codo con codo con Skype para profesionales en línea, por lo tanto, los clientes se muestran como "Usuario de equipos/SFB".

Puede encontrar más información en las siguientes topologías opcionales más adelante en el artículo:

- Skype para la empresa local implementación se describe en la **topología híbrida de los equipos**.
- Teléfono del sistema enrutamiento directo (para la conectividad de RTC) se describe en **los equipos con la topología de enrutamiento directo**.
- Ruta Express se describe en **los equipos con la optimización de la ruta de Express**.

**Flujo de descripciones**:
- **Flujo de 2** – representa un flujo iniciado por un usuario en la red del cliente a Internet como parte de la experiencia del usuario los equipos. Ejemplos de estos flujos son DNS y los medios de punto a punto.
- **Flujo de 2'** – representa un flujo iniciado por un usuario remoto de los equipos móvil, con VPN a la red del cliente. 
- **Flujo de 3** : representa un flujo iniciado por un usuario remoto de los equipos móvil a extremos de Office 365 y equipos. 
- **Flujo de 4** : representa un flujo iniciado por un usuario en la red del cliente a los extremos de Office 365 y equipos.
- **Flujo de 5** – representa un flujo de medios de punto a punto entre equipos o Skype de un usuario de los equipos y otro para usuarios de empresa dentro de la red del cliente.
- **Flujo de 6** – representa un flujo de medios de punto a punto entre un usuario remoto de los equipos móvil y remotos otro equipos móviles o Skype para usuarios de empresa a través de Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: uno a uno
Las llamadas de uno a uno utilizan un modelo común en el que el autor de la llamada adoptarán un conjunto de candidatos que consta de las direcciones o puertos--incluidos local IP, retransmisión y candidatos Reflexivos (dirección IP pública del cliente como se ha visto por la retransmisión). El autor de la llamada envía a estos candidatos a la parte de la llamada; el receptor también obtiene un conjunto similar de candidatos y los envía al autor de la llamada. Comprobación de conectividad STUN mensajes se utilizan para buscar qué llamador/llamado medios de terceros funcionan las rutas de acceso y la mejor ruta de trabajo está seleccionada. Medios (es decir, los paquetes RTP/RTCP protegidos a través de SRTP), a continuación, se envían mediante el par de candidato seleccionado. La retransmisión de transporte se implementa como parte de Office 365.

Si la dirección IP local dirección/puerto candidatos o los candidatos reflexivas tienen conectividad, a continuación, se seleccionará la ruta de acceso directo entre los clientes (o a través de un dispositivo NAT) para los medios. Si los clientes están en la red del cliente, debe seleccionarse la ruta de acceso directo. Esto requiere conectividad directa de UDP dentro de la red del cliente. Si los clientes son los dos usuarios de nube nómadas, a continuación, según la NAT y firewalls, medios pueden utilizar conectividad directa.

Si un cliente es interno en la red del cliente y un cliente es externo (por ejemplo, un usuario móvil en la nube), es poco probable que la conectividad directa entre los candidatos locales o reflexivas funciona. En este caso, es una opción usar uno de los candidatos de transporte retransmisión desde cualquier cliente (por ejemplo, el cliente interno obtenido un candidato de retransmisión de la retransmisión de transporte en Office 365; el cliente externo debe ser capaz de enviar paquetes STUN/RTP/RTCP a la retransmisión de transporte). Otra opción es que el cliente interno se envía al candidato retransmisión obtenido por el cliente móvil en la nube. Tenga en cuenta que, aunque se recomienda para los medios de la conectividad de UDP, TCP se admite.

**Pasos de alto nivel**:
1. Los equipos de usuario A resuelve dirección URL nombre de dominio (DNS) a través de flow2
2. Los equipos de usuario A asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 4
3. Los equipos de usuario A envía "Invitar" con candidatos ICE a través de flujo 4 a Office 365
4. Office 365 envía una notificación a los equipos de usuario B a través de flujo 4
5. Los equipos de usuario B asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 4
6. Los equipos de usuario B envía "respuesta" con candidatos ICE a través de flujo 4, que se reenvía a los equipos de usuario A través de flujo de 4
7. El usuario A los equipos y los equipos de usuario B invocan ICE pruebas de conectividad y se selecciona la mejor ruta de medios disponibles (vea diagramas siguientes para distintos casos de uso)
8. Los usuarios de los equipos enviar telemetría a Office 365 a través de flujo 4

**Dentro de la red de cliente:**

[![Figura 02 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*La figura 2 - dentro de la red de cliente*
 
En el paso 7, se selecciona el flujo de medios de punto a punto 5.
 
Media es bidireccional. La dirección del flujo 5 indica que un lado inicia la comunicación desde una perspectiva de conectividad, coherente con todos los flujos de este documento. En este caso, no importa qué dirección se utiliza porque ambos extremos están dentro de la red del cliente.

**Red del cliente para usuarios externos (medios retransmitidos mediante la retransmisión de los equipos de transporte):**

[![Figura 03 de flujos de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*La figura 3 - red de cliente para usuarios externos (retransmitidos por los equipos de transporte retransmisión de medios)*
 
En el paso 7, 4, un flujo de red del cliente a Office 365 y 3, un flujo de usuarios remotos de los equipos móviles a Office 365, se seleccionan. Estos flujos se retransmiten mediante la retransmisión de transporte de los equipos dentro de Office 365.

Media es bidireccional, donde dirección indica qué lado inicia la comunicación desde una perspectiva de conectividad. En este caso, se usan estos flujos de señalización y los medios a través de diferentes protocolos de transporte y las direcciones.

**Red del cliente para usuarios externos (medios directas):**

[![Figura 04 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*La figura 4 - red de cliente para usuarios externos (medios directas)*
 
En el paso 7, 2, un flujo de red del cliente a Internet (del cliente del mismo nivel), se selecciona.
- Medios directo con usuarios móviles remotos (que no es, retransmitir a través de Office 365) están opcional. En otras palabras, el cliente puede bloquear esta ruta de acceso para exigir la aplicación de una ruta de acceso de medios a través de retransmisión de transporte en Office 365.

- Media es bidireccional. La dirección de flujo de 2 a los usuarios móviles remotos indica que un lado inicia la comunicación desde una perspectiva de conectividad. 

**Usuario VPN a usuario interno (retransmitidos por los equipos de transporte retransmisión de medios)**

[![Figura 05 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*La figura 5 - usuario VPN a usuario interno (retransmitidos por los equipos de transporte retransmisión de medios)*
 
Señalización entre la red VPN a la red del cliente es a través de flujo 2'. Señalización entre la red del cliente y Office 365 es a través de flujo 4. Sin embargo, medios omiten la VPN y se enrutan a través de flujos de 3 y 4 a través de transmisión de medios de los equipos en Office 365.

**Usuario VPN a usuario interno (medios directas)**

[![Figura 06 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*La figura 6 - usuario VPN a usuario interno (medios directas)*

Señalización entre la red VPN a la red del cliente es a través de flujo 2'. Señalización entre la red del cliente y Office 365 es a través de flujo 4. Sin embargo, medios omiten la VPN y se enrutan a través de flujo 2 desde la red del cliente a Internet.

Media es bidireccional. La dirección del flujo 2 para el usuario móvil remoto indica que un lado inicia la comunicación desde una perspectiva de conectividad.

**Usuario VPN a usuarios externos (medios directas)**

[![Microsoft Teams llamar flujos 07 de figura](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*La figura 7 - usuario VPN a usuarios externos (medios directas)*

Señalización entre el usuario VPN a la red del cliente es a través de flujo 2' y flujo de 4 a Office 365. Sin embargo, medios omiten VPN y se enrutan a través del flujo de 6.

Media es bidireccional. La dirección del flujo 6 para el usuario móvil remoto indica que un lado inicia la comunicación desde una perspectiva de conectividad.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Caso de uso: Los equipos a RTC a través del tronco de Office 365
Office 365 tiene un sistema de teléfono que permite realizar y recibir llamadas desde la red telefónica pública conmutada (RTC). Si el tronco RTC está conectado mediante el Plan de llamada de sistema de teléfono, no hay ningún requisitos especiales de conectividad para este caso de uso. (Si va a conectar su propio tronco de RTC local a Office 365, puede usar el enrutamiento directo de teléfono del sistema).

[![Figura 08 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*La figura 8 - equipos a RTC a través del tronco de Office 365*

#### <a name="use-case-teams-meeting"></a>Caso de uso: Reunión de los equipos

El audio o vídeo o pantalla uso compartido (VBSS) el servidor de conferencia es parte de Office 365. Tiene una dirección IP pública que debe ser accesible desde la red de cliente y debe ser accesible desde un cliente de Nómadas en la nube. Cada extremo de cliente debe ser capaz de conectarse al servidor de conferencia.

Los clientes internos adoptarán local, Reflexivos y candidatos de retransmisión de la misma manera que se describen para las llamadas de uno a uno. Los clientes enviará a estos candidatos para el servidor de conferencia en una invitación. El servidor de conferencia no usa una retransmisión ya que tiene una dirección IP públicamente accesible, por lo que responde con su candidato de dirección IP local. El servidor de conferencia y de cliente va a comprobar la conectividad de la misma manera que se describen para las llamadas de uno a uno. 

Tenga en cuenta:

- Los clientes de los equipos no pueden unirse a Skype para reuniones de negocios y Skype para clientes empresariales no puede unirse a reuniones de los equipos.

- Un usuario de RTC, opcionalmente, "marca IN" o "marcado" OUT, según el organizador de la reunión RTC de llamada o conferencia de aprovisionamiento. 

- Desde una red privada de invitado, que está protegida mediante RV/NAT con reglas estrictas, puede unirse un usuario invitado o un usuario de cliente.

[![Figura 09 de flujos de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*En la figura 9 - de los equipos de reunión*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso de uso: Federación con Skype para la empresa local

**Medios retransmitidos mediante la retransmisión de transporte de los equipos en Office 365**

[![La figura 10 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*La figura 10 - medios retransmitidos mediante la retransmisión de transporte de los equipos en Office 365*

Tenga en cuenta:

- La federación es, por definición, una comunicación entre dos de los inquilinos. En este caso, inquilino A, que usa los equipos, permite la federación con inquilino B, que usa Skype para la empresa local. Si inquilino B también está usando Office 365, la Skype para clientes empresariales habría utiliza flujo 3 para conectar con Office 365.

- Señalización y medios desde la federada Skype para clientes empresariales a local Skype para Business Server está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- Se salvó la señalización entre los equipos y Skype para la empresa mediante una puerta de enlace en Office 365.

- En este caso, los medios se retransmiten mediante la retransmisión de transporte de los equipos en Office 365 a la red del cliente y Skype remoto para el cliente de negocios a través de flujo de 4.

**Medios retransmitidos por Skype para la transmisión de medios de negocio en el inquilino federada**

[![La figura 11 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*La figura 11 - medios retransmitidos por Skype para la transmisión de medios de negocio en el inquilino federada*

Tenga en cuenta:

- Señalización y medios desde la federada Skype para cliente de negocio a un Skype local para Business Server está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- Se salvó la señalización entre los equipos y Skype para la empresa mediante una puerta de enlace en Office 365.

- En este caso, los medios se retransmiten mediante Skype para la transmisión de medios de negocio local a la red de cliente a través de flujo 2. (Tenga en cuenta que el tráfico de usuario de los equipos a la transmisión de medios remotos en la red del cliente federado se bloqueará inicialmente con la transmisión de medios hasta que se inicia el tráfico en la dirección contraria a flujo. Sin embargo, el flujo bidireccional abrirá conectividad en ambas direcciones.)

**Directo (punto a punto)**

[![La figura 12 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*La figura 12 - directo (punto a punto)*

### <a name="teams-hybrid-topology"></a>Topología híbrida de los equipos
Esta topología incluye los equipos con un Skype para la implementación local de empresa.

[![La figura 13 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*La figura 13 - topología híbrida de los equipos*
 
- La dirección de las flechas en el diagrama anterior reflejar la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para los medios, es posible que flujo de la primera paquetes en la dirección inversa, pero estos paquetes se pueden bloquear hasta que se fluyan de paquetes en la otra dirección.

- Los equipos se implementa codo con codo con Skype para profesionales en línea, por lo tanto, los clientes se muestran como "Usuario de equipos/SFB".

Flujos de adicionales (encima de la topología de los equipos):
- **Flujo 5A** – representa un flujo de medios de punto a punto entre un usuario de los equipos dentro de la red del cliente y un Skype para la transmisión de medios de negocio local en el perímetro de red de cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: Skype para la empresa uno a uno de los equipos
**Híbrido dentro de la red del cliente**

[![La figura 14 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*La figura 14 - híbrida dentro de la red de cliente*
 
Se salvó la señalización entre los equipos y Skype para la empresa mediante una puerta de enlace en Office 365. Sin embargo, medios se enrutan directamente a través de flujo 5 de red punto a punto dentro del cliente.

**Red de cliente híbrida con Skype externo para usuarios de empresa – retransmitidos por Office 365**

[![La figura 15 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*La figura 15 - red de cliente híbrida con Skype externo para usuarios de empresa - retransmitidos por Office 365*

Tenga en cuenta:

- Señalización y medios desde la Skype para cliente de negocio a un Skype local para Business Server está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- Se salvó la señalización entre los equipos y Skype para la empresa mediante una puerta de enlace en Office 365.

- Medios se retransmiten a través de los equipos de retransmisión de transporte en Office 365 a la red de cliente a través de flujo de 4.

**Red de cliente híbrida con Skype externo para usuarios de empresa – retransmitidos por perimetral local**

[![La figura 16 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*La figura 16 - red de cliente híbrida con Skype externo para usuarios de empresa - retransmitidos por perimetral local*
 
Tenga en cuenta:

- Señalización y los medios de Skype para cliente de negocio a un Skype local para Business Server está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

- Señalización se salvó por una puerta de enlace en Office 365.

- Medios se retransmiten mediante Skype para la transmisión de medios de negocio dentro de Skype para el servidor perimetral local de negocio al usuario de los equipos dentro de la red del cliente a través de 5A de flujo de medios.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Equipos con la topología de enrutamiento directo de teléfono del sistema
Esta topología incluye los equipos con el enrutamiento directo teléfono del sistema. 

Enrutamiento directo le permite usar un proveedor de servicios de terceros pública red de telefónica conmutada (RTC) por el emparejamiento de un dispositivo de hardware de controlador de borde de sesión (SBC) de cliente posee de local compatible para Office 365 y, a continuación, conectar el tronco de telefonía para ese dispositivo. 

Para admitir este escenario, el cliente debe implementar un SBC certificado para el enrutamiento directo de uno de los asociados de negocios certificados de Microsoft. La SBC debe configurarse como se recomienda por el proveedor y ser enrutables desde Office 365 para dirigir el tráfico UDP. Los medios pueden flujo directamente desde el Skype para clientes empresariales o de los equipos a la SBC (no usar la puerta de enlace de los equipos) o atravesar a través de la puerta de enlace de los equipos. La conectividad con el SBC, cuando se configura el tronco a omitir la puerta de enlace de los equipos, se basa en ICE, donde SBC admite Lite ICE, mientras que los equipos/Skype de extremo de medios de negocio admite ICE completo. 

[![La figura 17 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* En la figura 17 - equipos con la topología de enrutamiento directo de teléfono del sistema

Tenga en cuenta:

- La dirección de las flechas en el diagrama anterior reflejar la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para los medios, es posible que flujo de la primera paquetes en la dirección inversa, pero estos paquetes se pueden bloquear hasta que se fluyan de paquetes en la otra dirección.

- Los equipos se implementa codo con codo con Skype para profesionales en línea, por lo tanto, los clientes se muestran como "Usuario de equipos/SFB".

Flujos de adicionales (encima de la topología de los equipos en línea):
- **Flujo de 4'** - representa un flujo de Office 365 a la red del cliente, utilizada para establecer una conexión entre el servidor de medios de los equipos en la nube con la SBC en local.
- **Flujo 5B** – representa un flujo de medios entre el usuario de los equipos dentro de la red del cliente con el SBC enrutamiento directa en modo de derivación.
- **Flujo de 5 C** – representa un flujo de medios entre la SBC directa de enrutamiento a otro SBC de enrutamiento directa en un modo de desvío de llamadas de RTC horquilla.

**Usuario interno con el enrutamiento directo (medios retransmitidos mediante la retransmisión de transporte de los equipos en Office 365)**

[![La figura 18 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*La figura 18 - usuario interno con el enrutamiento directo (medios retransmitidos mediante la retransmisión de transporte de los equipos en Office 365)*

Tenga en cuenta:
 
- La SBC debe tener una dirección IP pública que es enrutable de Office 365.

- Señalización y medios desde la SBC a Office 365 y viceversa usar flujo 4 o fluyen 4'.

- Señalización y medios desde el cliente dentro de la red del cliente a Office 365 usan flujo 4.


**Usuario remoto con el enrutamiento directo (medios se enrutan a través de un servidor de medios (MP) en Office 365)**

[![La figura 19 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*La figura 19 - usuarios remotos con el enrutamiento directo (medios se enrutan a través de un servidor de medios (MP) en Office 365)*
 
Tenga en cuenta:

- La SBC debe tener una dirección IP pública que es enrutable de Office 365.

- Señalización y medios desde la SBC a Office 365 y viceversa usar flujo 4 o fluyen 4'.

- Señalización y medios desde el cliente en Internet a Office 365 usan flujo 3.

**Usuario interno enrutamiento directo (el desvío de medios)**

[![La figura 20 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*La figura 20 - usuario interno enrutamiento directo (el desvío de medios)*
 
Tenga en cuenta:

- La SBC debe tener una dirección IP pública que es enrutable de Office 365.

- Uso de señalización de SBC a Office 365 y viceversa flujo 4 o flujo 4'.

- Señalización de cliente dentro de la red del cliente a flujo de uso de Office 365 4.

- Medios de cliente dentro de la red del cliente a SBC dentro de la red del cliente use 5B de flujo.

**Usuario remoto con el enrutamiento directo (retransmitido mediante la retransmisión de transporte de los equipos en Office 365 el desvío de medios)**

[![La figura 21 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*La figura 21 - usuarios remotos con el enrutamiento directo (retransmitido mediante la retransmisión de transporte de los equipos en Office 365 el desvío de medios)*

Tenga en cuenta:

- La SBC debe tener una dirección IP pública que es enrutable desde Office 365 y de Internet.

- Señalización de la SBC a Office 365 y viceversa utiliza flujo 4 o flujo 4'.

- Señalización desde el cliente en Internet a Office 365 usa flujo 3.

- Medios desde el cliente de Internet para los SBC dentro de la red del cliente usa flujos de 3 y 4, retransmitido mediante la retransmisión de transporte de los equipos en Office 365. 

**Usuario remoto enrutamiento directo (direct el desvío de medios)**

[![Figura 22 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*La figura 22 - usuario remoto enrutamiento directo (direct el desvío de medios)*
 
Tenga en cuenta:

- La SBC debe tener una dirección IP pública que es enrutable de Office 365 y de Internet.

- Señalización de la SBC a Office 365 y viceversa utiliza flujo 4 o flujo 4'.

- Señalización desde el cliente en Internet a Office 365 usa flujo 3.

- Medios desde el cliente de Internet para los SBC dentro de la red del cliente usa flujo 2.

**Enrutamiento (desvío de medios) – RTC horquilla llamada directa (debido a la llamada directa de transferencia)**

[![La figura 23 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*La figura 23 - enrutamiento directo (el desvío de medios) - llamada de horquilla RTC (debido a la llamada directa de transferencia)*
 
Tenga en cuenta:

- La SBC debe tener una dirección IP pública que es enrutable de Office 365.

- Señalización de la SBC a Office 365 y viceversa utiliza flujo 4 o flujo 4'.

- El cliente está fuera de la señalización y medios bucle después de la llamada es hairpinned de RTC a RTC.

- Medios de instancia SBC A dentro de la red del cliente a la instancia SBC B dentro de la red del cliente (donde, A y B pueden ser la misma instancia) usa flujo 5C.

**Enrutamiento (medios a través de Office 365) – RTC horquilla llamada directa en dos inquilinos**

[![La figura 24 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Llamada de la figura 24 - enrutamiento directo (medios a través de Office 365) – RTC horquilla en dos inquilinos*
 
Tenga en cuenta:

- La SBC debe tener una dirección IP pública que es enrutable de Office 365.

- Señalización de la SBC a Office 365 y viceversa utiliza flujo 4 o flujo 4'.

- El cliente está fuera de la señalización y medios bucle después de la llamada es hairpinned de RTC a RTC.

- Modo de desvío de medios de la instancia SBC A dentro de la red de cliente X a instancia SBC B debe transmitir a través del servidor de medios de Office 365 y no se puede usar.

## <a name="teams-with-express-route-optimization"></a>Equipos con la optimización de la ruta de Express

[![La figura 25 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*La figura 25 - equipos con optimización de la ruta de Express*
 
En el caso de que la ruta de Express está justificado e implementado, a continuación, flujos de equipos se puede volver a distribuir desde flujo 4 para flujo 1 y de flujo de 4' para flujo 1'. Sin embargo, los equipos de aplicación tiene una dependencia fuerte en otros flujos de Office 365 a través de internet a través de flujos de 4 y 4'; por lo tanto, no se deben bloquear estos flujos. 

Tenga en cuenta que Skype para entornos híbridos de negocio tráfico perimetral se enruta a Internet y no a la ruta de Express para comunicarse con usuarios externos y federar con otros inquilinos. 

Para evitar que los flujos de asimétricos, transporte alternativo debe ser en ambas direcciones. En otras palabras, una dirección dentro de la red del cliente es enrutable ya sea a través de Internet o ruta Express, basándose en la optimización, pero no a través de ambos.

Por ejemplo:

**Red del cliente para usuarios externos (medios retransmitidos mediante la retransmisión de los equipos de transporte):**

[![La figura 26 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*La figura 26 - red de cliente para usuarios externos (retransmitidos por los equipos de transporte retransmisión de medios)*
 
**Pasos generales:**
1. Los equipos de usuario dentro de la red del cliente resuelve el nombre de dominio de dirección URL (de dominio DNS) a través de flow2
2. Los equipos de usuario dentro de la red de cliente asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 1
3. Los equipos de usuario dentro de la red de cliente envía "Invitar" con candidatos ICE a través de flujo de 1 a Office 365
4. OFFICE 365 envía una notificación a los usuarios de los equipos externos a través de flujo 3
5. Usuarios externos de los equipos asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 3
6. Usuarios externos de los equipos envía "respuesta" con candidatos ICE a través de flujo 3, que se reenvía al usuario A con los equipos a través de flujo 1
7. El usuario A los equipos y los equipos de usuario B invocar pruebas de conectividad de ICE y selecciona flujos de 1 y 3, que se retransmiten mediante la retransmisión de transporte de los equipos en Office 365
8. Los usuarios de los equipos enviar telemetría a Office 365 a través de flujos de 1 y 3

>**Nota**: flujo 4 debe estar habilitada para admitir dependencias de aplicación de los equipos en otros servicios de micro que normas fluyan 4.
