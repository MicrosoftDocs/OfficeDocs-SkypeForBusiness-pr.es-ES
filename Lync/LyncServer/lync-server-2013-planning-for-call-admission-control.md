---
title: 'Lync Server 2013: Planeación del control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0d3173b3316d4e4dff704402da94c20aa2c9f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="29966-102">Planeación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29966-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="29966-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="29966-p101">Para las aplicaciones de comunicaciones unificadas (UC) basadas en IP, como la telefonía, el vídeo y el uso compartido de aplicaciones, el ancho de banda disponible de las redes de empresa no se considera normalmente un factor limitante dentro de los entornos de LAN; sin embargo, en los vínculos WAN que conectan sitios entre sí, el ancho de banda de red puede restringirse. Cuando una entrada de tráfico de red produce una suscripción excesiva en un vínculo WAN, los mecanismos actuales como la puesta en cola, el almacenamiento en búfer y la pérdida de paquetes se usan para solucionar la congestión. El tráfico adicional normalmente se retrasa hasta que la congestión de la red mejora o, si es necesario, se elimina el tráfico. Para el tráfico de datos convencional en estas situaciones, el cliente receptor puede recuperar. Para el tráfico en tiempo real como las comunicaciones unificadas, la congestión de la red no se puede solucionar de este modo porque el tráfico de las comunicaciones unificadas es sensible a la latencia y a la pérdida de paquetes. La congestión en la WAN puede ocasionar una baja Calidad de la experiencia (QoE) para los usuarios finales. Para el tráfico en tiempo real en condiciones de congestión, es mejor denegar llamadas que permitir conexiones de baja calidad.</span><span class="sxs-lookup"><span data-stu-id="29966-p101">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments. However, on WAN links that interconnect sites, network bandwidth can be limited. When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion. The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped. For conventional data traffic in such situations, the receiving client can recover. For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss. Congestion on the WAN can result in a poor Quality of Experience (QoE) for users. For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="29966-112">El servicio de control de admisión de llamadas (CAC) determina si hay suficiente ancho de banda de red para establecer una sesión en tiempo real con una calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="29966-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="29966-113">En Lync Server 2013, el CAC controla el tráfico en tiempo real solo para audio y vídeo, pero no afecta al tráfico de datos.</span><span class="sxs-lookup"><span data-stu-id="29966-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="29966-114">Si la ruta de acceso WAN predeterminada no tiene el ancho de banda necesario, CAC puede intentar enrutar la llamada a través de una ruta de acceso de Internet o de la RTC.</span><span class="sxs-lookup"><span data-stu-id="29966-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="29966-115">El CAC solo está disponible en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29966-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="29966-116">En esta sección se describen las funciones de control de admisión de llamadas y explica cómo planear para CAC.</span><span class="sxs-lookup"><span data-stu-id="29966-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29966-117">Lync Server tiene tres características avanzadas de telefonía IP empresarial: el control de admisión de llamadas (CAC), los servicios de emergencia (E9-1-1) y la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="29966-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="29966-118">Para obtener información general sobre la planeación de información común a las tres características, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="29966-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29966-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="29966-119">In This Section</span></span>

  - [<span data-ttu-id="29966-120">Información general sobre el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="29966-121">Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="29966-122">Ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="29966-123">Componentes y topologías para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="29966-124">Procedimientos recomendados para el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="29966-125">Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29966-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

