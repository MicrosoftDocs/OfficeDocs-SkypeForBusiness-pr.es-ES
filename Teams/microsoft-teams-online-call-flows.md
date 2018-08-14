---
title: Flujos de llamadas de los equipos de Microsoft Online
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 06/08/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
description: Describe cómo utiliza la carga de trabajo de los equipos flujos de Office 365 en varias topologías.
ms.openlocfilehash: 2374349f426de6fb25d25cc4ded7c6c8a776dd1d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964544"
---
# <a name="microsoft-teams-online-call-flows"></a>Flujos de llamadas de los equipos de Microsoft Online

## <a name="overview"></a>Información general
Este documento describe cómo utiliza la carga de trabajo de los equipos flujos de Office 365 en varias topologías. Además, especifica únicos flujos de los equipos que se usan para la comunicación de punto a punto medio. El documento enumera estos flujos y describe su propósito y sus redes de origen y terminación. Por ejemplo, flujo de X se usa en Office 365 cliente local para comunicarse con el servicio Office 365 en la nube, se originó en la red del cliente y finalizadas por un extremo en nube de Office 365, y flujo Y se usa en Office 365 cliente local para comunicarse con un servicio en Internet, que Office 365 tiene dependencia de, se originó en la red del cliente y se termina por un extremo en Internet.

El documento tiene tres secciones principales. La primera proporciona una información de fondo, como las redes (que es posible que atraviesan los flujos de Office 365), el tipo de tráfico, directrices sobre la conectividad de red del cliente para los extremos de servicio de Office 365, interoperabilidad con componentes de terceros y entidades de seguridad que se utilizan por parte de equipos para seleccionar los flujos de medios. La segunda ilustra el uso de estos flujos en varias topologías. Para cada topología, se enumeran todos los flujos de admitidos y se muestra cómo se utilizan estos flujos a través de varios casos de uso. Para cada caso de uso, describen la secuencia y selección de flujos de a través de un diagrama de flujo. La tercera describe cómo se utilizan estos flujos cuando se implementa ruta Express para la optimización, que se muestra a través de una topología simple.

## <a name="background"></a>Fondo
### <a name="network-segments"></a>Segmentos de red
**Red del cliente**: éste es el segmento de red que forma parte de la red general que puede controla y administrar. Esto incluye todas las conexiones de cliente dentro de las oficinas de atención al cliente, ya sea por cable o inalámbrica, entre edificios de oficinas, en centros de datos locales y las conexiones a proveedores, ruta de Express o cualquier otro interconexión privada de Internet. 

Normalmente, una red de cliente tiene varias perímetros de red con servidores de seguridad o servidores proxy, que aplicar las directivas de seguridad de una organización y que sólo permiten determinado el tráfico de red que ha configurado y configurado. Debido a que el cliente administra esta red, el cliente tiene control directo sobre el rendimiento de la red y se recomienda que el cliente completado red evaluaciones para validar el rendimiento dentro de los sitios en la red y de su red a la red de Office 365. Skype para profesionales de implementación local y controlador de borde de sesión de RTC para conectarse con RTC a través de la red (es decir, el enrutamiento directo) son opcionales.

**Internet**: éste es el segmento de red que forma parte de la red general que se usará por los usuarios que se conectan a Office 365 nube desde fuera de la red del cliente. También se usa por parte del tráfico de la red del cliente en la nube de Office 365. 

**Red privada visitado/invitado**: éste es el segmento de red fuera de la red del cliente, pero no en Internet pública, que es posible que visite los usuarios o sus invitados. Por ejemplo, principal red privada o una red privada de Enterprise, que no distribuye los equipos, donde es posible que residen los usuarios o sus clientes que interactúan con los servicios de los equipos.

>**Nota**: la conectividad con Office 365b también es aplicable a estas redes.

**En la nube de Office 365**: éste es el segmento de red que admita servicios de Office 365. Se distribuye en todo el mundo con bordes cerca de la red del cliente en la mayoría de las ubicaciones. Funciones que se mencionan en este documento incluyen retransmisión de transporte, servidor de conferencia y procesador de medios. 

**Ruta de Express (opcional)**: éste es el segmento de red que forma parte de la red general que le proporcionará una conexión privada y dedicada a la red de Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfico

**Multimedia en tiempo real**: datos que se encapsulan en RTP (Protocolo de transporte en tiempo real) y admite audio, vídeo y uso compartido de las cargas de trabajo de pantalla. En general, el tráfico de medios altamente es latencia confidencial, por lo que sería conveniente este tráfico para tomar la ruta más directa posible y usar UDP frente a TCP como protocolo de capa de transporte, que es el transporte recomendado para los medios interactivos en tiempo real desde la perspectiva de calidad. (Nota: como último recurso, pueden usar TCP/IP y también un túnel dentro del protocolo HTTP de medios, pero no se recomienda debido a las implicaciones de mala calidad.) Flujo RTP se protege mediante SRTP, en la que se cifra sólo la carga.

**Señalización**: el vínculo de comunicación entre el cliente y servidor u otros clientes que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y entregar los mensajes instantáneos. El tráfico de señales más las interfaces REST basada en HTTPS, aunque en algunos casos (por ejemplo, la conexión entre en la nube de Office 365 y un controlador de borde de sesión) utiliza el protocolo SIP. Es importante comprender que este tráfico es mucho menos sensible a la latencia pero puede provocar interrupciones de servicio o llamar a tiempos de espera de latencia entre los extremos sobrepase varios segundos. 

### <a name="connectivity-to-office-365"></a>Conectividad a Office 365

Servicio de los equipos requiere [conectividad a Internet](https://support.office.com/en-us/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Los extremos IP intervalos de direcciones y direcciones URL de los equipos se enumeran en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). (Nota: requiere para abrir la conectividad con los puertos TCP 80 y 443 y puertos UDP 3478 3481 a.) Además, el servicio de los equipos tiene dependencia de Skype para servicios en línea de negocio, por lo tanto, se requiere para conectar este servicio también a Internet.

Conectividad de flujos de medios de los equipos se implementa mediante procedimientos estándar de IETF ICE (establecimiento interactivo de conectividad).

### <a name="interoperability-restrictions"></a>Restricciones de interoperabilidad
**Medios de terceros retransmite**: los equipos de un flujo de medios (es decir, uno de los extremos de medios es equipos) puede atravesar sólo los equipos o Skype para retransmisiones de medios nativo de negocio. No se admite la interoperabilidad con una retransmisión de medios de terceros. (Nota: un tercero SBC en el límite con RTC debe terminar secuencias RTP/RTCP, protegida a través de SRTP y no se transmita al próximo salto.)

**Servidores Proxy SIP de terceros**: A los equipos de señalización SIP diálogo con un tercero SBC o puerta de enlace puede atravesar los equipos o Skype para servidores proxy SIP nativos de negocio. No se admite la interoperabilidad con un servidor Proxy SIP de otros fabricantes.

**B2BUA de terceros (es decir, SBC)**: los equipos de un flujo de medios de/a RTC se termina por terceros SBC. Sin embargo, interoperabilidad con un tercero SBC dentro de la red de los equipos (es decir, terceros SBC actúa de mediador en dos extremos de equipos/Skype para empresarial) no se admite.

### <a name="technologies-that-are-strongly-not-recommended-with-microsoft-teams"></a>Tecnologías que se recomiendan encarecidamente no con Microsoft Teams

**Red VPN**: se recomienda encarecidamente no para el tráfico de medios (es decir, flujo 2'). Cliente VPN debe usar dividido VPN y enrutar el tráfico de medios al igual que cualquier usuario externo que no sean de VPN, como se especifica enhttps://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/ 

>**Nota**: aunque el título es Lync, es aplicable a los equipos así como.

**Formadores de paquete**: cualquier tipo de snippers de paquetes, inspección de paquetes o dispositivos de Modelador de paquetes se recomienda encarecidamente no y puede degradar la calidad de forma significativa. 

### <a name="principles"></a>Principios de
Hay cuatro principios generales que le ayudarán a comprender los flujos de llamadas para Microsoft Teams. 
1.  Una conferencia de Microsoft Teams está hospedada en la nube de Office 365 en la misma región donde se unió la primera participante. (Nota: si habrá excepciones a esta regla en algunas topologías, a continuación, se describirá en este documento, se muestra en un flujo de llamada apropiada.)
2.  Un extremo de medios de los equipos (MP) en Office 365 se usa en la nube en función de las necesidades de procesamiento de medios y no según el tipo de llamada. (Por ejemplo, una llamada punto a punto puede usar un extremo de medios en la nube para procesar el medio para transcripción o grabar, mientras una conferencia con dos participantes no puede usar cualquier extremo de medios en la nube.) Sin embargo, la mayoría de las conferencias usará un MP para mezclar y enrutamiento, asignado donde se hospeda la conferencia. El tráfico de medios enviado desde un cliente para el panel de administración se pueden enrutar directamente o utilizar una retransmisión de transporte, en la nube de Office 365, si es necesario debido a restricciones del firewall de red del cliente. 
3.  El tráfico de medios para las llamadas de punto a punto toman la ruta más directa que está disponible, suponiendo que la llamada no exigir la aplicación de un panel de administración en la nube (vea #2 anterior). La ruta preferida es directa al interlocutor remoto (cliente), pero si esa ruta no está disponible, uno o más retransmisiones de transporte se retransmitir el tráfico. Se recomienda que el tráfico de medios será servidores no transversales como formadores de paquetes, servidores VPN, etc., ya que esto afectará a la calidad de los medios.
4.  El tráfico de señales siempre va al servidor más cercano al usuario. 

Para obtener más información acerca de los detalles en la ruta de acceso de medios que se ha elegido, consulte https://www.youtube.com/watch?v=aD5mUg2ZzLQ.

## <a name="call-flows-in-various-topologies"></a>Flujos de llamadas en varias topologías
### <a name="teams-online-pure-topology"></a>Topología de los equipos en línea ("pura")
Esta topología se usa en los clientes que aprovechan los servicios de los equipos de la nube sin implementar cualquier servidor, como Skype para la empresa y SBC para el enrutamiento directo, en local. Además, la interfaz a Office 365 se realiza a través de Internet sin ruta Express de Azure. 

[![Figura 01 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*En la figura 1 - topología ('puro') de los equipos en línea*

>**Notas**:
>- La dirección de las flechas en el diagrama anterior reflejar la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para los medios, es posible que flujo de la primera paquetes en la dirección inversa, pero estos paquetes se pueden bloquear hasta que se fluyan de paquetes en la otra dirección.
>- Se implementa en pantalla de los equipos codo con codo con Skype para profesionales en línea, por lo tanto, los clientes se muestran como "Usuario de equipos/SFB".

- Skype opcional para la empresa en la implementación local se describe en este documento en la sección **Topología híbrida en línea de los equipos**
- Enrutamiento directo opcional para RTC se describe en este documento en la sección **Los equipos en línea con la topología de enrutamiento directa**
- Ruta de Express opcional se describe en este documento en la sección **los equipos con la optimización de la ruta de Express**

**Flujos de descripciones**:
- **Flujo de 2** – representa un flujo iniciado por un usuario en la red del cliente a Internet como parte de su experiencia de los equipos. Ejemplos de estos flujos son DNS y los medios de punto a punto.
- **Flujo de 2'** – representa un flujo iniciado por un usuario móvil remoto de los equipos, qué VPN a la red del cliente. 
- **Flujo de 3** : representa un flujo iniciado por un usuario remoto de los equipos móvil a extremos de Office 365 y equipos. 
- **Flujo de 4** : representa un flujo iniciado por un usuario en la red del cliente a los extremos de Office 365 y equipos.
- **Flujo de 5** – representa un flujo de medios de punto a punto entre equipos o Skype de usuario de los equipos y otro para usuarios de empresa, dentro de la red de cliente.
- **Flujo de 6** – representa una media de punto a punto fluyen entre un usuario remoto de los equipos móvil y remotos otro equipos móviles o Skype para usuarios de empresa, a través de Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: uno a uno
Las llamadas de uno a uno utilizan un modelo común que el autor de la llamada adoptarán un conjunto de candidatos formado por las direcciones IP y puertos; local, retransmisión y Reflexivos (dirección IP pública del cliente como las ve la retransmisión). El autor de la llamada envía estos candidatos para el receptor en la invitación, el receptor también obtiene un conjunto similar de candidatos y los envía al autor de la llamada. Comprobación de conectividad STUN mensajes se utilizan para buscar qué llamador/llamado medios de terceros funcionan las rutas de acceso y la mejor ruta de trabajo está seleccionada. Medios (es decir, los paquetes RTP/RTCP protegidos a través de SRTP), a continuación, se envían mediante el par de candidato seleccionado. La retransmisión de transporte se implementa como parte de la nube de Office 365.

Si la dirección IP local dirección/puerto candidatos o los candidatos reflexivas tienen conectividad, a continuación, se seleccionará la ruta de acceso directo entre los clientes (o a través de un dispositivo NAT) para los medios. Si los clientes están en la red del cliente, debe seleccionarse la ruta de acceso directo. Esto requiere conectividad directa de UDP dentro de la red del cliente. Si los clientes son los dos usuarios de nube nómadas, a continuación, según la NAT y firewalls, medios pueden utilizar conectividad directa.

Si un cliente es interno en la red del cliente y un cliente es externo (por ejemplo, un usuario móvil en la nube), entonces se es poco probable que la conectividad directa entre los candidatos locales o reflexivas funciona. En este caso, es una opción usar uno de los candidatos de transporte retransmisión desde cualquier cliente (por ejemplo, el cliente interno obtenido un candidato de retransmisión de la retransmisión de transporte en la nube de Office 365, el cliente externo debe ser capaz de enviar paquetes STUN/RTP/RTCP a la retransmisión de transporte). Otra opción es que el cliente interno se envía al candidato retransmisión obtenido por el cliente móvil en la nube. Tenga en cuenta que aunque se recomienda para los medios de la conectividad de UDP, TCP se admite.

**Pasos generales**:
1. Los equipos de usuario A resuelve dirección URL nombre de dominio (DNS) a través de flow2
2. Los equipos de usuario A asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 4
3. Los equipos de usuario A envía "Invitar" con candidatos ICE a través de flujo 4 a Office 365
4. OFFICE 365 envía una notificación a los equipos de usuario B a través de flujo 4
5. Los equipos de usuario B asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 4
6. Los equipos de usuario B envía "respuesta" con candidatos ICE a través de flujo 4, que se reenvía a los equipos de usuario A través de flujo de 4
7. El usuario A los equipos y los equipos de usuario B invocan ICE pruebas de conectividad y se selecciona la mejor ruta de medios disponibles (vea diagramas siguientes para distintos casos de uso)
8. Los usuarios de los equipos enviar telemetría a Office 365 a través de flujo 4

**Dentro de la red de cliente:**

[![Figura 02 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*La figura 2 - dentro de la red de cliente*
 
En el paso 7, se selecciona el flujo de medios "punto a punto" 5 
>**Nota**: Media es bidireccional. La dirección del flujo 5 indica que un lado inicia la comunicación desde la perspectiva de conectividad, coherente con todos los flujos de este documento. En este caso, no importa qué dirección se utiliza porque ambos extremos están dentro de la red del cliente.

**Red del cliente para usuarios externos (medios retransmitidos mediante la retransmisión de los equipos de transporte):**

[![Figura 03 de flujos de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*La figura 3 - red de cliente para usuarios externos (retransmitidos por los equipos de transporte retransmisión de medios)*
 
En el paso 7, 4, un flujo de red del cliente a Office 365 y 3, un flujo de usuarios remotos de los equipos móviles a Office 365, se seleccionan. Estos flujos se retransmiten mediante la retransmisión de transporte de los equipos dentro de Office 365.

>**Nota**: Media es bidireccional, donde dirección indica qué lado inicia la comunicación desde la perspectiva de la conectividad. En este caso, se usan estos flujos de señalización y los medios a través de diferentes protocolos de transporte y las direcciones.

**Red del cliente para usuarios externos (medios directas):**

[![Figura 04 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*La figura 4 - red de cliente para usuarios externos (medios directas)*
 
En el paso 7, 2, un flujo de red del cliente a Internet (del cliente del mismo nivel), se selecciona.
>**Notas**: 
>- Directo multimedia con usuarios móviles remotos (es decir, si no se han transmitido a través de la nube de Office 365) es opcional. En otras palabras, atención al cliente puede bloquear esta ruta de acceso y de esta forma, aplicar una ruta de acceso de medios a través de retransmisión de transporte en la nube de Office 365.
>- Media es bidireccional. La dirección de flujo de 2 a los usuarios móviles remotos indica que un lado inicia la comunicación desde una perspectiva de conectividad. 

**Usuario de VPN a usuario interno (retransmitidos por los equipos de transporte retransmisión de medios)**

[![Figura 05 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*La figura 5 - usuario de VPN a usuario interno (retransmitidos por los equipos de transporte retransmisión de medios)*
 
Señalización VPN a la red del cliente a través de flujo 2' y el flujo de 4 a Office 365. Sin embargo, "desvío" VPN de medios y enrutan a través de flujos de 3 y 4 a través de transmisión de medios de los equipos en la nube de Office 365.

**Usuario de VPN a usuario interno (medios directas)**

[![Figura 06 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*La figura 6 - usuario de VPN a usuario interno (medios directas)*

Señalización VPN a la red del cliente a través de flujo 2' a la red del cliente y flujo de 4 a Office 365. Sin embargo, "desvío" VPN de medios y enrutan a través de flujo 2 desde la red del cliente a internet.

>**Nota**: Media es bidireccional. La dirección de flujo de 2 a los usuarios móviles remotos indica que un lado inicia la comunicación desde una perspectiva de conectividad.

**Usuario de VPN a usuarios externos (medios directas)**

[![Figura 07 flujos de llamada en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*La figura 7 - usuario de VPN a usuarios externos (medios directas)*

Señalización VPN a la red del cliente a través de flujo 2' a la red del cliente y flujo de 4 a Office 365. Sin embargo, "desvío" VPN de medios y enrutan a través de flujo de 6.

>**Nota**: Media es bidireccional. La dirección de flujo de 6 a usuarios móviles remotos indica que un lado inicia la comunicación desde una perspectiva de conectividad.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Caso de uso: Los equipos a RTC a través del tronco de Office 365
Nube de Office 365 tiene un sistema de teléfono que permite realizar y recibir las llamadas de red telefónica conmutada. Si el tronco RTC está conectado a través de la nube de Office 365, no hay ningún requisitos especiales de conectividad para este caso de uso. De lo contrario, (enrutamiento directo se implementa), a continuación, vea la sección **TBD**.

[![Figura 08 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*La figura 8 - equipos a RTC a través del tronco de Office 365*

#### <a name="use-case-teams-meeting"></a>Caso de uso: Reunión de los equipos

El audio o vídeo o pantalla uso compartido (VBSS) el servidor de conferencia es parte de la nube de Office 365. Tiene una dirección IP pública que debe ser accesible desde la red de cliente y debe ser accesible desde un cliente de Nómadas en la nube. Cada extremo de cliente debe ser capaz de conectarse al servidor de conferencia.

Los clientes internos adoptarán local, Reflexivos y candidatos de retransmisión de la misma manera que se describen para las llamadas de uno a uno. Los clientes enviará a estos candidatos para el servidor de conferencia en una invitación. El servidor de conferencia no usa una retransmisión ya que tiene una dirección IP públicamente accesible, por lo que responde con sólo su candidato local de la dirección IP. El servidor de conferencia y de cliente va a comprobar la conectividad de la misma manera que se describen para las llamadas de uno a uno. 

>**Notas**:
>- Los clientes de los equipos no pueden unirse a Skype para reuniones de negocios y Skype para clientes empresariales no puede unirse a reuniones de los equipos.
>- Usuario de RTC, opcionalmente, "marca IN" o "marcado" OUT, depende de RTC de llamada del organizador de la reunión o aprovisionamiento de conferencia. 
>- Desde una red privada de invitado, que está protegida mediante RV/NAT con reglas estrictas, puede unirse un usuario invitado o un usuario de cliente.

[![Figura 09 de flujos de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*En la figura 9 - de los equipos de reunión*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso de uso: Federación con Skype para la empresa local

**Medios retransmitidos mediante la retransmisión de transporte de los equipos en la nube de Office 365**

[![La figura 10 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*La figura 10 - medios retransmitidos mediante la retransmisión de transporte de los equipos en la nube de Office 365*

>**Notas**: 
>- "Federación" es, por definición, una comunicación entre dos de los inquilinos. En este caso, inquilino A, que usa los equipos en línea, permite la federación con inquilino B, que usa Skype para la empresa local. Si inquilino B también está usando Office 365, cliente de Skype para profesionales habría utiliza flujo 3 para conectar con Office 365.
>- Señalización y los medios de cliente federado de Skype para profesionales a su Skype para la empresa en el servidor local está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

Señalización entre los equipos y Skype para la empresa es "salvó" por una puerta de enlace en la nube de Office 365.

En este caso, los medios se retransmiten mediante la retransmisión de transporte de los equipos en la nube de Office 365 a la red del cliente y Skype remoto para el cliente de negocios a través de flujos de 4.

**Medios retransmitidos por Skype para la transmisión de medios de negocio en el inquilino federada**

[![La figura 11 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*La figura 11 - medios retransmitidos por Skype para la transmisión de medios de negocio en el inquilino federada*

>**Nota**: señalización y los medios de cliente federado de Skype para profesionales a su Skype para la empresa en el servidor local está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

Señalización entre los equipos y Skype para la empresa es "salvó" por una puerta de enlace en la nube de Office 365.

En este caso, los medios se retransmiten mediante Skype para la empresa local retransmisión de medios a la red del cliente a través de flujo 2. (Tenga en cuenta que el tráfico de usuario de los equipos a la transmisión de medios remotos en la red del cliente federado se bloqueará inicialmente con la transmisión de medios hasta que se inicia el tráfico en la dirección contraria a flujo. Sin embargo, el flujo bidireccional abrirá conectividad en ambas direcciones.)

**Directo (punto a punto)**

[![La figura 12 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12 - directa (de punto a punto)*

### <a name="teams-online-hybrid-topology"></a>Topología híbrida en línea de los equipos
Esta topología es similar a los equipos en línea predeterminada ("pura") pero "agrega en" Skype para la empresa local.

[![La figura 13 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*La figura 13 - topología híbrida en línea de los equipos*
 
>**Notas**:
>- La dirección de las flechas en el diagrama anterior reflejar la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para los medios, es posible que flujo de la primera paquetes en la dirección inversa, pero estos paquetes se pueden bloquear hasta que se fluyan de paquetes en la otra dirección.
>- Se implementa en pantalla de los equipos codo con codo con Skype para profesionales en línea, por lo tanto, los clientes se muestran como "Usuario de equipos/SFB".

Flujos de adicionales (encima de los equipos en línea topología "pura"):
- **Flujo 5A** – representa un flujo de medios de punto a punto entre el usuario de los equipos dentro de la red de cliente con un Skype para la empresa en la transmisión de medios locales en el borde de la red del cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: Skype para la empresa uno a uno de los equipos
**Híbrido dentro de la red de cliente**

[![La figura 14 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*La figura 14 - híbrida dentro de la red de cliente*
 
Señalización entre los equipos y Skype para la empresa es "salvó" por una puerta de enlace en la nube de Office 365. Sin embargo, medios se enrutan directamente "punto a punto" dentro de la red de cliente a través de flujo 5.

**Red de cliente híbrida con Skype externo para usuarios de empresa – retransmitidos por Office 365**

[![La figura 15 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*La figura 15 - híbrida la red del cliente con Skype externo para usuarios de empresa - retransmitidos por Office 365*
 
>**Nota**: señalización y los medios de Skype para clientes empresariales a Skype para la empresa en el servidor local está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

Señalización entre los equipos y Skype para la empresa es "salvó" por una puerta de enlace en la nube de Office 365.

Medios se retransmiten a través de los equipos de retransmisión de transporte en Office 365 a la red del cliente a través de flujos de 4.

**Red de cliente híbrida con Skype externo para usuarios de empresa – retransmitido por en perimetral local**

[![La figura 16 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*La figura 16 - híbrida la red del cliente con Skype externo para usuarios de empresa - retransmitido en perimetral local*
 
>**Nota**: señalización y los medios de Skype para clientes empresariales a Skype para la empresa en el servidor local está fuera del ámbito de este documento. Sin embargo, se muestra aquí para mayor claridad.

Señalización es "salvó" por una puerta de enlace en la nube de Office 365.

Medios se retransmiten mediante Skype para la transmisión de medios de negocio dentro de Skype para la empresa local perimetral al usuario de los equipos dentro de la red de cliente a través de 5A de flujo de medios.

### <a name="teams-online-with-direct-routing-topology"></a>Equipos en línea con topología "Enrutamiento directo"
Esta topología es similar a los equipos en línea ("pura") pero "agrega en" enrutamiento directo. 

Dirigir el enrutamiento, anteriormente conocido como transacciones manuales (Traer su propia tronco), con un proveedor de servicio de telefónica conmutada pública de terceros. Este método es posible mediante el emparejamiento de un dispositivo de hardware de controlador de borde de sesión de cliente posee de local compatible para la nube de Office 365 y la conexión del tronco de telefonía para ese dispositivo. 

Para admitir este escenario, el cliente debe implementar SBC(s) certificados para el enrutamiento directo de uno de los asociados de negocios certificados de Microsoft. La SBC debe configurarse correctamente, como se recomienda por el proveedor y ser enrutables de nube de Office 365 para dirigir el tráfico UDP. Los medios pueden flujo directamente desde los equipos/Skype para clientes empresariales al recorrido a través de la puerta de enlace de los equipos o SBC (el desvío de puerta de enlace de los equipos (es decir, MP)). La conectividad con el SBC, cuando se configura el tronco a omitir la puerta de enlace de los equipos, se basa en ICE, donde SBC admite Lite ICE, mientras que los equipos y Skype para el extremo de medios de negocio admite ICE completo. 

[![La figura 17 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Figura 17 - equipos en línea con topología 'Enrutamiento directo'*

>**Notas**:
>- La dirección de las flechas en el diagrama anterior reflejar la dirección de inicio de la comunicación que afecta a la conectividad en los perímetros de la empresa. En el caso de UDP para los medios, es posible que flujo de la primera paquetes en la dirección inversa, pero estos paquetes se pueden bloquear hasta que se fluyan de paquetes en la otra dirección.
>- Se implementa en pantalla de los equipos codo con codo con Skype para profesionales en línea, por lo tanto, los clientes se muestran como "Usuario de equipos/SFB".

Flujos de adicionales (encima de los equipos en línea topología "pura"):
- **Flujo de 4'** - representa un flujo de Office 365 en la nube a la red del cliente, se usa para establecer una conexión entre el servidor de medios de los equipos en la nube con la SBC en local.
- **Flujo 5B** – representa un flujo de medios entre el usuario de los equipos dentro de la red del cliente con SBC enrutamiento directa en modo de "Omitir".
- **Flujo de 5 C** – representa un flujo de medios entre SBC directa de enrutamiento a otro SBC de enrutamiento directa en modo de "desvío" de llamada de RTC horquilla.

**Usuario directa enrutamiento interno (medios retransmitidos mediante la retransmisión de transporte de los equipos en Office 365)**

[![La figura 18 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*La figura 18 - usuario directa enrutamiento interno (medios retransmitidos mediante la retransmisión de transporte de los equipos en Office 365)*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable de Office 365.

Señalización y los medios de SBC a Office 365 y viceversa utilizan flujo 4 o fluyen 4'.

Señalización y los medios de cliente dentro de la red de cliente a la nube de Office 365 usan flujo 4.


**Remoto usuario enrutamiento directo (medios se enrutan a través de un servidor de medios (MP) en Office 365)**

[![La figura 19 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*La figura 19 - remoto usuario enrutamiento directo (medios se enrutan a través de un servidor de medios (MP) en Office 365)*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable de Office 365.

Señalización y los medios de SBC a Office 365 y viceversa utilizan flujo 4 o fluyen 4'.

Señalización y los medios de cliente en Internet a Office 365 nube usan flujo 3.

**Usuario interno enrutamiento directo (el desvío de medios)**

[![La figura 20 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*La figura 20 - usuario interno enrutamiento directo (el desvío de medios)*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable de Office 365.

Uso de señalización de SBC a Office 365 y viceversa flujo 4 o flujo 4'.

Señalización de cliente dentro de la red de cliente a flujo de uso de la nube de Office 365 4.

Medios de cliente dentro de la red de cliente a SBC dentro de la red de cliente use 5B de flujo.

**Usuario remoto enrutamiento directo (retransmitido mediante la retransmisión de transporte de los equipos en Office 365 el desvío de medios)**

[![La figura 21 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*La figura 21 - usuario remoto enrutamiento directo (retransmitido mediante la retransmisión de transporte de los equipos en Office 365 el desvío de medios)*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable desde Office 365 y de Internet.

Uso de señalización de SBC a Office 365 y viceversa flujo 4 o flujo 4'.

Señalización de cliente en Internet a flujo de uso de la nube de Office 365 3.

Medios de cliente en Internet a SBC dentro de la red de cliente usar flujos de 3 y 4, retransmitido mediante la retransmisión de transporte de los equipos en la nube de Office 365. 

**Usuario remoto enrutamiento directo (direct el desvío de medios)**

[![Figura 22 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*La figura 22 - usuario remoto enrutamiento directo (direct el desvío de medios)*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable desde Office 365 y de Internet.

Uso de señalización de SBC a Office 365 y viceversa flujo 4 o flujo 4'.

Señalización de cliente en Internet a flujo de uso de la nube de Office 365 3.

Medios de cliente en Internet a SBC dentro de la red de cliente use flujo 2.

**Enrutamiento (desvío de medios) – RTC horquilla llamada directa (debido a la llamada directa de transferencia)**

[![La figura 23 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*La figura 23 - enrutamiento directo (el desvío de medios) - llamada de horquilla RTC (debido a la llamada directa de transferencia)*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable de Office 365.

Uso de señalización de SBC a Office 365 y viceversa flujo 4 o flujo 4'.

Cliente está fuera de la señalización y medios bucle después de la llamada es horquilla de RTC a RTC.

Medios de instancia SBC A dentro de la red de cliente a la instancia SBC B dentro de la red de cliente (donde, A y B pueden ser la misma instancia) usar flujo 5C.

**Enrutamiento (medios a través de Office 365) – RTC horquilla llamada directa en dos inquilinos**

[![La figura 24 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Llamada de la figura 24 - enrutamiento directo (medios a través de Office 365) – RTC horquilla en dos inquilinos*
 
>**Nota**: SBC debe tener una dirección IP pública que es enrutable de Office 365.

Uso de señalización de SBC a Office 365 y viceversa flujo 4 o flujo 4'.

Cliente está fuera de la señalización y medios bucle después de la llamada es horquilla de RTC a RTC.

Modo de desvío de medios de instancia SBC A dentro de X de red de cliente a la instancia SBC B debe transmitir a través del servidor de medios de O365 y no se puede usar.

## <a name="teams-w-express-route-optimization"></a>Equipos con la optimización de la ruta de Express

[![La figura 25 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*La figura 25 - equipos con optimización de la ruta de Express*
 
En el caso de que la ruta de Express está justificado e implementado, a continuación, flujos de equipos se puede volver a distribuir desde flujo 4 para flujo 1 y de flujo de 4' para flujo 1'. Sin embargo, los equipos de aplicación tiene dependencia de disco duro en otros flujos de OFFICE 365 a través de internet a través de flujos de 4 y 4'; por lo tanto, no se deben bloquear estos flujos. 

Tenga en cuenta que Skype para el tráfico de negocio híbrida perimetral se enruta a Internet y no a la ruta de Express para comunicarse con usuarios externos y "federación" con otros inquilinos. 

Para evitar que los flujos de asimétricos, transporte alternativo debe ser en ambas direcciones. En otras palabras, una dirección de red del cliente es enrutable ya sea a través de Internet o ruta Express, basándose en la optimización, pero no a través de ambos.

Por ejemplo:

**Red del cliente para usuarios externos (medios retransmitidos mediante la retransmisión de los equipos de transporte):**

[![La figura 26 fluyen de llamadas en línea de los equipos de Microsoft](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*La figura 26 - red de cliente para usuarios externos (retransmitidos por los equipos de transporte retransmisión de medios)*
 
**Pasos generales:**
1. Los equipos de usuario dentro de la red del cliente resuelve el nombre de dominio de dirección URL (de dominio DNS) a través de flow2
2. Los equipos de usuario dentro de la red de cliente asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 1
3. Los equipos de usuario dentro de la red de cliente envía "Invitar" con candidatos ICE a través de flujo de 1 a Office 365
4. OFFICE 365 envía una notificación a los usuarios de los equipos externos a través de flujo 3
5. Los equipos de usuarios externos asigna un medio de puerto de retransmisión en los equipos de transporte retransmisión a través de flujo 3
6. Los equipos de usuario externo envía "respuesta" con candidatos ICE a través de flujo 3, que se reenvía a los equipos de usuario A través de flujo 1
7. El usuario A los equipos y los equipos de usuario B invocar pruebas de conectividad de ICE y selecciona flujos de 1 y 3, que se retransmiten mediante la retransmisión de transporte de los equipos en la nube de Office 365.
8. Los usuarios de los equipos enviar telemetría a Office 365 a través de flujos de 1 y 3

>**Nota**: flujo 4 debe estar habilitada para admitir dependencias de aplicación de los equipos en otros servicios de micro que normas fluyan 4.
