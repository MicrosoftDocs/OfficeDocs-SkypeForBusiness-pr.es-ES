---
title: Componente del servidor de mediación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: 'Obtenga información acerca de los servidores de mediación en Skype para Business Server, incluyendo sus topologías admitidas y sus relaciones con los troncos m: n, omisión de medios y control de admisión de llamada.'
ms.openlocfilehash: a17c6d83c51c8de1101437072f8404202f600e12
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-component-in-skype-for-business-server-2015"></a>Componente del servidor de mediación en Skype Empresarial Server 2015
 
Obtenga información acerca de los servidores de mediación en Skype para Business Server, incluyendo sus topologías admitidas y sus relaciones con los troncos m: n, omisión de medios y control de admisión de llamada.
  
Para implementar la Telefonía IP empresarial, debe implementar uno o más servidores de mediación. 
  
El servidor de mediación traduce la señalización entre la infraestructura de Telefonía IP empresarial interna y una puerta de enlace de telefonía pública conmutada (PSTN) de la red o un tronco de protocolo de inicio de sesión (SIP). En algunas implementaciones, también convierte los propios medios entre estos puntos.
  
En Skype para lado Business Server, servidor de mediación escucha en una sola dirección de transporte mutuo (MTLS) de TLS. En el lado de la puerta de enlace, servidor de mediación se escucha en todos los puertos de escucha asociados asociados con los troncos. Todas las puertas de enlace calificadas necesitan compatibilidad con TLS, pero también pueden habilitar TCP. TCP es compatible con las puertas de enlace que no son compatibles con TLS.
  
Si tienes un Exchange de sucursales públicas (PBX) existente en su entorno, servidor de mediación controla las llamadas entre usuarios de Telefonía IP empresarial y la PBX. Si la PBX es una PBX IP, puede crear una conexión directa de SIP entre el PBX y el servidor de mediación. Si su PBX es un tiempo de división Multiplex (TDM) PBX, también debe implementar una puerta de enlace PSTN entre la PBX y el servidor de mediación.
  
El servidor de mediación está ubicado en el servidor Front-End de forma predeterminada. El servidor de mediación también puede implementarse en un grupo independiente.
  
## <a name="what-mediation-server-does"></a>Funciones del servidor de mediación

Las principales funciones del servidor de mediación son los siguientes:
  
- Cifrar y descifrar SRTP en el Skype para servidor de negocios. 
    
- Convertir SIP sobre TCP (para puertas de enlace que no admiten TLS) en SIP sobre Mutual TLS.
    
- Traducción de transmisiones multimedia entre Skype para Business Server y el interlocutor de puerta de enlace del servidor de mediación.
    
- Conectar clientes que están fuera de la red con componentes ICE internos, que habilitan el paso de los medios a través de NAT y los firewalls.
    
- Actúa como un intermediario para flujos de llamada que no admite una puerta de enlace, como las llamadas de trabajadores remotos en un clien.t de Telefonía IP empresarial
    
- En implementaciones que incluyen enlaces troncales SIP, trabajar con el proveedor de servicios de enlaces troncales SIP para proporcionar compatibilidad con la RTC, con lo que se elimina la necesidad de una puerta de enlace RTC.
    
La siguiente figura muestra los protocolos de señalización y los medios utilizados por el servidor de mediación cuando se comunica con una puerta de enlace PSTN básica y la infraestructura de Telefonía IP empresarial.
  
**Protocolos de señalización y los medios utilizados por el servidor de mediación**

![Diagrama de protocolos de servidor de mediación](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si está utilizando TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre el servidor de mediación y de la puerta de enlace PSTN, recomendamos tomar medidas para garantizar la seguridad y la privacidad de la red. 
  
## <a name="mn-trunk"></a>Tronco M:N

Skype para Business Server admite la flexibilidad en la definición de un tronco para propósitos de enrutamiento de llamada. Un tronco es una asociación lógica entre un servidor de mediación y el número de puerto de escucha, con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos de acceso a la misma puerta de enlace; un servidor de mediación puede tener varios troncos de acceso a puertas de enlace distintas; por el contrario, una puerta de enlace puede tener varios troncos de acceso a diferentes servidores de mediación.
  
Todavía debe crear un tronco de raíz cuando se agrega una puerta de enlace a su Skype para la topología del negocio mediante el generador de topología. El número de puertas de enlace que puede administrar un servidor de mediación determinado depende de la capacidad de procesamiento del servidor durante las horas de disponibilidad. Si implementa un servidor de mediación en hardware que cumpla los requisitos mínimos de hardware para Skype para Business Server, como se describe en los [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), a continuación, un servidor de mediación de independiente puede controlar aproximadamente 1000 llamadas. El servidor de mediación es realiza la transcodificación, pero seguir enrutando llamadas para varias puertas de enlace, incluso si las puertas de enlace no admite la omisión de medios.
  
Al definir una ruta de llamada, especificar los troncos asociados a esa ruta, pero no especifica que los servidores de mediación están asociados con esa ruta. En su lugar, utilice el generador de topología para asociar los troncos con servidores de mediación. En otras palabras, enrutamiento determina que el tronco para utilizarlo en una llamada y, posteriormente, el servidor de mediación asociado con ese tronco se envía a la señalización de esa llamada.
  
El servidor de mediación puede implementarse como un conjunto; Este grupo puede dar en combinación con un grupo de servidores Front-End, o se puede implementar como un grupo independiente. Cuando un servidor de mediación se combina con un grupo de servidores Front-End, el tamaño del grupo puede ser como máximo 12 (el límite del tamaño del registro). Juntas, estas capacidades aumentan la confiabilidad y la flexibilidad de implementación para servidores de mediación, pero requieren capacidades similares en lo siguiente:
  
- **Puerta de enlace RTC.** Un Skype para puerta de enlace completo Business Server debe implementar con equilibrio de carga DNS, lo que permite una puerta de enlace de red (conmutada PSTN) completo de telefonía pública conmutada para que actúe como un equilibrador de carga para un grupo de servidores de mediación y, por tanto, para equilibrar la carga de llamadas en todo el repositorio .
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del conjunto de servidor de mediación para el SBC, el SBC puede recibir conexiones desde cualquier servidor de mediación en el grupo. En la dirección de la CE a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación en el grupo. Esto puede conseguirse a través del equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa consiste en dar al proveedor de servicios de las direcciones IP de todos los servidores de mediación en el grupo y el proveedor de servicios le proveerá estos en su SBC como tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios gestionará el equilibrio de carga para sus propios servidores. Es posible que no todos los proveedores de servicios o SBC admitan estas capacidades. Además, es posible que el proveedor de servicios exija cargos adicionales para esta capacidad. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección del conjunto de servidor de mediación para la terminación SIP IP-PBX, IP-PBX puede recibir conexiones desde cualquier servidor de mediación en el grupo. En la dirección de IP-PBX a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación en el grupo. Porque la mayoría de IP-PBX no admiten equilibrio de carga DNS, se recomienda definir conexiones SIP directas individuales desde IP-PBX para cada servidor de mediación en el grupo. La IP-PBX gestionará su propio equilibrio de carga al distribuir el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en la IP-PBX. Si una determinada IP-PBX admite este concepto de grupo troncal y cómo se intersecta con la redundancia del IP-PBX propio y arquitectura de clustering debe determinarse antes de que usted puede decidir si un clúster de servidor de mediación puede interactuar correctamente con un IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con el que interactúa. Esto significa que todos los miembros del grupo obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por tanto, no hay ninguna forma de segmentar el grupo para que algunos servidores de mediación comunicarse con sólo ciertos pares de puerta de enlace para las llamadas salientes. Si es necesaria la segmentación de este tipo, debe utilizarse un conjunto independiente de servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, los troncos SIP o las IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo, tal y como se ha explicado anteriormente en este mismo tema.
  
Una puerta de enlace PSTN determinado, IP-PBX o interlocutor de troncal SIP puede enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que puede controlar un determinado grupo de servidores de mediación depende del número de llamadas que utilizan la omisión de medios. Si un gran número de llamadas utilice la omisión de medios, un servidor de mediación en el grupo puede controlar muchas más llamadas, porque sólo señalización capa es necesario. 
  
## <a name="call-admission-control-and-mediation-server"></a>Servicio de control de admisión de llamadas y servidor de mediación

El servicio de control de admisión de llamadas (CAC) administra el establecimiento de sesiones en tiempo real según el ancho de banda disponible para evitar que la calidad de la experiencia (QoE) de los usuarios sea deficiente en las redes congestionadas. Para ello, el servidor de mediación es responsable de la administración de ancho de banda para sus dos interacciones en el Skype para servidor de negocio y en el lado de la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad de terminación para una llamada gestiona la reserva del ancho de banda. Los interlocutores de gateway (puerta de enlace PSTN, IP-PBX, SBC) que el servidor de mediación interactúa con en el lado de la puerta de enlace no son compatibles con Skype Business Server llamada de control de admisión. Por lo tanto, el servidor de mediación tiene que controlar las interacciones de ancho de banda en nombre de su interlocutor de puerta de enlace. Siempre que sea posible, el servidor de mediación se reservan ancho de banda de antemano. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada saliente a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este comportamiento puede provocar la saturación del ancho de banda, pero es la única forma de evitar las llamadas falsas.
  
La omisión de medios y la reserva del ancho de banda se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el servicio de control de admisión de llamadas en esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se utiliza el control de admisión de llamada para una llamada particular que incluye al servidor de mediación, que la llamada no puede emplear la omisión de medios.
  
Para obtener más información acerca de los medios de derivación o llame al control de admisión, consulte [Plan para medios de derivación en Skype para negocios 2015](media-bypass.md) o [Plan de control de admisión de llamada en Skype para Business Server 2015](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 mejorado (E9-1-1) y servidor de mediación

El servidor de mediación tiene capacidades extendidas de modo que puede interactuar correctamente con los proveedores de servicios Enhanced 9-1-1 (E9-1-1). No es necesaria ninguna configuración especial en el servidor de mediación. Son las Extensiones SIP necesarias para la interacción de E9-1-1, de forma predeterminada, incluido en el protocolo SIP del servidor de mediación para sus interacciones con un interlocutor de gateway (puerta de enlace PSTN, IP-PBX o el SBC de un proveedor de servicios de telefonía de Internet, incluido el servicio E9-1-1 Proveedores)
  
Si el tronco SIP a un proveedor de servicios de E9-1-1 puede terminar en un grupo de servidor de mediación existente o requiere servidores de mediación independiente depende de si el SBC E9-1-1 puede interactuar con un grupo de servidores de mediación. Para obtener más información, consulte [m: n tronco en Skype para Business Server 2015](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Omisión de medios y servidor de mediación

Omisión de medios es un Skype para la capacidad del servidor de empresa que permite a los administradores configurar el enrutamiento de llamadas para fluir directamente entre el extremo de usuario y la puerta de enlace de telefónica pública conmutada (PSTN) de la red sin atravesar el servidor de mediación. Omisión de medios mejora la calidad de la llamada al reducir la latencia, traducción innecesaria, posibilidad de pérdida de paquetes y el número de posibles puntos de falla. Cuando un sitio remoto sin un servidor de mediación está conectado a un sitio central mediante uno o más vínculos WAN con ancho de banda limitado, omisión de medios reduce el requerimiento de ancho de banda habilitando los medios desde un cliente en un sitio remoto a fluir directamente a su puerta de enlace local sin primero tener que atravesar la WAN vincular a un servidor de mediación en el sitio central y trasera. Esta reducción de procesamiento de medios también complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.
  
La omisión de medios y el servicio de control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.
  
## <a name="topologies-for-mediation-server"></a>Topologías para el servidor de mediación

De forma predeterminada el Skype para Business Server, servidor de mediación es colocado con servidor Standard Edition, un grupo de servidores Front-End o dispositivo de sucursal que sobreviven. Todos los servidores de mediación de un grupo de servidores Front-End debe configurarse de forma idéntica.
  
Cuando el rendimiento es un problema, puede ser preferible implementar uno o más servidores de mediación en un grupo independiente dedicado. Recomendamos que implementes un grupo independiente si estás implementando enlaces troncales SIP. 
  
Si implementa conexiones SIP directo a una puerta de enlace PSTN completo que admite la omisión de medios y cargar DNS equilibrio, un servidor de mediación de independiente de grupo no es necesario. Esto es porque son capaces de DNS equilibrio de carga en un grupo de servidores de mediación completos de puertas de enlace y pueden recibir tráfico desde cualquier servidor de mediación en un grupo.
  
También se recomienda colocar el servidor de mediación en un grupo de servidores Front-End cuando se ha implementado IP-PBX o conectar a telefonía servidor del proveedor de Internet sesión Border Controller (SBC), siempre y cuando se cumple alguna de las condiciones siguientes:
  
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación en la piscina y puede enrutar tráfico de manera uniforme a todos los servidores de mediación en el grupo.
    
- El IP-PBX no admite la omisión de medios, pero el grupo de Front-End que aloja el servidor de mediación puede controlar transcodificación de voz para las llamadas a los que no se aplica la omisión de medios.
    
Puede utilizar el 2013 de Microsoft Lync Server, herramienta de planeación para evaluar si el grupo de Front-End donde desee colocar el servidor de mediación puede manejar la carga. Si su entorno no cumple estos requisitos, se debe implementar un conjunto de servidor de mediación de independiente.
  
En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados a través de un vínculo WAN. Está ubicado en el servidor de mediación en una agrupación de Front-End al sitio 1. Los servidores de mediación en sitio 1 controla la puerta de enlace PSTN en sitio 1 y la puerta de enlace en el sitio 2. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen la omisión habilitada.
  
**Ejemplo de sitios conectados mediante una red WAN vínculo con un servidor de mediación en el sitio 1 y una puerta de enlace PSTN en el sitio 2**

![Puerta de enlace de WAN de topología de voz con servidor de mediación](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
En la siguiente figura muestra una topología simple donde el servidor de mediación se combina en grupo de servidores Front-End en el sitio 1 y tiene una conexión directa SIP para IP-PBX en sitio 1. En esta figura, el servidor de mediación también controla una puerta de enlace PSTN en el sitio 2. Se supone que existe Skype para usuarios profesionales en los sitios 1 y 2. También se supone que el IP-PBX tiene un procesador de medios asociados que debe recorrerse por todos los medios de comunicación procedentes de Skype para extremos de negocio antes de ser enviados a los extremos de medios controlados por el IP-PBX. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a la puerta de enlace RTC y la PBX tienen la omisión de medios habilitada.
  
**Ejemplo de sitios conectados mediante una red WAN vínculo con un servidor de mediación en el sitio 1 y un PBX en sitio 2**

![PBX de WAN del servidor de mediación de topología de voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
La última figura de este tema muestra una topología donde está conectado el servidor de mediación para el SBC de un proveedor de servicios de telefonía de Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisiones de planificación para el servidor de mediación

Este tema describen las decisiones de planificación que necesita realizar para la implementación de servidor de mediación,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación colocadas o independiente?

De forma predeterminada, servidor de mediación se combina en el servidor Standard Edition o un servidor Front-End en un grupo de servidores Front-End en las sedes centrales. La cantidad de llamadas por la red telefónica conmutada (RTC) que se pueden gestionar y la cantidad de equipos necesarios en el grupo dependerán de los siguientes factores:
  
- El número de pares de gateway que controla el grupo de servidor de mediación
    
- Los períodos de gran tráfico de esas puertas de enlace
    
- El porcentaje de llamadas de llamadas cuyos medios omiten el servidor de mediación
    
Al planificar, asegúrate de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V no configuradas para la omisión de medios, además del procesamiento necesario para gestionar las interacciones de señalización para la cantidad de llamadas que es necesario admitir en las horas de más actividad. Si no tiene suficiente CPU, debe implementar un conjunto independiente de servidores de mediación; y puertas de enlace PSTN, PBX IP y SBCs deberá dividirse en subconjuntos que son controlados por los servidores de mediación colocadas en un grupo de servidores y los servidores de mediación independientes en uno o más grupos independientes.
  
Si implementó gateways PSTN, PBX IP o controladores de borde de sesión (SBCs) que no admiten las capacidades correctas para interactuar con un grupo de servidores de mediación, incluidas las siguientes, entonces necesitará estar asociado con un grupo independiente que consiste en de un único servidor de mediación:
  
- Realizar la capa de red, sistema de nombres de dominio (DNS) equilibrio de carga en los servidores de mediación en un grupo (o lo contrario enrutar tráfico uniformemente a todos los servidores de mediación en una piscina)
    
- Aceptar tráfico de cualquier servidor de mediación de un grupo
    
Puede utilizar el servidor de Microsoft Lync 2013, herramienta de planeación para evaluar si la colocación del servidor de mediación con el grupo de servidores Front-End puede manejar la carga. Si su entorno no cumple estos requisitos, se debe implementar un conjunto de servidor de mediación de independiente.
  
### <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

 Servidores de mediación en el sitio central sirve para dirigir las llamadas de IP-PBX o puertas de enlace PSTN en sitios de sucursal. Sin embargo, si implementa los troncos SIP, debe implementar un servidor de mediación en el sitio donde termina cada tronco. Tener un servidor de mediación en el sitio central enrutar llamadas de un IP-PBX o la puerta de enlace PSTN en un sitio de sucursal no requiere el uso de medios de derivación. Pero, si puedes habilitar la omisión de medios y así lo haces, se reducirá la latencia de la ruta de acceso a los medios y, por ello, mejorará la calidad de los medios, ya que la ruta de acceso a los medios ya no tendrá que seguir la ruta de acceso de señalización. Omisión de medios también reduce la carga de procesamiento en el grupo.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Omisión de medios es compatible sólo con los productos y versiones que se enumeran en [Unified Communications interoperabilidad programa abierto - Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Si se requiere la resistencia del sitio de sucursal, se debe implementar un dispositivo de sucursal que sobreviven o la combinación de un servidor Front-End, un servidor de mediación y una puerta de enlace en el sitio de la sucursal. (La suposición con resiliencia del sitio de sucursal es que presencia y conferencias no son flexibles en el sitio). Para obtener consejos sobre la planificación para la voz el sitio de sucursal, consulte [Plan de resiliencia de Telefonía IP empresarial en Skype para Business Server 2015](enterprise-voice-resiliency.md).
  
Para las interacciones con un IP-PBX, si el IP-PBX no admite correctamente temprano media interacciones con varios diálogos tempranas y RFC 3960 interacciones, puede haber algunas palabras del saludo llamadas entrantes de la IP-PBX en Skype para el recorte de la primera Extremos de negocio. Este problema puede ser más grave si un servidor de mediación en un sitio central es enrutar las llamadas de un IP-PBX donde finaliza la ruta en un sitio de sucursal, ya que se necesita más tiempo para señalización completar. Si experimenta este comportamiento, la implementación de un servidor de mediación en el sitio de la sucursal es la única forma de reducir el recorte de la primera pocas palabras.
  
Por último, si el sitio central tiene una PBX TDM o el IP-PBX no elimina la necesidad de una puerta de enlace PSTN, debe implementar una puerta de enlace en la ruta de llamada de conexión de servidor de mediación y la PBX.
  
> [!NOTE]
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, consulte ["lado de recepción escala mejoras en Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Para obtener más detalles sobre cómo habilitar RSS, mira la documentación de tu adaptador de red. 
  

