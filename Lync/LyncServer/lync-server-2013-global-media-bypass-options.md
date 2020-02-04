---
title: 'Lync Server 2013: opciones de omisión de multimedia global'
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
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="476f1-102">Opciones de omisión de multimedia global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476f1-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="476f1-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="476f1-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="476f1-104">En este tema se supone que ya ha configurado la omisión de medios para cualquier conexión a un interlocutor (una puerta de enlace de red telefónica conmutada (RTC), una IP-PBX o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet) para un sitio o servicio específico para que quiere que los medios omitan el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="476f1-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="476f1-p101">Además de habilitar la omisión de medios para las conexiones de tronco individuales asociadas a un nivel, también deberá habilitar la omisión de medios de forma global. La configuración de la omisión de medios global puede establecer que se intente realizar siempre una omisión de medios de las llamadas a RTC, o bien que la omisión de medios se use con la asignación de subredes a sitios y regiones de red, algo similar a lo que lleva a cabo el control de admisión de llamadas, que es otra característica de voz avanzada. Cuando tanto la omisión de medios como el control de admisión de llamadas están habilitados, la información de región de red, sitio de red y subred especificada para el control de admisión de llamadas se usa automáticamente para determinar si ha de usarse o no la omisión de medios, lo cual quiere decir que no siempre se va a poder especificar que se intente omitir los medios a RTC siempre cuando el control de admisión de llamadas está habilitado.</span><span class="sxs-lookup"><span data-stu-id="476f1-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="476f1-109">En este tema se describe cómo usar el panel de control de Lync Server y el shell de administración de Lync Server juntos para configurar las opciones globales de omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="476f1-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="476f1-110">Cuando se usan estos pasos para configurar la omisión de medios, se da por hecho que existe una buena conectividad entre los clientes y el nivel de servidor de mediación (por ejemplo, una puerta de enlace RTC, un sistema PBX IP o un SBC en un proveedor de enlace troncal SIP).</span><span class="sxs-lookup"><span data-stu-id="476f1-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="476f1-111">En caso de que haya limitaciones de ancho de banda en el vínculo, no podrá efectuarse la omisión de medios en la llamada.</span><span class="sxs-lookup"><span data-stu-id="476f1-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="476f1-112">La omisión de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC.</span><span class="sxs-lookup"><span data-stu-id="476f1-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="476f1-113">Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="476f1-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="476f1-114">La omisión de elementos multimedia solo se admite con productos y versiones que se incluyen en el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="476f1-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="476f1-115">Pasos siguientes: elegir la configuración de omisión de multimedia global</span><span class="sxs-lookup"><span data-stu-id="476f1-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="476f1-116">Después de habilitar la omisión de medios en las conexiones troncales a un interlocutor para determinados servicios o sitios, use el siguiente contenido para:</span><span class="sxs-lookup"><span data-stu-id="476f1-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="476f1-117">Habilite siempre la omisión de medios, como se describe en [configurar omisión de contenido multimedia en Lync Server 2013 para omitir siempre el servidor de mediación](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="476f1-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="476f1-118">También puede configurar la omisión de medios para usar la información del sitio y de la región, como se describe en [configurar la configuración global de omisión de contenido multimedia en Lync Server 2013 para usar la información de la región y el sitio](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="476f1-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="476f1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="476f1-119">See Also</span></span>


[<span data-ttu-id="476f1-120">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476f1-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="476f1-121">Asociar una subred a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476f1-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="476f1-122">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476f1-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="476f1-123">Omisión de medios y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="476f1-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

