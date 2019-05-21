---
title: Componente de servidor de mediación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Obtenga información sobre los servidores de mediación de Skype empresarial Server, incluidas las topologías compatibles y sus relaciones con los troncos de M:N, la omisión de medios y el control de admisión de llamadas.
ms.openlocfilehash: 8c58e0b866d62e7dd1ea60888ba611d78328489f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276701"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente de servidor de mediación en Skype empresarial Server
 
Obtenga información sobre los servidores de mediación de Skype empresarial Server, incluidas las topologías compatibles y sus relaciones con los troncos de M:N, la omisión de medios y el control de admisión de llamadas.
  
Para implementar la telefonía IP empresarial, debe implementar uno o varios servidores de mediación. 
  
El servidor de mediación traduce la señalización entre la infraestructura de telefonía interna de la empresa y una puerta de enlace de red telefónica conmutada (RTC) o un tronco de protocolo de inicio de sesión (SIP). En algunas implementaciones, también convierte los propios medios entre estos puntos.
  
En el servidor de Skype empresarial, el servidor de mediación escucha en una única dirección de transporte TLS Mutual (MTLS). En la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados a los troncos. Todas las puertas de enlace calificadas necesitan compatibilidad con TLS, pero también pueden habilitar TCP. TCP es compatible con las puertas de enlace que no son compatibles con TLS.
  
Si también tiene una central de conmutación (PBX) existente en su entorno, el servidor de mediación controla las llamadas entre los usuarios de voz de empresa y la PBX. Si su PBX es IP-PBX, puede crear una conexión SIP directa entre la PBX y el servidor de mediación. Si su PBX es un PBX de división de tiempo (TDM), también debe implementar una puerta de enlace RTC entre el servidor de mediación y la PBX.
  
El servidor de mediación se encuentra en el servidor front-end de forma predeterminada. El servidor de mediación también se puede implementar en un grupo independiente.
  
## <a name="what-mediation-server-does"></a>Funciones del servidor de mediación

Las funciones principales del servidor de mediación son las siguientes:
  
- Cifrar y descifrar SRTP en el lado servidor de Skype empresarial. 
    
- Convertir SIP sobre TCP (para puertas de enlace que no admiten TLS) en SIP sobre Mutual TLS.
    
- Traducción de transmisiones de medios entre Skype empresarial Server y Gateway peer of the Media Server.
    
- Conectar clientes que están fuera de la red con componentes ICE internos, que habilitan el paso de los medios a través de NAT y los firewalls.
    
- Actuar como intermediario de los flujos de llamadas que no admite una puerta de enlace, como las llamadas de trabajadores remotos en una clien de telefonía IP empresarial.
    
- En implementaciones que incluyen enlaces troncales SIP, trabajar con el proveedor de servicios de enlaces troncales SIP para proporcionar compatibilidad con la RTC, con lo que se elimina la necesidad de una puerta de enlace RTC.
    
La siguiente ilustración muestra los protocolos de señalización y multimedia que usa el servidor de mediación al comunicarse con una puerta de enlace PSTN básica y la infraestructura de telefonía IP empresarial.
  
**Señalización y protocolos multimedia que usa el servidor de mediación**

![Diagrama de protocolos de servidor de mediación](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si está usando TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace PSTN y el servidor de mediación, le recomendamos que tome medidas para garantizar la seguridad y la privacidad de la red. 
  
## <a name="mn-trunk"></a>Tronco M:N

Skype empresarial Server admite flexibilidad en la definición de un tronco para el enrutamiento de llamadas. Un tronco es una asociación lógica entre un servidor de mediación y un número de puerto de escucha, con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos para la misma puerta de enlace. un servidor de mediación puede tener varios troncos en diferentes puertas de enlace. a la inversa, una puerta de enlace puede tener varios troncos en diferentes servidores de mediación.
  
Aún debe crear un tronco raíz al agregar una puerta de enlace a su topología de Skype empresarial con el generador de topologías. El número de puertas de enlace que un servidor de mediación dado puede controlar depende de la capacidad de procesamiento del servidor durante las horas de mayor actividad. Si implementa un servidor de mediación en hardware que cumpla los requisitos mínimos de hardware para Skype empresarial Server, según se describe en [requisitos del servidor para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), un servidor de mediación independiente puede controlar aproximadamente llamadas de 1000. El servidor de mediación realiza la transcodificación, pero sigue enrutando las llamadas para varias puertas de enlace incluso si las puertas de enlace no admiten la omisión de medios.
  
Al definir una ruta de llamada, especifica los troncos asociados a esa ruta, pero no especifica qué servidores de mediación están asociados a esa ruta. En su lugar, use el generador de topología para asociar troncos con servidores de mediación. En otras palabras, el enrutamiento determina qué tronco se debe usar para una llamada y, posteriormente, el servidor de mediación asociado con ese tronco se envía a través de la señalización de esa llamada.
  
El servidor de mediación se puede implementar como un grupo; Este grupo se puede colocar con un grupo de servidores front-end o se puede implementar como un grupo independiente. Cuando un servidor de mediación se encuentra con un grupo de servidores front-end, el tamaño del grupo puede ser de hasta 12 (el límite del tamaño del conjunto de registradores). Tomadas en conjunto, estas capacidades aumentan la confiabilidad y la flexibilidad de implementación para servidores de mediación, pero requieren capacidades similares a las siguientes:
  
- **Puerta de enlace RTC.** Una puerta de enlace certificada de Skype empresarial Server debe implementar el equilibrio de carga de DNS, lo que permite que una puerta de enlace de red de telefonía pública conmutada (RTC) válida actúe como equilibrado de carga para un grupo de servidores de mediación y, por lo tanto, equilibre la carga de las llamadas en el grupo. .
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación al SBC, el SBC puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección de SBC a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación del grupo. Esto puede conseguirse a través del equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa es conceder al proveedor de servicios las direcciones IP de todos los servidores de mediación en el grupo y el proveedor de servicios los aprovisionará en su SBC como un enlace SIP independiente para cada servidor de mediación. Después, el proveedor de servicios gestionará el equilibrio de carga para sus propios servidores. Es posible que no todos los proveedores de servicios o SBC admitan estas capacidades. Además, es posible que el proveedor de servicios exija cargos adicionales para esta capacidad. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección del grupo de servidores de mediación a la terminación SIP IP-PBX, el IP-PBX puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección desde el IP-PBX a la agrupación, el tráfico puede enviarse a cualquier servidor de mediación del grupo. Dado que la mayoría de las PBX IP no admiten el equilibrio de carga de DNS, recomendamos que se definan conexiones SIP directas individuales desde la PBX IP a cada servidor de mediación del grupo. La IP-PBX gestionará su propio equilibrio de carga al distribuir el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en la IP-PBX. Si un IP-PBX en particular admite este concepto de grupo de troncal y cómo se intersecta con la arquitectura de clúster y redundancia de IP-PBX, debe determinarse antes de decidir si un clúster de servidor de mediación puede interactuar correctamente con un IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con la que interactúa. Esto significa que todos los miembros del grupo obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay ninguna forma de segmentar el grupo para que algunos servidores de mediación se comuniquen con solo algunos pares de puertas de enlace para las llamadas salientes. Si tal segmentación es necesaria, se debe usar un grupo de servidores de mediación independiente. Por ejemplo, esto sucedería si las puertas de enlace RTC, los troncos SIP o las IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo, tal y como se ha explicado anteriormente en este mismo tema.
  
Una puerta de enlace RTC en particular, IP-PBX o un troncal del mismo nivel SIP puede enrutar a varios servidores o troncos de mediación. El número de puertas de enlace que puede controlar un determinado grupo de servidores de media depende del número de llamadas que usan la omisión de medios. Si una gran cantidad de llamadas usa omisión de medios, un servidor de mediación del grupo puede controlar muchas más llamadas, porque solo es necesario el procesamiento de la capa de señalización. 
  
## <a name="call-admission-control-and-mediation-server"></a>Servicio de control de admisión de llamadas y servidor de mediación

El servicio de control de admisión de llamadas (CAC) administra el establecimiento de sesiones en tiempo real según el ancho de banda disponible para evitar que la calidad de la experiencia (QoE) de los usuarios sea deficiente en las redes congestionadas. Para ello, el servidor de mediación es responsable de la administración del ancho de banda de sus dos interacciones en el servidor de Skype empresarial y en el lado de la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad de terminación para una llamada gestiona la reserva del ancho de banda. Los pares de puertas de enlace (puerta de enlace PSTN, IP-PBX, SBC) con los que interactúa el servidor de mediación en la puerta de enlace no admiten el control de admisión de Skype empresarial Server. Por lo tanto, el servidor de mediación tiene que controlar las interacciones de ancho de banda en nombre de su punto de conexión. Siempre que sea posible, el servidor de mediación reservará el ancho de banda por adelantado. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada saliente a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este comportamiento puede provocar la saturación del ancho de banda, pero es la única forma de evitar las llamadas falsas.
  
La omisión de medios y la reserva del ancho de banda se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el servicio de control de admisión de llamadas en esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se usa el control de admisión de llamadas para una llamada en particular que implica el servidor de mediación, esa llamada no puede emplear la omisión de medios.
  
Para obtener más información acerca de la omisión de medios o el control de admisión de llamadas, consulte [plan de omisión de medios en Skype empresarial](media-bypass.md) o [plan de control de admisión de llamadas en Skype empresarial Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 mejorado (E9-1-1) y servidor de mediación

El servidor de mediación tiene capacidades extendidas para que pueda interactuar correctamente con proveedores de servicios mejorados de 9-1-1 (E9-1). No se necesita ninguna configuración especial en el servidor de mediación. Las extensiones SIP necesarias para la interacción E9-1-1 se incluyen, de forma predeterminada, en el protocolo SIP del servidor de mediación para sus interacciones con una puerta de enlace PSTN (puerta de enlace PSTN, IP-PBX o el SBC de un proveedor de servicios de telefonía por Internet, incluido el servicio E9-1-1. Provide
  
Si el tronco de SIP a un proveedor de servicios de E9-1-1 puede finalizar en un grupo de servidores de inmediación existente o necesitarán servidores de mediación autónomos dependerá de si el SBC E9-1-1 puede interactuar con un grupo de servidores de mediación. Para obtener más información, consulte [M:N troncal en Skype empresarial Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Omisión de medios y servidor de mediación

La omisión de medios es una función de Skype empresarial Server que permite a un administrador configurar el enrutamiento de llamadas para que fluya directamente entre el extremo de usuario y la puerta de enlace de red telefónica conmutada (RTC) sin atravesar el servidor de mediación. La omisión de medios mejora la calidad de las llamadas al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y la cantidad de puntos posibles de error. Cuando un sitio remoto sin un servidor de mediación se conecta a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios disminuye el requisito de ancho de banda al permitir que los medios de un cliente de un sitio remoto fluyan directamente a su puerta de enlace local sin en primer lugar, debe transmitirse a través del vínculo WAN a un servidor de mediación del sitio central y viceversa. Esta reducción en el procesamiento de medios también complementa la capacidad del servidor de mediación de controlar varias puertas de enlace.
  
La omisión de medios y el servicio de control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.
  
## <a name="topologies-for-mediation-server"></a>Topologías para el servidor de mediación

El servidor de mediación de Skype para empresas se encuentra de forma predeterminada en el servidor Standard Edition, en un grupo frontal o en un equipo de sucursal con la supervivencia. Todos los servidores de mediación de un grupo de servidores front-end se deben configurar de la misma manera.
  
Cuando el rendimiento es un problema, puede ser preferible implementar uno o varios servidores de mediación en un grupo independiente dedicado. Recomendamos que implementes un grupo independiente si estás implementando enlaces troncales SIP. 
  
Si implementa conexiones SIP directas en una puerta de enlace PSTN calificada que admite la omisión de medios y el equilibrio de carga de DNS, no es necesario disponer de un grupo de servidores de mediación independiente. Esto se debe a que las puertas de enlace completas permiten el equilibrio de carga de DNS para un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.
  
También le recomendamos que Collocate el servidor de mediación en un grupo de servidores front-end cuando haya implementado PBX IP o conecte con un controlador de borde de sesión (SBC) de un proveedor de servicios de telefonía por Internet, siempre que se cumpla cualquiera de las siguientes condiciones:
  
- El IP-PBX o SBC está configurado para recibir tráfico de cualquier servidor de mediación del grupo y puede enrutar uniformemente el tráfico a todos los servidores de mediación del grupo.
    
- El IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.
    
Puede usar la herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end en el que desea Collocate el servidor de mediación puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.
  
En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados a través de un vínculo WAN. El servidor de mediación se encuentra en un grupo de servidores front-end en el sitio 1. Los servidores de mediación del sitio 1 controlan la puerta de enlace PSTN en el sitio 1 y la puerta de enlace en el sitio 2. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen la omisión habilitada.
  
**Ejemplo de sitios conectados por medio de un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**

![Puerta de enlace de WAN de topología de voz con servidor de mediación](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
En la siguiente figura se muestra una topología simple en la que el servidor de mediación se encuentra en el grupo de servidores front-end en el sitio 1 y tiene una conexión SIP directa con IP-PBX en el sitio 1. En esta ilustración, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2. Supongamos que existen usuarios de Skype empresarial en los dos sitios 1 y 2. También Supongamos que el IP-PBX tiene un procesador de medios asociado que deben atravesar todos los medios que se originan desde los puntos de conexión de Skype empresarial antes de que se envíen a los puntos de conexión multimedia controlados por el IP-PBX. En esta topología, la omisión de medios se habilita de forma global para usar la información del sitio y de la región, y los troncos a la puerta de enlace RTC y la PBX tienen la omisión de medios habilitada.
  
**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**

![PBX de WAN del servidor de mediación de topología de voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
En la última ilustración de este tema se muestra una topología en la que el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisiones de planificación para el servidor de mediación

En este tema se describen las decisiones de planificación que debe tomar para la implementación de su servidor de mediación.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediación colocada o independiente?

De forma predeterminada, el servidor de mediación se encuentra en el servidor Standard Edition o en el servidor front-end de un grupo front-end en los sitios centrales. La cantidad de llamadas por la red telefónica conmutada (RTC) que se pueden gestionar y la cantidad de equipos necesarios en el grupo dependerán de los siguientes factores:
  
- El número de puertas de enlace o gateways controladas por el grupo de servidores de mediación
    
- Los períodos de gran tráfico de esas puertas de enlace
    
- El porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación
    
Al planificar, asegúrate de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V no configuradas para la omisión de medios, además del procesamiento necesario para gestionar las interacciones de señalización para la cantidad de llamadas que es necesario admitir en las horas de más actividad. Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; y las puertas de enlace RTC, IP-PBX y SBCs deberán dividirse en subconjuntos que se controlan mediante servidores de mediación en un mismo grupo y los servidores de mediación independientes en uno o más grupos de servidores independientes.
  
Si ha implementado puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBCs) que no son compatibles con las funciones correctas para interactuar con un grupo de servidores de mediación, entre los que se incluyen los siguientes, deberán asociarse con un conjunto independiente que contenga de un solo servidor de mediación:
  
- Realizar el equilibrio de carga del sistema de nombres de dominio (DNS) de nivel de red en los servidores de mediación de un grupo (o bien enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo)
    
- Aceptar el tráfico de cualquier servidor de mediación de un grupo
    
Puede usar la herramienta de planeación de Microsoft Lync Server 2013, para evaluar si collocating el servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.
  
### <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

 Los servidores de mediación del sitio central se pueden usar para enrutar llamadas para IP-PBX o puertas de enlace RTC en sitios de sucursales. Sin embargo, si implementas los troncos SIP, debes implementar un servidor de mediación en el sitio en el que termina cada tronco. Tener un servidor de mediación en el sitio central las llamadas a una puerta de enlace IP o RTC en un sitio de sucursal no requieren el uso de la omisión de medios. Pero, si puedes habilitar la omisión de medios y así lo haces, se reducirá la latencia de la ruta de acceso a los medios y, por ello, mejorará la calidad de los medios, ya que la ruta de acceso a los medios ya no tendrá que seguir la ruta de acceso de señalización. La omisión de elementos multimedia también disminuye la carga de procesamiento en el grupo.
  
> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco. La omisión de contenido multimedia solo se admite con productos y versiones que se muestran en [el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Si se requiere resistencia al sitio de la sucursal, se debe implementar en el sitio de la sucursal un dispositivo de aplicación de media o una combinación de un servidor front-end, un servidor de mediación y una combinación. (La hipótesis con la resistencia de los sitios de las sucursales es que la presencia y las conferencias no son resistentes en el sitio). Para obtener instrucciones sobre el planeamiento de sitios de las sucursales de voz, consulte [planear la resistencia de telefonía IP empresarial en Skype empresarial Server](enterprise-voice-resiliency.md).
  
En el caso de interacciones con un IP-PBX, si el IP-PBX no admite correctamente interacciones de medios iniciales con varios cuadros de diálogo y interacciones de RFC 3960, puede recortar las primeras palabras del saludo para las llamadas entrantes desde la IP-PBX a Skype para Puntos de conexión empresariales. Este problema puede ser más grave si un servidor de mediación de un sitio central está enrutando las llamadas a un IP-PBX donde la ruta termina en un sitio de sucursal, porque se necesita más tiempo para que se complete la señalización. Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de la sucursal es la única forma de reducir el recorte de las primeras palabras.
  
Por último, si su sitio central tiene un sistema PBX con TDM, o si su IP-PBX no elimina la necesidad de una puerta de enlace RTC, debe implementar una puerta de enlace en la ruta de llamada y en el servidor PBX.
  
> [!NOTE]
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, vea ["mejoras en la escala del lado de recepción en Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red. 
  

