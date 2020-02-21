---
title: Lync Server 2013 admite el enlace troncal SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31159a2d14facbdfed2f74f3567081699a7bde9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Compatibilidad con enlaces troncales SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Si planea usar la telefonía IP empresarial con enlace troncal SIP, debe implementar un servidor de mediación y asegurarse de que otros componentes y la infraestructura cumplan los requisitos de soporte técnico apropiados para el modelo de implementación. Para obtener más información sobre cómo determinar si implementar el enlace troncal SIP, consulte [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) en la documentación de planeación.

Puede usar el programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft para la infraestructura de telefonía empresarial para buscar puertas de enlace de red telefónica conmutada (RTC), PBX IP y servicios de enlace troncal SIP cualificados, incluida la telefonía IP completa. proveedores de servicios. Para obtener más información, consulte el sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft en [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).

<div>

## <a name="mediation-server-support"></a>Compatibilidad del servidor de mediación

Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios. El servidor de mediación descodifica el tráfico de medios de los clientes y servidores y lo vuelve a codificar antes de enviarlo al proveedor de servicios. La recodificación es necesaria porque los troncos SIP no admiten algunos códecs usados, como la negociación de protocolo de audio en tiempo real (RTA) o la negociación del Protocolo de establecimiento interactivo de conectividad (ICE) para un ataque transversal de Firewall.

Cada servidor de mediación puede tener dos adaptadores de red, para ofrecer una interfaz de red interna y otra externa. La interfaz externa suele denominarse interfaz de puerta de enlace porque, tradicionalmente, se ha usado para conectarse a una puerta de enlace RTC o a una IP-PBX. Para implementar un enlace troncal SIP, debe conectar la interfaz externa a un controlador de límite de sesión (SBC) de un proveedor de servicios.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Enlace troncal SIP centralizado y distribuido

*Centralizado* El enlace troncal SIP enruta todo el tráfico del Protocolo de voz sobre IP (VoIP), incluido el tráfico del sitio de sucursal, a través de su centro de datos. El modelo de implementación centralizada es sencillo, rentable y suele ser el método preferido para implementar troncos SIP con Lync Server 2013.

Según los patrones de uso de su empresa, es posible que no desee enrutar a todos los usuarios a través del enlace troncal SIP centralizado. Para analizar sus necesidades, responda a las siguientes preguntas:

  - ¿Qué tamaño tiene cada sitio? ¿Cuántos usuarios tiene?

  - ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?

El enlace troncal SIP *distribuido* es un modelo de implementación con el que se implementa un enlace troncal SIP local en una o más sucursales. A partir de entonces, el tráfico de VoIP se enruta desde la sucursal directamente al proveedor de servicios que le corresponda, sin pasar por su centro de datos.

El enlace troncal SIP distribuido solo se necesita en los siguientes casos:

  - Si la sucursal necesita una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN). Si la sucursal necesita redundancia y conmutación por error, el proveedor de servicios cobrará más por ello y la configuración llevará más tiempo. Se deben analizar estas características en cada sucursal. Es posible que algunas de las ramas requieran redundancia y conmutación por error, mientras que otras no.

  - Si la sucursal y el centro de datos se encuentran en países o regiones diferentes. Por motivos legales y de compatibilidad, necesita al menos un enlace troncal SIP por cada país o región.

La decisión de implementar un enlace troncal SIP centralizado o distribuido requiere un análisis de costos y beneficios. En algunos casos, puede ser ventajoso optar por el modo de implementación distribuida, incluso si no es necesario. En las implementaciones totalmente centralizadas, todo el tráfico de las sucursales se enruta a través de vínculos WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido.

<div>


> [!NOTE]  
> Para obtener más información sobre por qué y cómo podría usar el enlace troncal SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> en la documentación referente a la planeación.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexión de enlace troncal SIP compatibles

Lync Server 2013 admite los siguientes tipos de conexión para el enlace troncal SIP:

  - La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita VPN. Un posible inconveniente es que el exceso de tráfico de IP puede interferir con el funcionamiento de VoIP, salvo que se le dé prioridad al tráfico de VoIP.

  - En general, las conexiones privadas sin otro tipo de tráfico son el tipo de conexión más seguro y fiable (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada). Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tengan un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

  - La Internet pública es el tipo de conexión menos costoso, pero también el menos fiable y el que tiene la menor capacidad de transferencia de llamadas. El proveedor de servicios de telefonía por Internet (ITSP) puede ayudar a proteger este tipo de conexión de tronco de SIP si admite la seguridad de la capa de transporte (TLS) y el protocolo de transporte seguro en tiempo real (SRTP) para cifrar el tráfico multimedia y de señalización. Si no puede configurar una conexión de tronco SIP a través de Internet para que use TLS y SRTP, se recomienda encarecidamente que utilice un túnel de VPN para ofrecer una conexión más segura. Póngase en contacto con su ITSP para averiguar si admite TLS con SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Selección de un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.

  - Para una empresa de tamaño mediano o grande, una red MPLS suele proporcionar el máximo valor. Es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.

  - Las empresas grandes pueden necesitar una conexión de T1 o fibra óptica privada.

  - Para una empresa pequeña o un sitio de sucursal con un volumen de llamadas bajo, el enlace troncal SIP a través de Internet puede ser la mejor opción. Sin embargo, este tipo de conexión no se recomienda para sitios de tamaño mediano o grandes.

</div>

</div>

<div>

## <a name="codec-support"></a>Compatibilidad de códecs

El proxy del proveedor de servicios debe admitir los siguientes códecs:

  - G.711 Ley A (que se usa principalmente fuera de Norteamérica)

  - G.711 Ley µ (que se usa en Norteamérica)

</div>

</div>

<span> </span>

</div>

</div>

</div>

