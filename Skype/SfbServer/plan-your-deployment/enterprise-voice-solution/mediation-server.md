---
title: Componente del servidor de mediación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: 'Obtenga información acerca de los servidores de mediación en Skype para Business Server, incluidos sus topologías admitidas y sus relaciones de troncos m: n, el desvío de medios y control de admisión de llamadas.'
ms.openlocfilehash: 73166df66acac493717ce2c07e42e5429176a400
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="mediation-server-component-in-skype-for-business-server-2015"></a>Componente del servidor de mediación en Skype Empresarial Server 2015
 
Obtenga información acerca de los servidores de mediación en Skype para Business Server, incluidos sus topologías admitidas y sus relaciones de troncos m: n, el desvío de medios y control de admisión de llamadas.
  
Para implementar Enterprise Voice, debe implementar uno o varios servidores de mediación. 
  
El servidor de mediación traduce la señalización entre la infraestructura de telefonía IP empresarial interna y una puerta de enlace de telefónica conmutada (RTC) o un tronco de protocolo de inicio de sesión (SIP). En algunas implementaciones, también convierte los propios medios entre estos puntos.
  
En Skype para lado Business Server, servidor de mediación escucha en una sola dirección de transporte mutual TLS (MTLS). En el lado de la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados asociados con troncos. Todas las puertas de enlace calificadas necesitan compatibilidad con TLS, pero también pueden habilitar TCP. TCP es compatible con las puertas de enlace que no son compatibles con TLS.
  
Si también tiene una existente pública de conmutación (PBX) en su entorno, el servidor de mediación controla las llamadas entre los usuarios de Enterprise Voice y el sistema PBX. Si la PBX es una PBX IP, puede crear una conexión SIP directa entre el sistema PBX y el servidor de mediación. Si su sistema PBX no es un tiempo de división Multiplex (TDM) PBX, también debe implementar una puerta de enlace de RTC entre el servidor de mediación y el sistema PBX.
  
De forma predeterminada, el servidor de mediación se combina con el servidor Front-End. El servidor de mediación también puede implementarse en un grupo de servidores independiente.
  
## <a name="what-mediation-server-does"></a>Funciones del servidor de mediación

Las funciones principales del servidor de mediación son los siguientes:
  
- Cifrar y descifrar SRTP en el Skype para servidor empresarial. 
    
- Convertir SIP sobre TCP (para puertas de enlace que no admiten TLS) en SIP sobre Mutual TLS.
    
- Convertir secuencias multimedia entre Skype para Business Server y el par de puerta de enlace del servidor de mediación.
    
- Conectar clientes que están fuera de la red con componentes ICE internos, que habilitan el paso de los medios a través de NAT y los firewalls.
    
- Actuar como intermediario para flujos de llamada que una puerta de enlace no admite, como llamadas de trabajadores remotos en un clien.t de Enterprise Voice
    
- En implementaciones que incluyen enlaces troncales SIP, trabajar con el proveedor de servicios de enlaces troncales SIP para proporcionar compatibilidad con la RTC, con lo que se elimina la necesidad de una puerta de enlace RTC.
    
La siguiente ilustración muestra los protocolos de señalización y los medios que se usan por el servidor de mediación al comunicarse con una puerta de enlace RTC básica y la infraestructura de Enterprise Voice.
  
**Protocolos de señalización y medios utilizados por el servidor de mediación**

![Diagrama de protocolos de servidor de mediación](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si está utilizando TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace RTC y el servidor de mediación, se recomienda tomar medidas para ayudar a garantizar la seguridad y privacidad de la red. 
  
## <a name="mn-trunk"></a>Tronco M:N

Skype para Business Server admite la flexibilidad en la definición de un tronco para fines de enrutamiento de llamadas. Un tronco es una asociación entre un servidor de mediación y el número de puerto de escucha, lógica con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos de acceso a la misma puerta de enlace; un servidor de mediación puede tener varios troncos de acceso a distintas puertas de enlace; por el contrario, una puerta de enlace puede tener varios troncos a diferentes servidores de mediación.
  
Aún debe crear un tronco raíz cuando se agrega una puerta de enlace a su Skype para con el generador de topología de negocio. El número de puertas de enlace que puede administrar un servidor de mediación determinado depende de la capacidad de procesamiento del servidor durante las horas de disponibilidad. Si implementa un servidor de mediación en hardware que cumpla los requisitos de hardware mínimos de Skype para Business Server, como se describe en [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), a continuación, un servidor de mediación independiente puede controlar aproximadamente llamadas de 1000. El servidor de mediación es realiza la transcodificación, pero aún enrutar las llamadas para varias puertas de enlace incluso si las puertas de enlace no admite el desvío de medios.
  
Al definir una ruta de llamada, especifique los troncos asociados con esa ruta, pero no se especifica que los servidores de mediación están asociados a esa ruta. En su lugar, use el generador de topología para asociar troncos con los servidores de mediación. En otras palabras, el enrutamiento determina qué tronco que se usará para una llamada y, posteriormente, se envía el servidor de mediación asociado con ese tronco la señalización de que la llamada.
  
El servidor de mediación puede implementarse como un grupo de servidores; Este grupo de servidores se puede combinar con un grupo de servidores Front-End, o se puede implementar como un grupo de servidores independiente. Cuando un servidor de mediación se combina con un grupo de servidores Front-End, el tamaño del grupo de servidores puede ser como máximo 12 (el límite del tamaño del grupo de servidores de registrador). Juntas, estas capacidades aumentan la confiabilidad y la flexibilidad para la implementación de servidores de mediación, pero que requieren capacidades similares en lo siguiente:
  
- **Puerta de enlace RTC.** Un Skype para puerta de enlace completa Business Server debe implementar con equilibrio de carga DNS, lo que permite que una puerta de enlace de completa telefónica conmutada (RTC) para que actúen como un equilibrador de carga para un grupo de servidores de mediación y, desde allí, a las llamadas de equilibrar la carga entre el grupo de servidores .
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación a la SBC, los SBC puede recibir conexiones desde cualquier servidor de mediación del grupo de servidores. En la dirección de la SBC para el grupo de servidores, se puede enviar el tráfico a cualquier servidor de mediación del grupo de servidores. Esto puede conseguirse a través del equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa consiste en proporcionar al proveedor de servicios de las direcciones IP de todos los servidores de mediación en el grupo de servidores, y el proveedor de servicios se aprovisione estos en su SBC como un tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios gestionará el equilibrio de carga para sus propios servidores. Es posible que no todos los proveedores de servicios o SBC admitan estas capacidades. Además, es posible que el proveedor de servicios exija cargos adicionales para esta capacidad. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección del grupo de servidores de mediación para la terminación de SIP de IP-PBX, IP-PBX puede recibir conexiones desde cualquier servidor de mediación del grupo de servidores. En la dirección de la IP-PBX para el grupo de servidores, se puede enviar el tráfico a cualquier servidor de mediación del grupo de servidores. Debido a que la mayoría de las PBX IP no admiten el equilibrio de carga DNS, se recomienda que se defina individuales conexiones SIP directas desde el IP-PBX para cada servidor de mediación del grupo de servidores. La IP-PBX gestionará su propio equilibrio de carga al distribuir el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en la IP-PBX. Si un determinado sistema IP-PBX admite este concepto de grupo de tronco y cómo cruza con la redundancia del IP-PBX propio y agrupación en clústeres de arquitectura debe determinarse antes de que puede decidir si un clúster de servidor de mediación puede interactuar correctamente con un IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace de mismo nivel con el que interactúa. Esto significa que todos los miembros del grupo obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay ninguna forma para segmentar el grupo de servidores para que algunos servidores de mediación comunicarse con sólo ciertos interlocutores de puerta de enlace para las llamadas salientes. Si la segmentación de este tipo es necesaria, se debe usar un grupo de servidores independiente de los servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, los troncos SIP o las IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo, tal y como se ha explicado anteriormente en este mismo tema.
  
Una determinada puerta de enlace de RTC, IP-PBX o punto de tronco SIP puede enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que puede controlar un determinado grupo de servidores de mediación depende del número de llamadas que usan el desvío de medios. Si un gran número de llamadas usa el desvío de medios, un servidor de mediación del grupo de servidores pueden controlar muchas más llamadas, debido a que el procesamiento de capa de señalización sólo es necesario. 
  
## <a name="call-admission-control-and-mediation-server"></a>Servicio de control de admisión de llamadas y servidor de mediación

El servicio de control de admisión de llamadas (CAC) administra el establecimiento de sesiones en tiempo real según el ancho de banda disponible para evitar que la calidad de la experiencia (QoE) de los usuarios sea deficiente en las redes congestionadas. Para ello, el servidor de mediación es responsable de la administración de ancho de banda para sus dos interacciones en la Skype para profesionales de servidor y en el lado de la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad de terminación para una llamada gestiona la reserva del ancho de banda. El mismo nivel de puerta de enlace (puerta de enlace RTC, IP-PBX, SBC) que el servidor de mediación interactúa con en el lado de la puerta de enlace no admite Skype para control de admisión de llamadas de Business Server. Por lo tanto, el servidor de mediación tiene que controlar las interacciones de ancho de banda en nombre de su mismo nivel de puerta de enlace. Siempre que sea posible, el servidor de mediación va a reservar ancho de banda de antemano. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada saliente a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este comportamiento puede provocar la saturación del ancho de banda, pero es la única forma de evitar las llamadas falsas.
  
La omisión de medios y la reserva del ancho de banda se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el servicio de control de admisión de llamadas en esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si el control de admisión de llamadas se usa para una llamada concreta que implica al servidor de mediación, que la llamada no puede emplear el desvío de medios.
  
Para obtener información detallada acerca de los medios de desvío o el control de admisión de llamadas, consulte [Plan para los medios de desvío en Skype para 2015 empresarial](media-bypass.md) o tiene [previsto para el control de admisión de llamadas en Skype para Business Server 2015](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 mejorado (E9-1-1) y servidor de mediación

El servidor de mediación tiene capacidades extendidas que puede interactuar correctamente con los proveedores de servicios Enhanced 9-1-1 (E9-1-1). No es necesario realizar ninguna configuración especial en el servidor de mediación. Las Extensiones SIP necesarias para la interacción de E9-1-1 son, de forma predeterminada, incluido en el protocolo SIP del servidor de mediación para sus interacciones con un par de puerta de enlace (puerta de enlace RTC, IP-PBX o la SBC de un proveedor de servicios de telefonía de Internet, incluido el servicio de E9-1-1 Proveedores de)
  
Si el tronco SIP a un proveedor de servicios E9-1-1 puede terminar en un grupo de servidor de mediación existente o requiere servidores de mediación independiente depende de si la SBC E9-1-1 puede interactuar con un grupo de servidores de mediación. Para obtener información detallada, vea [tronco m: n en Skype para Business Server 2015](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Omisión de medios y servidor de mediación

Desvío de medios es un Skype para la función de servidor empresarial que permite a un administrador configurar el enrutamiento de llamadas para flujo directamente entre el extremo de usuario y la puerta de enlace de telefónica conmutada (RTC) sin cruzar el servidor de mediación. Desvío de medios mejora la calidad de las llamadas mediante la reducción de latencia, traducción innecesario, posibilidad de pérdida de paquetes y el número de posibles puntos de error. Cuando un sitio remoto sin un servidor de mediación está conectado a un sitio central por uno o más vínculos WAN con ancho de banda restringido, el desvío de medios reduce el requisito de ancho de banda mediante la habilitación de medios desde un cliente en un sitio remoto a flujo directamente a su puerta de enlace local sin en primer lugar tener que fluyen a través de la WAN vincular a un servidor de mediación en el sitio central y realizar una copia. Esta reducción de procesamiento de medios también complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.
  
La omisión de medios y el servicio de control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.
  
## <a name="topologies-for-mediation-server"></a>Topologías para el servidor de mediación

De forma predeterminada, el Skype para Business Server, servidor de mediación se combina con el servidor Standard Edition, un grupo de servidores Front-End o aplicación de sucursal con funciones de supervivencia. Todos los servidores de mediación en un grupo de servidores Front-End debe configurarse de forma idéntica.
  
Cuando el rendimiento es un problema, puede ser preferible para implementar uno o varios servidores de mediación en un grupo dedicado independiente. Recomendamos que implementes un grupo independiente si estás implementando enlaces troncales SIP. 
  
Si implementa conexiones SIP directas a una puerta de enlace RTC completa que admite el desvío de medios y de carga de DNS equilibrio, un servidor de mediación independiente de grupo de servidores no es necesario. Esto es debido a que las puertas de enlace completa son capaces de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico desde cualquier servidor de mediación en un grupo de servidores.
  
También se recomienda instalar el servidor de mediación en un grupo de servidores Front-End cuando se han implementado el IP-PBX o conectarse para el controlador de borde de sesión de telefonía Server del proveedor de Internet (SBC), siempre y cuando se cumple alguna de las siguientes condiciones:
  
- El IP-PBX o SBC está configurado para recibir tráfico desde cualquier servidor de mediación del grupo de servidores y puede enrutar el tráfico uniformemente a todos los servidores de mediación en el grupo de servidores.
    
- El IP-PBX no admite el desvío de medios, pero el grupo de servidores Front-End que hospeda el servidor de mediación puede gestionar la transcodificación de voz para las llamadas a la que no se aplica el desvío de medios.
    
Puede usar Microsoft Lync Server 2013, herramienta de planeación para evaluar si el grupo de servidores Front-End donde desea colocar el servidor de mediación puede administrar la carga. Si el entorno no cumple estos requisitos, a continuación, debe implementar un grupo de servidores de mediación independiente.
  
En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados a través de un vínculo WAN. Servidor de mediación se combina en un grupo de servidores Front-End en el sitio 1. Los servidores de mediación en el sitio 1 controla la puerta de enlace RTC en el sitio 1 y la puerta de enlace en el sitio 2. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen la omisión habilitada.
  
**Ejemplo de sitios conectados mediante una red WAN vínculo con un servidor de mediación en el sitio 1 y una puerta de enlace RTC en el sitio 2**

![Puerta de enlace de WAN de topología de voz con servidor de mediación](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
En la siguiente figura muestra una topología simple donde el servidor de mediación se combina en grupo de servidores Front-End en el sitio 1 y tiene una conexión SIP directa a la IP-PBX en el sitio 1. En esta figura, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2. Se supone que existen Skype para usuarios profesionales en los sitios 1 y 2. También se supone que el IP-PBX tiene un procesador de medios asociados que se debe recorrer por todos los medios que se originan de Skype para los extremos de negocio antes de que se está enviando a los extremos de medios controlados por el IP-PBX. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a la puerta de enlace RTC y la PBX tienen la omisión de medios habilitada.
  
**Ejemplo de sitios conectados mediante una red WAN vínculo con un servidor de mediación en el sitio 1 y un sistema PBX en el sitio 2**

![PBX de WAN del servidor de mediación de topología de voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
La última figura en este tema muestra una topología donde está conectado el servidor de mediación para la SBC de un proveedor de servicios de telefonía de Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisiones de planificación para el servidor de mediación

En este tema se describe decisiones de planeación que debe tomar para la implementación de servidor de mediación,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación independientes o combinados?

De forma predeterminada, el servidor de mediación se combina en el servidor Standard Edition o un servidor Front-End en un grupo de servidores Front-End en las sedes centrales. La cantidad de llamadas por la red telefónica conmutada (RTC) que se pueden gestionar y la cantidad de equipos necesarios en el grupo dependerán de los siguientes factores:
  
- El número de mismo nivel de puerta de enlace que controla el grupo de servidores de mediación
    
- Los períodos de gran tráfico de esas puertas de enlace
    
- El porcentaje de llamadas cuyos medios omiten el servidor de mediación
    
Al planificar, asegúrate de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V no configuradas para la omisión de medios, además del procesamiento necesario para gestionar las interacciones de señalización para la cantidad de llamadas que es necesario admitir en las horas de más actividad. Si no hay suficiente CPU, a continuación, debe implementar un grupo de servidores independiente de los servidores de mediación; y las puertas de enlace RTC, IP-PBX y SBCs tendrá que se pueden dividir en subconjuntos que se controlan mediante los servidores de mediación combinado en un grupo de servidores y los servidores de mediación independiente en uno o varios grupos de servidores independientes.
  
Si ha implementado las puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBCs) que no admiten las capacidades correctas para interactuar con un grupo de servidores de mediación, incluidos los siguientes, a continuación, deben asociarse con un grupo de servidores independiente que consiste en de un único servidor de mediación:
  
- Llevar a cabo a través de los servidores de mediación en un grupo de servidores de equilibrio de carga de sistema de nombres de dominio (DNS) de capa de red (o enrutar el tráfico uniformemente a todos los servidores de mediación en un grupo de servidores)
    
- Aceptar el tráfico desde cualquier servidor de mediación en un grupo de servidores
    
Puede usar Microsoft Lync Server 2013, herramienta de planeación para evaluar si combinar el servidor de mediación con el grupo de servidores Front-End puede administrar la carga. Si el entorno no cumple estos requisitos, a continuación, debe implementar un grupo de servidores de mediación independiente.
  
### <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

 Los servidores de mediación en el sitio central pueden utilizarse para enrutar las llamadas de IP-PBX o puertas de enlace RTC en sitios de sucursal. Sin embargo, si implementa troncos SIP, debe implementar un servidor de mediación en el sitio donde se finaliza cada tronco. Contar con un servidor de mediación en el sitio central enrutar llamadas para un IP-PBX o la puerta de enlace RTC en un sitio de sucursal no requiere el uso de medios de desvío. Pero, si puedes habilitar la omisión de medios y así lo haces, se reducirá la latencia de la ruta de acceso a los medios y, por ello, mejorará la calidad de los medios, ya que la ruta de acceso a los medios ya no tendrá que seguir la ruta de acceso de señalización. Desvío de medios también reduce la carga de procesamiento en el grupo de servidores.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. Desvío de medios es compatible solo con productos y versiones que aparece al [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Si se requiere la resistencia de la sucursal, una aplicación de sucursal con funciones de supervivencia o una combinación de un servidor Front-End, un servidor de mediación y una puerta de enlace debe estar implementado en el sitio de sucursal. (La suposición de resistencia de la sucursal es que presencia y conferencia no son resistentes en el sitio). Para obtener orientación sobre planeación de voz de sitio de sucursal, consulte [Plan para la resistencia de Enterprise Voice en Skype para Business Server 2015](enterprise-voice-resiliency.md).
  
Para las interacciones con un IP-PBX, si el IP-PBX no admite correctamente anticipado interacciones de medios con varios diálogos iniciales y las interacciones de RFC 3960, puede haber algunas palabras del saludo para las llamadas entrantes de la IP-PBX a Skype para el recorte de la primera Extremos de negocio. Este problema puede ser más grave si un servidor de mediación en un sitio central es enrutamiento de llamadas para un sistema IP-PBX donde finaliza la ruta en un sitio de sucursal, ya que se necesita más tiempo para señalización para llevar a cabo. Si experimenta este comportamiento, la implementación de un servidor de mediación en el sitio de sucursal es la única forma para reducir el recorte de la primera primeras palabras.
  
Por último, si el sitio central tiene una PBX TDM, o si el IP-PBX no elimina la necesidad de una puerta de enlace de RTC, debe implementar una puerta de enlace en la ruta de llamada de conexión de servidor de mediación y el sistema PBX.
  
> [!NOTE]
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener información detallada, vea ["lado de recepción de escala mejoras en Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Para obtener más detalles sobre cómo habilitar RSS, mira la documentación de tu adaptador de red. 
  

