---
title: 'Lync Server 2013: Compatibilidad con conexiones de enlace troncal SIP'
TOCTitle: Compatibilidad con conexiones de enlace troncal SIP
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48276978
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con conexiones de enlace troncal SIP en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Si piensa usar la Telefonía IP empresarial con enlace troncal SIP, debe implementar un servidor de mediación y asegurarse de que el resto de los componentes y la infraestructura cumplen los requisitos de compatibilidad correspondientes al modelo de su implementación. Para conocer los detalles acerca de cómo averiguar si es necesario implementar el enlace troncal SIP, consulte [Información general sobre los enlaces troncales SIP en Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) en la documentación de planeación.

Puede usar el Programa de interoperabilidad abierto de comunicaciones unificadas de Microsoft para la infraestructura de telefonía empresarial, con el fin de encontrar puertas de enlace RTC, PBX IP y servicios de enlace troncal SIP, incluidos los proveedores de servicios de telefonía IP cualificados. Para obtener información detallada, consulte el sitio web del Programa de interoperabilidad abierto de Comunicaciones unificadas de Microsoft en [http://go.microsoft.com/fwlink/?linkid=203309\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=203309%26clcid=0xc0a).

## Compatibilidad del servidor de mediación

Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un servidor de mediación, que envía a un proxy las sesiones de comunicación entre los clientes de Lync Server 2013 y el proveedor de servicios. El servidor de mediación descodifica el tráfico de medios de clientes y servidores y lo vuelve a codificar antes de enviarlo al proveedor de servicios. La recodificación es necesaria porque los troncos SIP no admiten algunos códecs usados, como la negociación de los protocolos de Audio en tiempo real (RTA) o el Establecimiento interactivo de conectividad (ICE) para el cruce seguro de firewall.

Todos los servidores de mediación pueden tener dos adaptadores de red para ofrecer una interfaz de red interna y otra externa. La interfaz externa se suele denominar interfaz de puerta de enlace porque se ha venido usando para la conexión con una puerta de enlace de RTC o una PBX IP. Para implementar un enlace troncal SIP, debe conectar la interfaz externa a un controlador de borde de sesión (SBC) de un proveedor de servicios.

## Enlace troncal SIP centralizado y distribuido

El enlace troncal SIP *centralizado* enruta todo el tráfico de VoIP, incluido el tráfico de las sucursales, a través de su centro de datos. El modelo de implementación centralizado es sencillo, rentable y, en general, el método que se suele preferir para implementar troncos SIP con Lync Server 2013.

Según los patrones de uso de su empresa, es posible que no desee enrutar a todos los usuarios a través del enlace troncal SIP centralizado. Para analizar sus necesidades, responda a las siguientes preguntas:

  - ¿Qué tamaño tiene cada sitio? ¿Cuántos usuarios tiene?

  - ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?

El enlace troncal SIP *distribuido* es un modelo de implementación con el que se implementa un enlace troncal SIP local en una o más sucursales. A partir de entonces, el tráfico de VoIP se enruta desde la sucursal directamente al proveedor de servicios que le corresponda, sin pasar por su centro de datos.

El enlace troncal SIP distribuido solo es necesario en los siguientes casos:

  - Si la sucursal necesita una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN). Si la sucursal necesita redundancia y conmutación por error, el proveedor de servicios cobrará más por ello y la configuración llevará más tiempo. Se deben analizar estas características en cada sucursal. Es posible que algunas requieran redundancia y conmutación por error y otras, no.

  - Si la sucursal y el centro de datos se encuentran en países o regiones diferentes. Por motivos legales y de compatibilidad, necesita al menos un enlace troncal SIP por cada país o región.

Para saber si es recomendable implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de coste-beneficio. En algunos casos, puede ser mejor optar por el modelo de implementación distribuido aunque no sea necesario. En las implementaciones totalmente centralizadas, todo el tráfico de las sucursales se enruta mediante vínculos WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido.


> [!NOTE]
> Para obtener detalles sobre cómo y por qué usar el enlace troncal SIP distribuido, vea <A href="lync-server-2013-branch-site-sip-trunking.md">Enlace troncal SIP de sitios de sucursal en Lync Server 2013</A> en la documentación de planeación.



## Tipos de conexión de enlace troncal SIP compatibles

Lync Server 2013 admite los siguientes tipos de conexión de enlace troncal SIP:

  - La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita VPN. Un posible inconveniente es que el exceso de tráfico de IP puede interferir con el funcionamiento de VoIP, salvo que se le dé prioridad al tráfico de VoIP.

  - En general, las conexiones privadas sin otro tipo de tráfico son el tipo de conexión más seguro y fiable (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada). Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tengan un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

  - La Internet pública es el tipo de conexión menos costoso, pero también el menos fiable y el que tiene la menor capacidad de transferencia de llamadas. El proveedor de servicios de telefonía por Internet (ITSP) puede ayudar a proteger este tipo de conexión de tronco SIP si es compatible con TLS y el protocolo de transporte seguro en tiempo real (SRTP) para cifrar la señal y el tráfico de medios. Si no puede configurar una conexión de tronco SIP a través de Internet para que use TLS y SRTP, se recomienda encarecidamente que utilice un túnel de VPN para ofrecer una conexión más segura. Póngase en contacto con su ITSP para averiguar si admite TLS con SRTP.

## Selección de un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.

  - Para empresas medianas o grandes normalmente la red MPLS ofrece el mejor servicio. Es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.

  - Las empresas grandes pueden necesitar una conexión de T1 o fibra óptica privada.

  - Para empresas pequeñas o sucursales con un volumen de llamadas escaso, el enlace troncal SIP a través de Internet puede ser la mejor opción; sin embargo, este tipo de conexión no se recomienda para sitios medianos o grandes.

## Compatibilidad de códecs

El proxy del proveedor de servicios debe admitir los siguientes códecs:

  - G.711 Ley A (que se usa principalmente fuera de Norteamérica)

  - G.711 Ley µ (que se usa en Norteamérica)

