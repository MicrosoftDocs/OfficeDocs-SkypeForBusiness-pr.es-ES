---
title: "Flujo de llamadas con ExpressRoute"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente."
---

# Flujo de llamadas con ExpressRoute

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](413acb29-ad83-4393-9402-51d88e7561ab.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/413acb29-ad83-4393-9402-51d88e7561ab). 
  
Con este artículo tratamos de explicar el flujo de llamadas básico para Skype Empresarial Online y ExpressRoute, y darle algunos ejemplos detallados de flujos de llamada para que pueda entenderlo y planificarlo correctamente.
  
Si va a implementar Skype empresarial Online como parte de Office 365, Skype empresarial Server Hybrid o Skype para Business Cloud conector Edition, debe comprender la comunicación entre la Skype para cliente de empresa y los servidores y el flujo de llamadas para un modo eficaz puede planear, implementar, operar y solucionar su Skype para servicios en línea de negocio.
  
## Información general sobre el flujo de llamadas

Este documento describe la permanecerán locales a su red en comparación con el tráfico que se van a través de Internet o ExpressRoute segmentos que pueden incluir datos en estos llamada fluye y le ayuda a comprender qué tráfico de red. Saber qué tráfico usa ExpressRoute le ayudará a evaluar los beneficios que recibirá su empresa mediante ExpressRoute, así como ayuda para que comprender la Guía de implementación de ExpressRoute para validar y solucionar problemas de la implementación una vez que haya decidido Para utilizar ExpressRoute.
  
Hay diferentes factores que puede controlar y que pueden repercutir en los flujos de llamada que se describen aquí; entre ellos, por ejemplo, las reglas de firewall, la configuración NAT, los servidores proxy y la configuración del enrutador. En este documento se da por hecho que se ha aplicado la configuración recomendada. Esta configuración recomendada se describe en:
  
- [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx)
    
- [Azure ExpressRoute para Office 365](http://technet.microsoft.com/library/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd%28Office.14%29.aspx)
    
- [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
Configuración y las configuraciones que todavía no lo ha seguido los pasos de configuración que se encuentra en la documentación anterior pueden tener flujos de llamada diferentes que los que nos hemos documentado aquí. Además, puede que tenga problemas de configuración, como las rutas de red asimétricos y no óptimo o protocolos de transporte no óptimo. Enrutamiento asimétricos tiene mucha relevancia siempre que se trate de ExpressRoute, porque ExpressRoute presenta un segundo trazado a Office 365, que se crea la posibilidad de una ruta que usa Internet en una dirección y otra ruta que usa ExpressRoute en la otra dirección. Esto puede provocar que se bloquean en la dirección de remite si lo atraviesa un firewall con estado del tráfico.
  
## Segmentos de red y tipos de tráfico

### Segmentos de red

Antes de que podamos explicar el flujo de llamada, necesitamos definir algunos términos que le ayudarán a comprender los segmentos de red y los tipos de soporte que se utilizan en Skype Empresarial Online. 
  
Los diagramas de flujo de llamada a continuación se muestran cuatro segmentos de red diferentes, cada una de las cuales se administran por diferentes organizaciones (la red interna, su proveedor de servicios de red y sus socios de interconexión de Internet y Microsoft) que tienen diferentes características de rendimiento. Para obtener instrucciones sobre los objetivos de rendimiento de red, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
A continuación puede ver cada segmento de red del que hablaremos.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **Su red** Este es el segmento de red que forma parte de la red general que controlan y administrar. Esto incluye todas las conexiones dentro de la oficina, si cableada o inalámbrica entre edificios, a los centros de datos locales y las conexiones a proveedores de Internet o socios de ExpressRoute.
  
Normalmente, el borde de la red tiene uno o más DMZ con los firewalls o servidores proxy, que aplicar directivas de seguridad de su organización y que solo permitir determinado tráfico de red que haya configurado y configurado. Porque administrar esta red, tiene control directo sobre el rendimiento de la red y se recomienda complete evaluaciones de la red para validar el rendimiento tanto dentro de los sitios de su red y de su red de Skype empresarial En línea. Para ver los requisitos de rendimiento, vea [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
 **Internet** Este es el segmento de red que forma parte de la red general que va a utilizar los usuarios que se están conectando a Skype empresarial Online desde fuera de la red y se utilizan para todas las conexiones cuando no está configurado ExpressRoute. Internet y todas sus conexiones no administrados por usted o Microsoft, por lo que no se puede determinar el rendimiento y rutas y tendrá el mayor impacto en el flujo de llamadas y la calidad general.
  
 **ExpressRoute** Este es el segmento de red que forma parte de la red general que proporcionan una conexión privada y dedicada a la red de Microsoft. Esta es la opción recomendada para conectar su red a la red de Microsoft (centros de datos de Office 365) para todas las cargas de trabajo que dependen de la velocidad de red y rendimiento, como Skype empresarial Online comunicación en tiempo real. ExpressRoute conexiones se realizan entre la red y el uso de red[proveedores de conectividad de ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) de Microsoft para proporcionar una red privada y administrada, con el tiempo de actividad del 99,9% y soporte técnico de calidad de servicio (QoS) que puede mejorar el rendimiento de multimedia en tiempo real durante los períodos de congestión de la red.
  
 **Microsoft network** Este es el segmento de red que forma parte de la red general compatible con servicios de Office 365. Esto incluye todas las comunicaciones entre servidores Online para Office 365. Esto puede incluir tráfico que atraviesa la red troncal de Microsoft y se transmite entre regiones geográficas.
  
### Tipos de tráfico

El tráfico de red para Skype empresarial Online se divide en dos categorías, que se muestra como rutas independientes en el flujo de llamadas:
  
 **Multimedia en tiempo real** datos encapsulados en RTP (Protocolo de transporte en tiempo real) y es compatible con audio, vídeo, uso compartido de aplicaciones y cargas de trabajo de transferencia de archivo. En general, tráfico de medios altamente es latencia confidencial, por lo que quiera que hay que tomar la ruta más directa posible este tráfico y utilizar UDP como protocolo de capa de transporte porque utilizando TCP presenta latencia mayor.
  
 **Señalización** es el vínculo de comunicación entre el cliente y servidor, u otros clientes de que se usan para controlar las actividades (por ejemplo, cuando se inicia una llamada) y enviar mensajes instantáneos. Mayor cantidad de tráfico de señalización usa el protocolo SIP, aunque algunos clientes usar interfaces resto basado en HTTP. Para que sea sencilla, estamos considerando una variedad de señalización que pueden viajar a través de conexiones HTTP y HTTPS o TLS en este tipo de tráfico. Es importante comprender que este tráfico es mucho menos sensible a la latencia, pero puede provocar interrupciones del servicio de llamada o tiempos de espera si la latencia entre los extremos superan unos segundos.
  
Los destinos para este tráfico se encuentran en [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) para todos los servicios de Office 365. Para cada dirección URL, indica si esa parte del tráfico puede recorrer la ExpressRoute para Office 365. Diagramas que muestran que Internet aún se usa para el tráfico cuando ExpressRoute está habilitado, vea[Azure ExpressRoute para Office 365](http://technet.microsoft.com/library/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd%28Office.14%29.aspx). Es importante comprender que incluso direcciones URL que se muestran como enrutables sobre ExpressRoute también son enrutables por Internet. Esto significa que en algunos casos, la determinación de si se usan Internet o ExpressRoute depende de la ubicación del cliente y la configuración de seguridad y servidores proxy. También es importante comprender que ya que no todas las direcciones URL asociadas con Office 365 pueden usar ExpressRoute, se requiere una conexión a Internet incluso si compra ExpressRoute de un socio ExpressRoute.
  
Tráfico que solo se pueden enviar a través de Internet incluye dependencias comunes de Internet, como listas de revocación de certificados (CRL), búsquedas DNS y resolución de nombres, direcciones URL de servicios compartidos de Office 365, como por ejemplo para el centro de administración de Office 365 y algunos no en tiempo real características de comunicación de Skype empresarial Online como telemetría y federación interoperabilidad con consumidor de Skype, como bien multimedia que se transmiten para la difusión de reunión de Skype. Para ayudarle a tomar decisiones, vea [Enrutamiento con ExpressRoute para Office 365](http://technet.microsoft.com/library/e1da26c6-2d39-4379-af6f-4da213218408%28Office.14%29.aspx) para obtener más información sobre si planea el enrutamiento de red.
  
## Principios para los flujos de llamadas con Skype Empresarial

Antes de entrar en los detalles de específicos de llamar a escenarios de flujo, hay seis principios generales que le ayudarán a entender flujos de llamada de Skype empresarial.
  
1. Un Skype para conferencias de empresa se hospeda en la misma región donde está alojado el organizador de la conferencia. Esto es en la nube de Office 365, si el organizador es un usuario en línea o en un centro de datos local, si el organizador de la reunión es un usuario local.
    
2. Tráfico de medios enviado de un cliente a una conferencia hospedada siempre va al servidor donde se hospeda la conferencia. Puede ser un servidor local dentro de un centro de datos que se encarga de administrar o un servidor en línea dentro de la nube de Office 365. Sin embargo, un servidor perimetral siempre se usa para el flujo de medios para conferencias en línea.
    
3. El tráfico multimedia de las llamadas de punto a punto toma la ruta más directa que esté disponible. La ruta preferida va directa al equipo remoto (cliente), pero si esa ruta no está disponible porque el firewall está bloqueando el tráfico o existe algún otro problema de este tipo, entonces uno o varios servidores perimetrales retransmitirán el tráfico.
    
4. El tráfico de señalización siempre se dirige al servidor en el que se aloja el usuario, ya sea en línea o local. Se utilizará un servidor perimetral si el servidor front-end no se puede conectar directamente.
    
5. Los usuarios que se unen a una conferencia hospedada en línea siempre usarán un servidor perimetral (o dos si es necesario por las configuraciones del firewall para cliente).
    
6. Los usuarios que se unen a una conferencia hospedada en local no utilizarán, por lo general, un servidor perimetral si se conectan desde dentro de la misma red que contiene la implementación local, y utilizarán uno o dos servidores perimetrales cuando se conectan desde fuera de la red. 
    
Para obtener más información acerca de los detalles de la ruta de medios que se ha elegido, vea [HIELO - borde multimedia conectividad](https://aka.ms/AVEdge). Aunque es este vídeo sobre Lync Server 2013, los protocolos y principios aplicarán a Skype empresarial.
  
## Los flujos de llamada de Skype Empresarial con ExpressRoute

Ahora que tiene una comprensión de los cuatro segmentos de red diferente y algunas orientaciones generales de Skype para los flujos de llamada de empresa, puede usar que información para ayudarle a entender qué Skype para el tráfico de empresa pasarán por un ExpressRoute segmento de red.
  
En general, el tráfico de red cruzará la conexión de ExpressRoute si un punto de conexión está en su red y el otro está en el centro de datos de Office 365. Esto incluirá el tráfico de señalización entre el cliente y el servidor, el tráfico multimedia usado durante las llamadas de conferencia o las llamadas de punto a punto que usan un servidor perimetral en línea.
  
Tráfico no recorre la conexión ExpressRoute si ambos de los extremos pueden comunicarse directamente a través de internet o se encuentran dentro de su red. Esto incluye media para llamadas de punto a punto, el tráfico de Internet destinado a una implementación local o todo el tráfico entre los servidores perimetrales de Office 365 e Internet. Un ejemplo de esto sería un usuario unirse a una conferencia en línea desde un hotel.
  
## Flujo de llamadas básico de Skype Empresarial

Para ayudarle a aplicar los principios generales de los flujos de llamada de Skype Empresarial que se han descrito anteriormente, la próxima sección de este artículo contiene diagramas como referencia. No se trata de una lista exhaustiva de todos los posibles flujos de llamadas, sino de un intento de ayudarle a aplicar los principios detallados anteriormente. Además, los escenarios de los diagramas se han seleccionado para cubrir los tipos de implementación más comunes; entre ellos, en línea, híbrida, conector de nube y, en un caso especial, la Difusión de reunión de Skype.
  
> [!NOTE]
> Un subconjunto de tráfico que utiliza Skype para la empresa no enrutable sobre ExpressRoute y siempre tendrá una ruta de acceso de Internet. Consulte la [URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx) para determinar las direcciones URL que pueden verse afectadas.
  
### Llamada de punto a punto para usuarios de Office 365 desde dentro de la red de clientes
<a name="bk_Figure2"> </a>

En las llamadas de punto a punto, el tráfico multimedia siempre toma la ruta más directa a su destino. No obstante, el tráfico de señalización va a un centro de datos de Office 365 en el que está alojado el usuario en línea. Puesto que ambos usuarios están en la misma WAN y nada impide que los clientes se comuniquen directamente, los elementos multimedia fluyen directamente entre ellos. El tráfico de señalización, en el caso de ambos usuarios, atraviesa la conexión de ExpressRoute que se destina al centro de datos de cada organización. Para mostrarle el flujo de llamadas en este escenario, vea esto.
  
 **Flujo de llamadas de punto a punto**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### Usuario en línea de su red que se une a una conferencia hospedada en línea
<a name="bk_Figure3"> </a>

En el ejemplo de punto a punto, el tráfico de medios siempre tiene la ruta más directa a su destino. Sin embargo, para una conferencia en línea, el destino es en la nube de Office 365. Esto significa que el tráfico de medios para todos los usuarios unirse a la conferencia desde dentro de su red pasarán por la conexión de ExpressRoute y el tráfico de señalización se desplaza a la nube de Office 365. El siguiente gráfico muestra que medios y señalización pasarán por la conexión de ExpressRoute para un usuario de su red y directamente pasarán por Internet para los usuarios que está conectado a Internet desde fuera de la red, como desde un café comprar o un hotel.
  
Recuerde que la ubicación de una conferencia está definida por el organizador de la reunión y no por los participantes. Esto significa que la reunión se ha programado por un cliente local, el tráfico de medios no desborde a la nube de Office 365 ExpressRoute, pero en su lugar atraviesa Internet al centro de datos local del organizador de la reunión.
  
El destino de los elementos multimedia en el caso de las conferencias en línea será un centro de datos en la nube de Office 365, pero este se puede encontrar en una región geográfica distinta a la de los usuarios que se están uniendo a la conferencia. Esta situación se da de una de estas dos formas:
  
- Si el organizador de la reunión pertenece a una empresa distinta a la de los asistentes o participantes, y la organización del organizador está hospedada en una ubicación geográfica, o país o región, distinta.
    
- Si un usuario se une desde un país o región distinto al de la organización de la empresa, ya sea porque es una empresa multinacional o porque el usuario esté viajando.
    
La ventaja de usar ExpressRoute en este escenario es que con el complemento de premium ExpressRoute, los datos que sigue la ruta de acceso ExpressRoute pasará automáticamente a través de la red troncal de Microsoft independientemente de la región geográfica del organizador de la reunión Centro de datos de la organización.
  
 **Flujo de llamadas de un usuario en línea con una reunión en línea**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### Unirse a una conferencia hospedada por un usuario local en una implementación híbrida
<a name="bk_Figure3"> </a>

Recuerde que los servidores de conferencia que admiten conferencias hospedadas determinan donde está alojado el organizador de la reunión. En este escenario, multimedia para todos los usuarios unirse a una conferencia programada por un usuario local en una implementación híbrida fluirá a un centro de datos local. Señalización para los usuarios alojados en línea se establecerá a través de su organización en la nube de Office 365, mientras media intentará una conexión directa. En este escenario, ya que los usuarios se conecten desde dentro de la red, una conexión directa de medios es posible, por lo que ExpressRoute se usa solamente para señales de tráfico para el usuario alojado en línea. Si se conecta un usuario alojado en línea desde Internet, multimedia podrían recorrer ExpressRoute si se usa un servidor perimetral en línea para conectar.
  
 **Flujo de llamadas de una conferencia organizada por usuario híbrido**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### Servidor perimetral local con conferencias hospedadas en Office 365
<a name="bk_Figure5"> </a>

Cuando un usuario se une híbrido en línea alojado conferencia, sabemos que señalización y elementos multimedia se destinados de la nube de Office 365 y dado que el usuario se une desde Internet, normalmente se tendrán una ruta de acceso directo de internet. Sin embargo, en algunos casos, por ejemplo, debido a las restricciones del firewall, una ruta de acceso directo de Internet no está disponible. En este caso, un servidor perimetral de local puede transmitir el tráfico de multimedia, lo que hace que el tráfico de medios volver a su red local antes de pasar el circuito ExpressRoute en la nube de Office 365.
  
 **Usuario local que se une a una llamada de conferencia en línea con un servidor perimetral local**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### Llamada RTC con Skype Empresarial Cloud Connector Edition
<a name="bk_Figure6"> </a>

Uso de la [Skype para Business Online nube conector Edition](https://aka.ms/CloudConnectorInstaller) ofrece conectividad de RTC con recursos locales como un tronco SIP o una puerta de enlace de RTC, o mediante un dispositivo de hardware mínimas integrar con Skype empresarial. Con la edición de conector de nube, los usuarios alojados en línea y actúen como normales usuarios en línea cuando no implican llamar a los planes. Señalización para escenarios de RTC se viaja entre el cliente y la nube a través de una conexión de ExpressRoute si está disponible y, a continuación, el tráfico de medios permanezca dentro de su WAN. En este caso, señalización gira alrededor de la nube de Office 365 y finaliza en el conector de la nube.
  
 **Llamada de RTC mediante el sistema telefónico en Office 365 y conector de nube**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### Difusión de reunión de Skype con usuarios que se unen desde la red del cliente
<a name="bk_Figure6"> </a>

Difusión de reunión de Skype es un especial caso de uso, que consta de una reunión de dos partes con cada elemento tiene perfiles de transporte de red diferente. La primera parte y que es más importante de una red punto de vista del rendimiento, es la reunión interna. Esta es la parte en tiempo real de la reunión que incluya uno o más extremos de cliente conectarse al servidor de conferencia en la nube de Office 365. Datos transmitidos mediante esta parte de la reunión están exactamente igual que el ejemplo encima, con una combinación de usuario de Office 365 y conferencia en línea.
  
¿Qué hace una difusión de reunión de Skype únicos es que la reunión se distribuye a un gran número de participantes de la conferencia mediante una servicio de transmisión de difusión. Este servicio de transmisión de difusión no enrutable sobre ExpressRoute, sino que utiliza Internet con el soporte opcional de servicios de red de entrega de contenido (CDN). Resulta útil reconocer que la transmisión es un flujo de medios unidireccional porque los asistentes escuchan pero no hable y es compatible con el búfer, por lo que es mucho menos sensible a problemas de rendimiento de red, como la latencia, la pérdida de paquetes y la vibración. En lugar de optimizar el tráfico de difusión para estos problemas, está optimizado para la utilización de ancho de banda porque es potencialmente un gran número de asistentes recibir el contenido multimedia.
  
 **Difusión de reunión de Skype con usuarios desde la red del cliente**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## Patrones de flujos de llamadas según el tipo de implementación

Con la común llame ejemplos de flujo anteriores y una descripción de los principios generales que controlan los patrones de tráfico, las tablas siguientes proporcionan un resumen de los patrones de tráfico de una combinación de grande de escenarios de implementación y uso. Estas tablas no capturan todas las combinaciones posibles de flujos de llamada, pero le será de utilidad para comprender mejor los principios generales de flujo de llamadas.
  
Datos se transmiten y se muestran como local a la organización. No deje la red de clientes, Internet o ExpressRoute. Los patrones que se muestran a continuación se basan en la configuración de red más comunes, como los firewalls, federación e Internet y se supone que todas las organizaciones implicadas en varios participantes o federados flujos tienen ExpressRoute. En la práctica, con distintos parámetros podría provocar patrones de tráfico distintos de los que se muestran a continuación.
  
### Flujos de llamadas para Skype Empresarial Online

Skype empresarial Online escenarios de uso involucrar a los usuarios que están alojados en línea y a continuación, pueden llamar desde la red interna o en Internet. Los servidores locales no forman parte de estas situaciones, para que todas las conferencias o medios relacionados de RTC fluirá a la nube de Office 365 y los usuarios en línea, servidor perimetral también estarán en la nube.
  
 **Resumen de los flujos de llamadas para Skype Empresarial Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos en su red.  <br/> |ExpressRoute  <br/> |Local  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde dentro de la red de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> ||
|Llamada de punto a punto  <br/> |Dos clientes, en la red (interna) y el otro cliente de Internet (externo).  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: Internet  <br/> |Usuario interno: ExpressRoute  <br/> Usuario externo: De Internet al servidor perimetral de Office 365.  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde dentro de la red de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Se supone que firewall bloquea las conexiones directas entre los clientes, que requiere un servidor perimetral en línea. Tráfico de usuario interno para el servidor perimetral Online sigue similar ruta de acceso que el servidor de conferencia llamada de conferencia.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, en su red (interno) y el usuario en línea en la red de la organización federada (federado).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Asume que un firewall bloquea las conexiones directas entre clientes, por lo que requiere un servidor perimetral en línea. El tráfico desde el usuario interno al servidor perimetral en línea sigue una ruta similar a la de un servidor de conferencias para la llamada de conferencia.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente  <br/> |El cliente en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Unirse a llamada de conferencia por usuario en Internet  <br/> |Cliente se encuentra en el servidor de Internet y conferencias en nube de Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Unirse a una conferencia hospedada por el servidor local de otra empresa  <br/> |El cliente en su red y el servidor de conferencias en el centro de datos de terceros.  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Dado que el servidor de conferencias que hospeda la conferencia está en una red local de otro cliente, ningún dato pasará por la nube de Microsoft.  <br/> |
|Llamada RTC  <br/> |Cliente en red de clientes y los servidores de sistema de teléfono en la nube de Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Llamada RTC  <br/> |Cliente en los servidores de Internet y el sistema telefónico de nube de Office 365  <br/> |Internet  <br/> |Internet  <br/> |No aplicable  <br/> |Multimedia y señalización will flujo al centro de datos de Office 365. Desde el extremo del cliente está en Internet, todos los datos fluirá al centro de datos de Microsoft a través de Internet (incluso si es necesario un servidor perimetral en línea para conectividad).  <br/> |
   
> [!NOTE]
> ExpressRoute se usan en la ruta de medios de un usuario que se encuentra en la red corporativa para un servidor perimetral en línea, pero no se utilizará si se usa el servidor perimetral para su implementación local de otro cliente. 
  
### Flujos de llamadas para la implementación híbrida de Skype Empresarial

Flujos de llamada híbrido se aplican cuando tiene un Skype para la implementación de empresa que incluya al menos algunos usuarios que están alojados en local. Los flujos de llamada en esta sección incluyen ambos conferencias locales y llamadas de punto a punto o RTC con al menos un usuario de alojados en local.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, en la red del cliente y alojados en local.  <br/> |Local  <br/> |Local  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde dentro de la red de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Como los usuarios se alojan en local, la señalización fluye en local al centro de datos local en lugar de a la nube de Office 365.  <br/> |
|Llamada de punto a punto  <br/> |Dos clientes, ambos conectados desde la red del cliente. Uno está alojado en línea y el otro en local.  <br/> |Usuario en línea: ExpressRoute  <br/> Usuario local: local  <br/> |Local  <br/> |[Llamada de punto a punto para usuarios de Office 365 desde dentro de la red de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Solo el usuario alojado en línea envía tráfico de señalización a la nube de Office 365.  <br/> |
|La llamada de punto a punto a un usuario en una organización federada  <br/> |Dos clientes, uno local en la red del cliente (interno) y un usuario en línea en la red de la organización federada (federado).  <br/> |Usuario interno: local  <br/> Usuario federado: ExpressRoute  <br/> |Internet o ExpressRoute (depende de si se usa el servidor en línea o perimetral local)  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) y parte de[Servidor perimetral local con conferencias hospedadas en Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) (para el tráfico multimedia). <br/> |Supone un firewall que bloquea las conexiones directas entre clientes, que requieren servidores perimetrales en línea. Negociación de HIELO ofrecerá Online (por el usuario en línea) y servidores perimetrales de local (por el usuario local) para la conectividad.  <br/> |
|Unirse a la llamada de conferencia por usuario en la red del cliente (conferencia programada por el usuario en línea)  <br/> |El usuario en local en su red y el servidor de conferencias en la nube de Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Usuario en línea de su red que se une a una conferencia hospedada en línea](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Recursos de servidor para la llamada de conferencia están definidos por el organizador de la reunión. En este caso, se ha programado de un usuario en línea, para que los recursos están en la nube de Office 365.  <br/> |
|Llamada RTC  <br/> |Usuario en local en su red y centro de datos Skype Empresarial local.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> |Similar escenario para usar Cloud Connector Edition, con la diferencia de que el usuario está alojado en local, de modo que la señalización permanece dentro de la red.  <br/> |
   
### Flujos de llamadas de Skype Empresarial con Cloud Connector

Todos los usuarios que se conectarán a Cloud Connector Edition están alojados en línea. Esto significa que las conferencias serán en línea y que la señalización sigue los mismos patrones que los usuarios en línea. Para otros escenarios distintos de las llamadas RTC, el flujo de llamadas será exactamente el mismo que el descrito anteriormente para Skype Empresarial Online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Escenario de uso** <br/> |**Puntos de conexión** <br/> |**Ruta de señalización** <br/> |**Ruta multimedia** <br/> |**Ejemplo de flujo** <br/> |**Notas** <br/> |
|Llamada RTC  <br/> |Usuario en línea en su red con Cloud Connector Edition.  <br/> |Local  <br/> |Local  <br/> |[Llamada RTC con Skype Empresarial Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> ||
|Llamada RTC  <br/> |Usuario en línea que usa Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinación de [Servidor perimetral local con conferencias hospedadas en Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) y[Llamada RTC con Skype Empresarial Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6).  <br/> |Los usuarios de Internet se conectarán a través del servidor perimetral que se incluye en Cloud Connector y Cloud Connector se conectará a la red RTC.  <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

