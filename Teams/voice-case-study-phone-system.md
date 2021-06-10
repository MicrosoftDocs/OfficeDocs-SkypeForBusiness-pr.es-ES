---
title: Teams caso práctico de Contoso de voz
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
description: Teams caso de voz para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101036"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="8c92a-103">Caso práctico de Contoso: Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8c92a-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="8c92a-104">Según la ubicación geográfica y otros factores, Contoso tenía oficinas con las siguientes soluciones de telefonía:</span><span class="sxs-lookup"><span data-stu-id="8c92a-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="8c92a-105">Tipo de sitio A: Skype Empresarial Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="8c92a-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="8c92a-106">Tipo de sitio B: Sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="8c92a-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="8c92a-107">Tipo de sitio C: una combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="8c92a-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="8c92a-108">Para implementar una solución del sistema Teléfono Microsoft para toda su organización, Contoso tenía que determinar para cada tipo de sitio cuál de las siguientes opciones se usaría con Sistema telefónico para conectarse a la red telefónica conmutada &mdash; &mdash; (RTC):</span><span class="sxs-lookup"><span data-stu-id="8c92a-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="8c92a-109">Sistema telefónico con plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="8c92a-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="8c92a-110">Sistema telefónico con un operador RTC propio a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8c92a-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="8c92a-111">Combinación de Sistema telefónico con plan de llamadas y Sistema telefónico con un operador RTC propio a través del enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8c92a-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="8c92a-112">Para determinar la solución adecuada para su organización, Contoso usó soluciones de telefonía de [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) y la sesión Ignite 2019 [Llamadas en Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="8c92a-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="8c92a-113">Tipo de sitio A: Skype Empresarial Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="8c92a-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="8c92a-114">Contoso Skype Empresarial Telefonía IP empresarial se ha configurado como concentrador y ha hablado.</span><span class="sxs-lookup"><span data-stu-id="8c92a-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="8c92a-115">Había una ubicación central que conservaba la puerta de enlace RTC en la región que proporcionaba la conexión a la RTC para los Skype Empresarial Telefonía IP empresarial en el país.</span><span class="sxs-lookup"><span data-stu-id="8c92a-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="8c92a-116">A menudo, estas oficinas de satélite no tienen su propia salida de Internet.</span><span class="sxs-lookup"><span data-stu-id="8c92a-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="8c92a-117">Los números de estos usuarios residían en el tronco SIP que se conectaba a un SBC existente.</span><span class="sxs-lookup"><span data-stu-id="8c92a-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="8c92a-118">Para determinar si el SBC ya implementado está certificado para enrutamiento directo y omisión de medios, Contoso ha activado la lista de controladores de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="8c92a-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="8c92a-119">Los hábitos de marcado del usuario eran marcar a un usuario en el sistema de telefonía heredado con una extensión, incluso cuando el usuario tiene un cliente de Skype Empresarial disponible para audio punto a punto.</span><span class="sxs-lookup"><span data-stu-id="8c92a-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="8c92a-120">Contoso basó su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="8c92a-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="8c92a-121">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-121">Q.</span></span> <span data-ttu-id="8c92a-122">¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="8c92a-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="8c92a-123">A.</span><span class="sxs-lookup"><span data-stu-id="8c92a-123">A.</span></span> <span data-ttu-id="8c92a-124">No</span><span class="sxs-lookup"><span data-stu-id="8c92a-124">No</span></span> 

- <span data-ttu-id="8c92a-125">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-125">Q.</span></span> <span data-ttu-id="8c92a-126">¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="8c92a-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="8c92a-127">A.</span><span class="sxs-lookup"><span data-stu-id="8c92a-127">A.</span></span> <span data-ttu-id="8c92a-128">No</span><span class="sxs-lookup"><span data-stu-id="8c92a-128">No</span></span> 

- <span data-ttu-id="8c92a-129">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-129">Q.</span></span> <span data-ttu-id="8c92a-130">¿Necesitamos conservar nuestro operador de terceros actual?</span><span class="sxs-lookup"><span data-stu-id="8c92a-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="8c92a-131">A. Sí (países regulados) y No</span><span class="sxs-lookup"><span data-stu-id="8c92a-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="8c92a-132">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-132">Q.</span></span> <span data-ttu-id="8c92a-133">¿Necesitamos implementar el ROI en SBC?</span><span class="sxs-lookup"><span data-stu-id="8c92a-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="8c92a-134">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="8c92a-134">A. Yes and No</span></span>  

- <span data-ttu-id="8c92a-135">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-135">Q.</span></span> <span data-ttu-id="8c92a-136">¿Los planes de llamadas RTC de Microsoft están disponibles en esta región?</span><span class="sxs-lookup"><span data-stu-id="8c92a-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="8c92a-137">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="8c92a-137">A. Yes and No</span></span> 

<span data-ttu-id="8c92a-138">En función de las respuestas a sus preguntas, Contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="8c92a-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="8c92a-139">Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c92a-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="8c92a-140">Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles, los usuarios ubicados en un sitio en el que aún no se ha cumplido el ROI de los SBC y los usuarios que residían en un país que tiene normativas de telefonía para Sistema telefónico con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8c92a-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="8c92a-141">En el siguiente diagrama se muestran las Skype Empresarial Telefonía IP empresarial iniciales y cómo se ha migrado esta implementación a planes de llamadas de Microsoft y enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="8c92a-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagrama que muestra los estados antes y después](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="8c92a-143">Tipo de sitio B: Sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="8c92a-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="8c92a-144">Contoso tenía muchas oficinas que aprovechaban sistemas de telefonía heredados.</span><span class="sxs-lookup"><span data-stu-id="8c92a-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="8c92a-145">Había un subconjunto de usuarios que tenían un número de teléfono E1.64, mientras que otros solo tenían una extensión.</span><span class="sxs-lookup"><span data-stu-id="8c92a-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="8c92a-146">Estos números residían en el tronco TDM de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="8c92a-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="8c92a-147">La marcación entre sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c92a-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="8c92a-148">Los hábitos de marcado de los usuarios eran marcar por extensión.</span><span class="sxs-lookup"><span data-stu-id="8c92a-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="8c92a-149">Contoso basó su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="8c92a-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="8c92a-150">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-150">Q.</span></span> <span data-ttu-id="8c92a-151">¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="8c92a-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="8c92a-152">A.</span><span class="sxs-lookup"><span data-stu-id="8c92a-152">A.</span></span> <span data-ttu-id="8c92a-153">No</span><span class="sxs-lookup"><span data-stu-id="8c92a-153">No</span></span> 

- <span data-ttu-id="8c92a-154">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-154">Q.</span></span> <span data-ttu-id="8c92a-155">¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="8c92a-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="8c92a-156">A. Sí</span><span class="sxs-lookup"><span data-stu-id="8c92a-156">A. Yes</span></span>

- <span data-ttu-id="8c92a-157">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-157">Q.</span></span> <span data-ttu-id="8c92a-158">¿Necesitamos conservar nuestro operador de terceros actual?</span><span class="sxs-lookup"><span data-stu-id="8c92a-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="8c92a-159">A. No</span><span class="sxs-lookup"><span data-stu-id="8c92a-159">A. No</span></span> 

- <span data-ttu-id="8c92a-160">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-160">Q.</span></span> <span data-ttu-id="8c92a-161">¿El Plan de llamadas RTC de Microsoft está disponible en nuestra región?</span><span class="sxs-lookup"><span data-stu-id="8c92a-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="8c92a-162">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="8c92a-162">A. Yes and No</span></span> 

<span data-ttu-id="8c92a-163">En función de las respuestas a sus preguntas, Contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="8c92a-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="8c92a-164">Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c92a-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="8c92a-165">Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8c92a-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="8c92a-166">Mantener una conexión RTC a dispositivos analógicos críticos para la empresa.</span><span class="sxs-lookup"><span data-stu-id="8c92a-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="8c92a-167">En los diagramas siguientes se muestra la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización de medios locales:</span><span class="sxs-lookup"><span data-stu-id="8c92a-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="8c92a-168">**Implementación heredada original**  
 ![ Diagrama que muestra los estados antes y después](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="8c92a-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="8c92a-169">**Implementación con enrutamiento directo**</span><span class="sxs-lookup"><span data-stu-id="8c92a-169">**Deployment with Direct Routing**</span></span>

![Diagrama que muestra los estados antes y después](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="8c92a-171">Tipo de sitio C: Combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="8c92a-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="8c92a-172">Contoso Skype Empresarial Telefonía IP empresarial los números de los usuarios residen en el tronco SIP al SBC desde el operador.</span><span class="sxs-lookup"><span data-stu-id="8c92a-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="8c92a-173">Los números de los sistemas de telefonía tradicionales residían en el tronco TDM de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="8c92a-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="8c92a-174">Contoso basó su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="8c92a-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="8c92a-175">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-175">Q.</span></span> <span data-ttu-id="8c92a-176">¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="8c92a-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="8c92a-177">A.</span><span class="sxs-lookup"><span data-stu-id="8c92a-177">A.</span></span> <span data-ttu-id="8c92a-178">No</span><span class="sxs-lookup"><span data-stu-id="8c92a-178">No</span></span> 

- <span data-ttu-id="8c92a-179">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-179">Q.</span></span> <span data-ttu-id="8c92a-180">¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="8c92a-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="8c92a-181">A. No</span><span class="sxs-lookup"><span data-stu-id="8c92a-181">A. No</span></span> 

- <span data-ttu-id="8c92a-182">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-182">Q.</span></span> <span data-ttu-id="8c92a-183">¿Necesitamos conservar nuestro operador de terceros actual?</span><span class="sxs-lookup"><span data-stu-id="8c92a-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="8c92a-184">A. No</span><span class="sxs-lookup"><span data-stu-id="8c92a-184">A. No</span></span> 

- <span data-ttu-id="8c92a-185">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-185">Q.</span></span> <span data-ttu-id="8c92a-186">¿Necesitamos implementar el ROI en SBC?</span><span class="sxs-lookup"><span data-stu-id="8c92a-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="8c92a-187">A. Sí y No</span><span class="sxs-lookup"><span data-stu-id="8c92a-187">A. Yes and No</span></span>  

- <span data-ttu-id="8c92a-188">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-188">Q.</span></span> <span data-ttu-id="8c92a-189">¿El Plan de llamadas RTC de Microsoft está disponible en esta región?</span><span class="sxs-lookup"><span data-stu-id="8c92a-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="8c92a-190">A. No</span><span class="sxs-lookup"><span data-stu-id="8c92a-190">A. No</span></span> 

<span data-ttu-id="8c92a-191">En función de las respuestas a sus preguntas, Contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c92a-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="8c92a-192">Para los usuarios de telefonía heredados que se habilitarán para enrutamiento directo, Contoso portó los números del tronco TDM al tronco SIP para el SBC, ya que el SBC está certificado para enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8c92a-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="8c92a-193">Para admitir un subconjunto de usuarios que se mueven a Sistema telefónico y permitir el enrutamiento continuo a través del sistema heredado, el sistema de telefonía heredado se ha configurado como el siguiente salto al SBC.</span><span class="sxs-lookup"><span data-stu-id="8c92a-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="8c92a-194">Además, para fomentar el cambio de comportamiento de los usuarios y quitar la dependencia en el marcado de extensiones entre sitios e internos, Contoso proporcionó instrucciones para usar Teams para todas las llamadas internas.</span><span class="sxs-lookup"><span data-stu-id="8c92a-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="8c92a-195">Los diagramas siguientes muestran la implementación original Skype Empresarial Telefonía IP empresarial sistema de telefonía heredado y la migración a una implementación mixta mediante enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="8c92a-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="8c92a-196">**Implementación mixta original** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="8c92a-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="8c92a-197">**Implementación mixta con enrutamiento directo** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="8c92a-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="8c92a-198">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="8c92a-198">Calling Plans</span></span>

<span data-ttu-id="8c92a-199">Para determinar los requisitos de configuración de los planes de llamadas, Contoso revisó las decisiones de implementación [principales del plan de llamadas.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="8c92a-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="8c92a-200">Se tomaron las decisiones resultantes:</span><span class="sxs-lookup"><span data-stu-id="8c92a-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="8c92a-201">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-201">Q.</span></span> <span data-ttu-id="8c92a-202">¿Mis usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="8c92a-202">Do my users need international calling?</span></span><br> <span data-ttu-id="8c92a-203">A. Sí</span><span class="sxs-lookup"><span data-stu-id="8c92a-203">A. Yes</span></span> 

- <span data-ttu-id="8c92a-204">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-204">Q.</span></span> <span data-ttu-id="8c92a-205">¿Mis usuarios tienen cada uno un número de teléfono did directo hacia adentro?</span><span class="sxs-lookup"><span data-stu-id="8c92a-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="8c92a-206">A. Hoy no.</span><span class="sxs-lookup"><span data-stu-id="8c92a-206">A. Not today.</span></span> <span data-ttu-id="8c92a-207">Todos los usuarios habilitados recibirán un DID.</span><span class="sxs-lookup"><span data-stu-id="8c92a-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="8c92a-208">P.</span><span class="sxs-lookup"><span data-stu-id="8c92a-208">Q.</span></span> <span data-ttu-id="8c92a-209">¿Quiero enmascarar o deshabilitar el identificador de llamada?</span><span class="sxs-lookup"><span data-stu-id="8c92a-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="8c92a-210">A. El identificador de llamada de un usuario se enmascarará con el número local de Contoso.</span><span class="sxs-lookup"><span data-stu-id="8c92a-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="8c92a-211">Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8c92a-211">Direct Routing</span></span>

<span data-ttu-id="8c92a-212">Contoso asistió a Ignite para mantenerse al día Office 365 características, incluidas las disponibles con Teléfono sistema y enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8c92a-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="8c92a-213">Los directores técnicos y los arquitectos usaron las instrucciones proporcionadas durante el Ignite 2019 para determinar su dirección.</span><span class="sxs-lookup"><span data-stu-id="8c92a-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="8c92a-214">Sesiones clave que se usaron:</span><span class="sxs-lookup"><span data-stu-id="8c92a-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="8c92a-215">Planear el éxito con Microsoft Teams enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8c92a-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="8c92a-216">Actualizaciones para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8c92a-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="8c92a-217">Configuración</span><span class="sxs-lookup"><span data-stu-id="8c92a-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="8c92a-218">Sitios de planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="8c92a-218">Calling Plans sites</span></span>

<span data-ttu-id="8c92a-219">Para obtener licencias y asignar números de teléfono a los usuarios, Contoso siguió los pasos de [Configurar planes de llamadas.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="8c92a-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="8c92a-220">Debido al número de usuarios a los que había que asignar números de teléfono, Contoso decidió usar PowerShell para asignar los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8c92a-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="8c92a-221">Para obtener información sobre cómo asignar números mediante PowerShell, además de otras opciones de configuración, Contoso usó el Teams información general &mdash; &mdash; de [PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8c92a-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="8c92a-222">Sitios de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8c92a-222">Direct Routing sites</span></span>

<span data-ttu-id="8c92a-223">Para conectar la infraestructura de telefonía local de Contoso a Microsoft Teams, el administrador de Contoso siguió los pasos de [Configurar](direct-routing-configure.md) enrutamiento directo y revisó el vídeo Enrutamiento directo [en Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8c92a-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="8c92a-224">Contoso también hizo referencia a la documentación de implementación de enrutamiento directo del proveedor certificado de SBC.</span><span class="sxs-lookup"><span data-stu-id="8c92a-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="8c92a-225">Una vez que el enrutamiento directo se configuró entre el sistema SBC y Teléfono Microsoft, era necesario que Contoso probara la configuración.</span><span class="sxs-lookup"><span data-stu-id="8c92a-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="8c92a-226">Para ello, los administradores de Contoso usaron el cliente probador SIP que se debatió en la sesión Actualizaciones para enrutamiento directo en [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="8c92a-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="8c92a-227">El script y la documentación del cliente de Prueba SIP se descargaron desde el script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="8c92a-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="8c92a-228">Optimización de medios locales</span><span class="sxs-lookup"><span data-stu-id="8c92a-228">Local Media Optimization</span></span>

<span data-ttu-id="8c92a-229">Contoso vio la oportunidad de aprovechar la optimización de medios locales en las diferentes regiones de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="8c92a-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="8c92a-230">Los escenarios admitidos para Contoso se describen en [Optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="8c92a-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="8c92a-231">La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c92a-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="8c92a-232">Los pasos de configuración de optimización de medios locales incluyen:</span><span class="sxs-lookup"><span data-stu-id="8c92a-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="8c92a-233">Configurar el usuario y los sitios de SBC</span><span class="sxs-lookup"><span data-stu-id="8c92a-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="8c92a-234">Configurar el SBC según la especificación de proveedor de SBC,</span><span class="sxs-lookup"><span data-stu-id="8c92a-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="8c92a-235">Agregar direcciones IP de confianza externa a cada sitio que se usa para la optimización de medios locales</span><span class="sxs-lookup"><span data-stu-id="8c92a-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="8c92a-236">Definir la topología de red</span><span class="sxs-lookup"><span data-stu-id="8c92a-236">Define the network topology</span></span> 

- <span data-ttu-id="8c92a-237">Definir la topología de red virtual</span><span class="sxs-lookup"><span data-stu-id="8c92a-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="8c92a-238">Determinar el modo: Omitir siempre o Solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="8c92a-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="8c92a-239">Consideraciones de red</span><span class="sxs-lookup"><span data-stu-id="8c92a-239">Networking considerations</span></span>

<span data-ttu-id="8c92a-240">Contoso tenía un número de usuarios que necesitaban trabajar de forma remota durante un período prolongado de tiempo después de que se habilitara para Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="8c92a-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="8c92a-241">Los usuarios usaron VPN para acceder a determinadas aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="8c92a-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="8c92a-242">Mientras se encuentra en VPN, Sistema telefónico usuarios experimentaron una degradación de la calidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c92a-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="8c92a-243">Para resolver el problema de calidad, Contoso implementó el túnel dividido de VPN, que permitía que su tráfico de Office 365 atravesara Internet mientras la conexión a las aplicaciones internas permanecía en la VPN.</span><span class="sxs-lookup"><span data-stu-id="8c92a-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="8c92a-244">Para implementar el túnel dividido de VPN, Contoso siguió las instrucciones de [Implementar túneles](/office365/enterprise/office-365-vpn-implement-split-tunnel)divididos de VPN para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="8c92a-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

