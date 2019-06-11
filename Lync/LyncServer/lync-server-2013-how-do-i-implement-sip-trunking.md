---
title: 'Lync Server 2013: ¿Cómo puedo implementar el enlace troncal SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c14375f9e0b7f3a7615c11ddaca2bc6c46ec72f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-18_

Para implementar la Troncalización SIP, debe enrutar la conexión a través de un servidor de mediación, que actúa como un proxy para las sesiones de comunicaciones entre los clientes de Lync Server 2013 y el proveedor de servicios, y transcodifican los medios cuando es necesario.

Cada servidor de mediación tiene una interfaz de red interna y una interfaz de red externa. La interfaz interna se conecta a los servidores front-end. La interfaz externa suele denominarse puerta de enlace porque se ha usado tradicionalmente para conectar el servidor de mediación a una puerta de enlace de red telefónica conmutada (RTC) o a un IP-PBX. Para implementar un tronco de SIP, debes conectar la interfaz externa del servidor de mediación con el componente de borde externo de la ITSP.

<div>


> [!NOTE]  
> El componente de borde externo del ITSP podría ser un controlador de borde de sesión (SBC), un enrutador o una puerta de enlace.



</div>

Para obtener más información sobre los servidores de mediación, vea [componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Enlace troncal SIP centralizado en comparación con uno distribuido

*Centralizado* El Troncalización SIP dirige todo el tráfico de voz sobre el protocolo de Internet (VoIP), incluido el tráfico de sitios de sucursales, a través de su sitio central. El modelo de implementación centralizada es simple, rentable y, por lo general, es el método recomendado para implementar los troncos SIP con Lync Server 2013.

*Distribuido* El Troncalización SIP es un modelo de implementación en el que se implementa un enlace SIP local en uno o más sitios de sucursales. El tráfico de VoIP se redirige directamente desde el sitio de la sucursal a un proveedor de servicios sin pasar por el sitio central.

El enlace troncal SIP distribuido solo es necesario en los siguientes casos:

  - El sitio de la sucursal requiere conectividad telefónica reactivable (por ejemplo, si la WAN deja de funcionar). Este requisito debe analizarse para cada sucursal; es posible que algunas de las sucursales requieran redundancia y conmutación por error, mientras que otras no.

  - Se requiere resistencia entre dos sitios centrales. Debes asegurarte de que un troncal de SIP finalice en cada sitio central. Por ejemplo, si tiene sitios centrales de Dublín y Tukwila y ambos usan solo el protocolo de tronco del SIP de un sitio, si el tronco deja de funcionar, los usuarios del otro sitio no pueden hacer llamadas RTC.

  - El sitio de la sucursal y el sitio central están en diferentes países o regiones. Por motivos legales y de compatibilidad, necesitas al menos un tronco SIP por cada país o región. Así, por ejemplo, en la Unión Europea las comunicaciones no pueden dejar un país o una región sin que terminen localmente en un punto centralizado.

En función de la ubicación geográfica de los sitios y de la cantidad de tráfico que anticipa dentro de su empresa, es posible que no desee enrutar a todos los usuarios a través del troncal SIP central o puede optar por enrutar a algunos usuarios a través de un protocolo troncal SIP en su sitio de sucursal. Para analizar tus necesidades, responde a las siguientes preguntas:

  - ¿Qué tamaño tiene cada sitio (es decir, cuántos usuarios están habilitados para Enterprise Voice)?

  - ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?

Para saber si compensa implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de coste-beneficio. En algunos casos, puede ser mejor decantarse por el modelo de implementación distribuido aunque no sea necesario. En una implementación completamente centralizada, todo el tráfico de los sitios de las sucursales se enruta a través de vínculos de WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefieras usar el enlace troncal SIP distribuido. Por ejemplo, es posible que desee implementar un servidor Standard Edition en un sitio de sucursal con la Federación al sitio central, o puede que desee implementar un dispositivo de sucursal que sea reviviente o un servidor de sucursal con la supervivencia con una pequeña puerta de enlace.

<div>


> [!NOTE]  
> Para obtener detalles sobre el Troncalización de SIP distribuido, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Troncalización SIP de sitio de sucursal en Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexión de enlace troncal SIP compatibles

Lync Server admite los siguientes tipos de conexión para Troncalización SIP:

  - La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita red privada virtual (VPN). Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.

  - En general, las conexiones privadas sin otro tipo de tráfico (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada) son el tipo de conexión más seguro y confiable. Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

  - Internet es el tipo de conexión menos costoso, pero también el menos confiable. Conexión a Internet es el único tipo de conexión de Troncalización SIP de Lync Server que requiere VPN.

<div>

## <a name="selecting-a-connection-type"></a>Seleccionar un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para tu empresa depende de las necesidades y el presupuesto del que dispongas.

  - En las empresas medianas o grandes, la red MPLS ofrece el mejor servicio en general, ya que es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.

  - Las grandes empresas pueden necesitar una conexión privada de fibra óptica, T1, T3 o superior (E1, E3 o superior en la Unión Europea).

  - En el caso de una pequeña empresa o sitio de sucursales con un volumen de llamada bajo, el Troncalización SIP a través de Internet puede ser la mejor opción. Este tipo de conexión no es recomendable en sitios de tamaño medio o mayor.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Requisitos de ancho de banda

La cantidad de ancho de banda necesaria en la implementación dependerá de la capacidad de llamada (esto es, del número de llamadas simultáneas que se admite). Necesitas tener en cuenta la disponibilidad de ancho de banda para poder sacar el máximo partido a la capacidad contratada. Usa la siguiente fórmula para calcular el requisito de ancho de banda máximo del tronco SIP:

Ancho de banda máximo del tronco SIP = n.º máx. de llamadas simultáneas x (64 kbps + tamaño del encabezado)

<div>


> [!NOTE]  
> El tamaño del encabezado es de 20 bytes como máximo.



</div>

</div>

<div>

## <a name="codec-support"></a>Compatibilidad de códecs

Lync Server 2013 solo admite los siguientes códecs:

  - G.711 Ley A (que se usa principalmente fuera de Norteamérica)

  - G.711 Ley µ (que se usa en Norteamérica)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Proveedor de servicios de telefonía por Internet

El modo en el que se implementa el lado del proveedor de servicios de una conexión basada en troncos SIP varía de un ITSP a otro. Para obtener más información sobre la implementación, ponte en contacto con tu proveedor de servicios. Para obtener una lista de proveedores de servicios de Troncalización de SIP certificados, consulte el [sitio web del programa](http://go.microsoft.com/fwlink/?linkid=287029)de interoperabilidad abierto de comunicaciones unificadas de Microsoft.

Para obtener más información sobre los proveedores de enlaces troncales SIP certificados por Microsoft, ponte en contacto con tu representante de Microsoft.

<div>


> [!IMPORTANT]  
> Necesitas usar un proveedor de servicios certificado por Microsoft para asegurarte de que tu ITSP admite todas las funciones que pasan por el tronco SIP (por ejemplo, la configuración y administración de sesiones y la compatibilidad con todos los servicios de VoIP ampliados). El Soporte técnico de Microsoft no se amplía para configuraciones que usan proveedores no certificados. Si estás usando actualmente un proveedor de servicios de Internet que no está certificado para enlaces troncales SIP, puedes seguir usando dicho proveedor como ISP y usar un proveedor certificado por Microsoft para enlaces troncales SIP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

