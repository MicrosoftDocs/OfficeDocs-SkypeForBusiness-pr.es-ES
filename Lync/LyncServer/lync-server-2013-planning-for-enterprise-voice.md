---
title: 'Lync Server 2013: Planeación de la telefonía IP empresarial'
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
ms.openlocfilehash: 8bac9e4020ae29ec7ff6ec85a42ae0ee5d30d3af
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="15d5c-102">Planear la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-102">Planning for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d5c-103">_**Última modificación del tema:** 2013-11-01_</span><span class="sxs-lookup"><span data-stu-id="15d5c-103">_**Topic Last Modified:** 2013-11-01_</span></span>

<span data-ttu-id="15d5c-104">El proceso de implementación de la telefonía IP empresarial depende de la topología, la infraestructura y la funcionalidad de telefonía IP empresarial existentes que desee admitir.</span><span class="sxs-lookup"><span data-stu-id="15d5c-104">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="15d5c-105">Los procedimientos pertinentes dependerán de las características que se eligen, pero también es preciso tener en cuenta otros aspectos de la planeación que deben realizarse en un nivel más específico.</span><span class="sxs-lookup"><span data-stu-id="15d5c-105">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>

<span data-ttu-id="15d5c-106">En general, debe tenerse en cuenta el tipo y la cantidad de sitios que desea implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si desea proporcionar redundancia y conmutación por error para funcionalidad de voz en cada sitio, y si desea usar el equipo de central de conmutación existente.</span><span class="sxs-lookup"><span data-stu-id="15d5c-106">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="15d5c-107">Hay ciertas consideraciones, como la alta disponibilidad, que debe tener en cuenta al planear el software de comunicaciones de Lync Server como un todo.</span><span class="sxs-lookup"><span data-stu-id="15d5c-107">There are certain considerations, such as high availability, that you should consider when you plan for Lync Server  communications software as a whole.</span></span> <span data-ttu-id="15d5c-108">Estas consideraciones se tratan en los temas de la sección según convenga.</span><span class="sxs-lookup"><span data-stu-id="15d5c-108">These considerations are discussed in topics throughout this section, as needed.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="15d5c-109">Consideraciones referentes a la planeación</span><span class="sxs-lookup"><span data-stu-id="15d5c-109">Planning Considerations</span></span>

<span data-ttu-id="15d5c-110">Para obtener información sobre la planeación de decisiones relacionadas con la implementación de una funcionalidad de telefonía IP empresarial o componente o escenario de implementación concretos, consulte los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="15d5c-110">For planning decisions that pertain to the deployment of a particular Enterprise Voice capability or deployment scenario or component, consult the topics in this section.</span></span>

  - [<span data-ttu-id="15d5c-111">Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-111">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-enterprise-voice.md)

  - [<span data-ttu-id="15d5c-112">Estimar el uso de voz y el tráfico para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-112">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="15d5c-113">Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-113">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

  - [<span data-ttu-id="15d5c-114">Componentes necesarios para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-114">Components required for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-components-required-for-enterprise-voice.md)

  - [<span data-ttu-id="15d5c-115">Planeación de la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-115">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="15d5c-116">Planeación de la integración de la mensajería unificada de Exchange en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-116">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)

  - [<span data-ttu-id="15d5c-117">Planeación del control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-117">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="15d5c-118">Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-118">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="15d5c-119">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-119">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

  - [<span data-ttu-id="15d5c-120">Planeación de líneas telefónicas privadas con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-120">Planning for private telephone lines with Lync Server 2013</span></span>](lync-server-2013-planning-for-private-telephone-lines.md)

  - [<span data-ttu-id="15d5c-121">Planeación del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-121">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)

  - [<span data-ttu-id="15d5c-122">Planeación de la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-122">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="15d5c-123">Instrucciones de implementación para telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-123">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-enterprise-voice.md)

  - [<span data-ttu-id="15d5c-124">Información general sobre el proceso de implementación para telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-124">Deployment process overview for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deployment-process-overview-for-enterprise-voice.md)

  - [<span data-ttu-id="15d5c-125">Mover usuarios a telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-125">Moving users to Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-moving-users-to-enterprise-voice.md)

  - [<span data-ttu-id="15d5c-126">Herramienta de diagnóstico de PRELLAMADA de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15d5c-126">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>](lync-server-2013-lync-precall-diagnostics-tool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

