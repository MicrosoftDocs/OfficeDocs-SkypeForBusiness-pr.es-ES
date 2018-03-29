---
title: Enlace troncal SIP en Skype Empresarial Server 2015
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Conozca más acerca de SIP trunking en Skype para Business Server Telefonía IP empresarial
ms.openlocfilehash: 434e013e2ee7d0d6736b39546ba7921aa15cdee3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sip-trunking-in-skype-for-business-server-2015"></a>Enlace troncal SIP en Skype Empresarial Server 2015
 
Conozca más acerca de SIP trunking en Skype para Business Server Telefonía IP empresarial
  
El Protocolo de inicio de sesión (SIP) se usa para iniciar y administrar sesiones de comunicaciones de voz sobre IP (VoIP) del servicio telefónico básico y para otros servicios de comunicación en tiempo real, como la mensajería instantánea, las conferencias, la detección de presencia y los elementos multimedia. Esta sección proporciona información de planificación de la implementación de troncos SIP, un tipo de conexión de SIP que se extiende más allá de los límites de la red local.
  
## <a name="what-is-sip-trunking"></a>¿Qué es el enlace troncal SIP?

Un tronco SIP es una conexión IP que establece un vínculo de comunicaciones SIP entre la organización y un proveedor de servicios de telefonía por Internet (ITSP) más allá del firewall. Normalmente, un tronco SIP se utiliza para conectar el sitio central de su organización con un ITSP. En ciertos casos, se puede usar también el enlace troncal SIP para conectar un sitio de sucursal a un ITSP.
  
Implementación de Troncalización SIP puede ser un gran paso hacia la simplificación de telecomunicaciones de la organización y preparación para obtener mejoras actualizadas de comunicaciones en tiempo real. Una de las principales ventajas de Troncalización SIP es que puede consolidar las conexiones de la organización a la red telefónica pública conmutada (PSTN) en una sitio central, a diferencia de su predecesor, tiempo division multiplexing (TDM) la Troncalización, que normalmente requiere un tronco independiente de cada sitio de sucursal.
  
### <a name="cost-savings"></a>Ahorro económico

El ahorro económico inherente al enlace troncal SIP puede ser considerable:
  
- El coste de las llamadas de larga distancia suele ser mucho menor con un tronco SIP.
    
- Es posible reducir tanto los costes de manejabilidad como la complejidad de la implementación.
    
- Las tasas de interfaz de acceso básica (BRI) y de interfaz de acceso principal (PRI) se pueden evitar si se conecta un tronco SIP directamente al ITSP, a un coste visiblemente menor. En los enlaces troncales TDM, los proveedores de servicios establecen el cargo de las llamadas por minuto. El coste del enlace troncal SIP se puede basar en el uso de ancho de banda, que puede comprarse en incrementos más pequeños y, por tanto, más económicos (el coste real depende del modelo de servicio del ITSP que elijas).
    
#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Enlace troncal SIP en comparación con el hospedaje de una puerta de enlace RTC o PBX IP

Como los troncos SIP se conectan directamente al proveedor de servicios, se puede prescindir de las puertas de enlace RTC y, en consecuencia, del coste de administración y complejidad que estas conllevan. El uso de un tronco SIP se traduce en un ahorro económico muy significativo, ya que requiere menos mantenimiento y administración. 
  
### <a name="expanded-voip-services"></a>Servicios de VoIP ampliados

Con frecuencia, las características de voz constituyen la principal motivación para implementar un enlace troncal SIP, si bien la compatibilidad de voz es solo el primer paso. Con Troncalización SIP, puede ampliar las capacidades de VoIP y habilitar Skype para Business Server ofrecer un conjunto más amplio de servicios. Por ejemplo:
  
- Detección de presencia mejorada para los dispositivos que no ejecutan Skype para Business Server puede proporcionar una mejor integración con los teléfonos móviles, lo que permite ver cuando un usuario está en una llamada de teléfono móvil.
    
- Llamada de emergencia E9-1-1 permite a las autoridades que responda a las llamadas al 911 para determinar la ubicación del llamador de su número de teléfono.
    
> [!NOTE]
> Ponte en contacto con tu ITSP para obtener una lista de los servicios que este admite y que puedes habilitar en tu organización. 
  
### <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP en comparación con conexiones SIP directas

El tronco del término se deriva de la tecnología de conmutación de circuitos. Se refiere a una línea física dedicada que conecta el equipo de conmutación telefónica. Al igual que su predecesor, división de tiempo multiplexación troncos (TDM), troncos SIP son las conexiones entre dos redes independientes de SIP: la Skype para Business Server enterprise y el ITSP. A diferencia de los troncos de circuitos conmutados, los troncos SIP son conexiones virtuales que se pueden establecer sobre cualquiera de los tipos de conexión de enlaces troncales SIP compatibles.
  
Por otra parte, las conexiones SIP directas son conexiones SIP que no cruzan los límites de la red local (es decir, que se conectan a una puerta de enlace de la red telefónica conmutada [RTC] o a una central de conmutación [PBX] dentro de la red local). Para obtener más información acerca de cómo utilizar conexiones SIP directas con Skype para Business Server, consulte [conexiones SIP directo en Skype para Business Server 2015](direct-sip.md). 
  
## <a name="how-do-i-implement-sip-trunking"></a>¿Cómo puedo implementar el enlace troncal SIP?

Para implementar la Troncalización SIP, debe distribuir la conexión a través de un servidor de mediación, que actúa como un proxy para la sesiones de comunicación entre Skype para clientes Business Server y el proveedor de servicios y transcodifica medios, cuando sea necesario.
  
Cada servidor de mediación tiene una interfaz de red interna y una interfaz de red externa. La interfaz interna se conecta a los servidores frontales. La interfaz externa se suele denominar la interfaz de puerta de enlace porque tradicionalmente se ha utilizado para conectar el servidor de mediación con una puerta de enlace de telefonía pública conmutada (PSTN) de red o una IP-PBX. Para implementar un troncal SIP, se conecta la interfaz externa del servidor de mediación para el componente de contorno externo de la ITSP. El componente de contorno externo de la ITSP podría ser un controlador de borde de sesión (SBC), un enrutador o una puerta de enlace.
  
Para obtener más información acerca de los servidores de mediación, vea [componentes de servidor de mediación en Skype para Business Server 2015](mediation-server.md). 
  
### <a name="centralized-vs-distributed-sip-trunking"></a>Enlace troncal SIP centralizado en comparación con uno distribuido

Troncalización SIP centralizada enruta todo el tráfico de VoIP, incluido el tráfico del sitio de sucursal, a través del sitio central. El modelo de implementación centralizada es simple, rentable y generalmente es el enfoque recomendado para implementar los troncos SIP con Skype para Business Server.
  
Troncalización SIP distribuida es un modelo de implementación en el que implementar los troncos SIP locales en uno o más sitios de sucursal. A continuación, se enruta tráfico de VoIP desde el sitio de la sucursal directamente a un proveedor de servicios sin tener que pasar a través del sitio central.
  
El enlace troncal SIP distribuido solo es necesario en los siguientes casos: 
  
- El sitio de sucursal requiere conectividad de teléfono que puede perdurar (por ejemplo, si la WAN deja de funcionar). Este requisito se debe analizar para cada sitio de la sucursal; algunas de las ramas pueden requerir redundancia y conmutación por error, mientras que otros no.
    
- Resiliencia es necesaria entre dos sitios centrales. Debe asegurarse de que finaliza un troncal SIP en cada sitio central. Por ejemplo, si tiene sitios centrales de Dublín y Tukwila y ambos utilizan el tronco SIP de un solo sitio, si el tronco deja de funcionar, los demás usuarios del sitio no pueden realizar llamadas PSTN.
    
- El sitio de sucursal y el sitio central están en distintos países o regiones. Por motivos legales y de compatibilidad, necesitas al menos un tronco SIP por cada país o región. Así, por ejemplo, en la Unión Europea las comunicaciones no pueden dejar un país o una región sin que terminen localmente en un punto centralizado.
    
Dependiendo de la ubicación geográfica de sitios y no desea enrutar todos los usuarios a través de la central troncal SIP cuánto tráfico prevé dentro de su empresa, o puede optar por la ruta de algunos usuarios a través de un SIP trunk en su sitio de sucursal. Para analizar tus necesidades, responde a las siguientes preguntas:
  
- ¿Qué tamaño tiene cada sitio (es decir, cuántos usuarios están habilitados para la Telefonía IP empresarial)? 
    
- ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio? 
    
Para saber si compensa implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de coste-beneficio. En algunos casos, puede ser mejor decantarse por el modelo de implementación distribuido aunque no sea necesario. En una implementación totalmente centralizada, se enruta todo el tráfico de sitio rama sobre vínculos WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefieras usar el enlace troncal SIP distribuido. Por ejemplo, puede que desee implementar un servidor Standard Edition en un sitio de sucursal con la federación en el sitio central o desea implementar un servidor de sucursal que sobreviven con una pequeña puerta de enlace o de un dispositivo de la rama que sobreviven.
  
> [!NOTE]
> Para obtener detalles sobre la Troncalización SIP distribuida, vea [SIP trunking de sitio de sucursal en Skype para Business Server 2015](branch-site.md). 
  
### <a name="supported-sip-trunking-connection-types"></a>Tipos de conexión de enlace troncal SIP compatibles

Skype para Business Server admite los siguientes tipos de conexión para Troncalización SIP:
  
- La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con otros suscriptores, y cada paquete de datos se asigna una etiqueta para distinguir los datos de un suscriptor de otro. Este tipo de conexión no necesita red privada virtual (VPN). Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.
    
- En general, las conexiones privadas sin otro tipo de tráfico (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada) son el tipo de conexión más seguro y confiable. Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.
    
- Internet es el tipo de conexión menos costoso, pero también el menos confiable. Conexión a Internet es la única Skype para Business Server SIP trunking tipo de conexión que requiere VPN.
    
#### <a name="selecting-a-connection-type"></a>Seleccionar un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para tu empresa depende de las necesidades y el presupuesto del que dispongas.
  
- En las empresas medianas o grandes, la red MPLS ofrece el mejor servicio en general, ya que es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.
    
- Las grandes empresas pueden necesitar una conexión privada de fibra óptica, T1, T3 o superior (E1, E3 o superior en la Unión Europea).
    
- Para una pequeña empresa o un sitio de sucursal con el volumen de llamada bajo, Troncalización SIP a través de Internet puede ser la mejor opción. Este tipo de conexión no es recomendable en sitios de tamaño medio o mayor.
    
### <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

La cantidad de ancho de banda necesaria en la implementación dependerá de la capacidad de llamada (esto es, del número de llamadas simultáneas que se admite). Necesitas tener en cuenta la disponibilidad de ancho de banda para poder sacar el máximo partido a la capacidad contratada. Usa la siguiente fórmula para calcular el requisito de ancho de banda máximo del tronco SIP:
  
Ancho de banda máximo del tronco SIP = n.º máx. de llamadas simultáneas x (64 kbps + tamaño del encabezado)
  
> [!NOTE]
> El tamaño del encabezado es de 20 bytes como máximo. 
  
### <a name="codec-support"></a>Compatibilidad de códecs

Skype para Business Server admite sólo los siguientes códecs:
  
- G.711 Ley A (que se usa principalmente fuera de Norteamérica)
    
- G.711 Ley µ (que se usa en Norteamérica)
    
### <a name="internet-telephony-service-provider"></a>Proveedor de servicios de telefonía por Internet

El modo en el que se implementa el lado del proveedor de servicios de una conexión basada en troncos SIP varía de un ITSP a otro. Para obtener más información sobre la implementación, ponte en contacto con tu proveedor de servicios. Para obtener una lista de proveedores de servicio de Troncalización SIP certificados, consulte el [sitio Web de Microsoft Unified Communications interoperabilidad programa abierto](https://go.microsoft.com/fwlink/p/?LinkId=287029).
  
Para obtener más información sobre los proveedores de enlaces troncales SIP certificados por Microsoft, ponte en contacto con tu representante de Microsoft.
  
> [!IMPORTANT]
> Necesitas usar un proveedor de servicios certificado por Microsoft para asegurarte de que tu ITSP admite todas las funciones que pasan por el tronco SIP (por ejemplo, la configuración y administración de sesiones y la compatibilidad con todos los servicios de VoIP ampliados). El Soporte técnico de Microsoft no se amplía para configuraciones que usan proveedores no certificados. Si estás usando actualmente un proveedor de servicios de Internet que no está certificado para enlaces troncales SIP, puedes seguir usando dicho proveedor como ISP y usar un proveedor certificado por Microsoft para enlaces troncales SIP. 
  
### <a name="topologies-and-components-for-sip-trunking"></a>Topologías y componentes del enlace troncal SIP

La siguiente figura muestra la topología de Troncalización SIP en Skype para Business Server.
  
**Topología de Troncalización SIP**

![Topología de enlace troncal SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)
  
Como se muestra en el diagrama, se usa una red privada virtual (VPN) de IP para la conectividad entre la red empresarial y el proveedor de servicios de la red telefónica conmutada (RTC). El objetivo de esta red privada es proporcionar conectividad IP, mejorar la seguridad y obtener garantías (opcionales) de calidad de servicio (QoS). Dada la naturaleza de una VPN, no necesitas usar seguridad de la capa de transporte (TLS) para el tráfico de señalización SIP ni el protocolo de transporte en tiempo real seguro (SRTP) para el tráfico de medios. Las conexiones entre la empresa y el proveedor de servicios constan, por lo tanto, de conexiones TCP simples para SIP y el protocolo de transporte en tiempo real (RTP) simple (sobre UDP) para los medios de túnel a través de una VPN de IP. Asegúrate de que todos los firewalls que hay entre los enrutadores de VPN tienen los puertos abiertos para permitir la comunicación de dichos enrutadores, y que las direcciones IP de los bordes externos de los enrutadores de VPN se pueden redirigir públicamente.
  
> [!IMPORTANT]
> Consulta a tu proveedor de servicios para saber si admite alta disponibilidad, incluida la conmutación por error. Si es así, tendrás que determinar los procedimientos para instalarla. Por ejemplo, ¿necesita configurar una única dirección IP y un troncal SIP en cada servidor de mediación o debe configurar varios troncos SIP en cada servidor de mediación? > Si tiene varios sitios centrales, preguntar también si el proveedor de servicio tiene la capacidad para permitir las conexiones desde y hacia otro sitio central. 
  
> [!NOTE]
> Para Troncalización SIP, recomendamos encarecidamente que implemente servidores de mediación independientes. Para obtener información detallada, vea [implementación de servidores de mediación y definir pares](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) en la documentación de implementación.
  
### <a name="securing-the-mediation-server-for-sip-trunking"></a>Protección del servidor de mediación para el enlace troncal SIP

Por motivos de seguridad, necesitas instalar una LAN virtual (VLAN) por cada conexión que haya entre ambos enrutadores de VPN. El proceso concreto para instalar una VLAN varía según el fabricante del enrutador. Para obtener más detalles, ponte en contacto con el proveedor de tu enrutador.
  
Recomendamos seguir estas instrucciones:
  
- Establecer de una LAN virtual (VLAN) entre el servidor de mediación y el enrutador VPN en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada).
    
- No permitas la difusión ni la transferencia de paquetes de multidifusión desde el enrutador a la VLAN.
    
- Bloquear las reglas de enrutamiento que enrute el tráfico desde el enrutador a cualquier parte, pero el servidor de mediación.
    
Si usas un servidor de VPN, recomendamos seguir estas instrucciones:
  
- Configurar una VLAN entre el servidor VPN y el servidor de mediación.
    
- No permitas la difusión ni la transmisión de paquetes de multidifusión desde el servidor de VPN a la VLAN.
    
- Bloquear cualquier regla de enrutamiento que enruta el tráfico del servidor VPN a cualquier parte, pero el servidor de mediación.
    
- Cifra los datos de la VPN con encapsulación de enrutamiento genérico (GRE).
    
## <a name="see-also"></a>Vea también

#### 

[Troncalización SIP de sitio de sucursal en Skype para Business Server 2015](branch-site.md)

