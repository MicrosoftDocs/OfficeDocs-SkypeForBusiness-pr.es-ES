---
title: 'Lync Server 2013: ¿Cómo puedo implementar el enlace troncal SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e5265f580e3894d0fc8214b974ad03c9559323c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-18_

Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios, y transcodifica los medios, cuando sea necesario.

Cada servidor de mediación tiene una interfaz de red interna y una interfaz de red externa. La interfaz interna se conecta a los servidores front-end. La interfaz externa suele denominarse interfaz de puerta de enlace porque se ha usado tradicionalmente para conectar el servidor de mediación a una puerta de enlace de red telefónica conmutada (RTC) o a una IP-PBX. Para implementar un tronco SIP, debe conectar la interfaz externa del servidor de mediación con el componente perimetral externo de la ITSP.

<div>


> [!NOTE]  
> El componente perimetral externo del ITSP puede ser un controlador SBC (controlador de borde de sesión), un enrutador o una puerta de enlace.



</div>

Para obtener más información sobre los servidores de mediación, vea [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Enlace troncal SIP centralizado y distribuido

*Centralizado* El enlace troncal SIP enruta todo el tráfico del Protocolo de voz sobre IP (VoIP), incluido el tráfico del sitio de sucursal, a través del sitio central. El modelo de implementación centralizada es sencillo, rentable y suele ser el enfoque recomendado para implementar troncos SIP con Lync Server 2013.

*Distribución* El enlace troncal SIP es un modelo de implementación en el que se implementa un tronco SIP local en uno o más sitios de sucursal. A continuación, el tráfico de VoIP se redirige directamente desde el sitio de sucursal a un proveedor de servicios sin pasar por el sitio central.

El enlace troncal SIP distribuido solo es necesario en los siguientes casos:

  - Si la sucursal necesita una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN). Este requisito debe analizarse para cada sitio de sucursal; es posible que algunas de las sucursales requieran redundancia y conmutación por error, mientras que otras no.

  - Se requiere resistencia entre dos sitios centrales. Debe asegurarse de que un tronco SIP finalice en cada sitio central. Por ejemplo, si tiene los sitios centrales de Dublín y Tukwila y ambos usan solo el tronco SIP de un sitio, si el tronco deja de funcionar, los usuarios del otro sitio no pueden realizar llamadas RTC.

  - El sitio de sucursal y el sitio central se encuentran en diferentes países o regiones. Por motivos legales y de compatibilidad, necesita al menos un tronco SIP por cada país o región. Así, por ejemplo, en la Unión Europea las comunicaciones no pueden dejar un país/región sin que termine localmente en un punto centralizado.

En función de la ubicación geográfica de los sitios y de la cantidad de tráfico que se prevé dentro de la empresa, es posible que no desee enrutar a todos los usuarios a través del tronco SIP central, o puede optar por enrutar a algunos usuarios a través de un tronco SIP en su sitio de sucursal. Para analizar sus necesidades, responda a las siguientes preguntas:

  - ¿Cuál es el tamaño de cada sitio (es decir, cuántos usuarios están habilitados para Enterprise Voice)?

  - ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?

Para saber si compensa implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de costo-beneficio. En algunos casos, puede ser mejor decantarse por el modelo de implementación distribuido aunque no sea necesario. En las implementaciones totalmente centralizadas, todo el tráfico de las sucursales se enruta a través de vínculos WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido. Por ejemplo, puede que desee implementar un servidor Standard Edition en un sitio de sucursal con Federación al sitio central, o puede que desee implementar una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña.

<div>


> [!NOTE]  
> Para obtener más información sobre el enlace troncal SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexión de enlace troncal SIP compatibles

Lync Server admite los siguientes tipos de conexión para el enlace troncal SIP:

  - La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita red privada virtual (VPN). Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.

  - En general, las conexiones privadas sin otro tipo de tráfico (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada) son el tipo de conexión más seguro y fiable. Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

  - Internet es el tipo de conexión menos costoso, pero también el menos fiable. La conexión a Internet es el único tipo de conexión de enlace troncal SIP de Lync Server que requiere VPN.

<div>

## <a name="selecting-a-connection-type"></a>Selección de un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.

  - En las empresas medianas o grandes, la red MPLS ofrece el mejor servicio en general, ya que es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.

  - Las grandes empresas pueden necesitar una conexión privada de fibra óptica, T1, T3 o superior (E1, E3 o superior en la Unión Europea).

  - Para una empresa pequeña o un sitio de sucursal con un volumen de llamadas bajo, el enlace troncal SIP a través de Internet puede ser la mejor opción. Este tipo de conexión no es recomendable en sitios de tamaño medio o mayor.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

La cantidad de ancho de banda necesaria en la implementación dependerá de la capacidad de llamada (esto es, del número de llamadas simultáneas que se admite). Debe tener en cuenta la disponibilidad de ancho de banda para poder sacar el máximo partido a la capacidad contratada. Use la siguiente fórmula para calcular el requisito de ancho de banda máximo del tronco SIP:

Ancho de banda máximo del tronco SIP = Nº máx. de llamadas simultáneas x (64 kbps + tamaño de encabezado)

<div>


> [!NOTE]  
> El tamaño de encabezado es de 20 bytes como máximo.



</div>

</div>

<div>

## <a name="codec-support"></a>Compatibilidad de códecs

Lync Server 2013 solo admite los siguientes códecs:

  - G.711 Ley A (que se usa principalmente fuera de Norteamérica)

  - G.711 Ley µ (que se usa en Norteamérica)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Proveedor de servicios de telefonía de Internet

El modo en el que se implementa el lado del proveedor de servicios de una conexión basada en troncos SIP varía de un ITSP a otro. Para obtener información acerca de la implementación, póngase en contacto con su proveedor de servicios. Para obtener una lista de los proveedores de servicios de troncales SIP certificados, consulte el [sitio web del programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft](https://go.microsoft.com/fwlink/?linkid=287029).

Para obtener más información acerca de los proveedores de enlaces troncales SIP certificados por Microsoft, póngase en contacto con su representante de Microsoft.

<div>


> [!IMPORTANT]  
> Debe usar un proveedor de servicios certificado por Microsoft para asegurarse de que su ITSP admite todas las funcionalidades que pasan por el tronco SIP (por ejemplo, la configuración y administración de sesiones y la compatibilidad con todos los servicios de VoIP ampliados). El Soporte técnico de Microsoft no se amplía para configuraciones que usan proveedores no certificados. Si está usando actualmente un proveedor de servicios de Internet que no está certificado para enlaces troncales SIP, puede seguir usando dicho proveedor como ISP y usar un proveedor certificado por Microsoft para enlaces troncales SIP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

