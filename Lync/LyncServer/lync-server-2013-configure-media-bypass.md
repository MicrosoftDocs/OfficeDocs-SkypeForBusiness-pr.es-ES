---
title: 'Lync Server 2013: Configurar la omisión de medios'
TOCTitle: Configurar la omisión de medios
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48277199
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En esta sección se da por supuesto que ya ha publicado y configurado como mínimo uno o varios servidores de mediación, como se describe en [Definir un servidor de mediación en el Generador de topologías en Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) y en [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), o bien en [Definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) y [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, en la documentación sobre implementación.

También se da por supuesto que ya ha definido como mínimo una puerta de enlace del mismo nivel para proporcionar conectividad con RTC, como se explica en [Definir una puerta de enlace en el Generador de topologías en Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Si el equivalente al que se conecta es el SBC de un proveedor de servicios de enlace troncal SIP, asegúrese de que sea un proveedor cualificado y que admita la omisión de medios. Por ejemplo, muchos proveedores de servicios de enlace troncal SIP solo permiten a sus SBC recibir tráfico del servidor de mediación. De ser así, la omisión no debe habilitarse para el tronco en cuestión. Además, no puede habilitar la omisión de medios a menos que la organización revele sus direcciones IP de redes internas al proveedor de servicios de enlace troncal SIP.


> [!NOTE]
> La omisión de medios no interactuará con todas las puertas de enlace RTC, sistemas IP-PBX y SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. La omisión de medios solo se permite con los productos y las versiones recogidos en Ingeniería completa para Microsoft Lync, en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



En esta sección se explica cómo habilitar la omisión de medios para reducir el procesamiento que debe realizar el servidor de mediación. Antes de habilitar la omisión de medios, asegúrese de que el entorno cumpla las condiciones necesarias para admitir la omisión de medios, como se indica en [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación sobre planeación. Asimismo, aplique la información de [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir si se habilita la configuración global de la omisión de medios para que siempre omita el servidor de mediación, o bien use la información de región y sitio para determinar si se omite el servidor de mediación.

Si ya ha configurado el control de admisión de llamadas, otra característica avanzada de la Telefonía IP empresarial, tenga en cuenta que la reserva de ancho de banda que realiza dicho control no se aplica a ninguna llamada en la que se emplee la omisión de medios. Primero se comprueba si se usa la omisión de medios; si se usa, no se emplea el control de admisión de llamadas; la comprobación para control de admisión de llamadas se realiza si la comprobación de omisión de medios no funciona correctamente. Por lo tanto, las dos características se excluyen mutuamente en cualquier llamada que se enrute a la RTC. Se aplica esta lógica porque la omisión de medios da por supuesto que no hay restricciones de ancho de banda entre los extremos de los medios en una llamada; la omisión de medios no puede realizarse en vínculos que tengan un ancho de banda restringido. Como consecuencia, solo se aplica una de las posibilidades siguientes a una llamada de RTC: a) el medio omite el servidor de mediación y el control de admisión de llamadas no reserva ancho de banda para la llamada; b) el control de admisión de llamadas aplica reserva de ancho de banda para la llamada y el servidor de mediación que interviene en la llamada procesa los medios.

## Pasos siguientes: Habilitar la omisión de medios en una conexión basada en troncos

Tras definir la configuración inicial de la conectividad con RTC (planes de marcado, directivas de voz, registros de uso de RTC, rutas de llamadas salientes y reglas de conversión), empiece el proceso de habilitar la omisión de medios aplicando los pasos que se describen en [Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

## Vea también

#### Tareas

[Configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar el desvío de medios en Lync Server 2013 para omitir siempre el servidor de mediación](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configurar las opciones globales del desvío de medios en Lync Server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  

#### Conceptos

[Opciones globales de desvío de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Otros recursos

[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

