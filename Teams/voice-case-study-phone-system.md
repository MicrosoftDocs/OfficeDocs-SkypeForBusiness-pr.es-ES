---
title: Caso práctico de Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786097"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="44ae4-103">Caso práctico Contoso: Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="44ae4-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="44ae4-104">Según la ubicación geográfica y otros factores, Contoso tenía oficinas con las siguientes soluciones de telefonía:</span><span class="sxs-lookup"><span data-stu-id="44ae4-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="44ae4-105">Tipo de sitio A: Skype Empresarial Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="44ae4-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="44ae4-106">Tipo de sitio B: sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="44ae4-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="44ae4-107">Tipo de sitio C: Una combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="44ae4-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="44ae4-108">Para implementar una solución de Microsoft Phone System para toda la organización, Contoso tenía que determinar para cada tipo de sitio cuál de las siguientes opciones se usaría con Sistema telefónico para conectarse a la red telefónica conmutada &mdash; &mdash; (RTC):</span><span class="sxs-lookup"><span data-stu-id="44ae4-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="44ae4-109">Sistema telefónico con plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="44ae4-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="44ae4-110">Sistema telefónico con un operador RTC propio a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="44ae4-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="44ae4-111">Combinación de sistema telefónico con plan de llamadas y sistema telefónico con un operador RTC propio a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="44ae4-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="44ae4-112">Para determinar la solución adecuada para su organización, Contoso usó soluciones de telefonía de [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) y las llamadas de sesión de Ignite 2019 [en Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="44ae4-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="44ae4-113">Tipo de sitio A: Skype Empresarial Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="44ae4-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="44ae4-114">El sitio de Skype Telefonía IP empresarial Contoso se ha configurado como un concentrador y se ha hablado.</span><span class="sxs-lookup"><span data-stu-id="44ae4-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="44ae4-115">Había una ubicación central donde se conservaba la puerta de enlace RTC en la región que proporcionaba la conexión a RTC para los usuarios de Skype Empresarial Telefonía IP empresarial del país.</span><span class="sxs-lookup"><span data-stu-id="44ae4-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="44ae4-116">A menudo, estas oficinas satélite no tenía su propia salida de Internet.</span><span class="sxs-lookup"><span data-stu-id="44ae4-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="44ae4-117">Los números de estos usuarios residen en el tronco SIP que se conecta a un SBC existente.</span><span class="sxs-lookup"><span data-stu-id="44ae4-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="44ae4-118">Para determinar si la SBC ya implementada está certificada para enrutamiento directo y omisión de medios, Contoso revisó la lista de controladores de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="44ae4-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="44ae4-119">Los hábitos de marcación del usuario eran marcar a un usuario en el sistema de telefonía heredado con una extensión, incluso cuando el usuario tiene un cliente de Skype Empresarial disponible para el audio de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="44ae4-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="44ae4-120">Contoso se basa en su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="44ae4-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="44ae4-121">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-121">Q.</span></span> <span data-ttu-id="44ae4-122">¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="44ae4-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="44ae4-123">A.</span><span class="sxs-lookup"><span data-stu-id="44ae4-123">A.</span></span> <span data-ttu-id="44ae4-124">No</span><span class="sxs-lookup"><span data-stu-id="44ae4-124">No</span></span> 

- <span data-ttu-id="44ae4-125">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-125">Q.</span></span> <span data-ttu-id="44ae4-126">¿Es necesario interactuar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="44ae4-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="44ae4-127">A.</span><span class="sxs-lookup"><span data-stu-id="44ae4-127">A.</span></span> <span data-ttu-id="44ae4-128">No</span><span class="sxs-lookup"><span data-stu-id="44ae4-128">No</span></span> 

- <span data-ttu-id="44ae4-129">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-129">Q.</span></span> <span data-ttu-id="44ae4-130">¿Debemos conservar nuestro operador actual de terceros?</span><span class="sxs-lookup"><span data-stu-id="44ae4-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="44ae4-131">A. Sí (países regulados) y No</span><span class="sxs-lookup"><span data-stu-id="44ae4-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="44ae4-132">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-132">Q.</span></span> <span data-ttu-id="44ae4-133">¿Es necesario implementar el ROI de los SBCs?</span><span class="sxs-lookup"><span data-stu-id="44ae4-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="44ae4-134">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="44ae4-134">A. Yes and No</span></span>  

- <span data-ttu-id="44ae4-135">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-135">Q.</span></span> <span data-ttu-id="44ae4-136">¿Los planes de llamadas RTC de Microsoft están disponibles en esta región?</span><span class="sxs-lookup"><span data-stu-id="44ae4-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="44ae4-137">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="44ae4-137">A. Yes and No</span></span> 

<span data-ttu-id="44ae4-138">Basándose en las respuestas a sus preguntas, Contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="44ae4-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="44ae4-139">Mueva los usuarios ubicados en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="44ae4-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="44ae4-140">Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles, los usuarios ubicados en un sitio donde aún no se ha cumplido el ROI de los SBCs y los usuarios que residen en un país que tiene normativas de telefonía a Sistema telefónico con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="44ae4-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="44ae4-141">En el siguiente diagrama se muestra la implementación inicial de Telefonía IP empresarial empresarial y cómo se ha migrado esta implementación tanto a los planes de llamadas de Microsoft como al enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="44ae4-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagrama que muestra los estados de antes y después](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="44ae4-143">Tipo de sitio B: sistemas de telefonía tradicionales heredados</span><span class="sxs-lookup"><span data-stu-id="44ae4-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="44ae4-144">Contoso tenía muchas oficinas que aprovechaban los sistemas de telefonía heredados.</span><span class="sxs-lookup"><span data-stu-id="44ae4-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="44ae4-145">Había un subconjunto de usuarios que tenían un número de teléfono E1.64 mientras que otros solo tenían una extensión.</span><span class="sxs-lookup"><span data-stu-id="44ae4-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="44ae4-146">Estos números residen en el tronco TDM de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="44ae4-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="44ae4-147">El marcado entre sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="44ae4-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="44ae4-148">Los hábitos de marcación de los usuarios eran marcar por extensión.</span><span class="sxs-lookup"><span data-stu-id="44ae4-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="44ae4-149">Contoso se basa en su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="44ae4-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="44ae4-150">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-150">Q.</span></span> <span data-ttu-id="44ae4-151">¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="44ae4-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="44ae4-152">A.</span><span class="sxs-lookup"><span data-stu-id="44ae4-152">A.</span></span> <span data-ttu-id="44ae4-153">No</span><span class="sxs-lookup"><span data-stu-id="44ae4-153">No</span></span> 

- <span data-ttu-id="44ae4-154">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-154">Q.</span></span> <span data-ttu-id="44ae4-155">¿Es necesario interactuar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="44ae4-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="44ae4-156">A. Sí</span><span class="sxs-lookup"><span data-stu-id="44ae4-156">A. Yes</span></span>

- <span data-ttu-id="44ae4-157">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-157">Q.</span></span> <span data-ttu-id="44ae4-158">¿Debemos conservar nuestro operador actual de terceros?</span><span class="sxs-lookup"><span data-stu-id="44ae4-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="44ae4-159">A. No</span><span class="sxs-lookup"><span data-stu-id="44ae4-159">A. No</span></span> 

- <span data-ttu-id="44ae4-160">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-160">Q.</span></span> <span data-ttu-id="44ae4-161">¿El plan de llamadas RTC de Microsoft está disponible en nuestra región?</span><span class="sxs-lookup"><span data-stu-id="44ae4-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="44ae4-162">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="44ae4-162">A. Yes and No</span></span> 

<span data-ttu-id="44ae4-163">Basándose en las respuestas a sus preguntas, Contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="44ae4-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="44ae4-164">Mueva los usuarios ubicados en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="44ae4-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="44ae4-165">Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="44ae4-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="44ae4-166">Mantenga una conexión RTC a dispositivos analógicos críticos para la empresa.</span><span class="sxs-lookup"><span data-stu-id="44ae4-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="44ae4-167">Los siguientes diagramas muestran la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización de medios locales:</span><span class="sxs-lookup"><span data-stu-id="44ae4-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="44ae4-168">**Implementación heredada original**  
 ![ Diagrama que muestra los estados de antes y después](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="44ae4-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="44ae4-169">**Implementación con enrutamiento directo**</span><span class="sxs-lookup"><span data-stu-id="44ae4-169">**Deployment with Direct Routing**</span></span>

![Diagrama que muestra los estados de antes y después](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="44ae4-171">Tipo de sitio C: combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="44ae4-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="44ae4-172">Contoso Skype Empresarial y Telefonía IP empresarial los números de los usuarios residen en el tronco SIP al SBC desde el operador.</span><span class="sxs-lookup"><span data-stu-id="44ae4-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="44ae4-173">Los números de los sistemas de telefonía tradicionales residen en el tronco TDM de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="44ae4-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="44ae4-174">Contoso se basa en su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="44ae4-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="44ae4-175">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-175">Q.</span></span> <span data-ttu-id="44ae4-176">¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="44ae4-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="44ae4-177">A.</span><span class="sxs-lookup"><span data-stu-id="44ae4-177">A.</span></span> <span data-ttu-id="44ae4-178">No</span><span class="sxs-lookup"><span data-stu-id="44ae4-178">No</span></span> 

- <span data-ttu-id="44ae4-179">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-179">Q.</span></span> <span data-ttu-id="44ae4-180">¿Es necesario interactuar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="44ae4-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="44ae4-181">A. No</span><span class="sxs-lookup"><span data-stu-id="44ae4-181">A. No</span></span> 

- <span data-ttu-id="44ae4-182">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-182">Q.</span></span> <span data-ttu-id="44ae4-183">¿Debemos conservar nuestro operador actual de terceros?</span><span class="sxs-lookup"><span data-stu-id="44ae4-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="44ae4-184">A. No</span><span class="sxs-lookup"><span data-stu-id="44ae4-184">A. No</span></span> 

- <span data-ttu-id="44ae4-185">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-185">Q.</span></span> <span data-ttu-id="44ae4-186">¿Es necesario implementar el ROI de los SBCs?</span><span class="sxs-lookup"><span data-stu-id="44ae4-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="44ae4-187">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="44ae4-187">A. Yes and No</span></span>  

- <span data-ttu-id="44ae4-188">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-188">Q.</span></span> <span data-ttu-id="44ae4-189">¿El plan de llamadas RTC de Microsoft está disponible en esta región?</span><span class="sxs-lookup"><span data-stu-id="44ae4-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="44ae4-190">A. No</span><span class="sxs-lookup"><span data-stu-id="44ae4-190">A. No</span></span> 

<span data-ttu-id="44ae4-191">Basándose en las respuestas a sus preguntas, Contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="44ae4-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="44ae4-192">Para los usuarios de telefonía heredados que se habilitarán para enrutamiento directo, Contoso portó los números desde el tronco TDM al tronco SIP para la SBC, ya que SBC está certificado para enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="44ae4-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="44ae4-193">Para admitir un subconjunto de usuarios que se mueven a Sistema telefónico y permitir la continuación del enrutamiento a través del sistema heredado, el sistema de telefonía heredado se estableció como el próximo salto a la SBC.</span><span class="sxs-lookup"><span data-stu-id="44ae4-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="44ae4-194">Además, para fomentar el cambio en el comportamiento de los usuarios y quitar la dependencia del marcado de extensiones entre sitios y entre sitios, Contoso proporciona una guía para usar Teams para todas las llamadas internas.</span><span class="sxs-lookup"><span data-stu-id="44ae4-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="44ae4-195">Los siguientes diagramas muestran la implementación original del Telefonía IP empresarial skype empresarial y del sistema de telefonía heredado y la migración a una implementación mixta mediante enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="44ae4-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="44ae4-196">**Implementación mixta original** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="44ae4-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="44ae4-197">**Implementación mixta con enrutamiento directo** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="44ae4-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="44ae4-198">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="44ae4-198">Calling Plans</span></span>

<span data-ttu-id="44ae4-199">Para determinar los requisitos de configuración para los planes de llamadas, Contoso revisó las decisiones de implementación [básicas del plan de llamadas.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="44ae4-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="44ae4-200">Se tomaron las decisiones resultantes:</span><span class="sxs-lookup"><span data-stu-id="44ae4-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="44ae4-201">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-201">Q.</span></span> <span data-ttu-id="44ae4-202">¿Mis usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="44ae4-202">Do my users need international calling?</span></span><br> <span data-ttu-id="44ae4-203">A. Sí</span><span class="sxs-lookup"><span data-stu-id="44ae4-203">A. Yes</span></span> 

- <span data-ttu-id="44ae4-204">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-204">Q.</span></span> <span data-ttu-id="44ae4-205">¿Tienen mis usuarios cada uno un número de teléfono que se haya recibido directamente?</span><span class="sxs-lookup"><span data-stu-id="44ae4-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="44ae4-206">A. Hoy no.</span><span class="sxs-lookup"><span data-stu-id="44ae4-206">A. Not today.</span></span> <span data-ttu-id="44ae4-207">Todos los usuarios habilitados recibirán un DID.</span><span class="sxs-lookup"><span data-stu-id="44ae4-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="44ae4-208">P.</span><span class="sxs-lookup"><span data-stu-id="44ae4-208">Q.</span></span> <span data-ttu-id="44ae4-209">¿Quiero enmascarar o deshabilitar la identificación de llamadas?</span><span class="sxs-lookup"><span data-stu-id="44ae4-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="44ae4-210">A. El identificador de llamada de un usuario se ocultará al número local de Contoso.</span><span class="sxs-lookup"><span data-stu-id="44ae4-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="44ae4-211">Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="44ae4-211">Direct Routing</span></span>

<span data-ttu-id="44ae4-212">Contoso ha asistido a Ignite para mantenerse al día sobre las características de Office 365, incluidas las disponibles con Sistema telefónico y Enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="44ae4-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="44ae4-213">El liderazgo técnico y los arquitectos usaron las instrucciones proporcionadas durante Ignite 2019 para determinar su dirección.</span><span class="sxs-lookup"><span data-stu-id="44ae4-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="44ae4-214">Sesiones clave que se han usado:</span><span class="sxs-lookup"><span data-stu-id="44ae4-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="44ae4-215">Plan de éxito con enrutamiento directo de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44ae4-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="44ae4-216">Actualizaciones de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="44ae4-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="44ae4-217">Configuración</span><span class="sxs-lookup"><span data-stu-id="44ae4-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="44ae4-218">Sitios de planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="44ae4-218">Calling Plans sites</span></span>

<span data-ttu-id="44ae4-219">Para obtener licencias y asignar números de teléfono a los usuarios, Contoso ha seguido los pasos de [Configurar planes de llamadas.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="44ae4-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="44ae4-220">Debido a la cantidad de usuarios a los que era necesario asignar números de teléfono, Contoso decidió usar PowerShell para asignar los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="44ae4-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="44ae4-221">Para obtener información sobre cómo asignar números con PowerShell, además de otras opciones de configuración, &mdash; &mdash; Contoso usó la información general de [PowerShell de Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="44ae4-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="44ae4-222">Sitios de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="44ae4-222">Direct Routing sites</span></span>

<span data-ttu-id="44ae4-223">Para conectar la infraestructura de telefonía local de Contoso a Microsoft Teams, el administrador de Contoso ha seguido los pasos de Configurar enrutamiento directo y ha revisado el vídeo Enrutamiento directo en [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones. [](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="44ae4-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="44ae4-224">Contoso también hizo referencia a la documentación de implementación de enrutamiento directo del proveedor certificado de SBC.</span><span class="sxs-lookup"><span data-stu-id="44ae4-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="44ae4-225">Una vez que se configuró el enrutamiento directo entre SBC y Microsoft Phone System, contoso era necesario para probar la configuración.</span><span class="sxs-lookup"><span data-stu-id="44ae4-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="44ae4-226">Para ello, los administradores de Contoso usaron el cliente evaluador de SIP analizado en la sesión actualizaciones de enrutamiento directo en [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="44ae4-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="44ae4-227">La documentación y el script del cliente del evaluador SIP se descargaron desde el script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="44ae4-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="44ae4-228">Optimización de medios locales</span><span class="sxs-lookup"><span data-stu-id="44ae4-228">Local Media Optimization</span></span>

<span data-ttu-id="44ae4-229">Contoso vio la oportunidad de aprovechar la optimización de medios locales en las distintas regiones de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="44ae4-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="44ae4-230">Los escenarios compatibles con Contoso se describen en la [optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="44ae4-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="44ae4-231">La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44ae4-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="44ae4-232">Los pasos de configuración para la optimización de medios locales incluyen:</span><span class="sxs-lookup"><span data-stu-id="44ae4-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="44ae4-233">Configurar los sitios de usuario y SBC</span><span class="sxs-lookup"><span data-stu-id="44ae4-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="44ae4-234">Configure la SBC según la especificación de proveedor de SBC,</span><span class="sxs-lookup"><span data-stu-id="44ae4-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="44ae4-235">Agregar direcciones IP de confianza externa a cada sitio usado para la optimización de medios locales</span><span class="sxs-lookup"><span data-stu-id="44ae4-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="44ae4-236">Definir la topología de red</span><span class="sxs-lookup"><span data-stu-id="44ae4-236">Define the network topology</span></span> 

- <span data-ttu-id="44ae4-237">Definir la topología de red virtual</span><span class="sxs-lookup"><span data-stu-id="44ae4-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="44ae4-238">Determinar el modo: Omitir siempre o solo para los usuarios locales</span><span class="sxs-lookup"><span data-stu-id="44ae4-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="44ae4-239">Consideraciones sobre redes</span><span class="sxs-lookup"><span data-stu-id="44ae4-239">Networking considerations</span></span>

<span data-ttu-id="44ae4-240">Contoso tenía un número de usuarios que necesitaban trabajar de forma remota durante un largo período de tiempo después de que se habilitara para Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="44ae4-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="44ae4-241">Los usuarios usaban una VPN para acceder a determinadas aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="44ae4-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="44ae4-242">Mientras utilizas una VPN, los usuarios del sistema telefónico experimentaron una degradación de la calidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="44ae4-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="44ae4-243">Para resolver el problema de calidad, Contoso implementó el túnel dividido de VPN, que permitía que el tráfico de Office 365 atravesara Internet mientras la conexión a las aplicaciones internas seguía estando en la VPN.</span><span class="sxs-lookup"><span data-stu-id="44ae4-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="44ae4-244">Para implementar el túnel dividido de VPN, Contoso siguió las instrucciones de Implementar el túnel dividido de [VPN para Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)</span><span class="sxs-lookup"><span data-stu-id="44ae4-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





