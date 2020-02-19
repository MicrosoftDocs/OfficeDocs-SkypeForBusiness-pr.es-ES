---
title: Requisitos de la infraestructura de red de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea383a77ff8d6089e2a01d7fb00df434f6d805e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="054c6-102">Requisitos de la infraestructura de red para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="054c6-102">Network infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="054c6-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="054c6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="054c6-104">La tarjeta adaptadora de red de cada servidor de la topología de Lync Server 2013 debe admitir al menos 1 Gigabit por segundo (Gbps).</span><span class="sxs-lookup"><span data-stu-id="054c6-104">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="054c6-105">En general, debe conectar todos los roles de servidor dentro de la topología de Lync Server usando una red de área local (LAN) de baja latencia y gran ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="054c6-105">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="054c6-106">El tamaño de la LAN depende del tamaño de la topología:</span><span class="sxs-lookup"><span data-stu-id="054c6-106">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="054c6-107">En las topologías de Standard Edition, los servidores deben estar en una red que admita Ethernet de 1 Gbps o equivalente.</span><span class="sxs-lookup"><span data-stu-id="054c6-107">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="054c6-108">En las topologías del grupo de servidores front-end, la mayoría de los servidores deben estar en una red que admita más de 1 Gbps, especialmente cuando se admiten conferencias de audio y vídeo (A/V) y uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="054c6-108">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="054c6-109">Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.</span><span class="sxs-lookup"><span data-stu-id="054c6-109">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="054c6-110">Requisitos de red para el audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="054c6-110">Audio/Video Network Requirements</span></span>

<span data-ttu-id="054c6-111">Entre los requisitos de red para audio y vídeo (A/V) en una implementación de Lync Server se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="054c6-111">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="054c6-112">Si va a implementar un solo servidor perimetral o un grupo de servidores perimetrales mediante el equilibrio de carga de DNS, puede configurar el firewall externo como NAT.</span><span class="sxs-lookup"><span data-stu-id="054c6-112">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="054c6-113">No puede configurar el firewall interno como un NAT.</span><span class="sxs-lookup"><span data-stu-id="054c6-113">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="054c6-114">Para obtener más información sobre estos requisitos, consulte [determine external a/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="054c6-114">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="054c6-115">Si tiene un grupo de servidores perimetrales y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en cada uno de los servidores perimetrales y no puede usar NAT para los servidores o el grupo en el dispositivo NAT (por ejemplo, el Firewall u otro dispositivo de infraestructura que pueda ser NAT Inbou tráfico ND o saliente).</span><span class="sxs-lookup"><span data-stu-id="054c6-115">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="054c6-116">Para obtener más información, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Summary-Scaled Consolidated Edge with hardware Load balances in Lync Server 2013</A> en la documentación de Planning for external User Access.</span><span class="sxs-lookup"><span data-stu-id="054c6-116">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="054c6-117">Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.</span><span class="sxs-lookup"><span data-stu-id="054c6-117">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="054c6-118">Si usa el protocolo de seguridad de Internet (IPsec), se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="054c6-118">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="054c6-119">Para obtener más información, consulte [excepciones de IPSec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="054c6-119">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="054c6-120">Para asegurar una calidad óptima de los medios, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="054c6-120">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="054c6-p105">Aprovisione los vínculos de red para que admitan una capacidad de proceso de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo en los períodos de uso máximo. Una sesión bidireccional de audio o vídeo consta de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="054c6-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="054c6-123">Para hacer frente a picos inesperados en el tráfico por encima de este nivel y mayor uso a lo largo del tiempo, los extremos de medios de Lync Server se pueden adaptar a distintas condiciones de red y admitir cargas tres veces el rendimiento (ver párrafo anterior) para audio y vídeo al mismo tiempo mantener la calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="054c6-123">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="054c6-124">No obstante, no se puede dar por sentado que esta capacidad de adaptación admita una red mal aprovisionada.</span><span class="sxs-lookup"><span data-stu-id="054c6-124">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="054c6-125">En una red aprovisionada inhabilitada, se reduce la capacidad de los extremos de medios de Lync Server para tratar dinámicamente las distintas condiciones de red (por ejemplo, una pérdida de paquetes alta temporal).</span><span class="sxs-lookup"><span data-stu-id="054c6-125">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="054c6-126">En el caso de los vínculos de red donde el aprovisionamiento resulta muy costoso y difícil, puede que se vea obligado a considerar un aprovisionamiento para un menor volumen de tráfico.</span><span class="sxs-lookup"><span data-stu-id="054c6-126">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="054c6-127">En este escenario, permita que la elasticidad de los puntos de conexión multimedia de Lync Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de una reducción de la calidad de la voz.</span><span class="sxs-lookup"><span data-stu-id="054c6-127">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="054c6-128">También hay una disminución en el margen que normalmente está disponible para absorber los picos de tráfico repentinos.</span><span class="sxs-lookup"><span data-stu-id="054c6-128">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="054c6-129">En el caso de los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN de muy poca calidad), considere la posibilidad de deshabilitar el vídeo para algunos usuarios.</span><span class="sxs-lookup"><span data-stu-id="054c6-129">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="054c6-130">Aprovisione la red para asegurar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) con carga máxima.</span><span class="sxs-lookup"><span data-stu-id="054c6-130">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="054c6-131">La latencia es la única discapacidad de red que los componentes multimedia de Lync Server no pueden reducir y es importante buscar y eliminar los puntos débiles.</span><span class="sxs-lookup"><span data-stu-id="054c6-131">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="054c6-132">En el caso de los servidores que ejecutan software antivirus, incluya todos los servidores que ejecutan Lync Server en la lista de excepciones para proporcionar un rendimiento y una calidad de audio óptimos.</span><span class="sxs-lookup"><span data-stu-id="054c6-132">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="054c6-133">Requisitos de red de la conferencia</span><span class="sxs-lookup"><span data-stu-id="054c6-133">Conferencing Network Requirements</span></span>

<span data-ttu-id="054c6-134">El ancho de banda que se usa para descargar contenido de conferencia del servidor de Internet Information Services (IIS) depende del tamaño del contenido que se carga.</span><span class="sxs-lookup"><span data-stu-id="054c6-134">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

