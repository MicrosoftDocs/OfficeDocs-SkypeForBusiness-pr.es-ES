---
title: Planear la telefonía IP empresarial en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Conceptos básicos de la planificación de telefonía IP empresarial en Skype empresarial Server, incluidos los sitios, las regiones, los vínculos de red entre los sitios y la estimación del tráfico de uso de voz.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802900"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="ff25f-103">Planear la telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="ff25f-104">Conceptos básicos de la planificación de telefonía IP empresarial en Skype empresarial Server, incluidos los sitios, las regiones, los vínculos de red entre los sitios y la estimación del tráfico de uso de voz.</span><span class="sxs-lookup"><span data-stu-id="ff25f-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="ff25f-105">El proceso de implementación de telefonía IP empresarial depende de la topología, la infraestructura y la funcionalidad de telefonía IP de empresa que desee admitir.</span><span class="sxs-lookup"><span data-stu-id="ff25f-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="ff25f-106">Los procedimientos necesarios dependerán de las características que seleccione, pero también es preciso tener en cuenta otros aspectos de la planeación que se necesitan realizar en un nivel más específico.</span><span class="sxs-lookup"><span data-stu-id="ff25f-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="ff25f-107">En general, hay que tener en cuenta el tipo y la cantidad de sitios que se quiere implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si se quiere proporcionar redundancia y conmutación por error para la función de voz en cada sitio y, asimismo, si se quiere usar el equipo de PBX existente.</span><span class="sxs-lookup"><span data-stu-id="ff25f-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="ff25f-108">Hay ciertas consideraciones, como la alta disponibilidad, que debe tener en cuenta al planificar Skype empresarial Server como un todo.</span><span class="sxs-lookup"><span data-stu-id="ff25f-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="ff25f-109">Estas consideraciones se tratan en los distintos temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="ff25f-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="ff25f-110">Sitios y regiones</span><span class="sxs-lookup"><span data-stu-id="ff25f-110">Sites and regions</span></span>

<span data-ttu-id="ff25f-111">En primer lugar, identifique los sitios de su topología en los que va a implementar Enterprise Voice y las regiones de red a las que pertenecen dichos sitios.</span><span class="sxs-lookup"><span data-stu-id="ff25f-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="ff25f-112">En concreto, tenga en cuenta la forma en que se va a proporcionar conectividad de red telefónica conmutada (RTC) a cada sitio.</span><span class="sxs-lookup"><span data-stu-id="ff25f-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="ff25f-113">Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo.</span><span class="sxs-lookup"><span data-stu-id="ff25f-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="ff25f-114">Decidir dónde se implementarán las puertas de enlace de forma local, donde se implementarán los dispositivos de sucursal (SBAs) supervivientes, y donde puede configurar los troncos SIP (ya sea de forma local o en el sitio central) a un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="ff25f-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="ff25f-115">Vínculos de red entre sitios</span><span class="sxs-lookup"><span data-stu-id="ff25f-115">Network links between sites</span></span>

<span data-ttu-id="ff25f-116">También debe considerar el uso de ancho de banda que espera en los vínculos de red entre su sitio central y sus sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="ff25f-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="ff25f-117">Si tiene, o planea implementar, vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de marcado directo local (sí) para los usuarios de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="ff25f-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="ff25f-118">Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="ff25f-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="ff25f-119">Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en el sitio de la sucursal y no tiene los administradores de servidores de Skype para empresas capacitados en el nivel local, le recomendamos que implemente una aplicación de mayor supervivencia en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ff25f-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="ff25f-120">Si se aloja entre usuarios de 1000 y 5000 en su sitio de sucursal, carece de una conexión WAN resistente y tiene disponibles los administradores de servidores de Skype para empresas, le recomendamos que implemente un servidor de sucursal con una pequeña puerta de enlace en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ff25f-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="ff25f-121">También debe considerar habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admite la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="ff25f-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="ff25f-122">Estimar el uso de voz y el tráfico</span><span class="sxs-lookup"><span data-stu-id="ff25f-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="ff25f-123">La herramienta de planeación de Microsoft Lync Server 2013 usa la siguiente métrica para estimar el tráfico de los usuarios en cada sitio y el número de puertos necesarios para ese tráfico.</span><span class="sxs-lookup"><span data-stu-id="ff25f-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="ff25f-124">Para **Tráfico reducido** (una llamada de RTC por usuario y hora), calcule 15 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="ff25f-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="ff25f-125">Para **Tráfico medio** (2 llamadas de RTC por usuario y hora), calcule 10 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="ff25f-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="ff25f-126">Para **Tráfico denso** (3 llamadas o más de RTC por usuario y hora), calcule 5 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="ff25f-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="ff25f-127">El número de puertos, a su vez, determina la cantidad de servidores de mediación y puertas de enlace que se requerirán.</span><span class="sxs-lookup"><span data-stu-id="ff25f-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="ff25f-128">Las puertas de enlace de red de telefonía pública conmutada (RTC) que la mayoría de las organizaciones consideran implementar intervalos de tamaño desde dos puertos hasta un máximo de 960 puertos.</span><span class="sxs-lookup"><span data-stu-id="ff25f-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="ff25f-129">(Hay incluso puertas de enlace más grandes, pero las usan principalmente los proveedores de servicios de telefonía).</span><span class="sxs-lookup"><span data-stu-id="ff25f-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="ff25f-p106">Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. La cantidad de puertas de enlace necesarias equivaldría a la cantidad total de puertos necesarios determinada por la capacidad total de las puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="ff25f-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="ff25f-132">Componentes, características y opciones de telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="ff25f-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="ff25f-133">Consulte las siguientes secciones para obtener más información sobre cómo planear la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ff25f-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="ff25f-134">Componentes necesarios para la telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="ff25f-135">Planear la conectividad RTC en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="ff25f-136">Configuración de red para las características avanzadas de telefonía empresarial de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="ff25f-137">Plan para el control de admisión de llamadas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="ff25f-138">Planear los servicios de emergencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="ff25f-139">Plan de omisión de multimedia en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ff25f-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="ff25f-140">Planear líneas telefónicas privadas con Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ff25f-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="ff25f-141">Planear el enrutamiento basado en la ubicación en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ff25f-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="ff25f-142">Planear las características de administración de llamadas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="ff25f-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="ff25f-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ff25f-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

