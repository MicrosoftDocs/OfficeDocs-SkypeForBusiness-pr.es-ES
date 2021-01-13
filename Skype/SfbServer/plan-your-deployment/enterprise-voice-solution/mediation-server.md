---
title: Componente de servidor de mediación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Obtenga información sobre los servidores de mediación de Skype Empresarial Server, incluidas sus topologías compatibles y sus relaciones con troncos M:N, desvío de medios y control de admisión de llamadas.
ms.openlocfilehash: 14cf5fff38146622467698ffa58ccb244fac8fad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813680"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente de servidor de mediación en Skype Empresarial Server
 
Obtenga información sobre los servidores de mediación de Skype Empresarial Server, incluidas sus topologías compatibles y sus relaciones con troncos M:N, desvío de medios y control de admisión de llamadas.
  
Para implementar Telefonía IP empresarial, debe implementar uno o más servidores de mediación. 
  
El servidor de mediación traduce la señalización entre la infraestructura Telefonía IP empresarial interna y una puerta de enlace de red telefónica conmutada (RTC) o un tronco sip (Protocolo de inicio de sesión). En algunas implementaciones, también traduce los medios en sí entre estos puntos.
  
En el lado de Skype Empresarial Server, el servidor de mediación escucha en una única dirección de transporte TLS mutua (MTLS). En el lado de la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados asociados con troncos. Todas las puertas de enlace cualificadas deben admitir TLS, pero pueden estar habilitadas también para TCP. El protocolo TCP es compatible con puertas de enlace que no admiten TLS.
  
Si también tiene una central de conmutación pública (PBX) existente en su entorno, el servidor de mediación administra las llamadas entre Telefonía IP empresarial usuarios y la PBX. Si su PBX es una IP-PBX, puede crear una conexión SIP directa entre la PBX y el servidor de mediación. Si su PBX es una PBX de multiplexación de división de tiempo (TDM), también debe implementar una puerta de enlace RTC entre el servidor de mediación y la PBX.
  
El servidor de mediación se coloca con el servidor front-end de forma predeterminada. El servidor de mediación también se puede implementar en un grupo independiente.
  
## <a name="what-mediation-server-does"></a>Qué hace el servidor de mediación

Las funciones principales del servidor de mediación son las siguientes:
  
- Cifrar y descifrar SRTP en el lado de Skype Empresarial Server. 
    
- Convertir SIP sobre TCP (para puertas de enlace que no admiten TLS) a SIP sobre TLS mutua.
    
- Traducción de secuencias multimedia entre Skype Empresarial Server y la puerta de enlace del mismo nivel del servidor de mediación.
    
- Conectar clientes que están fuera de la red a componentes internos de ICE, lo que permite el cruce seguro de medios de NAT y firewalls.
    
- Actuar como intermediario para flujos de llamadas que una puerta de enlace no admite, como llamadas de trabajadores remotos en un Telefonía IP empresarial clien.t
    
- En implementaciones que incluyen enlace troncal SIP, trabajar con el proveedor de servicios de enlace troncal SIP para proporcionar compatibilidad con RTC, lo que elimina la necesidad de una puerta de enlace RTC.
    
En la figura siguiente se muestran los protocolos de señalización y medios que usa el servidor de mediación al comunicarse con una puerta de enlace RTC básica y la infraestructura Telefonía IP empresarial cliente.
  
**Señalización y protocolos multimedia que usa el servidor de mediación**

![Diagrama de protocolos de servidor de mediación](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si usa TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace RTC y el servidor de mediación, le recomendamos que tome medidas para ayudar a garantizar la seguridad y privacidad de la red. 
  
## <a name="mn-trunk"></a>Tronco M:N

Skype Empresarial Server admite flexibilidad en la definición de un tronco para el enrutamiento de llamadas. Un tronco es una asociación lógica entre un servidor de mediación y un número de puerto de escucha, con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos a la misma puerta de enlace; Un servidor de mediación puede tener varios troncos a puertas de enlace diferentes; Por el contrario, una puerta de enlace puede tener varios troncos a diferentes servidores de mediación.
  
Todavía debe crear un tronco raíz cuando agregue una puerta de enlace a la topología de Skype Empresarial con topology Builder. El número de puertas de enlace que un servidor de mediación determinado puede controlar depende de la capacidad de procesamiento del servidor durante las horas de mayor actividad. Si implementa un servidor de mediación en hardware que cumpla los requisitos mínimos de hardware para Skype Empresarial Server, como se describe en Requisitos de servidor para Skype Empresarial [Server 2015,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)un servidor de mediación independiente puede administrar aproximadamente 1000 llamadas. El servidor de mediación realiza la transcodificación, pero sigue enrutando las llamadas de varias puertas de enlace incluso si las puertas de enlace no admiten la omisión de medios.
  
Al definir una ruta de llamada, se especifican los troncos asociados a dicha ruta, pero no se especifican los servidores de mediación asociados a esa ruta. En su lugar, use topology Builder para asociar troncos con servidores de mediación. En otras palabras, el enrutamiento determina qué tronco usar para una llamada y, posteriormente, se envía la señalización para esa llamada al servidor de mediación asociado con ese tronco.
  
El servidor de mediación se puede implementar como un grupo de servidores; este grupo se puede colocar con un grupo de servidores front-end o puede implementarse como un grupo independiente. Cuando un servidor de mediación se coloca con un grupo de servidores front-end, el tamaño del grupo puede ser como máximo 12 (el límite del tamaño del grupo de registrador). En conjunto, estas capacidades aumentan la confiabilidad y la flexibilidad de implementación para los servidores de mediación, pero requieren funcionalidades similares en lo siguiente:
  
- **Puerta de enlace RTC.** Una puerta de enlace cualificada de Skype Empresarial Server debe implementar el equilibrio de carga dns, lo que permite a una puerta de enlace de red telefónica conmutada (RTC) cualificada actuar como equilibrador de carga para un grupo de servidores de mediación y, por lo tanto, equilibrar la carga de las llamadas en todo el grupo.
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación al SBC, el SBC puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección del SBC al grupo de servidores, el tráfico se puede enviar a cualquier servidor de mediación del grupo. Esto puede conseguirse mediante el equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa es proporcionar al proveedor de servicios las direcciones IP de todos los servidores de mediación del grupo de servidores y el proveedor de servicios las aprovisionará en su SBC como un tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios administrará el equilibrio de carga para sus propios servidores. No todos los proveedores de servicios y SBC admiten estas capacidades. Además, es posible que el proveedor de servicios exija costos adicionales. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección desde el grupo de servidores de mediación hasta la terminación SIP de IP-PBX, la IP-PBX puede recibir conexiones de cualquier servidor de mediación del grupo. En la dirección desde la IP-PBX al grupo de servidores, el tráfico se puede enviar a cualquier servidor de mediación del grupo. Dado que la IP-PBXs no admite el equilibrio de carga de DNS, se recomienda definir conexiones SIP directas individuales desde la IP-PBX a cada servidor de mediación del grupo. El sistema IP-PBX administrará su propio equilibrio de carga distribuyendo el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en el sistema IP-PBX. Es necesario determinar si un IP-PBX determinado admite este concepto de grupo troncal y cómo se interseca con la arquitectura de agrupación en clústeres y redundancia de IP-PBX antes de decidir si un clúster de servidores de mediación puede interactuar correctamente con una IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con la que interactúa. Esto significa que todos los miembros del grupo de servidores obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay ninguna manera de segmentar el grupo de servidores para que algunos servidores de mediación se comuniquen solo con determinados sistemas del mismo nivel de puerta de enlace para las llamadas salientes. Si dicha segmentación es necesaria, debe usarse un grupo de servidores de mediación independiente. Por ejemplo, esto sucedería si las puertas de enlace RTC, troncos SIP o sistemas IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo de servidores, tal y como se ha explicado anteriormente en este mismo tema.
  
Una puerta de enlace RTC determinada, IP-PBX o tronco SIP del mismo nivel puede enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que un determinado grupo de servidores de mediación puede controlar depende del número de llamadas que usan la omisión de medios. Si un gran número de llamadas usa la omisión de medios, un servidor de mediación del grupo de servidores puede administrar muchas más llamadas, ya que solo es necesario procesar la capa de señalización. 
  
## <a name="call-admission-control-and-mediation-server"></a>Sistema de control de admisión de llamadas y servidor de mediación

El servicio de control de admisión de llamadas (CAC) administra el establecimiento de sesiones en tiempo real, en función del ancho de banda disponible, para ayudar a evitar una mala calidad de la experiencia (QoE) para los usuarios de redes congestionadas. Para ello, el servidor de mediación es responsable de la administración del ancho de banda de sus dos interacciones en el lado de Skype Empresarial Server y en el lado de la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad que finaliza una llamada controla la reserva del ancho de banda. Los sistemas del mismo nivel de puerta de enlace (puerta de enlace RTC, IP-PBX, SBC) con los que interactúa el servidor de mediación en el lado de la puerta de enlace no admiten el control de admisión de llamadas de Skype Empresarial Server. Por lo tanto, el servidor de mediación debe controlar las interacciones de ancho de banda en nombre de su punto de puerta de enlace. Siempre que sea posible, el servidor de mediación reservará el ancho de banda por adelantado. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada realizada a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este funcionamiento puede provocar la sobresuscripción del ancho de banda, pero es la única forma de evitar las llamadas falsas.
  
El desvío de medios y la reserva del ancho de banda se excluyen mutuamente. Si se utiliza la omisión de medios para una llamada, no se realiza el control de admisión de llamadas para esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se usa el control de admisión de llamadas para una llamada determinada que implica al servidor de mediación, dicha llamada no puede emplear la omisión de medios.
  
Para obtener más información sobre la omisión de medios o el control de admisión de llamadas, consulte [Plan for media bypass in Skype for Business](media-bypass.md) o Plan for call admission control in Skype for Business [Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 mejorado (E9-1-1) y servidor de mediación

El servidor de mediación cuenta con capacidades ampliadas para poder interactuar correctamente con los proveedores de servicios de 9-1-1 mejorado (E9-1-1). No se necesita ninguna configuración especial en el servidor de mediación. De forma predeterminada, las extensiones SIP necesarias para la interacción con E9-1-1 se incluyen en el protocolo SIP del servidor de mediación para sus interacciones con una puerta de enlace del mismo nivel (puerta de enlace RTC, IP-PBX o SBC de un proveedor de servicios de telefonía por Internet, incluidos los proveedores de servicios E9-1-1)
  
Si el tronco SIP a un proveedor de servicios E9-1-1 puede finalizarse en un grupo de servidores de mediación existente o requerirá servidores de mediación independientes dependerá de si el SBC E9-1-1 puede interactuar con un grupo de servidores de mediación. Para obtener más información, [consulte tronco M:N en Skype Empresarial Server.](m-n-trunk.md)
  
## <a name="media-bypass-and-mediation-server"></a>Desvío de medios y servidor de mediación

La omisión de medios es una funcionalidad de Skype Empresarial Server que permite a un administrador configurar el enrutamiento de llamadas para que fluya directamente entre el extremo de usuario y la puerta de enlace de la red telefónica conmutada (RTC) sin atravesar el servidor de mediación. La omisión de medios mejora la calidad de las llamadas al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y el número de posibles puntos de error. Cuando un sitio remoto sin un servidor de mediación está conectado a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios reduce el requisito de ancho de banda al permitir que los medios de un cliente en un sitio remoto fluyan directamente a su puerta de enlace local sin tener que fluir primero a través del vínculo WAN a un servidor de mediación en el sitio central y hacia atrás. Esta reducción del procesamiento de medios también complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.
  
El desvío de medios y el control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa desvío de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.
  
## <a name="topologies-for-mediation-server"></a>Topologías para el servidor de mediación

Skype Empresarial Server, el servidor de mediación se coloca de forma predeterminada con un servidor Standard Edition, un grupo de servidores front-end o una aplicación de sucursal con funciones de supervivencia. Todos los servidores de mediación de un grupo de servidores front-end deben configurarse de forma idéntica.
  
Cuando el rendimiento es un problema, puede ser preferible implementar uno o más servidores de mediación en un grupo independiente dedicado. Definitivamente recomendamos un grupo de servidores independiente si está implementando el enlace troncal SIP. 
  
Si implementa conexiones SIP directas a una puerta de enlace RTC cualificada que admite la omisión de medios y el equilibrio de carga de DNS, no es necesario un grupo de servidores de mediación independiente. Esto se debe a que las puertas de enlace cualificadas son capaces de equilibrar la carga de DNS con un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo de servidores.
  
También se recomienda instalar el servidor de mediación en un grupo de servidores front-end cuando haya implementado IP-PBXs o conectarse al controlador de borde de sesión (SBC) de un proveedor de telefonía por Internet, siempre que se cumple alguna de las siguientes condiciones:
  
- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.
    
- La IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede administrar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.
    
Puede usar la Herramienta de planeación de Microsoft Lync Server 2013 para evaluar si el grupo de servidores front-end donde desea colocar el servidor de mediación puede administrar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.
  
En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados mediante un vínculo WAN. El servidor de mediación se coloca en un grupo de servidores front-end en el sitio 1. Los servidores de mediación del sitio 1 controlan tanto la puerta de enlace RTC del sitio 1 como la puerta de enlace del sitio 2. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen el desvío habilitado.
  
**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**

![Topología de voz con puerta de enlace WAN del servidor de mediación](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
En la figura siguiente se muestra una topología sencilla en la que el servidor de mediación se coloca en el grupo de servidores front-end del sitio 1 y tiene una conexión SIP directa a la IP-PBX en el sitio 1. En esta figura, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2. Supongamos que los usuarios de Skype Empresarial existen en los sitios 1 y 2. Asimismo, suponga que la IP-PBX tiene un procesador de medios asociado que deben atravesar todos los medios procedentes de puntos de conexión de Skype Empresarial antes de ser enviados a extremos de medios controlados por la IP-PBX. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a la puerta de enlace RTC y al PBX tienen el desvío de medios habilitado.
  
**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**

![PBX WAN del servidor de mediación de topología de voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
La última figura de este tema muestra una topología en la que el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisiones de planeación para el servidor de mediación

En este tema se describen las decisiones de planeación que debe tomar para la implementación del servidor de mediación.
  
### <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación local o independiente?

El servidor de mediación se combina de forma predeterminada en el servidor Standard Edition o en el servidor front-end de un grupo de servidores front-end en los sitios centrales. El número de llamadas de red telefónica conmutada (RTC) que se pueden controlar y el número de máquinas necesarias en el grupo de servidores dependerán de lo siguiente:
  
- El número de puertas de enlace del mismo nivel que controla el grupo de servidores de mediación
    
- Los períodos de tráfico de gran volumen a través de esas puertas de enlace
    
- Porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación
    
Al planear, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y conferencias A/V que no están configuradas para la omisión de medios, así como el procesamiento necesario para controlar las interacciones de señalización para el número de llamadas en hora punta que deben ser compatibles. Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; y las puertas de enlace RTC, LAS IP-PBX y los SBC tendrán que dividirse en subconjuntos controlados por los servidores de mediación situados en un grupo de servidores y los servidores de mediación independientes en uno o más grupos de servidores independientes.
  
Si implementó puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBC) que no admiten las capacidades correctas para interactuar con un grupo de servidores de mediación, incluidos los siguientes, deberá asociarse a un grupo de servidores independiente formado por un único servidor de mediación:
  
- Realizar el equilibrio de carga del Sistema de nombres de dominio (DNS) de la capa de red entre los servidores de mediación de un grupo de servidores (o enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo de servidores)
    
- Aceptar tráfico de cualquier servidor de mediación de un grupo de servidores
    
Puede usar la Herramienta de planeación de Microsoft Lync Server 2013 para evaluar si la instalación del servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.
  
### <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y las sucursales

 Los servidores de mediación del sitio central se pueden usar para enrutar llamadas a puertas de enlace RTC o IP-PBX en las sucursales. Sin embargo, si implementa troncos SIP, deberá implementar un servidor de mediación en el sitio donde termina cada tronco. Para que un servidor de mediación del sitio central enrute las llamadas a una puerta de enlace RTC o IP-PBX en una sucursal, no es necesario usar desvío de medios. Sin embargo, si puede habilitar la omisión de medios, si lo hace, se reducirá la latencia de la ruta de acceso multimedia y se mejorará la calidad de los medios, ya que ya no es necesario seguir la ruta de acceso de señalización. La omisión de medios también reduce la carga de procesamiento en el grupo de servidores.
  
> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco. La omisión de medios solo se admite con los productos y versiones enumerados en el Programa de comunicaciones unificadas [de interoperabilidad abierta - Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Si se necesita resistencia en la sucursal, se debe implementar una aplicación de sucursal con funciones de supervivencia o una combinación de servidor front-end, servidor de mediación y puerta de enlace en la sucursal. (La suposición con resistencia de sitios de sucursal es que la presencia y las conferencias no son resistentes en el sitio). For guidance on branch site planning for voice, see [Plan for Telefonía IP empresarial resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
  
En el caso de las interacciones con una IP-PBX, si la IP-PBX no admite correctamente las interacciones de medios iniciales con varios cuadros de diálogo iniciales e interacciones RFC 3960, puede haber un recorte de las primeras palabras del saludo para las llamadas entrantes desde la IP-PBX a los extremos de Skype Empresarial. Este problema puede ser más grave si un servidor de mediación de un sitio central enruta las llamadas de una IP-PBX en la que la ruta finaliza en un sitio de sucursal, ya que se necesita más tiempo para que se complete la señalización. Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de sucursal es la única forma de reducir el recorte de las primeras palabras.
  
Por último, si el sitio central tiene un PBX TDM, o si el IP-PBX no evita la necesidad de una puerta de enlace RTC, deberá implementar una puerta de enlace en la ruta de la llamada para conectar el servidor de mediación y el PBX.
  
> [!NOTE]
> Para mejorar el rendimiento multimedia del servidor de mediación independiente, debe habilitar el ajuste de escala del lado de recepción (RSS) en los adaptadores de red de estos servidores. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, consulte "Mejoras de escalado del lado [de recepción en Windows Server".](https://go.microsoft.com/fwlink/p/?LinkId=268731) Para obtener más información sobre cómo habilitar RSS, consulte la documentación del adaptador de red. 
  

