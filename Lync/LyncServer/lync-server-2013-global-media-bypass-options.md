---
title: 'Lync Server 2013: opciones globales de desvío de medios'
description: 'Lync Server 2013: opciones globales de desvío de medios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554556"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="b498a-103">Opciones de omisión de medios globales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b498a-103">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b498a-104">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b498a-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b498a-105">En este tema se supone que ya se ha configurado un desvío de medios para los troncos a un interlocutor (una puerta de enlace de red telefónica conmutada (RTC), un IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet) para un sitio o servicio específico para el que desea que los medios omitan el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="b498a-105">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="b498a-106">Además de habilitar el desvío de medios para conexiones de tronco individuales asociadas con un par, también debe habilitar la omisión de medios globalmente.</span><span class="sxs-lookup"><span data-stu-id="b498a-106">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="b498a-107">La configuración de desvío de medios globales puede especificar que se intente siempre una omisión de medios para las llamadas a la RTC o que la omisión de medios se emplee mediante la asignación de subredes a sitios de red y regiones de red, de manera similar a lo que hace el control de admisión de llamadas, otra característica avanzada de voz.</span><span class="sxs-lookup"><span data-stu-id="b498a-107">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="b498a-108">Cuando se habilitan tanto el desvío de medios como el control de admisión de llamadas, la región de red, el sitio de red y la información de subred especificados para el control de admisión de llamadas se usan automáticamente al determinar si se debe emplear una omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="b498a-108">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="b498a-109">Esto significa que no puede especificar que el desvío de medios se intente siempre para las llamadas a la RTC cuando el control de admisión de llamadas esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="b498a-109">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="b498a-110">En este tema se describe cómo usar el panel de control de Lync Server y el shell de administración de Lync Server a la vez que se configura la configuración de omisión de medios globales.</span><span class="sxs-lookup"><span data-stu-id="b498a-110">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b498a-111">Cuando se usan estos pasos para configurar el desvío de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP).</span><span class="sxs-lookup"><span data-stu-id="b498a-111">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="b498a-112">En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse el desvío de medios en la llamada.</span><span class="sxs-lookup"><span data-stu-id="b498a-112">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="b498a-113">La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC.</span><span class="sxs-lookup"><span data-stu-id="b498a-113">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="b498a-114">Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="b498a-114">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="b498a-115">La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="b498a-115">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="b498a-116">Pasos siguientes: Elegir la configuración de desvío de medios global</span><span class="sxs-lookup"><span data-stu-id="b498a-116">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="b498a-117">Una vez habilitado el desvío de medios en las conexión de tronco a un nivel de los sitios o servicios especificados, haga uso del siguiente contenido para cualquiera de los siguientes cometidos:</span><span class="sxs-lookup"><span data-stu-id="b498a-117">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="b498a-118">Habilite siempre la omisión de medios, como se describe en [Configure media bypass in Lync Server 2013 para omitir siempre el servidor de mediación](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="b498a-118">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="b498a-119">O bien, configure la omisión de medios para usar la información de sitio y región, como se describe en [configurar la configuración global de desvío de medios en Lync Server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="b498a-119">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b498a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b498a-120">See Also</span></span>


[<span data-ttu-id="b498a-121">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b498a-121">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="b498a-122">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b498a-122">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="b498a-123">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b498a-123">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="b498a-124">Omisión de medios y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b498a-124">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

