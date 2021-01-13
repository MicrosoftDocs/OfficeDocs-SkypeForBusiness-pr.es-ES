---
title: Plan for Telefonía IP empresarial in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Telefonía IP empresarial conceptos básicos de planeación en Skype Empresarial Server, incluidos sitios, regiones, vínculos de red entre sitios y estimación del tráfico de uso de voz.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825680"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="53840-103">Plan for Telefonía IP empresarial in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="53840-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="53840-104">Telefonía IP empresarial conceptos básicos de planeación en Skype Empresarial Server, incluidos sitios, regiones, vínculos de red entre sitios y estimación del tráfico de uso de voz.</span><span class="sxs-lookup"><span data-stu-id="53840-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="53840-105">El proceso de implementación Telefonía IP empresarial depende de la topología, la infraestructura y la funcionalidad de Telefonía IP empresarial existentes que desee admitir.</span><span class="sxs-lookup"><span data-stu-id="53840-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="53840-106">Los procedimientos pertinentes dependerán de las características que se eligen, pero también es preciso tener en cuenta otros aspectos de la planeación que deben realizarse en un nivel más específico.</span><span class="sxs-lookup"><span data-stu-id="53840-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="53840-107">En general, debe tenerse en cuenta el tipo y la cantidad de sitios que desea implementar, así como sus ubicaciones geográficas, el volumen de llamadas de cada sitio, las clases de vínculos de red que conectan sitios, si desea proporcionar redundancia y conmutación por error para funcionalidad de voz en cada sitio, y si desea usar el equipo de central de conmutación existente.</span><span class="sxs-lookup"><span data-stu-id="53840-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="53840-108">Hay algunas consideraciones, como la alta disponibilidad, que debe tener en cuenta al planear Skype Empresarial Server en su totalidad.</span><span class="sxs-lookup"><span data-stu-id="53840-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="53840-109">Estas consideraciones se tratan en los temas de la sección según convenga.</span><span class="sxs-lookup"><span data-stu-id="53840-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="53840-110">Sitios y regiones</span><span class="sxs-lookup"><span data-stu-id="53840-110">Sites and regions</span></span>

<span data-ttu-id="53840-111">En primer lugar, identifique los sitios de la topología en los que implementará Telefonía IP empresarial y las regiones de red a las que pertenecen dichos sitios.</span><span class="sxs-lookup"><span data-stu-id="53840-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="53840-112">En concreto, tenga en cuenta la forma en que proporcionará conectividad de red telefónica conmutada (RTC) a cada sitio.</span><span class="sxs-lookup"><span data-stu-id="53840-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="53840-113">Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo.</span><span class="sxs-lookup"><span data-stu-id="53840-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="53840-114">Decida dónde se implementarán las puertas de enlace localmente, dónde se implementarán las aplicaciones de sucursal con funciones de supervivencia (SBA) y dónde puede configurar troncos SIP (ya sea localmente o en el sitio central) para un proveedor de servicios de telefonía por Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="53840-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="53840-115">Vínculos de red entre sitios</span><span class="sxs-lookup"><span data-stu-id="53840-115">Network links between sites</span></span>

<span data-ttu-id="53840-116">También debe tener en cuenta el uso de ancho de banda que espera en los vínculos de red entre el sitio central y sus sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="53840-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="53840-117">Si tiene o planea implementar vínculos WAN resistentes entre sitios, le recomendamos que implemente una puerta de enlace en cada sitio de sucursal para proporcionar una terminación de llamada directa a la extensión (DID) local para los usuarios de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="53840-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="53840-118">Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN esté restringido, configure el control de admisión de llamadas para ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="53840-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="53840-119">Si no tiene vínculos WAN resistentes, aloje menos de 1000 usuarios en su sucursal y no tenga disponibles administradores locales formados de Skype Empresarial Server, le recomendamos que implemente una aplicación de sucursal con funciones de supervivencia en la sucursal.</span><span class="sxs-lookup"><span data-stu-id="53840-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="53840-120">Si hospeda entre 1000 y 5000 usuarios en su sucursal, carece de una conexión WAN resistente y dispone de administradores de Skype Empresarial Server formados, le recomendamos que implemente un servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña en la sucursal.</span><span class="sxs-lookup"><span data-stu-id="53840-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="53840-121">Considere también la posibilidad de habilitar la omisión de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admita la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="53840-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="53840-122">Estimación del tráfico y el uso de voz</span><span class="sxs-lookup"><span data-stu-id="53840-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="53840-123">La Herramienta de planeación de Microsoft Lync Server 2013 usa la siguiente métrica para calcular el tráfico de usuarios en cada sitio y el número de puertos necesarios para admitir ese tráfico.</span><span class="sxs-lookup"><span data-stu-id="53840-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="53840-124">Para **Tráfico reducido** (una llamada de RTC por usuario y hora) calcula 15 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="53840-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="53840-125">Para **Tráfico medio** (dos llamadas de RTC por usuario y hora) calcula 10 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="53840-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="53840-126">Para **Tráfico denso** (tres llamadas o más de RTC por usuario y hora) calcula 5 usuarios por puerto.</span><span class="sxs-lookup"><span data-stu-id="53840-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="53840-127">A su vez, el número de puertos determina el número de servidores de mediación y puertas de enlace que serán necesarios.</span><span class="sxs-lookup"><span data-stu-id="53840-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="53840-128">Las puertas de enlace de la red telefónica conmutada (RTC) que la mayoría de las organizaciones consideran implementar varían de 2 puertos a hasta 960 puertos.</span><span class="sxs-lookup"><span data-stu-id="53840-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="53840-129">(Hay puertas de enlace incluso más grandes, pero las usan principalmente los proveedores de servicios de telefonía).</span><span class="sxs-lookup"><span data-stu-id="53840-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="53840-p106">Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. El número de puertas de enlace requeridas equivaldría al número total de puertos requeridos determinado por la capacidad total de las puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="53840-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="53840-132">Componentes, características y opciones de Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="53840-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="53840-133">Vea las siguientes secciones para obtener más información sobre la planeación de la Telefonía IP empresarial implementación.</span><span class="sxs-lookup"><span data-stu-id="53840-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="53840-134">Componentes necesarios para Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53840-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="53840-135">Planear la conectividad con RTC en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53840-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="53840-136">Configuración de red para las características de Telefonía IP empresarial avanzadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53840-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="53840-137">Planear el control de admisión de llamadas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53840-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="53840-138">Planificar los servicios de emergencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53840-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="53840-139">Planear la omisión de medios en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="53840-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="53840-140">Planificar líneas de teléfono privadas con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="53840-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="53840-141">Plan for Location-Based Routing in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="53840-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="53840-142">Planear las características de administración de llamadas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="53840-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="53840-143">Planeación de Telefonía IP empresarial resistencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="53840-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

