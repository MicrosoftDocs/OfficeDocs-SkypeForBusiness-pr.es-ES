---
title: Flujo de llamadas con ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.
ms.openlocfilehash: 8549104b4fe27afcdb157325ea5564298a886432
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253884"
---
# <a name="call-flow-using-expressroute"></a>Flujo de llamadas con ExpressRoute

[] Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.

Si va a implementar Skype para profesionales en línea como parte de Office 365, Skype para entornos híbridos de servidor empresarial o Skype para Business Edition de conector en la nube, necesita comprender por lo que la comunicación entre el Skype para clientes empresariales y los servidores y el flujo de llamadas forma eficaz puede planear, implementar, operar y solucionar problemas de su Skype para servicios en línea de negocio.

## <a name="call-flow-overview"></a>Información general sobre el flujo de llamadas

En este documento se describen la red segmentos que pueden incluir datos para estas llamadas fluyen y le ayuda a comprender qué tráfico permanecerá locales a la red en comparación con el tráfico que se trasladarán a través de Internet o a través de ExpressRoute. Saber qué tráfico usa ExpressRoute le ayudará a evaluar los beneficios que recibirá su compañía mediante el uso de ExpressRoute, así como también le ayudarán a que comprender la orientación sobre la implementación de ExpressRoute para validar y solución de problemas de la implementación una vez que haya decidido Para utilizar ExpressRoute.

Hay diferentes factores que puede controlar y que pueden repercutir en los flujos de llamada que se describen aquí; entre ellos, por ejemplo, las reglas de firewall, la configuración NAT, los servidores proxy y la configuración del enrutador. En este documento se da por hecho que se ha aplicado la configuración recomendada. Esta configuración recomendada se describe en:

- [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Información general de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

El programa de instalación y las configuraciones que no han seguido los pasos de configuración que se encuentran en la documentación anterior pueden tener flujos de llamadas diferentes a los documentados aquí. Además, es posible que encuentre usted mismo con problemas de configuración, como rutas de red que no son óptimos y asimétrica o protocolos de transporte que no son óptimos. Enrutamiento asimétrica es una consideración importante siempre que se trate de ExpressRoute, debido a que ExpressRoute presenta una segunda ruta de acceso a Office 365, que crea la posibilidad de una ruta que usa Internet en una dirección y otra ruta que usa ExpressRoute en la otra dirección. Esta situación puede provocar que se bloquee el tráfico en la dirección de retorno si atraviesa un firewall con estado.

## <a name="network-segments-and-traffic-types"></a>Segmentos de red y tipos de tráfico

### <a name="network-segments"></a>Segmentos de red

Antes de que podamos explicar el flujo de llamada, necesitamos definir algunos términos que le ayudarán a comprender los segmentos de red y los tipos de soporte que se utilizan en Skype Empresarial Online.

Los diagramas de flujo de llamada que aparece a continuación se muestran cuatro segmentos de red diferentes, cada uno de los cuales son administrados por distintas organizaciones (la red interna, su proveedor de servicios de red y sus socios de interconexión de Internet y Microsoft) que tienen diferentes características de rendimiento. Para obtener instrucciones sobre los objetivos de rendimiento de red, hacer referencia a la [calidad de los medios y el rendimiento de la conectividad de red en Skype para profesionales en línea](media-quality-and-network-connectivity-performance.md).

A continuación puede ver cada segmento de red del que hablaremos.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **La red** Éste es el segmento de red que forma parte de la red general que puede controla y administrar. Esto incluye todas las conexiones dentro de sus oficinas, si por cable o inalámbrica, entre edificios de oficinas, en centros de datos locales y las conexiones a proveedores de Internet o ExpressRoute socios.

Normalmente, el borde de la red tiene uno o más DMZ con firewalls o servidores proxy, que aplicar directivas de seguridad de la organización y que sólo permiten determinado el tráfico de red que ha configurado y configurado. Debido a que administrar esta red, tienen un control directo sobre el rendimiento de la red y se recomienda complete las evaluaciones de red para validar el rendimiento tanto dentro de los sitios en la red y de la red de Skype para la empresa En línea. Para ver los requisitos de rendimiento, vea [calidad de los medios y el rendimiento de la conectividad de red en Skype para profesionales en línea](media-quality-and-network-connectivity-performance.md).

 **Internet** Éste es el segmento de red que forma parte de la red general que se utilizan los usuarios que se va a conectar Skype para profesionales Online desde fuera de la red y se usan para todas las conexiones cuando no se ha configurado ExpressRoute. Internet y todas sus conexiones no están administrados por usted o por Microsoft, por lo que no se puede determinar el rendimiento y las rutas de acceso de enrutamiento, y esto tendrá el mayor impacto en el flujo de llamadas y calidad general.

 **ExpressRoute** Éste es el segmento de red que forma parte de la red general que le proporcionará una conexión privada y dedicada a la red de Microsoft. Esto es la opción recomendada para conectar la red a la red de Microsoft (centros de datos de Office 365) para todas las cargas de trabajo que dependen de la velocidad de la red y el rendimiento, como Skype para la comunicación en tiempo real en línea de negocio. ExpressRoute conexiones se realizan entre la red y el uso de red de Microsoft [ExpressRoute proveedores de conectividad](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para proporcionar una red privada y administrada, con compatibilidad para calidad de servicio (QoS) que puede mejorar el rendimiento y el tiempo de actividad del 99,9% para los medios en tiempo real durante los períodos de congestión de la red.

 **Red de Microsoft** Éste es el segmento de red que forma parte de la red general que es compatible con servicios de Office 365. Esto incluye todas las comunicaciones entre los servidores en línea para Office 365. Esto puede incluir el tráfico que atraviesa la red troncal de Microsoft y se transmite entre las regiones geográficas.

### <a name="types-of-traffic"></a>Tipos de tráfico

El tráfico de red de Skype para profesionales en línea se divide en dos categorías, que se muestra como rutas de acceso independientes en el flujo de llamadas:

 **Multimedia en tiempo real** es datos encapsuladas en RTP (Protocolo de transporte en tiempo real) y es compatible con audio, vídeo, uso compartido de aplicaciones y cargas de trabajo de transferencia de archivo. En general, el tráfico de medios altamente es confidencial, latencia, por lo que ¿desea que este tráfico a tomar la ruta más directa posible, y utilizar UDP como protocolo de capa de transporte debido a que el uso de TCP presenta latencia superior.

 **Señalización** es el vínculo de comunicación entre el cliente y servidor, u otros clientes que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y entregar mensajes instantáneos. La mayor parte del tráfico de señalización utiliza el protocolo SIP, aunque algunos clientes emplean interfaces REST basadas en HTTP. Para facilitar el proceso, estamos considerando una gran variedad de señalización que es posible que viajan a través de conexiones HTTP y HTTPS o TLS en este tipo de tráfico. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede originar cortes en el servicio o tiempos de espera en las llamadas si la latencia entre los puntos de conexión sobrepasa varios segundos.

Los destinos de este tráfico se encuentran en [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para todos los servicios de Office 365. Para cada dirección URL, indica si esa porción de tráfico puede atravesar ExpressRoute para Office 365. Para diagramas que muestran que Internet aún se usa para el tráfico de algunos cuando ExpressRoute está habilitada, consulte [ExpressRoute de Azure para Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Es importante comprender que incluso las direcciones URL que se muestran como enrutables a través de ExpressRoute también son enrutables a través de Internet. Esto significa que en algunos casos, la decisión sobre si se usará la Internet o ExpressRoute depende de la ubicación del cliente y la configuración de los servidores proxy y firewalls. También es importante comprender que dado que no todas las direcciones URL asociadas con Office 365 son capaces de usar ExpressRoute, se requiere una conexión a Internet incluso si comprar ExpressRoute desde un socio ExpressRoute.

El tráfico que sólo se puede enviar a través de Internet incluye dependencias de Internet comunes, como listas de revocación de certificados (CRL), las búsquedas de DNS y resolución de nombres, las direcciones URL de servicios compartidos de Office 365, como para el centro de administración de Office 365 y algunos que no son en tiempo real características de comunicación de Skype para en línea de negocio, como la telemetría y la federación para la interoperabilidad con Skype consumidor, como bien multimedia que se transmite para difundir presentación de reunión de Skype. Para ayudarle a tomar decisiones, consulte [Enrutamiento con ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para ver más consideraciones a la hora de planificar su enrutamiento de red.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principios para los flujos de llamadas con Skype Empresarial

Antes de entrar en los detalles de los escenarios concretos de los flujos de llamada, hay seis principios generales que le ayudarán a comprender los flujos de llamada para Skype Empresarial.

1. Un Skype para conferencia de negocios se hospeda en la misma región donde se hospeda el organizador de la conferencia. Se trata de la nube de Office 365 si el organizador es un usuario en línea o de un centro de datos local si el organizador de la reunión es un usuario local.

2. El tráfico de medios enviado desde un cliente a una conferencia hospedada siempre va al servidor donde se hospeda la conferencia. Esto puede ser un servidor local dentro de un centro de datos que administre o un servidor en línea dentro de la nube de Office 365. Sin embargo, un servidor perimetral siempre se usa para el flujo de medios para conferencias en línea.

3. El tráfico multimedia de las llamadas de punto a punto toma la ruta más directa que esté disponible. La ruta preferida va directa al equipo remoto (cliente), pero si esa ruta no está disponible porque el firewall está bloqueando el tráfico o existe algún otro problema de este tipo, entonces uno o varios servidores perimetrales retransmitirán el tráfico.

4. El tráfico de señalización siempre se dirige al servidor en el que se aloja el usuario, ya sea en línea o local. Se utilizará un servidor perimetral si el servidor front-end no se puede conectar directamente.

5. Los usuarios que se unen a una conferencia hospedada en línea siempre usarán un servidor perimetral (o dos si es necesario por las configuraciones del firewall para cliente).

6. Los usuarios que se unen a una conferencia hospedada en local no utilizarán, por lo general, un servidor perimetral si se conectan desde dentro de la misma red que contiene la implementación local, y utilizarán uno o dos servidores perimetrales cuando se conectan desde fuera de la red.

Para obtener más información sobre los detalles de la ruta multimedia que se elige, consulte [ICE: conectividad multimedia perimetral](https://aka.ms/AVEdge). Aunque en este vídeo es acerca de Lync Server 2013, los principios y los protocolos aún se aplican a Skype para la empresa.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Los flujos de llamada de Skype Empresarial con ExpressRoute

Ahora que tiene una comprensión de los cuatro segmentos de red diferentes y algunos principios de guía general para Skype empresarial flujos de llamada, puede usar que la información que le ayudarán a comprender qué Skype para el tráfico de negocio atravesará un ExpressRoute segmento de red.

En general, el tráfico de red cruzará la conexión de ExpressRoute si un punto de conexión está en su red y el otro está en el centro de datos de Office 365. Esto incluirá el tráfico de señalización entre el cliente y el servidor, el tráfico multimedia usado durante las llamadas de conferencia o las llamadas de punto a punto que usan un servidor perimetral en línea.

El tráfico no cruzará la conexión de ExpressRoute si los dos puntos de conexión se pueden comunicar directamente a través de Internet o si están situados dentro de su red. Esto incluirá medios para las llamadas de punto a punto, el tráfico de Internet destinado a una implementación local o todo el tráfico entre Internet y los servidores perimetrales de Office 365. Un ejemplo sería un usuario que se une a una conferencia en línea desde un hotel.

## <a name="basic-skype-for-business-call-flow"></a>Flujo de llamadas básico de Skype Empresarial

Para ayudarle a aplicar los principios generales de los flujos de llamada de Skype Empresarial que se han descrito anteriormente, la próxima sección de este artículo contiene diagramas como referencia. No se trata de una lista exhaustiva de todos los posibles flujos de llamadas, sino de un intento de ayudarle a aplicar los principios detallados anteriormente. Además, los escenarios de los diagramas se han seleccionado para cubrir los tipos de implementación más comunes; entre ellos, en línea, híbrida, conector de nube y, en un caso especial, la Difusión de reunión de Skype.

> [!NOTE]
> Un subconjunto de tráfico usado por Skype para la empresa no se pueden enrutar a través de ExpressRoute y siempre tendrá una ruta de acceso de Internet. Hacer referencia a la [URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar las direcciones URL que pueden verse afectadas.

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Llamada de punto a punto para los usuarios de Office 365 desde dentro de la red de cliente
<a name="bk_Figure2"> </a>

En las llamadas de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. No obstante, el tráfico de señalización va a un centro de datos de Office 365 en el que está alojado el usuario en línea. Puesto que ambos usuarios están en la misma WAN y nada impide que los clientes se comuniquen directamente, los elementos multimedia fluyen directamente entre ellos. El tráfico de señalización, en el caso de ambos usuarios, atraviesa la conexión de ExpressRoute que se destina al centro de datos de cada organización. Para mostrarle el flujo de llamadas en este escenario, vea esto.

 **Flujo de llamadas de punto a punto**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuario en línea de su red que se une a una conferencia hospedada en línea
<a name="bk_Figure3"> </a>

En el ejemplo de punto a punto, el tráfico de medios siempre toma la ruta más directa a su destino. Sin embargo, para una conferencia en línea, el destino es en la nube de Office 365. Esto significa que el tráfico multimedia de todos los usuarios que se unen a la conferencia desde su red atravesará la conexión de ExpressRoute y el tráfico de señalización viajará hasta la nube de Office 365. El siguiente gráfico muestra que medios y señalización atravesarán la conexión de ExpressRoute para un usuario dentro de la red y atravesarán directamente a Internet para los usuarios que están conectados a Internet desde fuera de la red, por ejemplo, desde un café comprar o un hotel.

Recuerde que la ubicación de una conferencia es definida por el organizador de la reunión y no por los participantes. Esto significa que si la reunión se programó por un cliente local, el tráfico de medios no flujo a la nube de Office 365 a través de ExpressRoute, pero en su lugar, debería atravesar Internet al centro de datos local del organizador de la reunión.

El destino de los elementos multimedia en el caso de las conferencias en línea será un centro de datos en la nube de Office 365, pero este se puede encontrar en una región geográfica distinta a la de los usuarios que se están uniendo a la conferencia. Esta situación se da de una de estas dos formas:

- Si el organizador de la reunión pertenece a una empresa distinta a la de los asistentes o participantes, y la organización del organizador está hospedada en una ubicación geográfica, o país o región, distinta.

- Si un usuario se une desde un país o región distinto al de la organización de la empresa, ya sea porque es una empresa multinacional o porque el usuario esté viajando.

La buena noticia sobre el uso de ExpressRoute en este escenario es que con el complemento de premium ExpressRoute, datos que sigue a la ruta de acceso ExpressRoute pasará automáticamente a través de la red troncal de Microsoft, independientemente de la región geográfica del organizador de la reunión Centro de datos de la organización.

 **Flujo de llamadas de un usuario en línea con una reunión en línea**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Unirse a una conferencia hospedada por un usuario local en una implementación híbrida
<a name="bk_Figure3"> </a>

Recuerde que los servidores de conferencia que admiten conferencias con host vienen determinados por donde se hospeda el organizador de la reunión. En este escenario, los medios para todos los usuarios que se unan a una conferencia programada por un usuario local en una implementación híbrida fluirá a un centro de datos local. Señalización para los usuarios asignados en línea se establecerá a través de su organización en la nube de Office 365, mientras que los medios intentan una conexión directa. En este escenario, puesto que los dos usuarios se conectan desde dentro de la red, una conexión directa de medios es posible, por lo que ExpressRoute solo se usa para el tráfico para el usuario alojado en línea de señalización. Si un usuario alojado en línea se conecta desde Internet, los medios podrían atravesar ExpressRoute si se usa un servidor perimetral en línea para conectarse.

 **Flujo de llamadas de una conferencia organizada por usuario híbrido**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Servidor perimetral local con conferencias hospedadas en Office 365
<a name="bk_Figure5"> </a>

Cuando un usuario se une híbrida en una línea hospeda la conferencia, sabemos que señalización y medios va a estar destinados a la nube de Office 365 y, puesto que el usuario se está uniendo desde Internet, normalmente una ruta de acceso directo de internet debería tomarse. Sin embargo, en algunos casos, por ejemplo, debido a restricciones del firewall, una ruta de acceso directo de Internet no está disponible. En este caso, un servidor perimetral de local puede retransmitir el tráfico de medios, que hace que el tráfico de medios volver a la red local antes de atravesar el circuito ExpressRoute a la nube de Office 365.

 **Usuario local que se une a una llamada de conferencia en línea con un servidor perimetral local**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Llamada RTC con Skype Empresarial Cloud Connector Edition
<a name="bk_Figure6"> </a>

Con [Skype Empresarial Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) se proporciona conectividad RTC al usar recursos locales, como un tronco SIP o una puerta de enlace RTC, o al usar un dispositivo de hardware mínimo para integrarlo con Skype Empresarial. Con la edición de conector en la nube, los usuarios están hospedados en línea y actúan como normales usuarios en línea cuando no afectan a los planes de llamada. La señalización en escenarios RTC viajará entre el cliente y la nube a través de una conexión de ExpressRoute si está disponible, y el tráfico multimedia permanece dentro de su WAN. En este caso, la señalización se gira en la nube de Office 365 y termina en Cloud Connector.

 **Llamada de RTC a través del sistema de teléfono en Office 365 y el conector de la nube**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Difusión de reunión de Skype con usuarios que se unen desde la red del cliente
<a name="bk_Figure6"> </a>

La Difusión de reunión de Skype es un caso de uso especial que consiste en una reunión de dos partes en la que cada parte tiene diferentes perfiles de transporte de red. La primera parte y que es más importante de una red punto de vista del rendimiento, es la reunión interna. Se trata de la parte en tiempo real de la reunión que incluye uno o más extremos de cliente que se conectan al servidor de conferencia en la nube de Office 365. Datos que se transmiten utilizando esta parte de la reunión están exactamente igual que el ejemplo encima, con una combinación de usuario de Office 365 y conferencia en línea.

¿Qué hace una difusión de reunión de Skype únicos es que la reunión se distribuye a un gran número de asistentes a la conferencia mediante una transmisión por secuencias de servicio de difusión. Esta difusión de transmisión por secuencias de servicio no se pueden enrutar a través de ExpressRoute, sino que utiliza Internet con la compatibilidad opcional de los servicios de red de entrega de contenido (CDN). Es útil reconocer que la transmisión de difusión es un flujo de medios unidireccional debido a que los asistentes escuchan pero no hablar y es compatible con el almacenamiento en búfer, por lo que es mucho menos sensible a problemas de rendimiento de red como latencia, la pérdida de paquetes y vibración. En lugar de optimizar el tráfico de difusión para estos problemas, está optimizado para la utilización de ancho de banda porque no hay potencialmente un gran número de asistentes recibir los medios de transmisión por secuencias.

 **Difusión de reunión de Skype con usuarios desde la red del cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Patrones de flujos de llamadas según el tipo de implementación

Con el common llamar ejemplos de flujo anteriores, y una descripción de los principios generales que controlan los patrones de tráfico, las siguientes tablas proporcionan un resumen de los patrones de tráfico de una combinación de escenarios de implementación y uso de gran tamaño. En estas tablas no se trata de capturar todas las posibles combinaciones de flujos de llamadas, sino que se han creado como una ayuda para comprender mejor sus principios generales.

Datos se transmiten y se anuncia como local a la organización; no sale de la red del cliente, Internet o ExpressRoute. Los modelos enumerados a continuación se basan en la configuración de red más comunes, como los servidores de seguridad, federación e Internet y se suponen que todas las organizaciones que participan en flujos de varios participantes o federados tienen ExpressRoute. En la práctica, tener diferentes configuraciones podría derivar en otros patrones de tráfico, distintos a los que se indican a continuación.

### <a name="call-flows-for-skype-for-business-online"></a>Flujos de llamadas para Skype Empresarial Online

Skype para los escenarios de uso en línea de negocio relacionadas con los usuarios que están hospedados en línea y pueden llamar desde la red interna o en Internet. Los servidores locales no forman parte de estos escenarios, por lo que todas las conferencias o medios relacionados de RTC fluirá a la nube de Office 365 y los usuarios en línea servidor perimetral también estarán en la nube.

 **Resumen de los flujos de llamadas para Skype Empresarial Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos en su red.  <br/> |ExpressRoute  <br/> |Local  <br/> |[Llamada de punto a punto para los usuarios de Office 365 desde dentro de la red de cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Llamada de punto a punto  <br/> |Los clientes de dos, uno en la red (interna) y el otro cliente de Internet (externo).  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: De Internet al servidor perimetral de Office 365.  <br/> |[Llamada de punto a punto para los usuarios de Office 365 desde dentro de la red de cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Se da por supuesto que firewall bloquea las conexiones directas entre los clientes, que requiere un servidor perimetral en línea. El tráfico de usuario interno al servidor perimetral en línea sigue similar ruta de acceso que al servidor de conferencia para llamada de conferencia.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, en su red (interno) y el usuario en línea en la red de la organización federada (federado).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la de un servidor de conferencias para la llamada de conferencia.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente  <br/> |El cliente en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a llamada de conferencia por usuario en Internet  <br/> |Cliente está en el servidor de Internet y conferencia en Office 365 en la nube.  <br/> |Internet  <br/> |Internet  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a una conferencia hospedada por el servidor local de otra empresa  <br/> |El cliente en su red y el servidor de conferencias en el centro de datos de terceros.  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Dado que el servidor de conferencias que hospeda la conferencia está en una red local de otro cliente, ningún dato pasará por la nube de Microsoft.  <br/> |
|Llamada RTC  <br/> |Cliente de red de cliente y los servidores de sistema telefónico en nube de Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Llamada RTC  <br/> |Cliente en los servidores de Internet y el sistema telefónico en nube de Office 365  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Flujo de los medios y señalización realizarán al centro de datos de Office 365. Dado que el extremo de cliente está en Internet, todos los datos fluirá al centro de datos de Microsoft a través de Internet (incluso si es necesario un servidor perimetral en línea para la conectividad).  <br/> |

> [!NOTE]
> ExpressRoute se usará en la ruta de acceso de medios de un usuario que se encuentra en la red corporativa a un servidor perimetral en línea, pero no se utilizará si se usa el servidor perimetral para la implementación local de otro cliente.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flujos de llamadas para la implementación híbrida de Skype Empresarial

Los flujos de llamadas híbridos se aplican cuando tiene una implementación de Skype Empresarial que incluye al menos algunos usuarios que están hospedados en local. Los flujos de llamada en esta sección incluyen tanto las conferencias locales y punto a punto o RTC llama con al menos un usuario asignado local.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, en la red del cliente y alojados en local.  <br/> |Local  <br/> |Local  <br/> |[Llamada de punto a punto para los usuarios de Office 365 desde dentro de la red de cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Como los usuarios se alojan en local, la señalización fluye en local al centro de datos local en lugar de a la nube de Office 365.  <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos conectados desde la red del cliente. Uno está alojado en línea y el otro en local.  <br/> |Usuario en línea: ExpressRoute  <br/> Usuario local: local  <br/> |Local  <br/> |[Llamada de punto a punto para los usuarios de Office 365 desde dentro de la red de cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo el usuario alojado en línea envía tráfico de señalización a la nube de Office 365.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, uno local en la red del cliente (interno) y un usuario en línea en la red de la organización federada (federado).  <br/> |Usuario interno: local  <br/> Usuario federado: ExpressRoute  <br/> |Internet o ExpressRoute (depende de si se usa el servidor en línea o perimetral local)  <br/> |[Usuario en línea en la red que se unan a una conferencia que está hospedado en línea](call-flow-using-expressroute.md#bk_Figure3) y el elemento de [servidor perimetral local con Office 365 aloja conferencias](call-flow-using-expressroute.md#bk_Figure5) (para el tráfico de medios). <br/> |Se da por supuesto un firewall bloquea las conexiones directas entre los clientes, que requiere el servidor perimetral en línea. La negociación de ICE ofrecerá Online (por el usuario en línea) y los servidores perimetrales de local (por el usuario local) para la conectividad.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente (conferencia programada por el usuario en línea)  <br/> |El usuario en local en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |Recursos de servidor para la llamada de conferencia se definen mediante el organizador de la reunión. En este caso, la programó un usuario en línea, por lo que los recursos están en la nube de Office 365.  <br/> |
|Llamada RTC  <br/> |Usuario en local en su red y centro de datos Skype Empresarial local.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Similar escenario para usar Cloud Connector Edition, con la diferencia de que el usuario está alojado en local, de modo que la señalización permanece dentro de la red.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flujos de llamadas de Skype Empresarial con Cloud Connector

Todos los usuarios que se conectarán a Cloud Connector Edition están alojados en línea. Esto significa que las conferencias serán en línea y que la señalización sigue los mismos patrones que los usuarios en línea. Para otros escenarios distintos de las llamadas RTC, el flujo de llamadas será exactamente el mismo que el descrito anteriormente para Skype Empresarial Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada RTC  <br/> |Usuario en línea en su red con Cloud Connector Edition.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Llamada RTC  <br/> |Usuario en línea que usa Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinación de [servidor perimetral local con Office 365 hospedados conferencias](call-flow-using-expressroute.md#bk_Figure5) y [RTC llamar con Skype para Business Edition de conector en la nube](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Los usuarios de Internet se conectarán a través del servidor perimetral que se incluye en Cloud Connector y Cloud Connector se conectará a la red RTC.  <br/> |

## <a name="related-topics"></a>See also

[Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


