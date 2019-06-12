---
title: 'Lync Server 2013: Compatibilidad con conexiones de enlace troncal SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2bdcf814a62bed4954c77be76bef32e1b6807ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Compatibilidad con conexiones de enlace troncal SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Si planea usar telefonía IP empresarial con Troncalización SIP, debe implementar un servidor de mediación y asegurarse de que otros componentes y la infraestructura cumplan con los requisitos de soporte técnico adecuados para su modelo de implementación. Para obtener más información sobre cómo determinar si implementar la Troncalización SIP, consulte [información general sobre el enlace troncal de SIP en Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) en la documentación de planificación.

Puede usar el programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft para la infraestructura de telefonía empresarial para encontrarse con puertas de enlace de red telefónica conmutada (RTC) públicas, PBX IP y servicios de Troncalización SIP, incluida la telefonía IP calificada. proveedores de servicios. Para obtener más información, consulte el sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).

<div>

## <a name="mediation-server-support"></a>Compatibilidad con el servidor de mediación

Para implementar la Troncalización SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios. El servidor de mediación descodifica el tráfico multimedia de los clientes y los servidores y lo vuelve a codificar antes de enviarlo al proveedor de servicios. La recodificación es necesaria porque los troncos SIP no admiten algunos códecs usados, como la entrada de audio en tiempo real (RTA) o la negociación de protocolo ICE (establecimiento de conectividad interactiva) para el recorrido de Firewall.

Cada servidor de mediación puede tener dos adaptadores de red, que proporcionan una interfaz de red interna y externa. La interfaz externa suele denominarse puerta de enlace porque, tradicionalmente, se ha usado para conectarse a una puerta de enlace PSTN o IP-PBX. Para implementar un tronco de SIP, debe conectar la interfaz externa a un controlador de borde de sesión (SBC) en un proveedor de servicios.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Enlace troncal SIP centralizado en comparación con uno distribuido

*Centralizado* El Troncalización SIP dirige todo el tráfico de voz sobre el protocolo de Internet (VoIP), incluido el tráfico de sitios de sucursales, a través de su centro de datos. El modelo de implementación centralizada es simple, rentable y, por lo general, es el método preferido para implementar los troncos SIP con Lync Server 2013.

Según los patrones de uso dentro de su empresa, es posible que no desee enrutar a todos los usuarios a través del tronco SIP centralizado. Para analizar tus necesidades, responde a las siguientes preguntas:

  - ¿Qué tamaño tiene cada sitio? ¿Cuántos usuarios?

  - ¿Cuáles son los números de marcación directa directos de cada sitio que reciben las llamadas más telefónicas?

*Distribuido* El Troncalización SIP es un modelo de implementación en el que se implementa un enlace SIP local en uno o más sitios de sucursales. El tráfico de VoIP se enruta directamente desde el sitio de la sucursal a su proveedor de servicios, sin necesidad de pasar por su centro de datos.

El enlace troncal SIP distribuido solo es necesario en los siguientes casos:

  - El sitio de la sucursal requiere conectividad telefónica reactivable (por ejemplo, si la WAN deja de funcionar). Si la sucursal necesita redundancia y conmutación por error, el proveedor de servicios cobrará más y la configuración tardará más tiempo. Debe analizarse para cada sitio de sucursal. Es posible que algunas de las sucursales requieran redundancia y conmutación por error, mientras que otras no.

  - El sitio de la sucursal y el centro de datos se encuentran en diferentes países o regiones. Por motivos legales y de compatibilidad, necesitas al menos un tronco SIP por cada país o región.

La decisión de implementar Troncalización SIP centralizada o distribuida requiere un análisis de costo-beneficio. En algunos casos, puede resultar ventajoso optar por el modo de implementación distribuida, incluso si no es necesario. En una implementación completamente centralizada, todo el tráfico de los sitios de las sucursales se enruta a través de vínculos de WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefieras usar el enlace troncal SIP distribuido.

<div>


> [!NOTE]  
> Para obtener más información sobre por qué y cómo puede usar la Troncalización de SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Troncalización SIP de sitio de sucursal en Lync Server 2013</A> en la documentación de planeación.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexión de enlace troncal SIP compatibles

Lync Server 2013 admite los siguientes tipos de conexión para Troncalización SIP:

  - La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no requiere VPN. Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.

  - Normalmente, una conexión privada sin otro tráfico es el tipo de conexión más confiable y confiable (por ejemplo, una conexión de fibra óptica con leasing o una línea T1). Este tipo de conexión proporciona la mayor capacidad de carga de llamadas, pero generalmente es la más costosa. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

  - La Internet pública es el tipo de conexión menos costosa, pero también el menos confiable y el que tiene la capacidad de hacer llamadas más económicas. El proveedor de servicios de telefonía por Internet (ITSP) puede ayudar a proteger este tipo de conexión de troncal de SIP, si es compatible con la seguridad de la capa de transporte (TLS) y el protocolo de transporte seguro en tiempo real (SRTP) para cifrar el tráfico de señales y multimedia. Si no puede configurar una conexión de troncal de SIP a través de Internet para usar TLS y SRTP, le recomendamos encarecidamente que use un túnel VPN para proporcionar una conexión más segura. Póngase en contacto con su ITSP para determinar si proporciona compatibilidad con TLS con SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Seleccionar un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para tu empresa depende de las necesidades y el presupuesto del que dispongas.

  - En el caso de una empresa de tamaño mediano o grande, una red MPLS generalmente proporciona el máximo valor. Puede proporcionar el ancho de banda necesario a una tarifa económica que una red privada especializada.

  - Las grandes empresas pueden requerir una conexión privada de fibra óptica o T1.

  - En el caso de una pequeña empresa o sitio de sucursales con un volumen de llamada bajo, el Troncalización SIP a través de Internet puede ser la mejor opción. Sin embargo, no se recomienda este tipo de conexión para los sitios de tamaño mediano o más grande.

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

