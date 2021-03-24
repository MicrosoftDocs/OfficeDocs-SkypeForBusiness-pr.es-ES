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
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.
ms.openlocfilehash: 968b0a991e89d8c9cfd9ef3e26e2e30806c069b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100736"
---
# <a name="call-flow-using-expressroute"></a>Flujo de llamadas con ExpressRoute

Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.

Si va a implementar Skype Empresarial Online como parte de Microsoft 365 u Office 365, Skype Empresarial Server Híbrido o Skype Empresarial Cloud Connector Edition, tendrá que comprender la comunicación entre el cliente y los servidores de Skype Empresarial y el flujo de llamadas para que pueda planear, implementar, operar y solucionar problemas de forma eficaz sus servicios de Skype Empresarial Online.

## <a name="call-flow-overview"></a>Información general sobre el flujo de llamadas

En este documento se describen los segmentos de red que pueden transportar datos para estos flujos de llamadas y le ayuda a comprender qué tráfico permanecerá local en su red en comparación con el tráfico que viajará a través de Internet o a través de ExpressRoute. Al saber qué trafico utiliza ExpressRoute, podrá evaluar las ventajas que recibirá su empresa si decide usarlo, y podrá comprender la guía de implementación de ExpressRoute para validar y solucionar los problemas de su implementación una vez que haya decidido usarlo.

Hay diferentes factores que puede controlar y que pueden repercutir en los flujos de llamada que se describen aquí; entre ellos, por ejemplo, las reglas de firewall, la configuración NAT, los servidores proxy y la configuración del enrutador. En este documento se da por hecho que se ha aplicado la configuración recomendada. Esta configuración recomendada se describe en:

- [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Información general de ExpressRoute](/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Las configuraciones y configuraciones que no han seguido los pasos de configuración que se encuentran en la documentación anterior pueden tener flujos de llamadas diferentes a los que hemos documentado aquí. Además, es posible que se encuentre con problemas de configuración, como rutas de red asimétricas y no óptimas, o protocolos de transporte no óptimos. El enrutamiento asimétrico es una consideración importante siempre que ExpressRoute esté implicado, ya que ExpressRoute introduce una segunda ruta de acceso a Office 365, que crea la posibilidad de una ruta que usa Internet en una dirección y otra que usa ExpressRoute en la otra dirección. Esta situación puede provocar que se bloquee el tráfico en la dirección de retorno si atraviesa un firewall con estado.

## <a name="network-segments-and-traffic-types"></a>Segmentos de red y tipos de tráfico

### <a name="network-segments"></a>Segmentos de red

Antes de que podamos explicar el flujo de llamada, necesitamos definir algunos términos que le ayudarán a comprender los segmentos de red y los tipos de soporte que se utilizan en Skype Empresarial Online.

Los diagramas de flujo de llamadas siguientes muestran cuatro segmentos de red diferentes, cada uno de los cuales están administrados por diferentes organizaciones (su red interna, su proveedor de servicios de red y sus partners de emparejamiento de Internet, y Microsoft) que tienen características de rendimiento diferentes. Para obtener directrices sobre los destinos de rendimiento de red, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance.md).

A continuación puede ver cada segmento de red del que hablaremos.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Su red** Este es el segmento de red que forma parte de la red general que controla y administra. Esto incluye todas las conexiones dentro de sus oficinas, ya sea cableadas o inalámbricas, entre edificios de oficinas, a centros de datos locales y sus conexiones a proveedores de Internet o socios de ExpressRoute.

Normalmente, el borde de la red tiene una o más DMZ con firewalls o servidores proxy, que aplican las directivas de seguridad de su organización y que solo permiten cierto tráfico de red que haya configurado y configurado. Dado que administra esta red, tiene control directo sobre el rendimiento de su red y es muy recomendable que complete evaluaciones de red para validar el rendimiento tanto dentro de los sitios de su red como desde su red a Skype Empresarial Online. Para ver los requisitos de rendimiento, vea Calidad multimedia y Rendimiento de conectividad de [red en Skype Empresarial Online.](media-quality-and-network-connectivity-performance.md)

 **Internet** Este es el segmento de red que forma parte de la red general que usarán los usuarios que se conecten a Skype Empresarial Online desde fuera de la red y que se usa para todas las conexiones cuando ExpressRoute no está configurado. Internet y todas sus conexiones no son administradas por usted o Microsoft, por lo que no se pueden determinar las rutas de enrutamiento y rendimiento, lo que tendrá el mayor impacto en el flujo de llamadas y la calidad general.

 **ExpressRoute** Este es el segmento de red que forma parte de su red general que le dará una conexión privada dedicada a la red de Microsoft. Esta es la opción recomendada para conectar su red a la red de Microsoft (centros de datos de Microsoft 365 u Office 365) para todas las cargas de trabajo que dependen de la velocidad y el rendimiento de la red, como la comunicación en tiempo real de Skype Empresarial Online. Las conexiones de ExpressRoute se realizan entre su red y la red de Microsoft usan proveedores de conectividad [de ExpressRoute](/azure/expressroute/expressroute-locations) para proporcionar una red privada y administrada, con un 99,9 % de tiempo de actividad y compatibilidad con calidad de servicio (QoS) que puede mejorar el rendimiento de los medios en tiempo real durante períodos de congestión de red.

 **Red de Microsoft** Este es el segmento de red que forma parte de la red global compatible con los servicios de Microsoft 365 y Office 365. Esto incluye toda la comunicación entre servidores en línea para Microsoft 365 u Office 365. Esto puede incluir tráfico que atraviesa la red troncal de Microsoft y se transmite entre regiones geográficas.

### <a name="types-of-traffic"></a>Tipos de tráfico

El tráfico de red de Skype Empresarial Online se divide en dos grandes categorías, que se muestran como rutas separadas en el flujo de llamadas:

 **Los** medios en tiempo real son datos encapsulados dentro de RTP (Protocolo de transporte en tiempo real) y admiten cargas de trabajo de audio, vídeo, uso compartido de aplicaciones y transferencia de archivos. En general, el tráfico multimedia es muy sensible a la latencia, por lo que sería mejor que este tráfico tomara la ruta más directa posible y que usara UDP como el protocolo de capa de transporte, puesto que con el protocolo TCP se introduciría una latencia mayor.

 **La señalización** es el vínculo de comunicación entre el cliente y el servidor, u otros clientes que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y entregar MI. La mayor parte del tráfico de señalización utiliza el protocolo SIP, aunque algunos clientes emplean interfaces REST basadas en HTTP. Para que sea sencillo, estamos pensando en una señalización de variedad que puede desplazarse a través de conexiones HTTP y HTTPS o TLS en este tipo de tráfico. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede originar cortes en el servicio o tiempos de espera en las llamadas si la latencia entre los puntos de conexión sobrepasa varios segundos.

Los destinos de este tráfico se encuentran en direcciones URL e intervalos de direcciones IP de [Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para todos los servicios de Microsoft 365 u Office 365. Para cada dirección URL, indica si esa parte del tráfico puede atravesar ExpressRoute para Microsoft 365 u Office 365. Para ver los diagramas que muestran que Internet se sigue utilizando para cierto tráfico cuando ExpressRoute está habilitado, consulte [Azure ExpressRoute para Office 365.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) Es importante comprender que incluso las direcciones URL que aparecen como enrutables a través de ExpressRoute también son enrutables a través de Internet. Esto significa que, en algunos escenarios, la determinación sobre si se usará Internet o ExpressRoute depende de la ubicación del cliente y la configuración de servidores proxy y firewalls. También es importante comprender que, dado que no todas las direcciones URL asociadas a Microsoft 365 u Office 365 pueden usar ExpressRoute, se requiere una conexión a Internet incluso si compra ExpressRoute a un partner de ExpressRoute.

El tráfico que solo se puede enviar a través de Internet incluye dependencias comunes de Internet, como listas de revocación de certificados (CRL), búsquedas DNS y resolución de nombres, direcciones URL para servicios compartidos de Microsoft 365 u Office 365, como para el Centro de administración de Microsoft 365, y algunas características de comunicación no en tiempo real de Skype Empresarial Online, como telemetría y federación para interoperabilidad con el consumidor de Skype , así como los medios que se transmiten para difusión de reunión de Skype. Para ayudarle a tomar decisiones, consulte [Enrutamiento con ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para ver más consideraciones a la hora de planificar su enrutamiento de red.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principios para los flujos de llamadas con Skype Empresarial

Antes de entrar en los detalles de los escenarios concretos de los flujos de llamada, hay seis principios generales que le ayudarán a comprender los flujos de llamada para Skype Empresarial.

1. Una conferencia de Skype Empresarial se hospeda en la misma región donde se hospeda el organizador de la conferencia. Esto se encuentra en la nube si el organizador es un usuario en línea o en un centro de datos local si el organizador de la reunión es un usuario local.

2. El tráfico multimedia que se envía desde un cliente a una conferencia hospedada siempre se dirige al servidor en el que se aloja la conferencia. Puede ser un servidor local dentro de un centro de datos que administra o un servidor en línea dentro de la nube. Sin embargo, siempre se utiliza un servidor perimetral para el flujo multimedia de las conferencias en línea.

3. El tráfico multimedia de las llamadas de punto a punto toma la ruta más directa que esté disponible. La ruta preferida va directa al equipo remoto (cliente), pero si esa ruta no está disponible porque el firewall está bloqueando el tráfico o existe algún otro problema de este tipo, entonces uno o varios servidores perimetrales retransmitirán el tráfico.

4. El tráfico de señalización siempre se dirige al servidor en el que se aloja el usuario, ya sea en línea o local. Se utilizará un servidor perimetral si el servidor front-end no se puede conectar directamente.

5. Los usuarios que se unen a una conferencia hospedada en línea siempre usarán un servidor perimetral (o dos si es necesario por las configuraciones del firewall para cliente).

6. Los usuarios que se unen a una conferencia hospedada en local no utilizarán, por lo general, un servidor perimetral si se conectan desde dentro de la misma red que contiene la implementación local, y utilizarán uno o dos servidores perimetrales cuando se conectan desde fuera de la red.

Para obtener más información sobre los detalles de la ruta multimedia que se elige, consulte [ICE: conectividad multimedia perimetral](https://aka.ms/AVEdge). Aunque este vídeo trata sobre Lync Server 2013, los principios y protocolos se siguen aplicando a Skype Empresarial.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Los flujos de llamada de Skype Empresarial con ExpressRoute

Ahora que conoce los cuatro segmentos de red diferentes y algunos principios guía generales para los flujos de llamadas de Skype Empresarial, puede usar esa información para ayudarle a comprender qué tráfico de Skype Empresarial atravesará un segmento de red de ExpressRoute.

En general, el tráfico de red atravesará la conexión de ExpressRoute si un punto de conexión está en la red y el otro punto de conexión está en el centro de datos de Microsoft 365 u Office 365. Esto incluirá el tráfico de señalización entre el cliente y el servidor, el tráfico multimedia usado durante las llamadas de conferencia o las llamadas de punto a punto que usan un servidor perimetral en línea.

El tráfico no cruzará la conexión de ExpressRoute si los dos puntos de conexión se pueden comunicar directamente a través de Internet o si están situados dentro de su red. Esto incluirá medios para llamadas punto a punto, tráfico de Internet destinado a una implementación local o cualquier tráfico entre Internet y Microsoft 365 u Servidores perimetrales de Office 365. Un ejemplo sería un usuario que se une a una conferencia en línea desde un hotel.

## <a name="basic-skype-for-business-call-flow"></a>Flujo de llamadas básico de Skype Empresarial

Para ayudarle a aplicar los principios generales de los flujos de llamada de Skype Empresarial que se han descrito anteriormente, la próxima sección de este artículo contiene diagramas como referencia. No se trata de una lista exhaustiva de todos los posibles flujos de llamadas, sino de un intento de ayudarle a aplicar los principios detallados anteriormente. Además, los escenarios de los diagramas se han seleccionado para cubrir los tipos de implementación más comunes; entre ellos, en línea, híbrida, conector de nube y, en un caso especial, la Difusión de reunión de Skype.

> [!NOTE]
> Un subconjunto de tráfico usado por Skype Empresarial no es enrutable a través de ExpressRoute y siempre tendrá una ruta de Acceso a Internet. Consulte [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar las direcciones URL que se pueden ver afectadas.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Llamada punto a punto para usuarios de Microsoft 365 u Office 365 desde la red de clientes
<a name="bk_Figure2"> </a>

En las llamadas de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. Sin embargo, el tráfico de señalización va a un centro de datos de Microsoft 365 u Office 365 donde se encuentra el usuario en línea. Puesto que ambos usuarios están en la misma WAN y nada impide que los clientes se comuniquen directamente, los elementos multimedia fluyen directamente entre ellos. El tráfico de señalización, en el caso de ambos usuarios, atraviesa la conexión de ExpressRoute que se destina al centro de datos de cada organización. Para mostrarle el flujo de llamadas en este escenario, vea esto.

 **Flujo de llamadas de punto a punto**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuario en línea de su red que se une a una conferencia hospedada en línea
<a name="bk_Figure3"> </a>

En el ejemplo punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. Sin embargo, para una conferencia en línea, el destino está en la nube. Esto significa que el tráfico multimedia para todos los usuarios que se unan a la conferencia desde dentro de la red atravesará la conexión de ExpressRoute y el tráfico de señalización viajará a la nube. El siguiente gráfico muestra que los medios y la señalización atravesarán la conexión de ExpressRoute para un usuario dentro de la red y atravesarán directamente Internet para los usuarios conectados a Internet desde fuera de la red, como desde una cafetería o un hotel.

Recuerde que la ubicación de una conferencia la define el organizador de la reunión y no los participantes. Esto significa que si un cliente local programó la reunión, el tráfico multimedia no fluirá a la nube a través de ExpressRoute, sino que atravesará Internet hasta el centro de datos local del organizador de la reunión.

El destino de los medios para conferencias en línea será un centro de datos dentro de la nube de Microsoft 365 u Office 365, pero el centro de datos puede estar en una región geográfica diferente de los usuarios que se unen a la conferencia. Esta situación se da de una de estas dos formas:

- Si el organizador de la reunión pertenece a una empresa distinta a la de los asistentes o participantes, y la organización del organizador está hospedada en una ubicación geográfica, o país o región, distinta.

- Si un usuario se une desde un país o región distinto al de la organización de la empresa, ya sea porque es una empresa multinacional o porque el usuario esté viajando.

La buena noticia sobre el uso de ExpressRoute en este escenario es que, con el complemento Premium de ExpressRoute, los datos que siguen a la ruta de acceso de ExpressRoute pasarán automáticamente por la columna vertebral de Microsoft independientemente de la región geográfica del organizador del centro de datos de la organización de la reunión.

 **Flujo de llamadas de un usuario en línea con una reunión en línea**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Unirse a una conferencia hospedada por un usuario local en una implementación híbrida
<a name="bk_Figure3"> </a>

Recuerde que los servidores de conferencia que admiten conferencias hospedadas se determinan por el lugar en el que se encuentra el organizador de la reunión. En este escenario, los elementos multimedia de todos los usuarios que se unen a una conferencia programada por un usuario local en una implementación híbrida fluirán hasta un centro de datos local. La señalización para los usuarios de inicio en línea se establecerá a través de su organización en la nube, mientras que los medios intentarán una conexión directa. En este escenario, dado que ambos usuarios se conectan desde dentro de la red, es posible una conexión multimedia directa, por lo que ExpressRoute solo se usa para señalizar tráfico para el usuario conectado en línea. Si un usuario de inicio en línea se conecta desde Internet, el medio podría atravesar ExpressRoute si se usa un servidor perimetral en línea para conectarse.

 **Flujo de llamadas de una conferencia organizada por usuario híbrido**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Servidor perimetral local con conferencias hospedadas en Microsoft 365 u Office 365
<a name="bk_Figure5"> </a>

Cuando un usuario híbrido se une a una conferencia hospedada en línea, sabemos que la señalización y los medios se destinarán a la nube de Microsoft 365 u Office 365 y, como el usuario se une desde Internet, normalmente se tomaría una ruta de acceso a Internet directa. Sin embargo, en algunos casos, como por ejemplo debido a restricciones del firewall, una ruta de acceso a Internet directa no está disponible. En este caso, un servidor perimetral local puede retransmitir el tráfico multimedia, lo que hace que el tráfico multimedia vuelva a su red local antes de atravesar el circuito de ExpressRoute a la nube.

 **Usuario local que se une a una llamada de conferencia en línea con un servidor perimetral local**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Llamada RTC con Skype Empresarial Cloud Connector Edition
<a name="bk_Figure6"> </a>

Con [Skype Empresarial Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) se proporciona conectividad RTC al usar recursos locales, como un tronco SIP o una puerta de enlace RTC, o al usar un dispositivo de hardware mínimo para integrarlo con Skype Empresarial. Con Cloud Connector Edition, los usuarios se encuentran en línea y actúan como usuarios en línea normales cuando no implican planes de llamadas. La señalización en escenarios RTC viajará entre el cliente y la nube a través de una conexión de ExpressRoute si está disponible, y el tráfico multimedia permanece dentro de su WAN. En este caso, la señalización gira en la nube de Microsoft 365 u Office 365 y termina en cloud Connector.

 **Llamada RTC a través del sistema telefónico en Microsoft 365 u Office 365 y Conector en la nube**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Difusión de reunión de Skype con usuarios que se unen desde la red del cliente
<a name="bk_Figure6"> </a>

La Difusión de reunión de Skype es un caso de uso especial que consiste en una reunión de dos partes en la que cada parte tiene diferentes perfiles de transporte de red. La primera parte, y la más importante desde el punto de vista de rendimiento de red, es la reunión interna. Esta es la parte en tiempo real de la reunión que incluye uno o varios puntos de conexión de cliente que se conectan al servidor de conferencias en la nube. Los datos transmitidos con esta parte de la reunión son exactamente iguales al ejemplo anterior, con un usuario que se une a una conferencia en línea.

Lo que hace que la difusión de reunión de Skype sea única es que la reunión se distribuye a un gran número de asistentes a la conferencia mediante un servicio de transmisión de difusión. Este servicio de streaming de difusión no es enrutable a través de ExpressRoute, sino que usa Internet con el soporte opcional de los servicios de red de entrega de contenido (CDN). Es útil reconocer que el streaming de difusión es un flujo multimedia unidireccional porque los asistentes escuchan pero no hablan y admiten el almacenamiento en búfer, por lo que es mucho menos sensible a los problemas de rendimiento de red como la latencia, la pérdida de paquetes y la vibración. En lugar de optimizar el tráfico de difusión para estos problemas, está optimizado para el uso del ancho de banda, ya que potencialmente hay un gran número de asistentes que reciben los medios transmitidos.

 **Difusión de reunión de Skype con usuarios desde la red del cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Patrones de flujos de llamadas según el tipo de implementación

Con los ejemplos de flujo de llamadas comunes anteriores y una comprensión de los principios generales que controlan los patrones de tráfico, las tablas siguientes proporcionan un resumen de los patrones de tráfico para una gran combinación de escenarios de implementación y uso. En estas tablas no se trata de capturar todas las posibles combinaciones de flujos de llamadas, sino que se han creado como una ayuda para comprender mejor sus principios generales.

Los datos se transmiten y se muestran como locales para la organización; no deja la red de clientes, Internet o ExpressRoute. Los patrones enumerados a continuación se basan en la configuración de red más común, como firewalls, federación e Internet, y suponen que todas las organizaciones involucradas en flujos federados o de varias partes tienen ExpressRoute. En la práctica, tener diferentes configuraciones podría derivar en otros patrones de tráfico, distintos a los que se indican a continuación.

### <a name="call-flows-for-skype-for-business-online"></a>Flujos de llamadas para Skype Empresarial Online

Los escenarios de uso de Skype Empresarial Online implican a los usuarios que se encuentran en el hogar en línea y pueden estar llamando desde su red interna o desde Internet. Los servidores locales no forman parte de estos escenarios, por lo que todas las conferencias o medios relacionados con RTC fluirán a la nube y el servidor perimetral de los usuarios en línea también estará en la nube.

 **Resumen de los flujos de llamadas para Skype Empresarial Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos en su red.  <br/> |ExpressRoute  <br/> |Local  <br/> |[Llamada punto a punto para usuarios de Microsoft 365 u Office 365 desde la red de clientes](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Llamada de punto a punto  <br/> |Dos clientes, uno en su red (interno) y el otro cliente en Internet (externo).  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet para Microsoft 365 u servidor perimetral de Office 365.  <br/> |[Llamada punto a punto para usuarios de Microsoft 365 u Office 365 desde la red de clientes](call-flow-using-expressroute.md#bk_Figure2) <br/> |Asume que el firewall bloquea las conexiones directas entre clientes, que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la del servidor de conferencias para llamadas de conferencia.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, en su red (interno) y el usuario en línea en la red de la organización federada (federado).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la de un servidor de conferencias para la llamada de conferencia.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente  <br/> |Cliente en su red y servidor de conferencias en la nube.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a una llamada de conferencia por usuario en Internet  <br/> |El cliente está en Internet y el servidor de conferencias en la nube.  <br/> |Internet  <br/> |Internet  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a una conferencia hospedada por el servidor local de otra empresa  <br/> |El cliente en su red y el servidor de conferencias en el centro de datos de terceros.  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Dado que el servidor de conferencias que hospeda la conferencia está en una red local de otro cliente, ningún dato pasará por la nube de Microsoft.  <br/> |
|Llamada RTC  <br/> |Cliente en servidores de red de cliente y sistema telefónico en la nube  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Llamada RTC  <br/> |Cliente en internet y servidores del sistema telefónico en la nube  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Los medios y la señalización fluirán al centro de datos de Microsoft 365 u Office 365. Puesto que el punto de conexión del cliente está en Internet, todos los datos fluirán al centro de datos de Microsoft a través de Internet (incluso si se necesita un servidor perimetral en línea para la conectividad).  <br/> |

> [!NOTE]
> ExpressRoute se usará en la ruta de acceso multimedia de un usuario ubicado en la red corporativa a un servidor perimetral en línea, pero no se usará si se usa el servidor perimetral para la implementación local de otro cliente.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flujos de llamadas para la implementación híbrida de Skype Empresarial

Los flujos de llamadas híbridos se aplican cuando tiene una implementación de Skype Empresarial que incluye al menos algunos usuarios que están hospedados en local. Los flujos de llamadas de esta sección incluyen conferencias locales y llamadas de punto a punto o RTC con al menos un usuario local.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, en la red del cliente y alojados en local.  <br/> |Local  <br/> |Local  <br/> |[Llamada punto a punto para usuarios de Microsoft 365 u Office 365 desde la red de clientes](call-flow-using-expressroute.md#bk_Figure2) <br/> |Dado que los usuarios se encuentran en el entorno local, la señalización fluye localmente al centro de datos local en lugar de a la nube.  <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos conectados desde la red del cliente. Uno está alojado en línea y el otro en local.  <br/> |Usuario en línea: ExpressRoute  <br/> Usuario local: local  <br/> |Local  <br/> |[Llamada punto a punto para usuarios de Microsoft 365 u Office 365 desde la red de clientes](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo el usuario conectado en línea envía tráfico de señalización a la nube.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, uno local en la red del cliente (interno) y un usuario en línea en la red de la organización federada (federado).  <br/> |Usuario interno: local  <br/> Usuario federado: ExpressRoute  <br/> |Internet o ExpressRoute (depende de si se usa el servidor en línea o perimetral local)  <br/> |Usuario en línea de su red que se une [a](call-flow-using-expressroute.md#bk_Figure3) una conferencia hospedada en línea y parte del servidor perimetral local con conferencias hospedadas en [Microsoft 365 u Office 365](call-flow-using-expressroute.md#bk_Figure5) (para tráfico multimedia). <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. La negociación de ICE ofrecerá tanto servidores en línea (por el usuario en línea) como servidores perimetrales en local (por el usuario local) para la conectividad.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente (conferencia programada por el usuario en línea)  <br/> |Usuario local en su red y servidor de conferencias en la nube.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |El organizador de la reunión define los recursos del servidor para las llamadas de conferencia. En este caso, lo programó un usuario en línea, por lo que los recursos están en la nube.  <br/> |
|Llamada RTC  <br/> |Usuario en local en su red y centro de datos Skype Empresarial local.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Similar escenario para usar Cloud Connector Edition, con la diferencia de que el usuario está alojado en local, de modo que la señalización permanece dentro de la red.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flujos de llamadas de Skype Empresarial con Cloud Connector

Todos los usuarios que se conectarán a Cloud Connector Edition están alojados en línea. Esto significa que las conferencias serán en línea y que la señalización sigue los mismos patrones que los usuarios en línea. Para otros escenarios distintos de las llamadas RTC, el flujo de llamadas será exactamente el mismo que el descrito anteriormente para Skype Empresarial Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada RTC  <br/> |Usuario en línea en su red con Cloud Connector Edition.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Llamada RTC  <br/> |Usuario en línea que usa Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinación de servidor perimetral local con conferencias hospedadas de [Microsoft 365 u Office 365](call-flow-using-expressroute.md#bk_Figure5) y llamadas RTC con [Skype Empresarial Cloud Connector Edition.](call-flow-using-expressroute.md#bk_Figure6)  <br/> |Los usuarios de Internet se conectarán a través del servidor perimetral que se incluye en Cloud Connector y Cloud Connector se conectará a la red RTC.  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Documentación de ExpressRoute](/azure/expressroute/)