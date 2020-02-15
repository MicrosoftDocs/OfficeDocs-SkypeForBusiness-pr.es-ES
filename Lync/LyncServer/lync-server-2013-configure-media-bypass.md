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
ms.openlocfilehash: 9bf2fb06f25ccf1871393cf4d80ffa3c33a42fc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="3729c-102">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3729c-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3729c-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="3729c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="3729c-104">En esta sección se da por hecho que ya ha publicado y configurado al menos uno o varios servidores de mediación (como se describe en [definir un servidor de mediación en el generador de topologías en Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) y [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), o bien [definir y configurar un grupo de servidores front-end o un servidor standard Edition en Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) y [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="3729c-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="3729c-105">En esta sección también se presupone que ha definido al menos una puerta de enlace del mismo nivel para proporcionar conectividad con RTC, como se describe en [definir una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3729c-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="3729c-106">Si el punto al que se conecta es el SBC de un proveedor de enlace troncal SIP, asegúrese de que el proveedor es un proveedor calificado y de que el proveedor admite la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="3729c-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="3729c-107">Por ejemplo, muchos proveedores de servicios de enlace troncal SIP solo permiten a sus SCN recibir tráfico del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3729c-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="3729c-108">De ser así, el desvío no debe habilitarse para el tronco en cuestión.</span><span class="sxs-lookup"><span data-stu-id="3729c-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="3729c-109">Además, no puede habilitar el desvío de medios a menos que la organización revele sus direcciones IP de redes internas al proveedor de servicios de enlace troncal SIP.</span><span class="sxs-lookup"><span data-stu-id="3729c-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3729c-110">El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC.</span><span class="sxs-lookup"><span data-stu-id="3729c-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="3729c-111">Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="3729c-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3729c-112">La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="3729c-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="3729c-113">En esta sección se explica cómo habilitar el desvío de medios para reducir el procesamiento que debe realizar el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3729c-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="3729c-114">Antes de habilitar la omisión de medios, asegúrese de que su entorno cumple con las condiciones necesarias para admitir la omisión de medios, como se describe en [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="3729c-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="3729c-115">Además, asegúrese de que ha usado la información de [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir si desea habilitar la configuración global de omisión de medios para omitir siempre el servidor de mediación o usar la información de sitio y región cuando se determina si se va a omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3729c-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="3729c-p104">Si ya ha configurado el control de admisión de llamadas, otra característica avanzada de Telefonía IP empresarial, tenga en cuenta que la reserva de ancho de banda que realiza dicho control no se aplica a ninguna llamada en la que se emplee el desvío de medios. Primero se comprueba si se usa el desvío de medios; si se usa, no se emplea el control de admisión de llamadas; la comprobación para control de admisión de llamadas se realiza si la comprobación de desvío de medios no funciona correctamente. Por lo tanto, las dos características se excluyen mutuamente en cualquier llamada que se enrute a la RTC. Se aplica esta lógica porque el desvío de medios da por supuesto que no hay restricciones de ancho de banda entre los extremos de los medios en una llamada; el desvío de medios no puede realizarse en vínculos que tengan un ancho de banda restringido. Como consecuencia, solo se aplica una de las posibilidades siguientes a una llamada de RTC: a) el medio omite el servidor de mediación y el control de admisión de llamadas no reserva ancho de banda para la llamada; b) el control de admisión de llamadas aplica reserva de ancho de banda para la llamada y el servidor de mediación que interviene en la llamada procesa los medios.</span><span class="sxs-lookup"><span data-stu-id="3729c-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="3729c-121">Pasos siguientes: Habilitar el desvío de medios en una conexión basada en troncos</span><span class="sxs-lookup"><span data-stu-id="3729c-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="3729c-122">Después de configurar las opciones iniciales de conectividad con RTC (planes de marcado, directivas de voz, registros de uso de RTC, rutas de llamadas salientes y reglas de conversión), inicie el proceso de habilitación del desvío de medios mediante los pasos de [configurar un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="3729c-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3729c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3729c-123">See Also</span></span>


[<span data-ttu-id="3729c-124">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3729c-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="3729c-125">Configurar la omisión de medios en Lync Server 2013 para omitir siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="3729c-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="3729c-126">Configurar las opciones globales de omisión de medios en Lync Server 2013 para usar la información de sitio y región</span><span class="sxs-lookup"><span data-stu-id="3729c-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="3729c-127">Opciones de omisión de medios globales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3729c-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="3729c-128">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3729c-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

