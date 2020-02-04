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
ms.openlocfilehash: 3c728dab868177aab07c6fe618fba3a8c357eaa2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706675"
---
# <a name="call-flow-using-expressroute"></a>Flujo de llamadas con ExpressRoute

[] Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.

Si implementa Skype empresarial online como parte de Office 365, entorno híbrido de Skype empresarial Server o Skype Connector para la empresa, tendrá que comprender la comunicación entre el cliente y los servidores de Skype empresarial y el flujo de llamadas para puede planificar, implementar, operar y solucionar problemas de los servicios de Skype empresarial en forma eficaz.

## <a name="call-flow-overview"></a>Información general sobre el flujo de llamadas

Este documento describe los segmentos de red que pueden transmitir datos para estos flujos de llamada y le ayudan a comprender qué tráfico permanecerá local en su red en comparación con el tráfico que viaja a través de Internet o a través de ExpressRoute. Saber qué tráfico usa ExpressRoute le ayudará a evaluar los beneficios que su compañía recibirá mediante ExpressRoute, así como ayudarle a comprender la guía de implementación de ExpressRoute para validar y solucionar problemas de su implementación una vez que haya decidido para usar ExpressRoute.

Hay diferentes factores que puede controlar y que pueden repercutir en los flujos de llamada que se describen aquí; entre ellos, por ejemplo, las reglas de firewall, la configuración NAT, los servidores proxy y la configuración del enrutador. En este documento se da por hecho que se ha aplicado la configuración recomendada. Esta configuración recomendada se describe en:

- [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL de Office 365 e intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Información general de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

La configuración y las configuraciones que no han seguido los pasos de configuración que se encuentran en la documentación anterior pueden tener flujos de llamada diferentes a los que hemos documentado aquí. Además, puede encontrarse con problemas de configuración como rutas de red asimétricas y no óptimas, o protocolos de transporte no óptimos. El enrutamiento asimétrico es una consideración importante siempre que se trata de ExpressRoute, porque ExpressRoute introduce una segunda ruta a Office 365, lo que crea la posibilidad de que una ruta use Internet en una dirección y otra ruta que use ExpressRoute en la otra dirección. Esto puede dar lugar a que el tráfico se bloquee en la dirección de devolución si recorre un firewall con estado.

## <a name="network-segments-and-traffic-types"></a>Segmentos de red y tipos de tráfico

### <a name="network-segments"></a>Segmentos de red

Antes de que podamos explicar el flujo de llamada, necesitamos definir algunos términos que le ayudarán a comprender los segmentos de red y los tipos de soporte que se utilizan en Skype Empresarial Online.

Los diagramas de flujo de llamadas a continuación muestran cuatro segmentos de red diferentes, cada uno de los cuales son administrados por diferentes organizaciones (la red interna, el proveedor de servicios de red y sus socios de emparejamiento de Internet y Microsoft) que tienen diferentes características de rendimiento. Para obtener instrucciones sobre los objetivos de rendimiento de red, consulte [calidad de medios y rendimiento de conectividad de red en Skype empresarial online](media-quality-and-network-connectivity-performance.md).

A continuación puede ver cada segmento de red del que hablaremos.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Tu red** Este es el segmento de red que forma parte de su red general que usted controla y administra. Esto incluye todas las conexiones de las oficinas, ya sean cableadas o inalámbricas, entre los edificios de oficina, los centros de trabajo locales y las conexiones a proveedores de Internet o socios de ExpressRoute.

Por lo general, el borde de la red tiene una o más DMZ con firewalls o servidores proxy, que aplican las directivas de seguridad de su organización y que solo permiten un determinado tráfico de red que haya configurado y configurado. Como usted administra esta red, tiene control directo sobre el rendimiento de su red y se recomienda encarecidamente que complete las evaluaciones de red para validar el rendimiento dentro de los sitios de su red y de su red con Skype empresarial online. Para ver los requisitos de rendimiento, consulte [calidad de medios y rendimiento de conectividad de red en Skype empresarial online](media-quality-and-network-connectivity-performance.md).

 **Internet** Este es el segmento de red que forma parte de su red general que usarán los usuarios que se conectan a Skype empresarial online desde fuera de la red, y se usa para todas las conexiones cuando ExpressRoute no está configurado. Internet y todas sus conexiones no son administradas por usted ni por Microsoft, por lo que no se pueden determinar las rutas de rendimiento y enrutamiento, y esto tendrá un mayor impacto en el flujo general de llamadas y la calidad.

 **ExpressRoute** Este es el segmento de red que forma parte de su red general y que le proporcionará una conexión privada y dedicada a la red de Microsoft. Esta es la opción recomendada para conectar su red a Microsoft Network (centros de información de Office 365) para todas las cargas de trabajo que dependen de la velocidad y el rendimiento de la red, como la comunicación en tiempo real de Skype empresarial online. Las conexiones de ExpressRoute se realizan entre su red y la red de Microsoft use [proveedores de conectividad de expressroute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para proporcionar una red privada y administrada, con 99,9% de tiempo de actividad y compatibilidad con calidad de servicio (QoS) que puede mejorar el rendimiento de los medios en tiempo real durante períodos de congestión de la red.

 **Red de Microsoft** Este es el segmento de red que forma parte de su red general compatible con los servicios de Office 365. Esto incluye toda la comunicación entre los servidores de Internet para Office 365. Esto puede incluir tráfico que atraviesa el backbone de red de Microsoft y se transmite entre regiones geográficas.

### <a name="types-of-traffic"></a>Tipos de tráfico

El tráfico de red de Skype empresarial online es de dos categorías amplias, que se muestran como rutas diferentes en el flujo de llamadas:

 Los **medios en tiempo real** son datos encapsulados en RTP (Protocolo de transporte en tiempo real) y admiten cargas de trabajo de audio, vídeo, uso compartido de aplicaciones y transferencia de archivos. En general, el tráfico multimedia es sensible a la latencia, por lo que le gustaría que este tráfico tomara la ruta más directa posible y usar UDP como protocolo de la capa de transporte porque el uso de TCP genera una mayor latencia.

 La **señalización** es el vínculo de comunicación entre el cliente y el servidor, u otros clientes que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y enviar mensajes instantáneos. La mayoría de las señales de tráfico usan el protocolo SIP, aunque algunos clientes usan interfaces de REST basadas en HTTP. Para simplificarlo, estamos considerando una variedad de señales que pueden viajar a través de conexiones HTTP y HTTPS o TLS en este tipo de tráfico. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede provocar interrupciones de servicio o tiempos de espera de llamadas si la latencia entre los puntos de conexión excede varios segundos.

Los destinos de este tráfico se encuentran en las [direcciones URL e intervalos de direcciones IP de office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para todos los servicios de Office 365. Para cada dirección URL, indica si esa parte del tráfico puede atravesar ExpressRoute para Office 365. Para los diagramas que muestran que Internet aún se usa para algún tráfico cuando ExpressRoute está habilitado, consulte [Azure ExpressRoute para Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). Es importante comprender que incluso las direcciones URL que se muestran como enrutables a través de ExpressRoute también se pueden enrutar a través de Internet. Esto significa que, en algunos escenarios, la determinación de si se usará Internet o ExpressRoute depende de la ubicación del cliente y de la configuración de los servidores proxy y los firewalls. También es importante comprender que, como no todas las direcciones URL asociadas con Office 365 pueden usar ExpressRoute, se necesita una conexión a Internet aunque compre ExpressRoute desde un asociado de ExpressRoute.

El tráfico que solo puede enviarse a través de Internet incluye dependencias de Internet comunes, como las listas de revocación de certificados (CRL), las búsquedas DNS y la resolución de nombres, las direcciones URL de los servicios compartidos de Office 365, como el centro de administración de Microsoft 365 y algunas características de comunicación no en tiempo real de Skype empresarial online, como telemetría y Federación, para la interoperabilidad con consumidores de Skype, así Para ayudarle a tomar decisiones, consulte [enrutamiento con ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para obtener más información cuando planee el enrutamiento de red.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principios para los flujos de llamadas con Skype Empresarial

Antes de entrar en los detalles de los escenarios concretos de los flujos de llamada, hay seis principios generales que le ayudarán a comprender los flujos de llamada para Skype Empresarial.

1. Una conferencia de Skype empresarial se hospeda en la misma región en la que se ha alojado el organizador de la Conferencia. Esto se encuentra en la nube de Office 365 si el organizador es un usuario en línea o en un centro de recursos local si el organizador de la reunión es un usuario local.

2. El tráfico multimedia enviado desde un cliente a una conferencia hospedada siempre va al servidor donde se hospeda la Conferencia. Puede ser un servidor local en un centro de información que administre o un servidor en línea en la nube de Office 365. Sin embargo, siempre se usa un servidor perimetral para el flujo de medios en conferencias en línea.

3. El tráfico multimedia de las llamadas de punto a punto toma la ruta más directa que esté disponible. La ruta preferida va directa al equipo remoto (cliente), pero si esa ruta no está disponible porque el firewall está bloqueando el tráfico o existe algún otro problema de este tipo, entonces uno o varios servidores perimetrales retransmitirán el tráfico.

4. El tráfico de señalización siempre se dirige al servidor en el que se aloja el usuario, ya sea en línea o local. Se utilizará un servidor perimetral si el servidor front-end no se puede conectar directamente.

5. Los usuarios que se unen a una conferencia hospedada en línea siempre usarán un servidor perimetral (o dos si es necesario por las configuraciones del firewall para cliente).

6. Los usuarios que se unen a una conferencia hospedada en local no utilizarán, por lo general, un servidor perimetral si se conectan desde dentro de la misma red que contiene la implementación local, y utilizarán uno o dos servidores perimetrales cuando se conectan desde fuera de la red.

Para obtener más información sobre la ruta de medios seleccionada, consulte [conectividad de medios con el borde](https://aka.ms/AVEdge). Aunque este vídeo se recierne a Lync Server 2013, los principios y protocolos siguen aplicándose a Skype empresarial.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Los flujos de llamada de Skype Empresarial con ExpressRoute

Ahora que ya conoce los cuatro segmentos de red y algunos principios generales de GUID para los flujos de llamadas de Skype empresarial, puede usar esta información para ayudarle a entender qué tráfico de Skype empresarial atravesará una ExpressRoute segmento de red.

En general, el tráfico de red cruzará la conexión de ExpressRoute si un punto de conexión está en su red y el otro está en el centro de datos de Office 365. Esto incluirá el tráfico de señalización entre el cliente y el servidor, el tráfico multimedia usado durante las llamadas de conferencia o las llamadas de punto a punto que usan un servidor perimetral en línea.

El tráfico no atraviesa la conexión de ExpressRoute si ambos puntos de conexión se pueden comunicar directamente a través de Internet o si se encuentran en su red. Esto incluirá los medios para las llamadas de punto a punto, el tráfico de Internet destinado a una implementación local o el tráfico entre los servidores perimetrales de Internet y Office 365. Un ejemplo de esto sería un usuario que se une a una conferencia en línea desde un hotel.

## <a name="basic-skype-for-business-call-flow"></a>Flujo de llamadas básico de Skype Empresarial

Para ayudarle a aplicar los principios generales de los flujos de llamada de Skype Empresarial que se han descrito anteriormente, la próxima sección de este artículo contiene diagramas como referencia. No se trata de una lista exhaustiva de todos los posibles flujos de llamadas, sino de un intento de ayudarle a aplicar los principios detallados anteriormente. Además, los escenarios de los diagramas se han seleccionado para cubrir los tipos de implementación más comunes; entre ellos, en línea, híbrida, conector de nube y, en un caso especial, la Difusión de reunión de Skype.

> [!NOTE]
> Un subconjunto de tráfico usado por Skype empresarial no se encuentra enrutable a través de ExpressRoute y siempre tomará una ruta de acceso a Internet. Consulte las [direcciones URL y los intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar las direcciones URL que pueden verse afectadas.

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Llamada de punto a punto para usuarios de Office 365 desde la red del cliente
<a name="bk_Figure2"> </a>

En las llamadas de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. No obstante, el tráfico de señalización va a un centro de datos de Office 365 en el que está alojado el usuario en línea. Puesto que ambos usuarios están en la misma WAN y nada impide que los clientes se comuniquen directamente, los elementos multimedia fluyen directamente entre ellos. El tráfico de señalización, en el caso de ambos usuarios, atraviesa la conexión de ExpressRoute que se destina al centro de datos de cada organización. Para mostrarle el flujo de llamadas en este escenario, vea esto.

 **Flujo de llamadas de punto a punto**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuario en línea de su red que se une a una conferencia hospedada en línea
<a name="bk_Figure3"> </a>

En el ejemplo de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. Sin embargo, para una conferencia en línea, el destino se encuentra en la nube de Office 365. Esto significa que el tráfico multimedia de todos los usuarios que se unan a la Conferencia desde dentro de la red atravesará la conexión de ExpressRoute y el tráfico de señalización se desplazará a la nube de Office 365. En el siguiente gráfico se muestra que tanto los medios como la señalización atravesarán la conexión de ExpressRoute para un usuario de su red y que recorrerán directamente a Internet los usuarios que están conectados a Internet desde fuera de la red, por ejemplo, de un café tienda o Hotel.

Recuerde que la ubicación de una conferencia está definida por el organizador de la reunión y no por los participantes. Esto significa que si la reunión ha sido programada por un cliente local, el tráfico multimedia no fluye a la nube de Office 365 sobre ExpressRoute, sino que, en su lugar, atravesará Internet hasta el centro de proceso de reuniones local del organizador de la reunión.

El destino de los elementos multimedia en el caso de las conferencias en línea será un centro de datos en la nube de Office 365, pero este se puede encontrar en una región geográfica distinta a la de los usuarios que se están uniendo a la conferencia. Esta situación se da de una de estas dos formas:

- Si el organizador de la reunión pertenece a una empresa distinta a la de los asistentes o participantes, y la organización del organizador está hospedada en una ubicación geográfica, o país o región, distinta.

- Si un usuario se une desde un país o región distinto al de la organización de la empresa, ya sea porque es una empresa multinacional o porque el usuario esté viajando.

La buena noticia de usar ExpressRoute en este escenario es que con el complemento ExpressRoute Premium, los datos que siguen a la ruta de acceso de ExpressRoute pasarán automáticamente por la red troncal de Microsoft independientemente de la región geográfica del organizador de la reunión. Centro de recursos de la organización.

 **Flujo de llamadas de un usuario en línea con una reunión en línea**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Unirse a una conferencia hospedada por un usuario local en una implementación híbrida
<a name="bk_Figure3"> </a>

Recuerde que los servidores de conferencia que admiten conferencias hospedadas dependen de dónde se aloje el organizador de la reunión. En este escenario, los medios para todos los usuarios que se unen a una conferencia programada por un usuario local en una implementación híbrida fluyen a un centro de proceso de información local. La señalización de usuarios alojados en línea se establecerá a través de su organización en la nube de Office 365, mientras que los medios intentarán una conexión directa. En este escenario, puesto que los dos usuarios se conectan desde la red, es posible una conexión de medios directos, de modo que ExpressRoute solo se usa para la señalización de tráfico para el usuario alojado en línea. Si un usuario alojado en línea se conecta a través de Internet, los medios podrían atravesar ExpressRoute si se usa un servidor perimetral en línea para conectarse.

 **Flujo de llamadas de una conferencia organizada por usuario híbrido**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Servidor perimetral local con conferencias hospedadas en Office 365
<a name="bk_Figure5"> </a>

Cuando un usuario híbrido se une a una conferencia hospedada en línea, sabemos que la señalización y los medios se destinarán a la nube de Office 365, y como el usuario se une desde Internet, normalmente se tomará una ruta de acceso directa a Internet. Sin embargo, en algunos casos, como por restricciones de firewall, no está disponible una ruta directa a través de Internet. En este caso, un servidor perimetral local puede retransmitir el tráfico de medios, lo que hace que el tráfico multimedia vuelva a su red local antes de atravesar el circuito de ExpressRoute a la nube de Office 365.

 **Usuario local que se une a una llamada de conferencia en línea con un servidor perimetral local**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Llamada RTC con Skype Empresarial Cloud Connector Edition
<a name="bk_Figure6"> </a>

El uso de la edición del conector en la [nube para Skype empresarial online](https://aka.ms/CloudConnectorInstaller) proporciona conectividad RTC con recursos locales, como un tronco de SIP, una puerta de enlace PSTN o un dispositivo de hardware mínimo para integrarse con Skype empresarial. Con Cloud Connector Edition, los usuarios están alojados en línea y actúan como usuarios en línea normales cuando no implican planes de llamadas. La señalización de escenarios de RTC viajará entre el cliente y la nube a través de una conexión de ExpressRoute, si está disponible, y el tráfico multimedia permanece dentro de la WAN. En este caso, la señalización se convierte en la nube de Office 365 y finaliza en el conector de nube.

 **Llamada RTC a través del sistema telefónico en Office 365 y el conector de nube**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Difusión de reunión de Skype con usuarios que se unen desde la red del cliente
<a name="bk_Figure6"> </a>

Difusión de reunión de Skype es un caso de uso especial, que consiste en una reunión de dos partes con cada parte que tiene perfiles de transporte de red diferentes. La primera parte, y la más importante desde un punto de vista de rendimiento de red, es la reunión interna. Esta es la parte en tiempo real de la reunión que incluye uno o varios puntos de conexión cliente que se conectan al servidor de conferencia en la nube de Office 365. Los datos que se transmiten a través de esta parte de la reunión son exactamente iguales al ejemplo anterior, con una reunión de usuario de Office 365 y una conferencia en línea.

Lo que hace que la difusión de reunión de Skype sea única es que la reunión se distribuye a un gran número de asistentes que usan un servicio de transmisión por secuencias de difusión. Este servicio de transmisión por secuencias de difusión no se encuentra enrutado sobre ExpressRoute, sino que usa Internet con la compatibilidad opcional de los servicios de red de entrega de contenido (CDN). Es útil reconocer que la transmisión por secuencias de difusión es un flujo de medios unidireccionales porque los asistentes escuchan pero no hablan y admiten el almacenamiento en búfer, por lo que es mucho menos sensible a los problemas de rendimiento de la red, como latencia, pérdida de paquetes y vibración. En lugar de optimizar el tráfico de difusión para estos problemas, está optimizado para la utilización del ancho de banda porque es posible que haya una gran cantidad de asistentes recibiendo los medios transmitidos.

 **Difusión de reunión de Skype con usuarios desde la red del cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Patrones de flujos de llamadas según el tipo de implementación

Con los ejemplos de flujo de llamadas más arriba mencionados y una comprensión de los principios generales que controlan los patrones de tráfico, las tablas siguientes proporcionan un resumen de los patrones de tráfico para una gran combinación de escenarios de implementación y uso. Estas tablas no capturan todas las combinaciones posibles de los flujos de llamadas, pero le ayudan a comprender aún más los principios generales del flujo de llamadas.

Los datos se transmiten y aparecen como locales para la organización; no deja la red del cliente, Internet o ExpressRoute. Los patrones que se enumeran a continuación se basan en la configuración de red más común, como firewalls, Federación e Internet, y Supongamos que todas las organizaciones implicadas en flujos de varios participantes o federados tienen ExpressRoute. En la práctica, tener una configuración diferente puede dar lugar a patrones de tráfico diferentes a los que se enumeran a continuación.

### <a name="call-flows-for-skype-for-business-online"></a>Flujos de llamadas para Skype Empresarial Online

Los escenarios de uso de Skype empresarial online implican a los usuarios que están alojados en línea y pueden estar llamando desde la red interna o desde Internet. Los servidores locales no forman parte de estos escenarios, por lo que todos los medios relacionados con la Conferencia o la RTC fluyen a la nube de Office 365 y el servidor perimetral de los usuarios en línea también estará en la nube.

 **Resumen de los flujos de llamadas para Skype Empresarial Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos en su red.  <br/> |ExpressRoute  <br/> |Local  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Llamada de punto a punto  <br/> |Dos clientes, uno en su red (interno) y el otro cliente en Internet (externo).  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: De Internet al servidor perimetral de Office 365.  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Supone que Firewall bloquea las conexiones directas entre clientes, que requieren un servidor perimetral en línea. El tráfico de usuarios internos a servidores perimetrales en línea sigue una ruta similar a la del servidor de conferencias para la llamada de conferencia.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, en su red (interno) y el usuario en línea en la red de la organización federada (federado).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la de un servidor de conferencias para la llamada de conferencia.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente  <br/> |El cliente en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a la llamada en conferencia por usuario en Internet  <br/> |Cliente está en Internet y en el servidor de conferencias en la nube de Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Unirse a una conferencia hospedada por el servidor local de otra empresa  <br/> |El cliente en su red y el servidor de conferencias en el centro de datos de terceros.  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Dado que el servidor de conferencias que hospeda la conferencia está en una red local de otro cliente, ningún dato pasará por la nube de Microsoft.  <br/> |
|Llamada RTC  <br/> |Cliente en servidores de red y de sistema telefónico del cliente en la nube de Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Llamada RTC  <br/> |Cliente en los servidores de sistema de Internet y teléfono en la nube de Office 365  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Los medios y la señalización fluyen al centro de proceso de Office 365. Puesto que el punto de conexión del cliente está en Internet, todos los datos se transmiten al centro de datos de Microsoft a través de Internet (incluso si se necesita un servidor perimetral en línea para la conectividad).  <br/> |

> [!NOTE]
> ExpressRoute se usará en la ruta multimedia de un usuario que se encuentra en la red corporativa a un servidor perimetral en línea, pero no se usará si se usa el servidor perimetral para la implementación local de otro cliente.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flujos de llamadas para la implementación híbrida de Skype Empresarial

Los flujos de llamadas híbridas se aplican cuando tiene una implementación de Skype empresarial que incluye al menos algunos usuarios alojados en el local. Los flujos de llamadas de esta sección incluyen tanto conferencias locales como llamadas RTC o de par a par con al menos un usuario local.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, en la red del cliente y alojados en local.  <br/> |Local  <br/> |Local  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Como los usuarios se alojan en local, la señalización fluye en local al centro de datos local en lugar de a la nube de Office 365.  <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos conectados desde la red del cliente. Uno está alojado en línea y el otro en local.  <br/> |Usuario en línea: ExpressRoute  <br/> Usuario local: local  <br/> |Local  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde la red del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo el usuario alojado en línea envía tráfico de señalización a la nube de Office 365.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, uno local en la red del cliente (interno) y un usuario en línea en la red de la organización federada (federado).  <br/> |Usuario interno: local  <br/> Usuario federado: ExpressRoute  <br/> |Internet o ExpressRoute (depende de si se usa el servidor en línea o perimetral local)  <br/> |[Usuario en línea de la red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) y parte de un [servidor perimetral local con Office 365 conferencias hospedadas](call-flow-using-expressroute.md#bk_Figure5) (para el tráfico multimedia). <br/> |Supone que un Firewall bloquea las conexiones directas entre clientes, lo que requiere un servidor perimetral en línea. La negociación de ICE ofrecerá tanto los servidores perimetrales en línea (por el usuario en línea) como locales (por el usuario local) para la conectividad.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente (conferencia programada por el usuario en línea)  <br/> |El usuario en local en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](call-flow-using-expressroute.md#bk_Figure3) <br/> |El organizador de la reunión define los recursos de servidor para llamadas en conferencia. En este caso, lo programó un usuario en línea, por lo que los recursos se encuentran en la nube de Office 365.  <br/> |
|Llamada RTC  <br/> |Usuario en local en su red y centro de datos Skype Empresarial local.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Similar escenario para usar Cloud Connector Edition, con la diferencia de que el usuario está alojado en local, de modo que la señalización permanece dentro de la red.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flujos de llamadas de Skype Empresarial con Cloud Connector

Todos los usuarios que se conectarán a Cloud Connector Edition están alojados en línea. Esto significa que las conferencias serán en línea y que la señalización sigue los mismos patrones que los usuarios en línea. Para otros escenarios distintos de las llamadas RTC, el flujo de llamadas será exactamente el mismo que el descrito anteriormente para Skype Empresarial Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada RTC  <br/> |Usuario en línea en su red con Cloud Connector Edition.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Llamada RTC  <br/> |Usuario en línea que usa Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinación de [servidor perimetral local con Office 365 conferencias hospedadas](call-flow-using-expressroute.md#bk_Figure5) y [llamadas RTC con Skype empresarial Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Los usuarios de Internet se conectarán a través del servidor perimetral que se incluye en Cloud Connector y Cloud Connector se conectará a la red RTC.  <br/> |

## <a name="related-topics"></a>Temas relacionados

[Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


