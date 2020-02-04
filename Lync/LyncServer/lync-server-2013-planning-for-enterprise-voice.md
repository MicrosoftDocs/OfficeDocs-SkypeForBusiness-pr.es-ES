---
title: 'Lync Server 2013: planificación de telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice
ms:assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413081(v=OCS.15)
ms:contentKeyID: 48185959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83b0ec944ad857ffccb419cf9ed36fbca92306c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41753260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="7c985-102">Planificación de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c985-103">_**Última modificación del tema:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="7c985-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="7c985-104">El proceso de implementación de telefonía IP empresarial depende de la topología, la infraestructura y la funcionalidad de telefonía IP de empresa que desee admitir.</span><span class="sxs-lookup"><span data-stu-id="7c985-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="7c985-105">Los procedimientos necesarios dependerán de las características que seleccione, pero también es preciso tener en cuenta otros aspectos de la planeación que se necesitan realizar en un nivel más específico.</span><span class="sxs-lookup"><span data-stu-id="7c985-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="7c985-106">En general, hay que tener en cuenta el tipo y la cantidad de sitios que se quiere implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si se quiere proporcionar redundancia y conmutación por error para la función de voz en cada sitio y, asimismo, si se quiere usar el equipo de PBX existente.</span><span class="sxs-lookup"><span data-stu-id="7c985-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="7c985-107">Hay ciertas consideraciones, como la alta disponibilidad, que debe tener en cuenta al planear el software de comunicaciones de Lync Server como un todo.</span><span class="sxs-lookup"><span data-stu-id="7c985-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="7c985-108">Estas consideraciones se tratan en los distintos temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="7c985-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="7c985-109">Consideraciones de planeación</span><span class="sxs-lookup"><span data-stu-id="7c985-109">Planning Considerations</span></span>

<span data-ttu-id="7c985-110">Para conocer las decisiones de planeación relacionadas con la implementación de una funcionalidad de telefonía empresarial determinada o un componente o escenario de implementación, consulte los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="7c985-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="7c985-111">Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="7c985-112">Estimar el uso de voz y el tráfico para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="7c985-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="7c985-114">Components required for Enterprise Voice in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="7c985-115">Planear la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="7c985-116">Planear la integración de la mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="7c985-117">Planear el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="7c985-118">Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="7c985-119">Planificar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="7c985-120">Planificación de líneas telefónicas privadas con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="7c985-121">Planificar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="7c985-122">Planear la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="7c985-123">Instrucciones para la implementación de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="7c985-124">Información general sobre el proceso de implementación para telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="7c985-125">Mover usuarios a telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="7c985-126">Herramienta de diagnóstico de PRELLAMADA de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c985-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

