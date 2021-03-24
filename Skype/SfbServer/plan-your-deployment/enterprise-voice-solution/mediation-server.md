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
description: Obtenga información sobre los servidores de mediación en Skype Empresarial Server, incluidas sus topologías admitidas y sus relaciones con troncos M:N, desvío de medios y control de admisión de llamadas.
ms.openlocfilehash: ef95e03bb9cc604b50e0e417f8358f6d922a7819
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101356"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente de servidor de mediación en Skype Empresarial Server
 
Obtenga información sobre los servidores de mediación en Skype Empresarial Server, incluidas sus topologías admitidas y sus relaciones con troncos M:N, desvío de medios y control de admisión de llamadas.
  
Para implementar Telefonía IP empresarial, debe implementar uno o varios servidores de mediación. 
  
El servidor de mediación traduce la señalización entre la infraestructura Telefonía IP empresarial interna y una puerta de enlace de red telefónica conmutada (RTC) o un tronco del Protocolo de inicio de sesión (SIP). En algunas implementaciones, también traduce los medios en sí entre estos puntos.
  
En el lado de Skype Empresarial Server, el servidor de mediación escucha una sola dirección de transporte TLS mutua (MTLS). En el lado de la puerta de enlace, el servidor de mediación escucha en todos los puertos de escucha asociados asociados con troncos. Todas las puertas de enlace cualificadas deben admitir TLS, pero pueden estar habilitadas también para TCP. El protocolo TCP es compatible con puertas de enlace que no admiten TLS.
  
Si también tiene una central de conmutación (PBX) existente en su entorno, el servidor de mediación administra las llamadas entre Telefonía IP empresarial usuarios y la PBX. Si su PBX es una IP-PBX, puede crear una conexión SIP directa entre la PBX y el servidor de mediación. Si la PBX es una PBX multiplex (TDM) de división de tiempo, también debe implementar una puerta de enlace RTC entre el servidor de mediación y la PBX.
  
El servidor de mediación se asocia con el servidor front-end de forma predeterminada. El servidor de mediación también se puede implementar en un grupo independiente.
  
## <a name="what-mediation-server-does"></a>Qué hace el servidor de mediación

Las funciones principales del servidor de mediación son las siguientes:
  
- Cifrar y descifrar SRTP en el lado de Skype Empresarial Server. 
    
- Traducir SIP a través de TCP (para puertas de enlace que no admiten TLS) a SIP a través de TLS mutua.
    
- Traducción de secuencias multimedia entre Skype Empresarial Server y el mismo nivel de puerta de enlace del servidor de mediación.
    
- Conectar clientes que están fuera de la red a componentes internos de ICE, que permiten el cruce de medios de NAT y firewalls.
    
- Actuar como intermediario para flujos de llamadas que una puerta de enlace no admite, como llamadas de trabajadores remotos en un Telefonía IP empresarial clien.t
    
- En implementaciones que incluyen enlace troncal SIP, trabajar con el proveedor de servicios de enlace troncal SIP para proporcionar compatibilidad con RTC, lo que elimina la necesidad de una puerta de enlace RTC.
    
En la figura siguiente se muestran los protocolos de señalización y medios que usa el servidor de mediación al comunicarse con una puerta de enlace RTC básica y la infraestructura Telefonía IP empresarial medios.
  
**Señalización y protocolos multimedia que usa el servidor de mediación**

![Diagrama de protocolos de servidor de mediación](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Si usa TCP o RTP/RTCP (en lugar de SRTP o SRTCP) en la red entre la puerta de enlace RTC y el servidor de mediación, le recomendamos que tome medidas para garantizar la seguridad y privacidad de la red. 
  
## <a name="mn-trunk"></a>Tronco M:N

Skype Empresarial Server admite flexibilidad en la definición de un tronco para fines de enrutamiento de llamadas. Un tronco es una asociación lógica entre un servidor de mediación y un número de puerto de escucha, con una puerta de enlace y un número de puerto de escucha. Esto implica varias cosas: un servidor de mediación puede tener varios troncos en la misma puerta de enlace; un servidor de mediación puede tener varios troncos a puertas de enlace diferentes; Por el contrario, una puerta de enlace puede tener varios troncos a distintos servidores de mediación.
  
Todavía debe crear un tronco raíz al agregar una puerta de enlace a la topología de Skype Empresarial mediante el Generador de topologías. El número de puertas de enlace que un servidor de mediación determinado puede controlar depende de la capacidad de procesamiento del servidor durante las horas de mayor actividad. Si implementa un servidor de mediación en hardware que cumpla los requisitos mínimos de hardware para Skype Empresarial Server, como se describe en Requisitos de servidor para [Skype Empresarial Server 2015,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)un servidor de mediación independiente puede administrar aproximadamente 1000 llamadas. El servidor de mediación realiza la transcodificación, pero sigue enrutando llamadas para varias puertas de enlace incluso si las puertas de enlace no admiten la omisión de medios.
  
Al definir una ruta de llamada, se especifican los troncos asociados a esa ruta, pero no se especifica qué servidores de mediación están asociados a esa ruta. En su lugar, se usa el Generador de topologías para asociar troncos con servidores de mediación. En otras palabras, el enrutamiento determina qué tronco usar para una llamada y, posteriormente, el servidor de mediación asociado a ese tronco se envía la señalización de esa llamada.
  
El servidor de mediación se puede implementar como un grupo de servidores; este grupo puede colocarse con un grupo de servidores front-end o puede implementarse como un grupo independiente. Cuando un servidor de mediación se asocia con un grupo de servidores front-end, el tamaño del grupo puede ser como máximo 12 (el límite del tamaño del grupo de registradores). En conjunto, estas capacidades aumentan la confiabilidad y la flexibilidad de implementación para los servidores de mediación, pero requieren capacidades similares en lo siguiente:
  
- **Puerta de enlace RTC.** Una puerta de enlace calificada de Skype Empresarial Server debe implementar el equilibrio de carga dns, lo que permite que una puerta de enlace de red telefónica conmutada (RTC) calificada actúe como equilibrador de carga para un grupo de servidores de mediación y, por lo tanto, equilibrar la carga de las llamadas en todo el grupo.
    
- **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del grupo de servidores de mediación al SBC, el SBC puede recibir conexiones desde cualquier servidor de mediación del grupo. En la dirección del SBC al grupo de servidores, el tráfico se puede enviar a cualquier servidor de mediación del grupo. Esto puede conseguirse mediante el equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una alternativa es proporcionar al proveedor de servicios las direcciones IP de todos los servidores de mediación del grupo y el proveedor de servicios las aprovisionará en su SBC como un tronco SIP independiente para cada servidor de mediación. Después, el proveedor de servicios administrará el equilibrio de carga para sus propios servidores. No todos los proveedores de servicios y SBC admiten estas capacidades. Además, es posible que el proveedor de servicios exija costos adicionales. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.
    
- **IP-PBX.** En la dirección desde el grupo de servidores de mediación hasta la terminación SIP IP-PBX, la IP-PBX puede recibir conexiones desde cualquier servidor de mediación del grupo. En la dirección desde la IP-PBX al grupo de servidores, el tráfico se puede enviar a cualquier servidor de mediación del grupo. Dado que IP-PBXs no admiten el equilibrio de carga dns, se recomienda definir conexiones SIP directas individuales desde la IP-PBX a cada servidor de mediación del grupo. El sistema IP-PBX administrará su propio equilibrio de carga distribuyendo el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en el sistema IP-PBX. Debe determinarse si una IP-PBX determinada admite este concepto de grupo troncal y cómo se cruza con la propia arquitectura de agrupación y redundancia de IP-PBX antes de decidir si un clúster de servidor de mediación puede interactuar correctamente con una IP-PBX.
    
Un grupo de servidores de mediación debe tener una vista uniforme de la puerta de enlace del mismo nivel con la que interactúa. Esto significa que todos los miembros del grupo de servidores obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no hay forma de segmentar el grupo de modo que algunos servidores de mediación se comuniquen con solo determinados pares de puerta de enlace para las llamadas salientes. Si dicha segmentación es necesaria, debe usarse un grupo independiente de servidores de mediación. Por ejemplo, esto sucedería si las puertas de enlace RTC, troncos SIP o sistemas IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo de servidores, tal y como se ha explicado anteriormente en este mismo tema.
  
Una puerta de enlace RTC determinada, IP-PBX o el mismo nivel troncal SIP pueden enrutar a varios servidores de mediación o troncos. El número de puertas de enlace que puede controlar un grupo determinado de servidores de mediación depende del número de llamadas que usan la omisión de medios. Si un gran número de llamadas usan desvío de medios, un servidor de mediación del grupo de servidores puede controlar muchas más llamadas, ya que solo es necesario procesar la capa de señalización. 
  
## <a name="call-admission-control-and-mediation-server"></a>Sistema de control de admisión de llamadas y servidor de mediación

Control de admisión de llamadas (CAC), administra el establecimiento de sesiones en tiempo real, en función del ancho de banda disponible, para ayudar a evitar una mala calidad de la experiencia (QoE) para los usuarios de redes congestionadas. Para ello, el servidor de mediación es responsable de la administración del ancho de banda de sus dos interacciones en el lado de Skype Empresarial Server y en el lado de la puerta de enlace. En el servicio de control de admisión de llamadas, la entidad que finaliza una llamada controla la reserva del ancho de banda. Los sistemas del mismo nivel de puerta de enlace (puerta de enlace RTC, IP-PBX, SBC) con los que interactúa el servidor de mediación en el lado de la puerta de enlace no admiten el control de admisión de llamadas de Skype Empresarial Server. Por lo tanto, el servidor de mediación debe controlar las interacciones de ancho de banda en nombre de su par de puerta de enlace. Siempre que sea posible, el servidor de mediación reservará el ancho de banda por adelantado. Si no es posible (por ejemplo, si se desconoce la localidad del extremo multimedia definitivo de una llamada realizada a la puerta de enlace del mismo nivel, en el lado de la puerta de enlace), se reserva el ancho de banda cuando se establece la llamada. Este funcionamiento puede provocar la sobresuscripción del ancho de banda, pero es la única forma de evitar las llamadas falsas.
  
El desvío de medios y la reserva del ancho de banda se excluyen mutuamente. Si se emplea la omisión de medios para una llamada, el control de admisión de llamadas no se realiza para esa llamada. En este caso, se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda. Si se usa el control de admisión de llamadas para una llamada determinada que implica el servidor de mediación, esa llamada no puede usar la omisión de medios.
  
Para obtener más información sobre la omisión de medios o el control de admisión de llamadas, vea [Plan for media bypass in Skype for Business](media-bypass.md) o Plan for call admission control in Skype for Business [Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>9-1-1 mejorado (E9-1-1) y servidor de mediación

El servidor de mediación cuenta con capacidades ampliadas para poder interactuar correctamente con los proveedores de servicios de 9-1-1 mejorado (E9-1-1). No se necesita ninguna configuración especial en el servidor de mediación. Las extensiones SIP necesarias para la interacción E9-1-1 se incluyen, de forma predeterminada, en el protocolo SIP del servidor de mediación para sus interacciones con un par de puertas de enlace (puerta de enlace RTC, IP-PBX o SBC de un proveedor de servicios de telefonía por Internet, incluidos los proveedores de servicios E9-1-1)
  
Si el tronco SIP de un proveedor de servicios E9-1-1 puede finalizarse en un grupo de servidores de mediación existente o requerirá servidores de mediación independientes dependerá de si el SBC de E9-1-1 puede interactuar con un grupo de servidores de mediación. Para obtener más información, [vea tronco M:N en Skype Empresarial Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Desvío de medios y servidor de mediación

La omisión de medios es una funcionalidad de Skype Empresarial Server que permite a un administrador configurar el enrutamiento de llamadas para que fluya directamente entre el extremo de usuario y la puerta de enlace de la red telefónica conmutada (RTC) sin atravesar el servidor de mediación. La omisión de medios mejora la calidad de la llamada al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y el número de posibles puntos de error. Cuando un sitio remoto sin un servidor de mediación está conectado a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios reduce el requisito de ancho de banda al permitir que los medios de un cliente en un sitio remoto fluyan directamente a su puerta de enlace local sin tener que fluir primero a través del vínculo WAN a un servidor de mediación en el sitio central y atrás. Esta reducción en el procesamiento de medios también complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.
  
El desvío de medios y el control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa desvío de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.
  
## <a name="topologies-for-mediation-server"></a>Topologías para el servidor de mediación

Skype Empresarial Server, Mediation Server se asocia de forma predeterminada con el servidor Standard Edition, un grupo de servidores front-end o una aplicación de sucursal con funciones de supervivencia. Todos los servidores de mediación de un grupo de servidores front-end deben configurarse de forma idéntica.
  
Cuando el rendimiento es un problema, puede ser preferible implementar uno o más servidores de mediación en un grupo de servidores independiente dedicado. Definitivamente recomendamos un grupo de servidores independiente si está implementando el enlace troncal SIP. 
  
Si implementa conexiones SIP directas en una puerta de enlace RTC calificada que admita la omisión de medios y el equilibrio de carga DNS, no es necesario un grupo de servidores de mediación independiente. Esto se debe a que las puertas de enlace calificadas son capaces de equilibrar la carga de DNS en un grupo de servidores de mediación y pueden recibir tráfico de cualquier servidor de mediación de un grupo.
  
También se recomienda colocar el servidor de mediación en un grupo de servidores front-end cuando haya implementado IP-PBXs o conectarse al controlador de borde de sesión (SBC) de un proveedor de telefonía por Internet, siempre y cuando se cumple cualquiera de las siguientes condiciones:
  
- El sistema IP-PBX o SBC esté configurado para recibir tráfico de cualquier servicio de mediación del grupo de servidores y pueda enrutar el tráfico uniformemente a todos los servidores de mediación del grupo.
    
- La IP-PBX no admite la omisión de medios, pero el grupo de servidores front-end que hospeda el servidor de mediación puede controlar la transcodificación de voz para las llamadas a las que no se aplica la omisión de medios.
    
Puede usar microsoft Lync Server 2013, herramienta de planeación para evaluar si el grupo de servidores front-end donde desea colocar el servidor de mediación puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.
  
En la siguiente figura se muestra una topología sencilla que consta de dos sitios conectados mediante un vínculo WAN. El servidor de mediación se coloca en un grupo de servidores front-end en el sitio 1. Los servidores de mediación del sitio 1 controlan tanto la puerta de enlace RTC en el sitio 1 como la puerta de enlace en el sitio 2. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a cada una de las puertas de enlace RTC (GW1 y GW2) tienen el desvío habilitado.
  
**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y una puerta de enlace RTC en el Sitio 2**

![Topología de voz con puerta de enlace WAN del servidor de mediación](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
La siguiente figura muestra una topología sencilla donde el servidor de mediación se coloca en el grupo de servidores front-end en el sitio 1 y tiene una conexión SIP directa a la IP-PBX en el sitio 1. En esta figura, el servidor de mediación también controla una puerta de enlace RTC en el sitio 2. Suponga que los usuarios de Skype Empresarial existen en los sitios 1 y 2. Asimismo, supongamos que la IP-PBX tiene un procesador multimedia asociado que debe recorrer todos los medios que se originaron en los puntos de conexión de Skype Empresarial antes de enviarse a extremos multimedia controlados por la IP-PBX. En esta topología, el desvío de medios se habilita globalmente para usar la información de sitio y de región, y los troncos a la puerta de enlace RTC y al PBX tienen el desvío de medios habilitado.
  
**Ejemplo de sitios conectados mediante un vínculo WAN con un servidor de mediación en el Sitio 1 y un sistema PBX en el Sitio 2**

![PBX WAN del servidor de mediación de topología de voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
La última figura de este tema muestra una topología donde el servidor de mediación está conectado al SBC de un proveedor de servicios de telefonía por Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Decisiones de planeación para el servidor de mediación

En este tema se describen las decisiones de planeación que debe tomar para la implementación del servidor de mediación,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>¿Servidor de mediación local o independiente?

El servidor de mediación se combina de forma predeterminada en el servidor Standard Edition o en el servidor front-end de un grupo de servidores front-end en los sitios centrales. El número de llamadas de red telefónica conmutada (RTC) que se pueden controlar y el número de máquinas necesarias en el grupo dependerá de lo siguiente:
  
- El número de sistemas del mismo nivel de puerta de enlace que controla el grupo de servidores de mediación
    
- Los períodos de tráfico de alto volumen a través de esas puertas de enlace
    
- Porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación
    
Al planear, asegúrese de tener en cuenta los requisitos de procesamiento multimedia para llamadas RTC y conferencias A/V que no están configurados para la omisión de medios, así como el procesamiento necesario para controlar las interacciones de señalización para el número de llamadas de hora de disponibilidad que deben ser compatibles. Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; y las puertas de enlace RTC, IP-PBX y SBC tendrán que dividirse en subconjuntos controlados por los servidores de mediación de un grupo de servidores y los servidores de mediación independientes en uno o varios grupos de servidores independientes.
  
Si implementó puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBC) que no admiten las capacidades correctas para interactuar con un grupo de servidores de mediación, incluidos los siguientes, tendrán que asociarse a un grupo independiente que consta de un único servidor de mediación:
  
- Realizar el equilibrio de carga del Sistema de nombres de dominio (DNS) de la capa de red entre los servidores de mediación de un grupo (o bien enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo de servidores)
    
- Aceptar tráfico de cualquier servidor de mediación de un grupo de servidores
    
Puede usar la Herramienta de planeación de Microsoft Lync Server 2013 para evaluar si la asociación del servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.
  
### <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y las sucursales

 Los servidores de mediación del sitio central se pueden usar para enrutar llamadas a puertas de enlace RTC o IP-PBX en las sucursales. Sin embargo, si implementa troncos SIP, deberá implementar un servidor de mediación en el sitio donde termina cada tronco. Para que un servidor de mediación del sitio central enrute las llamadas a una puerta de enlace RTC o IP-PBX en una sucursal, no es necesario usar desvío de medios. Sin embargo, si puede habilitar la omisión de medios, si lo hace, reducirá la latencia de la ruta de acceso multimedia y mejorará la calidad de los medios, ya que la ruta de acceso multimedia ya no es necesaria para seguir la ruta de señalización. La omisión de medios también disminuye la carga de procesamiento en el grupo.
  
> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones enumerados en el Programa de interoperabilidad abierta de comunicaciones unificadas [- Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). 
  
Si se necesita resistencia en la sucursal, se debe implementar una aplicación de sucursal con funciones de supervivencia o una combinación de servidor front-end, servidor de mediación y puerta de enlace en la sucursal. (La suposición con la resistencia del sitio de sucursal es que la presencia y las conferencias no son resistentes en el sitio). Para obtener instrucciones sobre la planeación de sitios de sucursal para voz, [vea Plan for Telefonía IP empresarial resiliency in Skype for Business Server](enterprise-voice-resiliency.md).
  
En el caso de las interacciones con una IP-PBX, si la IP-PBX no admite correctamente las interacciones de medios tempranos con varios cuadros de diálogo iniciales y las interacciones rfc 3960, puede haber recorte de las primeras palabras del saludo para las llamadas entrantes de ip-PBX a puntos de conexión de Skype Empresarial. Este problema puede ser más grave si un servidor de mediación de un sitio central está enrutando llamadas para una IP-PBX donde la ruta finaliza en un sitio de sucursal, ya que se necesita más tiempo para que se complete la señalización. Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de sucursal es la única manera de reducir el recorte de las primeras palabras.
  
Por último, si el sitio central tiene un PBX TDM, o si el IP-PBX no evita la necesidad de una puerta de enlace RTC, deberá implementar una puerta de enlace en la ruta de la llamada para conectar el servidor de mediación y el PBX.
  
> [!NOTE]
> Para mejorar el rendimiento multimedia del servidor de mediación independiente, debe habilitar el escalado del lado de recepción (RSS) en los adaptadores de red de estos servidores. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, consulta "Mejoras de [escalado del lado de recepción en Windows Server".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Para obtener más información sobre cómo habilitar RSS, consulte la documentación del adaptador de red. 
