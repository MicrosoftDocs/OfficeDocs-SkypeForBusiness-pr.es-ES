---
title: 'Lync Server 2013: ¿Cómo puedo implementar el enlace troncal SIP?'
TOCTitle: ¿Cómo puedo implementar el enlace troncal SIP?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48274735
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ¿Cómo puedo implementar el enlace troncal SIP en Lync Server 2013?

 

_**Última modificación del tema:** 2016-12-08_

Para implementar el enlace troncal SIP, debe enrutar la conexión a través de un Servidor de mediación, que actúa como proxy sesiones de comunicación entre los clientes de Lync Server 2013 y el proveedor de servicios y transcodifica los medios si procede.

Cada Servidor de mediación dispone de una interfaz de red interna y otra externa: la primera se conecta con los servidores Servidores front-end, mientras que la segunda se denomina habitualmente interfaz de puerta de enlace, ya que se suele usar para conectar el Servidor de mediación a una puerta de enlace de red telefónica conmutada (RTC) o una PBX IP. Para implementar un enlace troncal SIP, la interfaz externa del Servidor de mediación se conecta al componente perimetral externo del ITSP.


> [!NOTE]
> El componente perimetral externo del ITSP puede ser un controlador SBC (controlador de borde de sesión), un enrutador o una puerta de enlace.



Para obtener información detallada sobre los Servidores de mediación, vea [Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md).

## Enlace troncal SIP centralizado y distribuido

El enlace troncal SIP *centralizado* enruta todo el tráfico voz sobre IP (VoIP), incluido el tráfico de Sitio de sucursal a través del sitio central. El modelo de implementación centralizado es sencillo, rentable y, en general, el método que se suele recomendar para implementar troncos SIP con Lync Server 2013.

El enlace troncal SIP *distribuido* es un modelo de implementación con el que se implementa un tronco SIP local en una o más sucursales. De este modo, el tráfico de VoIP se enruta desde la Sitio de sucursal directamente a un proveedor de servicio, sin tener que pasar por el sitio central.

El enlace troncal SIP distribuido solo es necesario en los siguientes casos:

  - Cuando la Sitio de sucursal precisa de una conectividad telefónica con funciones de supervivencia (por ejemplo, si se cae la red WAN). Este requisito deberá sopesarse en cada Sitio de sucursal, ya que algunas sucursales pueden necesitar redundancia y conmutación por error, pero otras no.

  - La resistencia es necesaria entre dos sitios centrales. Deberá asegurarse de que hay un tronco SIP que finaliza en cada sitio central. Por ejemplo, si tiene sitios centrales en Dublín y en Tukwila, y ambos usan únicamente el tronco SIP de un sitio, cuando este no esté activo, los usuarios del otro sitio no podrán realizar llamadas RTC.

  - La Sitio de sucursal y el sitio central se encuentran en países/regiones distintos. Por motivos legales y de compatibilidad, necesita al menos un tronco SIP por cada país o región. Así, por ejemplo, en la Unión Europea las comunicaciones no pueden dejar un país/región sin que termine localmente en un punto centralizado.

En función de la ubicación geográfica de los sitios y de la densidad de tráfico que haya anticipado en la organización, puede que no quiera enrutar a todos los usuarios a través del tronco SIP central, o bien que opte por enturar a algunos usuario a través de un tronco SIP de su Sitio de sucursal. Para analizar sus necesidades, responda a las siguientes preguntas:

  - ¿Qué cabida tiene el sitio (es decir, cuántos usuarios están habilitados para Telefonía IP empresarial)?

  - ¿Qué números de llamada directa a la extensión (DID) reciben más llamadas en cada sitio?

Para saber si compensa implementar un enlace troncal SIP centralizado o distribuido, se necesita un análisis de costo-beneficio. En algunos casos, puede ser mejor decantarse por el modelo de implementación distribuido aunque no sea necesario. En las implementaciones totalmente centralizadas, todo el tráfico de Sitio de sucursal se enruta a través de vínculos WAN. En lugar de pagar por el ancho de banda necesario para la vinculación WAN, es posible que prefiera usar el enlace troncal SIP distribuido. Así, puede que quiera implementar un Servidor Standard Edition en una Sitio de sucursal con federación con el sitio central, o que desee implementar una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia con una pequeña puerta de enlace.


> [!NOTE]
> Para obtener información detallada sobre el enlace troncal SIP distribuido y el modo de hacerlo, vea <A href="lync-server-2013-branch-site-sip-trunking.md">Enlace troncal SIP de sitios de sucursal en Lync Server 2013</A>.



## Tipos de conexión de enlace troncal SIP compatibles

Lync Server admite los siguientes tipos de conexión de enlace troncal SIP:

  - La conmutación de etiquetas multiprotocolo (MPLS) es una red privada que dirige y transfiere datos de un nodo de red al siguiente. El ancho de banda de una red MPLS se comparte con los demás suscriptores, y a cada paquete de datos se le asigna una etiqueta para distinguir los datos de cada suscriptor. Este tipo de conexión no necesita red privada virtual (VPN). Un posible inconveniente es que el exceso de tráfico de IP puede interferir en el funcionamiento de VoIP, salvo que el tráfico de VoIP tenga prioridad.

  - En general, las conexiones privadas sin otro tipo de tráfico (por ejemplo, una línea de T1 o una conexión de fibra óptica alquilada) son el tipo de conexión más seguro y fiable. Este tipo de conexión ofrece la mayor capacidad de transferencia de llamadas, pero suele ser el más caro. No se necesita VPN. Las conexiones privadas son adecuadas para las organizaciones que tienen un gran volumen de llamadas o requisitos de seguridad y disponibilidad muy estrictos.

  - Internet es el tipo de conexión menos costoso, pero también el menos fiable. La conexión a Internet es el único tipo de conexión de enlace troncal SIP de Lync Server que requiere VPN.

## Selección de un tipo de conexión

El tipo de conexión de enlace troncal SIP más adecuado para su empresa depende de las necesidades y el presupuesto del que disponga.

  - En las empresas medianas o grandes, la red MPLS ofrece el mejor servicio en general, ya que es capaz de proporcionar el ancho de banda necesario a un precio menor que el de las redes privadas especializadas.

  - Las grandes empresas pueden necesitar una conexión privada de fibra óptica, T1, T3 o superior (E1, E3 o superior en la Unión Europea).

  - En el caso de una pequeña empresa o una Sitio de sucursal con un bajo volumen de llamadas, el enlace troncal SIP a través de Internet probablemente sea la mejor opción. Este tipo de conexión no es recomendable en sitios de tamaño medio o mayor.

## Requisitos de ancho de banda

La cantidad de ancho de banda necesaria en la implementación dependerá de la capacidad de llamada (esto es, del número de llamadas simultáneas que se admite). Debe tener en cuenta la disponibilidad de ancho de banda para poder sacar el máximo partido a la capacidad contratada. Use la siguiente fórmula para calcular el requisito de ancho de banda máximo del tronco SIP:

Ancho de banda máximo del tronco SIP = Nº máx. de llamadas simultáneas x (64 kbps + tamaño de encabezado)


> [!NOTE]
> El tamaño de encabezado es de 20&nbsp;bytes como máximo.



## Compatibilidad de códecs

Lync Server 2013 admite únicamente los siguientes códecs:

  - G.711 Ley A (que se usa principalmente fuera de Norteamérica)

  - G.711 Ley µ (que se usa en Norteamérica)

## Proveedor de servicios de telefonía de Internet

El modo en el que se implementa el lado del proveedor de servicios de una conexión basada en troncos SIP varía de un ITSP a otro. Para obtener información acerca de la implementación, póngase en contacto con su proveedor de servicios. Para obtener una lista de proveedores de servicios de enlaces troncales SIP, consulte el [sitio web del Programa de interoperabilidad abierto de comunicaciones unificadas de Microsoft](http://go.microsoft.com/fwlink/?linkid=287029).

Para obtener más información acerca de los proveedores de enlaces troncales SIP certificados por Microsoft, póngase en contacto con su representante de Microsoft.

> [!IMPORTANT]  
> Debe usar un proveedor de servicios certificado por Microsoft para asegurarse de que su ITSP admite todas las funcionalidades que pasan por el tronco SIP (por ejemplo, la configuración y administración de sesiones y la compatibilidad con todos los servicios de VoIP ampliados). El Soporte técnico de Microsoft no se amplía para configuraciones que usan proveedores no certificados. Si está usando actualmente un proveedor de servicios de Internet que no está certificado para enlaces troncales SIP, puede seguir usando dicho proveedor como ISP y usar un proveedor certificado por Microsoft para enlaces troncales SIP.


