---
title: Enlace troncal SIP en Skype Empresarial Server
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Obtenga información sobre el enlace troncal SIP en Skype Empresarial Server Telefonía IP empresarial
ms.openlocfilehash: 8254df8366fdbfd03dd5ad0aa2f3253e5f4284b8248d26b131f056d28714bd77
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289738"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Enlace troncal SIP en Skype Empresarial Server

Obtenga información sobre el enlace troncal SIP en Skype Empresarial Server Telefonía IP empresarial

El Protocolo de inicio de sesión (SIP) se usa para iniciar y administrar sesiones de comunicaciones de voz sobre IP (VoIP) del servicio telefónico básico y para otros servicios de comunicación en tiempo real, como la mensajería instantánea, las conferencias, la detección de presencia y los elementos multimedia. Esta sección ofrece información sobre la planeación para implementar troncos SIP, un tipo de conexión SIP que se extiende más allá del límite de su red local.

## <a name="what-is-sip-trunking"></a>¿Qué es el enlace troncal SIP?

Un tronco SIP es una conexión IP que establece un vínculo de comunicaciones SIP entre su organización y un proveedor de servicios de telefonía de Internet (ITSP) más allá de su firewall. Normalmente, se usa un tronco SIP para conectar el sitio central de la organización a un ITSP. En ciertos casos, se puede usar también el enlace troncal SIP para conectar una sucursal a un ITSP.

La implementación del enlace troncal SIP puede ser un gran paso para simplificar las telecomunicaciones de su organización y prepararse para mejoras actualizadas en las comunicaciones en tiempo real. Una de las principales ventajas del enlace troncal SIP es que puede consolidar las conexiones de su organización a la red telefónica conmutada (RTC) en un sitio central, en lugar de su predecesor, el enlace troncal de multiplexación de división de tiempo (TDM), que normalmente requiere un tronco independiente de cada sitio de sucursal.

### <a name="cost-savings"></a>Ahorro económico

El ahorro económico inherente al enlace troncal SIP puede ser considerable:

- El costo de las llamadas de larga distancia suele ser mucho menor con un tronco SIP.

- Es posible reducir tanto los costos de facilidad de uso como la complejidad de la implementación.

- Las tasas de interfaz de acceso básica (BRI) y de interfaz de acceso principal (PRI) se pueden evitar si se conecta un tronco SIP directamente al ITSP, a un costo visiblemente menor. En los troncos TDM, los proveedores del servicio establecían el cargo de las llamadas por minuto. El costo del enlace troncal SIP se puede basar en el uso de ancho de banda, que puede adquirirse en incrementos más pequeños y, por tanto, más económicos (el costo real depende del modelo de servicio del ITSP que se elija).

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Enlace troncal SIP frente a puerta de enlace RTC o PBX IP

Como los troncos SIP se conectan directamente al proveedor del servicio, se puede prescindir de las puertas de enlace RTC y, en consecuencia, del costo de administración y complejidad que estas conllevan. El uso de un tronco SIP se traduce en un ahorro económico muy significativo gracias a que se requiere menos mantenimiento y administración.

### <a name="expanded-voip-services"></a>Servicios de VoIP ampliados

Con frecuencia, las características de voz constituyen la principal motivación para implementar un enlace troncal SIP, si bien la compatibilidad de voz es solo el primer paso. Con el enlace troncal SIP, puede ampliar las capacidades de VoIP y Skype Empresarial Server ofrecer un conjunto de servicios más enriquecido. Por ejemplo:

- La detección de presencia mejorada para dispositivos que no se ejecutan Skype Empresarial Server puede proporcionar una mejor integración con los teléfonos móviles, lo que permite ver cuándo un usuario está en una llamada de teléfono móvil.

- Las llamadas de emergencia E9-1-1 permiten a las autoridades que responden a las llamadas al 911 determinar la ubicación del autor de la llamada desde su número de teléfono.

> [!NOTE]
> Contacte con su ITSP para obtener una lista de los servicios que este admite y que se pueden habilitar en la organización.

### <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP y conexiones SIP directas

El término tronco deriva de la tecnología de circuitos conmutados. Se refiere a una línea física dedicada que conecta el equipo de conmutación telefónica. Al igual que su predecesora, los troncos de multiplexación de división de tiempo (TDM), los troncos SIP son conexiones entre dos redes SIP independientes: la empresa Skype Empresarial Server y el ITSP. A diferencia de los troncos de circuitos conmutados, los enlaces troncales SIP son conexiones virtuales que se pueden establecer sobre cualquiera de los tipos de conexión de enlaces troncales SIP compatibles.

Por otra parte, las conexiones SIP directas son conexiones SIP que no cruzan los límites de la red local (es decir, que se conectan a central de conmutación (PBX) o a una red telefónica conmutada (RTC) dentro de su red local). Para obtener más información sobre cómo puede usar conexiones SIP directas con Skype Empresarial Server, vea [Direct SIP connections in Skype Empresarial Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>¿Cómo implemento el enlace troncal SIP?

Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como proxy para las sesiones de comunicaciones entre los clientes de Skype Empresarial Server y el proveedor de servicios y transcodifica los medios, cuando sea necesario.

Cada servidor de mediación tiene una interfaz de red interna y una interfaz de red externa. La interfaz interna se conecta a los servidores front-end. La interfaz externa se denomina comúnmente interfaz de puerta de enlace porque tradicionalmente se ha usado para conectar el servidor de mediación a una puerta de enlace de red telefónica conmutada (RTC) o a una IP-PBX. Para implementar un tronco SIP, debe conectar la interfaz externa del servidor de mediación al componente perimetral externo del ITSP. El componente perimetral externo del ITSP puede ser un controlador SBC (controlador de borde de sesión), un enrutador o una puerta de enlace.

Para obtener más información acerca de los servidores de mediación, vea [Mediation Server component in Skype Empresarial Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Enlace troncal SIP centralizado y distribuido

El enlace troncal SIP centralizado enruta todo el tráfico voIP, incluido el tráfico de sitios de sucursal, a través del sitio central. El modelo de implementación centralizada es simple, rentable y suele ser el método recomendado para implementar troncos SIP con Skype Empresarial Server.

El enlace troncal SIP distribuido es un modelo de implementación en el que se implementan troncos SIP locales en uno o varios sitios de sucursal. A continuación, el tráfico voIP se enruta desde el sitio de sucursal directamente a un proveedor de servicios sin pasar por el sitio central.

El enlace troncal SIP distribuido solo es necesario en los siguientes casos:

- Si la sucursal necesita una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN). Este requisito debe analizarse para cada sitio de sucursal; algunas de las ramas pueden requerir redundancia y conmutación por error, mientras que otras no.

- La resistencia es necesaria entre dos sitios centrales. Debe asegurarse de que un tronco SIP finaliza en cada sitio central. Por ejemplo, si tiene sitios centrales de Dublín y Tukwila y ambos usan solo el tronco SIP de un sitio, si el tronco baja, los usuarios del otro sitio no pueden realizar llamadas RTC.

- El sitio de sucursal y el sitio central se encuentran en diferentes países o regiones. Por motivos legales y de compatibilidad, necesita al menos un tronco SIP por cada país o región. Así, por ejemplo, en la Unión Europea las comunicaciones no pueden dejar un país/región sin que termine localmente en un punto centralizado.

Según la ubicación geográfica de los sitios y la cantidad de tráfico que prevea en su empresa, es posible que no desee enrutar a todos los usuarios a través del tronco SIP central, o puede optar por enrutar a algunos usuarios a través de un tronco SIP en su sitio de sucursal. Para analizar sus necesidades, responda a las siguientes preguntas:

- ¿Qué tamaño tiene cada sitio (es decir, cuántos usuarios están habilitados para Telefonía IP empresarial)?

- ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?

Para saber si compensa implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de costo-beneficio. En algunos casos, puede ser mejor decantarse por el modelo de implementación distribuido aunque no sea necesario. En las implementaciones totalmente centralizadas, todo el tráfico de las sucursales se enruta a través de vínculos WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido. Por ejemplo, es posible que desee implementar un servidor de Standard Edition en un sitio de sucursal con federación en el sitio central, o puede que desee implementar una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña.

> [!NOTE]
> Para obtener más información sobre el enlace troncal SIP distribuido, vea [Branch site SIP trunking in Skype Empresarial Server](branch-site.md).

### <a name="supported-sip-trunking-connection-types"></a>Tipos de conexión de enlace troncal SIP compatibles

Skype Empresarial Server admite los siguientes tipos de conexión para el enlace troncal SIP:

- La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con otros suscriptores y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de un suscriptor de los de otros. Este tipo de conexión no necesita red privada virtual (VPN). Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.

- En general, las conexiones privadas sin otro tipo de tráfico (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada) son el tipo de conexión más seguro y fiable. Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

- Internet es el tipo de conexión menos costoso, pero también el menos fiable. La conexión a Internet es Skype Empresarial Server tipo de conexión troncal SIP que requiere VPN.

#### <a name="selecting-a-connection-type"></a>Selección de un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.

- En las empresas medianas o grandes, la red MPLS ofrece el mejor servicio en general, ya que es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.

- Las grandes empresas pueden necesitar una conexión privada de fibra óptica, T1, T3 o superior (E1, E3 o superior en la Unión Europea).

- Para una pequeña empresa o un sitio de sucursal con bajo volumen de llamadas, el enlace troncal SIP a través de Internet puede ser la mejor opción. Este tipo de conexión no es recomendable en sitios de tamaño medio o mayor.

### <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

La cantidad de ancho de banda necesaria en la implementación dependerá de la capacidad de llamada (esto es, del número de llamadas simultáneas que se admite). Debe tener en cuenta la disponibilidad de ancho de banda para poder sacar el máximo partido a la capacidad contratada. Use la siguiente fórmula para calcular el requisito de ancho de banda máximo del tronco SIP:

Ancho de banda máximo del tronco SIP = Nº máx. de llamadas simultáneas x (64 kbps + tamaño de encabezado)

> [!NOTE]
> El tamaño de encabezado es de 20 bytes como máximo.

### <a name="codec-support"></a>Compatibilidad de códecs

Skype Empresarial Server admite solo los siguientes códecs:

- G.711 Ley A (que se usa principalmente fuera de Norteamérica)

- G.711 Ley µ (que se usa en Norteamérica)

### <a name="internet-telephony-service-provider"></a>Proveedor de servicios de telefonía de Internet

El modo en el que se implementa el lado del proveedor de servicios de una conexión basada en troncos SIP varía de un ITSP a otro. Para obtener información acerca de la implementación, póngase en contacto con su proveedor de servicios. Para obtener una lista de proveedores de servicios troncales SIP certificados, consulte Sitio web del Programa de [interoperabilidad](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)abierta de comunicaciones unificadas de Microsoft .

Para obtener más información acerca de los proveedores de enlaces troncales SIP certificados por Microsoft, póngase en contacto con su representante de Microsoft.

> [!IMPORTANT]
> Debe usar un proveedor de servicios certificado por Microsoft para asegurarse de que su ITSP admite todas las funcionalidades que pasan por el tronco SIP (por ejemplo, la configuración y administración de sesiones y la compatibilidad con todos los servicios de VoIP ampliados). El Soporte técnico de Microsoft no se amplía para configuraciones que usan proveedores no certificados. Si está usando actualmente un proveedor de servicios de Internet que no está certificado para enlaces troncales SIP, puede seguir usando dicho proveedor como ISP y usar un proveedor certificado por Microsoft para enlaces troncales SIP.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologías y componentes para enlace troncal SIP

En la siguiente figura se muestra la topología de enlace troncal SIP en Skype Empresarial Server.

**Topología del enlace troncal SIP**

![Topología de enlace troncal SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Como se muestra en el diagrama, se usa una red privada virtual (VPN) de IP para la conectividad entre la red empresarial y el proveedor de servicios de la red telefónica conmutada (RTC). El objetivo de esta red privada es proporcionar conectividad IP, mejorar la seguridad y obtener garantías (opcionales) de Calidad de servicio (QoS). Dada la naturaleza de una VPN, no necesita usar Seguridad de la capa de transporte (TLS) para el tráfico de señalización SIP ni el Protocolo de transporte en tiempo real seguro (SRTP) para el tráfico de medios. Las conexiones entre la empresa y el proveedor de servicios constan, por lo tanto, de conexiones TCP simples para SIP y el Protocolo de transporte en tiempo real (RTP) simple (sobre UDP) para los medios de túnel a través de una VPN de IP. Asegúrese de que todos los firewalls que hay entre los enrutadores de VPN tienen los puertos abiertos para permitir la comunicación de dichos enrutadores, y que las direcciones IP de los bordes externos de los enrutadores de VPN se pueden redirigir públicamente.

> [!IMPORTANT]
> Consulte a su proveedor de servicios para saber si admite alta disponibilidad, incluida la conmutación por error. Si es así, tendrá que averiguar los procedimientos para instalarla. Por ejemplo, ¿necesita configurar solo una dirección IP y un tronco SIP en cada servidor de mediación o necesita configurar varios troncos SIP en cada servidor de mediación? > Si tiene varios sitios centrales, pregunte también si el proveedor de servicios tiene la capacidad de habilitar conexiones desde y hacia otro sitio central.

> [!NOTE]
> Para el enlace troncal SIP, se recomienda encarecidamente implementar servidores de mediación independientes. Para ver más detalles, consulte [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) en la documentación sobre implementación.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Protección del servidor de mediación para el enlace troncal SIP

Por motivos de seguridad, debe instalar una LAN virtual (VLAN) por cada conexión que haya entre ambos enrutadores de VPN. El proceso concreto para instalar una VLAN varía según el fabricante del enrutador. Para obtener información detallada, contacte con el proveedor de su enrutador.

Se recomienda seguir estas instrucciones:

- Configure una LAN virtual (VLAN) entre el servidor de mediación y el enrutador VPN en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred con pantalla).

- No permita la difusión ni la transferencia de paquetes multidifusión desde el enrutador a la VLAN.

- Bloquee las reglas de enrutamiento que enruten el tráfico desde el enrutador a cualquier lugar menos al servidor de mediación.

Si usa un servidor de VPN, se recomienda seguir estas instrucciones:

- Configure una VLAN entre el servidor VPN y el servidor de mediación.

- No permita la difusión ni la transmisión de paquetes multidifusión desde el servidor de VPN a la VLAN.

- Bloquear cualquier regla de enrutamiento que enruta el tráfico del servidor VPN a cualquier lugar, menos al servidor de mediación.

- Cifre los datos de la VPN mediante encapsulación de enrutamiento genérico (GRE).

## <a name="see-also"></a>Consulte también

[Enlace troncal SIP del sitio de sucursal en Skype Empresarial Server](branch-site.md)