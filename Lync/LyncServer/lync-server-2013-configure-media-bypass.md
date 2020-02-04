---
title: 'Lync Server 2013: Configurar la omisión de medios'
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
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurar la omisión de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

En esta sección se supone que ya ha publicado y configurado al menos uno o varios servidores de mediación (como se describe en [definir un servidor de mediación en el generador de topologías de Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) y [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), o bien, [defina y configure un grupo de servidores front-end o un servidor standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) y [publique la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, en la documentación de implementación.

En esta sección también se supone que ha definido al menos una puerta de enlace del mismo nivel para proporcionar conectividad RTC, como se describe en [definir una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Si el equivalente al que se conecta es el SBC de un proveedor de servicios de enlace troncal SIP, asegúrese de que sea un proveedor cualificado y que admita la omisión de medios. Por ejemplo, muchos proveedores de servicios de enlace troncal SIP solo permiten a sus SBC recibir tráfico del servidor de mediación. De ser así, la omisión no debe habilitarse para el tronco en cuestión. Además, no puede habilitar la omisión de medios a menos que la organización revele sus direcciones IP de redes internas al proveedor de servicios de enlace troncal SIP.

<div>


> [!NOTE]  
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco. La omisión de elementos multimedia solo se admite con productos y versiones que se incluyen en el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

En esta sección se describe cómo habilitar la omisión de medios para reducir el procesamiento requerido para el servidor de mediación. Antes de habilitar la omisión de medios, asegúrese de que su entorno cumple las condiciones necesarias para admitir la omisión de medios, como se describe en [planeamiento de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación de planeación. Además, asegúrese de que ha usado la información de [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir si quiere habilitar la configuración global de omisión de medios para omitir siempre el servidor de mediación o para usar la información del sitio y la región cuando determine si quiere omitir el servidor de mediación.

Si ya ha configurado el control de admisión de llamadas (CAC), otra característica avanzada de la Telefonía IP empresarial, tenga en cuenta que la reserva de ancho de banda que realiza dicho control no se aplica a ninguna llamada en la que se emplee la omisión de medios. Primero se comprueba si se usa la omisión de medios; si se usa, no se emplea el control de admisión de llamadas; la comprobación para control de admisión de llamadas se realiza únicamente si la comprobación de omisión de medios no funciona correctamente. Por lo tanto, las dos características se excluyen mutuamente en cualquier llamada que se enrute a la RTC. Se aplica esta lógica porque la omisión de medios da por supuesto que no hay restricciones de ancho de banda entre los extremos de los medios en una llamada; la omisión de medios no puede realizarse en vínculos que tengan un ancho de banda restringido. Como consecuencia, solo se aplica una de las posibilidades siguientes a una llamada de RTC: a) el medio omite el servidor de mediación y el control de admisión de llamadas no reserva ancho de banda para la llamada; o b) el control de admisión de llamadas aplica reserva de ancho de banda para la llamada y el servidor de mediación que interviene en la llamada procesa los medios.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Pasos siguientes: habilitar la omisión de medios en la conexión troncal

Después de configurar las opciones iniciales de conectividad RTC (planes de marcado, directivas de voz, registros de uso de RTC, rutas de llamadas salientes y reglas de traducción), inicie el proceso de habilitar la omisión de medios usando los pasos de [configurar un tronco con omisión de multimedia en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Vea también


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Opciones de omisión de multimedia global en Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

