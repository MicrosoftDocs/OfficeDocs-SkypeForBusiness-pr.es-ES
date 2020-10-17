---
title: 'Lync Server 2013: configurar la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6153be57ec60e58b404370ece2c2214ae33083c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520649"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurar la omisión de medios en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

En esta sección se da por hecho que ya ha publicado y configurado al menos uno o varios servidores de mediación (como se describe en [definir un servidor de mediación en el generador de topologías en Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) y [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), o bien [definir y configurar un grupo de servidores front-end o un servidor standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) y [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, en la documentación de implementación.

En esta sección también se presupone que ha definido al menos una puerta de enlace del mismo nivel para proporcionar conectividad con RTC, como se describe en [definir una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Si el punto al que se conecta es el SBC de un proveedor de enlace troncal SIP, asegúrese de que el proveedor es un proveedor calificado y de que el proveedor admite la omisión de medios. Por ejemplo, muchos proveedores de servicios de enlace troncal SIP solo permiten a sus SCN recibir tráfico del servidor de mediación. De ser así, el desvío no debe habilitarse para el tronco en cuestión. Además, no puede habilitar el desvío de medios a menos que la organización revele sus direcciones IP de redes internas al proveedor de servicios de enlace troncal SIP.

<div>


> [!NOTE]  
> El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

En esta sección se explica cómo habilitar el desvío de medios para reducir el procesamiento que debe realizar el servidor de mediación. Antes de habilitar la omisión de medios, asegúrese de que su entorno cumple con las condiciones necesarias para admitir la omisión de medios, como se describe en [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación referente a la planeación. Además, asegúrese de que ha usado la información de [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir si desea habilitar la configuración global de omisión de medios para omitir siempre el servidor de mediación o usar la información de sitio y región cuando se determina si se va a omitir el servidor de mediación.

Si ya ha configurado el control de admisión de llamadas, otra característica avanzada de Telefonía IP empresarial, tenga en cuenta que la reserva de ancho de banda que realiza dicho control no se aplica a ninguna llamada en la que se emplee el desvío de medios. Primero se comprueba si se usa el desvío de medios; si se usa, no se emplea el control de admisión de llamadas; la comprobación para control de admisión de llamadas se realiza si la comprobación de desvío de medios no funciona correctamente. Por lo tanto, las dos características se excluyen mutuamente en cualquier llamada que se enrute a la RTC. Se aplica esta lógica porque el desvío de medios da por supuesto que no hay restricciones de ancho de banda entre los extremos de los medios en una llamada; el desvío de medios no puede realizarse en vínculos que tengan un ancho de banda restringido. Como consecuencia, solo se aplica una de las posibilidades siguientes a una llamada de RTC: a) el medio omite el servidor de mediación y el control de admisión de llamadas no reserva ancho de banda para la llamada; b) el control de admisión de llamadas aplica reserva de ancho de banda para la llamada y el servidor de mediación que interviene en la llamada procesa los medios.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Pasos siguientes: Habilitar el desvío de medios en una conexión basada en troncos

Después de configurar las opciones iniciales de conectividad con RTC (planes de marcado, directivas de voz, registros de uso de RTC, rutas de llamadas salientes y reglas de conversión), inicie el proceso de habilitación del desvío de medios mediante los pasos de [configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurar la omisión de medios en Lync Server 2013 para omitir siempre el servidor de mediación](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configurar las opciones globales de omisión de medios en Lync Server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Opciones de omisión de medios globales en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

