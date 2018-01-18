---
title: Flujo de llamadas con ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente."
ms.openlocfilehash: 757dc1c918a6d7a78cc636fa5269ce8cad334909
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="call-flow-using-expressroute"></a>Flujo de llamadas con ExpressRoute

[] Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.
  
Si va a implementar Skype para los negocios en línea como parte de Office 365, Skype para negocios servidor híbrido o Skype para conector de nube Business Edition, necesitará comprender por lo que la comunicación entre el Skype para servidores y clientes de negocios y el flujo de llamadas efectivamente puede planear, implementar, operar y solucionar su Skype para servicios empresariales en línea. 
  
## <a name="call-flow-overview"></a>Información general sobre el flujo de llamadas

Este documento describe la red en segmentos que pueden llevar los datos de estas llamadas fluyen y le ayuda a comprender qué tráfico permanecerá locales a la red en comparación con el tráfico que viajará a través de Internet o a través de ExpressRoute. Saber qué tráfico utiliza ExpressRoute le ayudará a evaluar los beneficios que su empresa recibirá mediante ExpressRoute, así como ayudarle a que entender la Guía de implementación de ExpressRoute para validar y solucionar problemas de la implementación una vez que haya decidido Para utilizar ExpressRoute.
  
Hay diferentes factores que puede controlar y que pueden repercutir en los flujos de llamada que se describen aquí; entre ellos, por ejemplo, las reglas de firewall, la configuración NAT, los servidores proxy y la configuración del enrutador. En este documento se da por hecho que se ha aplicado la configuración recomendada. Esta configuración recomendada se describe en:
  
- [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Resumen de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)
    
- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)
    
El programa de instalación y las configuraciones que no han seguido los pasos de instalación en la documentación anterior pueden tener flujos de llamada diferentes a los que hemos documentado aquí. Además, puede que tenga problemas de configuración tales como rutas de red asimétrica y no óptimo o protocolos de transporte no es óptimo. Enrutamiento asimétrico obedece una consideración importante cuando interviene ExpressRoute, ExpressRoute presenta una segunda ruta de acceso a Office 365, que crea la posibilidad de una ruta que utiliza Internet en una dirección y otra ruta que utiliza ExpressRoute en la otra dirección. Esto puede resultar en que se bloquean en la dirección de retorno si atraviesan un firewall con estado del tráfico.
  
## <a name="network-segments-and-traffic-types"></a>Segmentos de red y tipos de tráfico

### <a name="network-segments"></a>Segmentos de red

Antes de que podamos explicar el flujo de llamada, necesitamos definir algunos términos que le ayudarán a comprender los segmentos de red y los tipos de soporte que se utilizan en Skype Empresarial Online. 
  
Los diagramas de flujo de llamada siguientes muestran cuatro segmentos de red diferentes, cada uno de los cuales son administrados por diferentes organizaciones (la red interna, su proveedor de servicios de red y sus socios de interconexión de Internet y Microsoft) que tienen diferentes características de rendimiento. Para obtener directrices sobre los objetivos de rendimiento de red, consulte [calidad Media y rendimiento de conectividad de red en Skype para los negocios en línea](media-quality-and-network-connectivity-performance.md).
  
A continuación puede ver cada segmento de red del que hablaremos.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **La red** Éste es el segmento de red que forma parte de la red global que controlar y administrar. Esto incluye todas las conexiones dentro de sus oficinas, ya sea con cables o inalámbrica entre edificios, a los centros de datos locales y las conexiones a proveedores de Internet o asociados de ExpressRoute.
  
Normalmente, el borde de la red tiene una o varias DMZ con servidores de seguridad o servidores proxy, que exigir directivas de seguridad de su organización y que sólo permitir cierto tráfico de red que haya creado y configurado. Porque administrar esta red, tiene un control directo sobre el rendimiento de la red y se recomienda complete las evaluaciones de la red para validar el rendimiento tanto dentro de los sitios de la red y desde la red a Skype para empresas En línea. Para ver los requisitos de rendimiento, vea [calidad Media y rendimiento de conectividad de red en Skype para los negocios en línea](media-quality-and-network-connectivity-performance.md).
  
 **Internet** Éste es el segmento de red que forma parte de la red general que será utilizada por los usuarios que se conexión a Skype por negocios Online desde fuera de la red y se utilizan para todas las conexiones cuando no está configurado ExpressRoute. Internet y todas sus conexiones no están administradas por usted o por Microsoft, por lo que no se puede determinar el rendimiento y rutas y esto tendrá el mayor impacto en el flujo de llamadas y calidad generales.
  
 **ExpressRoute** Éste es el segmento de red que forma parte de la red general que le proporcionará una conexión dedicada y privada a la red de Microsoft. Esta es la opción recomendada para conectar la red a la red de Microsoft (centros de datos de Office 365) para todas las cargas de trabajo que dependen de la velocidad de la red y el rendimiento, como Skype para la comunicación en tiempo real los negocios en línea. ExpressRoute conexiones se realizan entre la red y el uso de red de Microsoft [ExpressRoute proveedores de conectividad](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para proporcionar una red privada y administrada, con un 99,9% de tiempo activo y la compatibilidad con calidad de servicio (QoS) que puede mejorar el rendimiento para multimedia en tiempo real durante los períodos de congestión de la red.
  
 **Red de Microsoft** Éste es el segmento de red que forma parte de la red general que admite servicios de Office 365. Esto incluye todas las comunicaciones entre servidores Online para Office 365. Esto puede incluir el tráfico que atraviesa la red troncal de Microsoft y se transmite entre las regiones geográficas.
  
### <a name="types-of-traffic"></a>Tipos de tráfico

El tráfico de red para Skype para los negocios en línea se divide en dos categorías, que se muestra como trazados independientes en el flujo de llamadas:
  
 **Multimedia en tiempo real** los datos encapsulados en RTP (Protocolo de transporte en tiempo real) y es compatible con audio, vídeo, uso compartido de aplicaciones y cargas de trabajo de transferencia de archivos. En general, tráfico de medios es altamente confidencial, latencia por lo que es conveniente que tomen la ruta más directa posible este tráfico y utilizar UDP como protocolo de capa de transporte ya utilizando TCP presenta una latencia mayor.
  
 **Señalización** es el vínculo de comunicación entre el cliente y el servidor, u otros clientes que se utilizan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y entregar IMs. Mayor cantidad de tráfico de señalización utiliza el protocolo SIP, aunque algunos clientes utilizan interfaces de resto basado en HTTP. Para facilitar el proceso, estamos considerando una gran variedad de señalización que pueden viajar a través de conexiones HTTP y HTTPS o TLS en este tipo de tráfico. Es importante entender que este tráfico es mucho menos sensible a la latencia, pero pueden causar interrupciones del servicio o llamar a los tiempos de espera si la latencia entre los extremos superior varios segundos.
  
Los destinos de este tráfico se encuentran en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para todos los servicios de Office 365. Para cada URL, indica si esa parte del tráfico puede atravesar la ExpressRoute para Office 365. Los diagramas que muestran que todavía se utiliza Internet para cierto tráfico cuando ExpressRoute está habilitado, consulte [ExpressRoute de Azure para Office 365](http://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Es importante comprender que incluso las direcciones URL que se muestran como se pueden enrutar a través de ExpressRoute también son enrutables en Internet. Esto significa que en algunos escenarios, la determinación sobre si se utilizará la Internet o ExpressRoute depende de la ubicación del cliente y la configuración de seguridad y servidores proxy. También es importante comprender que puesto que no todas las direcciones URL asociadas con Office 365 son capaces de utilizar ExpressRoute, se requiere una conexión a Internet incluso si compra ExpressRoute de un socio de ExpressRoute. 
  
Tráfico que sólo pueden enviarse a través de Internet incluye las dependencias comunes de Internet, como listas de revocación de certificados (CRL), búsquedas DNS y resolución de nombres, las direcciones URL para los servicios compartidos de Office 365, como para el centro de administración de Office 365 y algunos no son en tiempo real características de comunicación de Skype para los negocios en línea, como telemetría y federación para la interoperabilidad con el consumidor de Skype, como medio de bien que se transmite para difundir reunión de Skype. Para ayudarle a tomar decisiones, vea [enrutamiento con ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para obtener más información sobre cuando planee la ruta de red.
  
## <a name="principles-for-call-flows-with-skype-for-business"></a>Principios para los flujos de llamadas con Skype Empresarial

Antes de entrar en los detalles de los escenarios concretos de los flujos de llamada, hay seis principios generales que le ayudarán a comprender los flujos de llamada para Skype Empresarial.
  
1. Un Skype para conferencia de negocios se hospeda en la misma región donde está alojado el organizador de la conferencia. Esto es en la nube Office 365 si el organizador es un usuario en línea o en un centro de datos local si el organizador de la reunión es un usuario local.
    
2. Tráfico multimedia enviado desde un cliente a una conferencia alojada siempre va al servidor donde se aloja la conferencia. Esto puede ser un servidor local dentro de un centro de datos que administra o un servidor en línea dentro de la nube de Office 365. Sin embargo, siempre se utiliza un servidor perimetral de flujo de medios de conferencias en línea.
    
3. El tráfico multimedia de las llamadas de punto a punto toma la ruta más directa que esté disponible. La ruta preferida va directa al equipo remoto (cliente), pero si esa ruta no está disponible porque el firewall está bloqueando el tráfico o existe algún otro problema de este tipo, entonces uno o varios servidores perimetrales retransmitirán el tráfico.
    
4. El tráfico de señalización siempre se dirige al servidor en el que se aloja el usuario, ya sea en línea o local. Se utilizará un servidor perimetral si el servidor front-end no se puede conectar directamente.
    
5. Los usuarios que se unen a una conferencia hospedada en línea siempre usarán un servidor perimetral (o dos si es necesario por las configuraciones del firewall para cliente).
    
6. Los usuarios que se unen a una conferencia hospedada en local no utilizarán, por lo general, un servidor perimetral si se conectan desde dentro de la misma red que contiene la implementación local, y utilizarán uno o dos servidores perimetrales cuando se conectan desde fuera de la red. 
    
Para obtener más información acerca de los detalles en la ruta de acceso de medios que se ha elegido, vea [HIELO - borde conectividad de medios](https://aka.ms/AVEdge). Aunque este vídeo es acerca de Lync Server 2013, los principios y protocolos se siguen aplican a Skype para el negocio.
  
## <a name="skype-for-business-call-flows-with-expressroute"></a>Los flujos de llamada de Skype Empresarial con ExpressRoute

Ahora que tiene una comprensión de los cuatro segmentos de red diferentes y algunos principios rectores de Skype para flujos de llamada de negocios, puede utilizar que información para ayudarle a comprender qué Skype para el tráfico de negocios pasarán por un ExpressRoute segmento de red.
  
En general, el tráfico de red cruzará la conexión de ExpressRoute si un punto de conexión está en su red y el otro está en el centro de datos de Office 365. Esto incluirá el tráfico de señalización entre el cliente y el servidor, el tráfico multimedia usado durante las llamadas de conferencia o las llamadas de punto a punto que usan un servidor perimetral en línea.
  
Tráfico no recorren la conexión ExpressRoute si los dos puntos finales son capaces de comunicarse directamente a través de internet o se encuentran dentro de la red. Esto incluirá medios para todo el tráfico entre Internet y los servidores perimetrales de Office 365, el tráfico de Internet destinado a una implementación local o llamadas de punto a punto. Un ejemplo de esto sería un usuario unirse a una conferencia en línea de un hotel.
  
## <a name="basic-skype-for-business-call-flow"></a>Flujo de llamadas básico de Skype Empresarial

Para ayudarle a aplicar los principios generales de los flujos de llamada de Skype Empresarial que se han descrito anteriormente, la próxima sección de este artículo contiene diagramas como referencia. No se trata de una lista exhaustiva de todos los posibles flujos de llamadas, sino de un intento de ayudarle a aplicar los principios detallados anteriormente. Además, los escenarios de los diagramas se han seleccionado para cubrir los tipos de implementación más comunes; entre ellos, en línea, híbrida, conector de nube y, en un caso especial, la Difusión de reunión de Skype.
  
> [!NOTE]
> Un subconjunto de tráfico que utiliza Skype para empresas no se pueden enrutar a través de ExpressRoute y siempre tendrá una ruta de acceso de Internet. Consulte las [direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar las direcciones URL que pueden verse afectadas.
  
### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Llamada Peer-to-peer para usuarios de Office 365 desde dentro de la red del cliente
<a name="bk_Figure2"> </a>

En las llamadas de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. No obstante, el tráfico de señalización va a un centro de datos de Office 365 en el que está alojado el usuario en línea. Puesto que ambos usuarios están en la misma WAN y nada impide que los clientes se comuniquen directamente, los elementos multimedia fluyen directamente entre ellos. El tráfico de señalización, en el caso de ambos usuarios, atraviesa la conexión de ExpressRoute que se destina al centro de datos de cada organización. Para mostrarle el flujo de llamadas en este escenario, vea esto.
  
 **Flujo de llamadas de punto a punto**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuario en línea de su red que se une a una conferencia hospedada en línea
<a name="bk_Figure3"> </a>

En el ejemplo de peer-to-peer, tráfico de medios siempre toma la ruta más directa a su destino. Sin embargo, para una conferencia en línea, el destino está en la nube de Office 365. Esto significa que el tráfico de medios para todos los usuarios unirse a la conferencia desde dentro de la red pasarán por la conexión de ExpressRoute y se transporta el tráfico de señalización a la nube de Office 365. El siguiente gráfico muestra que los medios de comunicación y señalización pasarán por la conexión de ExpressRoute para un usuario dentro de la red y directamente pasarán por Internet para los usuarios que se conectan a Internet desde fuera de la red, como desde un café taller o un hotel.
  
Recuerde que la ubicación de una conferencia es definida por el organizador de la reunión y no por los participantes. Esto significa que si la reunión se programó un cliente local, el tráfico de medios no desborde a la nube de Office 365 ExpressRoute, pero en su lugar podría pasar por Internet en el centro de datos local del organizador de la reunión.
  
El destino de los elementos multimedia en el caso de las conferencias en línea será un centro de datos en la nube de Office 365, pero este se puede encontrar en una región geográfica distinta a la de los usuarios que se están uniendo a la conferencia. Esta situación se da de una de estas dos formas:
  
- Si el organizador de la reunión pertenece a una empresa distinta a la de los asistentes o participantes, y la organización del organizador está hospedada en una ubicación geográfica, o país o región, distinta.
    
- Si un usuario se une desde un país o región distinto al de la organización de la empresa, ya sea porque es una empresa multinacional o porque el usuario esté viajando.
    
La buena noticia sobre el uso de ExpressRoute en este escenario es que con el complemento de la prima de ExpressRoute, datos que sigue la ruta de acceso ExpressRoute pasará automáticamente a través de la red troncal de Microsoft sin tener en cuenta la región geográfica del organizador de la reunión Centro de datos de la organización.
  
 **Flujo de llamadas de un usuario en línea con una reunión en línea**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Unirse a una conferencia hospedada por un usuario local en una implementación híbrida
<a name="bk_Figure3"> </a>

Recuerde que los servidores de conferencias que admiten conferencias con host están determinados por donde está alojado el organizador de la reunión. En este escenario, los medios de comunicación para todos los usuarios unirse a una conferencia programada por un usuario local en una implementación híbrida fluirá a un centro de datos local. Señalización para los usuarios alojados en línea se establecerá a través de su organización en la nube de Office 365, mientras que los medios se intentará una conexión directa. En este escenario, puesto que ambos usuarios se están conectando desde dentro de la red, una conexión directa de medios es posible, así que ExpressRoute se utiliza únicamente para la señalización de tráfico del usuario alojados en línea. Si se conecta un usuario alojado en línea desde Internet, los medios podrían atravesar ExpressRoute si se utiliza un servidor perimetral en línea para conectarse.
  
 **Flujo de llamadas de una conferencia organizada por usuario híbrido**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Servidor perimetral local con conferencias hospedadas en Office 365
<a name="bk_Figure5"> </a>

Cuando un usuario se une híbrido en línea alojado conferencia, sabemos que la señalización y los medios se destinará a la nube de Office 365 y, puesto que se va a unir el usuario desde Internet, normalmente una ruta directa de internet debería tomarse. Sin embargo, en algunos casos, por ejemplo, debido a restricciones del firewall, una ruta de acceso directo de Internet no está disponible. En este caso, un servidor perimetral de locales puede retransmitir el tráfico multimedia, que hace que el tráfico de medios volver a la red local antes de atravesar el circuito de ExpressRoute a la nube de Office 365.
  
 **Usuario local que se une a una llamada de conferencia en línea con un servidor perimetral local**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Llamada RTC con Skype Empresarial Cloud Connector Edition
<a name="bk_Figure6"> </a>

Usando el [Skype para Business Edition de conector de nube en línea](https://aka.ms/CloudConnectorInstaller) proporciona conectividad de RTC usando recursos locales como un tronco SIP o puerta de enlace PSTN, o mediante un dispositivo de hardware mínima para integrarse con Skype para el negocio. Con la edición de conector de nube, los usuarios alojados en línea y actúan como normales usuarios en línea cuando no constituyan planes de llamada. Señalización para escenarios PSTN viajarán entre el cliente y la nube a través de una conexión de ExpressRoute si está disponible, y el tráfico de medios se mantiene en la WAN. En este caso, la señalización gira alrededor de la nube de Office 365 y finaliza en el conector de la nube.
  
 **Llamada PSTN a través del sistema de teléfono en Office 365 y conector de nube**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Difusión de reunión de Skype con usuarios que se unen desde la red del cliente
<a name="bk_Figure6"> </a>

Difundir reunión de Skype es un especial de caso de uso, que consiste en una reunión de dos partes cada parte tiene perfiles de transporte de red diferentes. La primera parte y que es más importante, desde un punto de vista de la performance de red, es la reunión interna. Ésta es la parte en tiempo real de la reunión que incluye uno o más extremos de cliente conectar con el servidor de conferencia en la nube de Office 365. Datos transmitidos mediante esta parte de la reunión son exactamente igual que en el ejemplo de arriba, con una combinación de usuario de Office 365 y conferencia en línea. 
  
¿Qué hace Skype reunión difusión única es que la reunión se distribuye a un gran número de asistentes a la conferencia mediante una servicio de transmisión por secuencias de difusión. Este servicio de transmisión por secuencias de difusión no se pueden enrutar a través de ExpressRoute, sino que utiliza Internet con el soporte opcional de servicios Content Delivery Network (CDN). Resulta útil reconocer que la transmisión es un flujo unidireccional media porque los asistentes escuchan pero no hablan y admite el almacenamiento en búfer, por lo que es mucho menos sensible a problemas de rendimiento de red, como la vibración, latencia y pérdida de paquetes. En lugar de optimizar el tráfico de difusión de estos problemas, está optimizado para la utilización de ancho de banda porque es potencialmente un gran número de asistentes recibir la multimedia en secuencias.
  
 **Difusión de reunión de Skype con usuarios desde la red del cliente**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## <a name="call-flow-patterns-by-deployment-type"></a>Patrones de flujos de llamadas según el tipo de implementación

Con la común llamada ejemplos de flujo anteriores y comprender los principios generales que controlan los patrones de tráfico, las siguientes tablas proporcionan un resumen de los patrones de tráfico de una gran combinación de escenarios de implementación y uso. Estas tablas no captura todas las combinaciones posibles de los flujos de llamada, pero deberían ayudarle a entender mejor los principios generales del flujo de llamadas.
  
Los datos se transmiten y se anuncia como local en la organización; no sale de la red de cliente, Internet o ExpressRoute. Los modelos enumerados a continuación se basan en la configuración de red más comunes, como firewalls, federación e Internet y se supone que todas las organizaciones implicadas en varias partes o federados flujos tienen ExpressRoute. En la práctica, tener una configuración diferente podría resultar en patrones de tráfico distintos de los que se enumeran a continuación.
  
### <a name="call-flows-for-skype-for-business-online"></a>Flujos de llamadas para Skype Empresarial Online

Skype para escenarios de uso de negocios en línea implican que los usuarios que están alojados en línea y pueden llamar desde la red interna o en Internet. Servidores locales no forman parte de estos escenarios, por lo que todas las conferencias o medios relacionados PSTN fluirá a la nube de Office 365 y el servidor perimetral también estará en la nube de usuarios en línea.
  
 **Resumen de los flujos de llamadas para Skype Empresarial Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos en su red.  <br/> |ExpressRoute  <br/> |Local  <br/> |[Llamada Peer-to-peer para usuarios de Office 365 desde dentro de la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Llamada de punto a punto  <br/> |Dos clientes, en la red (interna) y el otro cliente en Internet (externo).  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: De Internet al servidor perimetral de Office 365.  <br/> |[Llamada Peer-to-peer para usuarios de Office 365 desde dentro de la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Se supone que firewall bloquea las conexiones directas entre clientes, que requiere un servidor perimetral en línea. Tráfico de usuario interno a servidor perimetral en línea sigue la ruta similar que al servidor de conferencia para la llamada de conferencia.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, en su red (interno) y el usuario en línea en la red de la organización federada (federado).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la de un servidor de conferencias para la llamada de conferencia.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente  <br/> |El cliente en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a llamada de conferencia por usuario en Internet  <br/> |Cliente está en el servidor de Internet y conferencias en nube Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a una conferencia hospedada por el servidor local de otra empresa  <br/> |El cliente en su red y el servidor de conferencias en el centro de datos de terceros.  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Dado que el servidor de conferencias que hospeda la conferencia está en una red local de otro cliente, ningún dato pasará por la nube de Microsoft.  <br/> |
|Llamada RTC  <br/> |Cliente de red de cliente y servidores de sistema de teléfono en la nube de Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Llamada RTC  <br/> |Cliente en los servidores de Internet y sistema de teléfono en la nube de Office 365  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Los medios de comunicación y señalización será de flujo en el centro de datos de Office 365. Puesto que el extremo del cliente está en Internet, todos los datos fluirán al centro de datos de Microsoft a través de Internet (incluso si se necesita un servidor de borde en línea para la conectividad).  <br/> |
   
> [!NOTE]
> ExpressRoute se utiliza en la ruta de acceso de los medios de comunicación de un usuario de la red corporativa a un servidor en línea de borde, pero no se utilizará si se utiliza el servidor perimetral para implementación de local de otro cliente. 
  
### <a name="call-flows-for-skype-for-business-hybrid"></a>Flujos de llamadas para la implementación híbrida de Skype Empresarial

Flujos de llamada híbrido aplican cuando haya un Skype para la implementación de empresa que incluya al menos algunos usuarios que están alojados en locales. El flujo de la llamada en esta sección incluye ambas conferencias locales y peer-to-peer o RTC llama con al menos un usuario alojados en locales.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, en la red del cliente y alojados en local.  <br/> |Local  <br/> |Local  <br/> |[Llamada Peer-to-peer para usuarios de Office 365 desde dentro de la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Como los usuarios se alojan en local, la señalización fluye en local al centro de datos local en lugar de a la nube de Office 365.  <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos conectados desde la red del cliente. Uno está alojado en línea y el otro en local.  <br/> |Usuario en línea: ExpressRoute  <br/> Usuario local: local  <br/> |Local  <br/> |[Llamada Peer-to-peer para usuarios de Office 365 desde dentro de la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo el usuario alojado en línea envía tráfico de señalización a la nube de Office 365.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, uno local en la red del cliente (interno) y un usuario en línea en la red de la organización federada (federado).  <br/> |Usuario interno: local  <br/> Usuario federado: ExpressRoute  <br/> |Internet o ExpressRoute (depende de si se usa el servidor en línea o perimetral local)  <br/> |[Usuario en línea de la red unirse a una conferencia que está alojada en línea](call-flow-using-expressroute.md#bk_Figure3) y la parte de [servidor perimetral de local con Office 365 aloja conferencias](call-flow-using-expressroute.md#bk_Figure5) (para el tráfico de medios). <br/> |Se supone un firewall bloquea las conexiones directas entre clientes, que requiere el servidor perimetral en línea. Negociación de HIELO ofrecerá Online (por el usuario en línea) y servidores de borde locales (por parte del usuario local) para la conectividad.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente (conferencia programada por el usuario en línea)  <br/> |El usuario en local en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |Recursos de servidor para llamadas de conferencia son definidos por el organizador de la reunión. En este caso, se encontraba programado por un usuario en línea, los recursos están en la nube de Office 365.  <br/> |
|Llamada RTC  <br/> |Usuario en local en su red y centro de datos Skype Empresarial local.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Similar escenario para usar Cloud Connector Edition, con la diferencia de que el usuario está alojado en local, de modo que la señalización permanece dentro de la red.  <br/> |
   
### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flujos de llamadas de Skype Empresarial con Cloud Connector

Todos los usuarios que se conectarán a Cloud Connector Edition están alojados en línea. Esto significa que las conferencias serán en línea y que la señalización sigue los mismos patrones que los usuarios en línea. Para otros escenarios distintos de las llamadas RTC, el flujo de llamadas será exactamente el mismo que el descrito anteriormente para Skype Empresarial Online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada RTC  <br/> |Usuario en línea en su red con Cloud Connector Edition.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Llamada RTC  <br/> |Usuario en línea que usa Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinación de [servidor perimetral de local con Office 365 organizado conferencias](call-flow-using-expressroute.md#bk_Figure5) [PSTN llame mediante Skype para conector de nube Business Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Los usuarios de Internet se conectarán a través del servidor perimetral que se incluye en Cloud Connector y Cloud Connector se conectará a la red RTC.  <br/> |
   
## <a name="related-topics"></a>Temas relacionados

[Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
