---
title: Caso práctico de voz de Contoso
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
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786097"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="1af20-103">Caso práctico de Contoso: sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="1af20-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="1af20-104">En función de la ubicación geográfica y de otros factores, contoso tenía oficinas con las siguientes soluciones de telefonía:</span><span class="sxs-lookup"><span data-stu-id="1af20-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="1af20-105">Tipo de sitio A: voz de Skype empresarial Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af20-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="1af20-106">Tipo de sitio B: sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="1af20-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="1af20-107">Tipo de sitio C: una combinación de voz empresarial de Skype empresarial y sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="1af20-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="1af20-108">Para implementar una solución de sistema de Microsoft Phone para toda su organización, contoso tuvo que determinar &mdash; para cada tipo &mdash; de sitio cuáles de las siguientes opciones se usarían con el sistema telefónico para conectarse a la red de telefonía pública conmutada (RTC):</span><span class="sxs-lookup"><span data-stu-id="1af20-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="1af20-109">Sistema telefónico con plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="1af20-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="1af20-110">Sistema telefónico con su propio operador PSTN mediante enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1af20-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="1af20-111">Combinación de sistema telefónico con plan de llamadas y sistema telefónico con su propio operador PSTN por enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1af20-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="1af20-112">Para determinar la solución adecuada para su organización, contoso usó [soluciones de telefonía de Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) y las [llamadas de sesión de encendido 2019 en Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="1af20-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="1af20-113">Tipo de sitio A: voz de Skype empresarial Enterprise</span><span class="sxs-lookup"><span data-stu-id="1af20-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="1af20-114">Contoso Skype empresarial Enterprise Voice se configuró como un concentrador y un radio.</span><span class="sxs-lookup"><span data-stu-id="1af20-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="1af20-115">Había una ubicación central que mantuvo la puerta de enlace RTC en la región que proporcionó la conexión a la RTC para los usuarios de voz de Skype empresarial Enterprise en el país.</span><span class="sxs-lookup"><span data-stu-id="1af20-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="1af20-116">A menudo, estas oficinas satélite no tenían su propia conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="1af20-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="1af20-117">Los números de estos usuarios han residido en el tronco del SIP que se conecta a un SBC existente.</span><span class="sxs-lookup"><span data-stu-id="1af20-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="1af20-118">Para determinar si el SBC ya implementado está certificado para el enrutamiento directo y la omisión de medios, contoso ha activado la [lista de controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="1af20-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="1af20-119">Los hábitos de marcado del usuario han marcado a un usuario en el sistema de telefonía heredado con una extensión, incluso cuando el usuario tiene un cliente de Skype empresarial disponible para el audio de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1af20-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="1af20-120">Contoso basó su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="1af20-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="1af20-121">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-121">Q.</span></span> <span data-ttu-id="1af20-122">¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="1af20-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="1af20-123">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="1af20-123">A.</span></span> <span data-ttu-id="1af20-124">No</span><span class="sxs-lookup"><span data-stu-id="1af20-124">No</span></span> 

- <span data-ttu-id="1af20-125">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-125">Q.</span></span> <span data-ttu-id="1af20-126">¿Es necesario interoperar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="1af20-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="1af20-127">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="1af20-127">A.</span></span> <span data-ttu-id="1af20-128">No</span><span class="sxs-lookup"><span data-stu-id="1af20-128">No</span></span> 

- <span data-ttu-id="1af20-129">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-129">Q.</span></span> <span data-ttu-id="1af20-130">¿Necesitamos conservar nuestro operador actual de terceros?</span><span class="sxs-lookup"><span data-stu-id="1af20-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="1af20-131">A. sí (países regulados) y no</span><span class="sxs-lookup"><span data-stu-id="1af20-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="1af20-132">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-132">Q.</span></span> <span data-ttu-id="1af20-133">¿Necesitamos obtener la rentabilidad de la implementación de SBCs?</span><span class="sxs-lookup"><span data-stu-id="1af20-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="1af20-134">A. sí y no</span><span class="sxs-lookup"><span data-stu-id="1af20-134">A. Yes and No</span></span>  

- <span data-ttu-id="1af20-135">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-135">Q.</span></span> <span data-ttu-id="1af20-136">¿Están disponibles los planes de llamadas RTC de Microsoft en esta región?</span><span class="sxs-lookup"><span data-stu-id="1af20-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="1af20-137">A. sí y no</span><span class="sxs-lookup"><span data-stu-id="1af20-137">A. Yes and No</span></span> 

<span data-ttu-id="1af20-138">En función de las respuestas a sus preguntas, contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="1af20-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="1af20-139">Mueva los usuarios que se encuentren en una región en la que los planes de llamadas RTC estén disponibles para el sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1af20-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="1af20-140">Mueva los usuarios que no se encuentren en una región en la que los planes de llamadas RTC estén disponibles, los que se encuentren en un sitio donde todavía se haya cumplido el ROI de la SBCs y los usuarios que hayan residido en un país con la normativa de telefonía en el sistema telefónico con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="1af20-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="1af20-141">En el siguiente diagrama se muestra la implementación inicial de Skype empresarial Enterprise Voice y cómo se migró esta implementación a los planes de llamadas de Microsoft y al enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="1af20-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagrama que muestra los Estados antes y después](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="1af20-143">Tipo de sitio B: sistemas de telefonía heredados tradicionales</span><span class="sxs-lookup"><span data-stu-id="1af20-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="1af20-144">Contoso tenía muchas oficinas que aprovechaban sistemas de telefonía heredados.</span><span class="sxs-lookup"><span data-stu-id="1af20-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="1af20-145">Había un subconjunto de usuarios con un número de teléfono E 1.64, mientras que otros solo tenían una extensión.</span><span class="sxs-lookup"><span data-stu-id="1af20-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="1af20-146">Estos números residían en el tronco de los TDM para la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="1af20-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="1af20-147">El marcado interno de sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="1af20-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="1af20-148">Los hábitos de marcado de los usuarios han marcado por extensión.</span><span class="sxs-lookup"><span data-stu-id="1af20-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="1af20-149">Contoso basó su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="1af20-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="1af20-150">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-150">Q.</span></span> <span data-ttu-id="1af20-151">¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="1af20-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="1af20-152">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="1af20-152">A.</span></span> <span data-ttu-id="1af20-153">No</span><span class="sxs-lookup"><span data-stu-id="1af20-153">No</span></span> 

- <span data-ttu-id="1af20-154">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-154">Q.</span></span> <span data-ttu-id="1af20-155">¿Es necesario interoperar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="1af20-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="1af20-156">A. sí</span><span class="sxs-lookup"><span data-stu-id="1af20-156">A. Yes</span></span>

- <span data-ttu-id="1af20-157">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-157">Q.</span></span> <span data-ttu-id="1af20-158">¿Necesitamos conservar nuestro operador actual de terceros?</span><span class="sxs-lookup"><span data-stu-id="1af20-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="1af20-159">A. no</span><span class="sxs-lookup"><span data-stu-id="1af20-159">A. No</span></span> 

- <span data-ttu-id="1af20-160">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-160">Q.</span></span> <span data-ttu-id="1af20-161">¿Está disponible el plan de llamadas de Microsoft RTC en nuestra región?</span><span class="sxs-lookup"><span data-stu-id="1af20-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="1af20-162">A. sí y no</span><span class="sxs-lookup"><span data-stu-id="1af20-162">A. Yes and No</span></span> 

<span data-ttu-id="1af20-163">En función de las respuestas a sus preguntas, contoso decidió:</span><span class="sxs-lookup"><span data-stu-id="1af20-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="1af20-164">Mueva los usuarios que se encuentren en una región en la que los planes de llamadas RTC estén disponibles para el sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1af20-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="1af20-165">Mueva los usuarios que no se encuentren en una región en la que los planes de llamadas RTC estén disponibles para el sistema telefónico con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="1af20-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="1af20-166">Mantener una conexión RTC a dispositivos analógicos empresariales fundamentales.</span><span class="sxs-lookup"><span data-stu-id="1af20-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="1af20-167">Los siguientes diagramas muestran la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización local de elementos multimedia:</span><span class="sxs-lookup"><span data-stu-id="1af20-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="1af20-168">**Original legacy deployment**  
 Implementación ![ heredada original Diagrama que muestra los Estados antes y después](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="1af20-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="1af20-169">**Implementación con enrutamiento directo**</span><span class="sxs-lookup"><span data-stu-id="1af20-169">**Deployment with Direct Routing**</span></span>

![Diagrama que muestra los Estados antes y después](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="1af20-171">Tipo de sitio C: combinación de Skype empresarial Enterprise Voice y sistemas tradicionales de telefonía heredados</span><span class="sxs-lookup"><span data-stu-id="1af20-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="1af20-172">Los números de los usuarios de Skype empresarial empresarial de Contoso residen en el tronco del SIP para el SBC del transportista.</span><span class="sxs-lookup"><span data-stu-id="1af20-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="1af20-173">Los números de los sistemas de telefonía tradicionales residieron en el tronco de los TDM para la puerta de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="1af20-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="1af20-174">Contoso basó su decisión en las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="1af20-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="1af20-175">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-175">Q.</span></span> <span data-ttu-id="1af20-176">¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?</span><span class="sxs-lookup"><span data-stu-id="1af20-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="1af20-177">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="1af20-177">A.</span></span> <span data-ttu-id="1af20-178">No</span><span class="sxs-lookup"><span data-stu-id="1af20-178">No</span></span> 

- <span data-ttu-id="1af20-179">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-179">Q.</span></span> <span data-ttu-id="1af20-180">¿Es necesario interoperar con sistemas PBX de terceros y otros equipos de telefonía?</span><span class="sxs-lookup"><span data-stu-id="1af20-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="1af20-181">A. no</span><span class="sxs-lookup"><span data-stu-id="1af20-181">A. No</span></span> 

- <span data-ttu-id="1af20-182">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-182">Q.</span></span> <span data-ttu-id="1af20-183">¿Necesitamos conservar nuestro operador actual de terceros?</span><span class="sxs-lookup"><span data-stu-id="1af20-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="1af20-184">A. no</span><span class="sxs-lookup"><span data-stu-id="1af20-184">A. No</span></span> 

- <span data-ttu-id="1af20-185">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-185">Q.</span></span> <span data-ttu-id="1af20-186">¿Necesitamos obtener la rentabilidad de la implementación de SBCs?</span><span class="sxs-lookup"><span data-stu-id="1af20-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="1af20-187">A. sí y no</span><span class="sxs-lookup"><span data-stu-id="1af20-187">A. Yes and No</span></span>  

- <span data-ttu-id="1af20-188">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-188">Q.</span></span> <span data-ttu-id="1af20-189">¿Está disponible el plan de llamadas RTC de Microsoft en esta región?</span><span class="sxs-lookup"><span data-stu-id="1af20-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="1af20-190">A. no</span><span class="sxs-lookup"><span data-stu-id="1af20-190">A. No</span></span> 

<span data-ttu-id="1af20-191">En función de las respuestas a sus preguntas, contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1af20-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="1af20-192">Para los usuarios de telefonía heredados que se habilitarán para el enrutamiento directo, contoso transportó los números del tronco de los TDM al tronco del SIP para el SBC, ya que la SBC está certificada para el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="1af20-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="1af20-193">Para admitir un subconjunto de usuarios que se mueven a un sistema telefónico y para permitir el enrutamiento continuo a través del sistema heredado, el sistema de telefonía heredado se configuró como el próximo salto a SBC.</span><span class="sxs-lookup"><span data-stu-id="1af20-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="1af20-194">Además, para alentar el cambio del comportamiento de los usuarios y quitar la dependencia de la llamada de extensión entre sitios y entre sitios, contoso ofreció la orientación de usar Teams para todas las llamadas internas.</span><span class="sxs-lookup"><span data-stu-id="1af20-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="1af20-195">Los siguientes diagramas muestran la implementación original de Skype empresarial Enterprise Voice y del sistema de telefonía heredada y la migración a una implementación mixta con enrutamiento directo:</span><span class="sxs-lookup"><span data-stu-id="1af20-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="1af20-196">**Original mixed deployment** 
 Implementación ![ mixta original Diagrama que muestra antes del estado](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="1af20-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="1af20-197">**Implementación mixta con enrutamiento directo** 
 ![ Diagrama que muestra antes del estado](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="1af20-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="1af20-198">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="1af20-198">Calling Plans</span></span>

<span data-ttu-id="1af20-199">Para determinar los requisitos de configuración para los planes de llamadas, contoso ha revisado las [decisiones básicas de implementación del plan de llamadas](calling-plan-landing-page.md#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="1af20-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="1af20-200">Las decisiones resultantes se hicieron:</span><span class="sxs-lookup"><span data-stu-id="1af20-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="1af20-201">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-201">Q.</span></span> <span data-ttu-id="1af20-202">¿Los usuarios necesitan llamadas internacionales?</span><span class="sxs-lookup"><span data-stu-id="1af20-202">Do my users need international calling?</span></span><br> <span data-ttu-id="1af20-203">A. sí</span><span class="sxs-lookup"><span data-stu-id="1af20-203">A. Yes</span></span> 

- <span data-ttu-id="1af20-204">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-204">Q.</span></span> <span data-ttu-id="1af20-205">¿Cada uno de mis usuarios tiene un número de teléfono directo?</span><span class="sxs-lookup"><span data-stu-id="1af20-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="1af20-206">A. no hoy.</span><span class="sxs-lookup"><span data-stu-id="1af20-206">A. Not today.</span></span> <span data-ttu-id="1af20-207">Todos los usuarios habilitados recibirán una.</span><span class="sxs-lookup"><span data-stu-id="1af20-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="1af20-208">W.</span><span class="sxs-lookup"><span data-stu-id="1af20-208">Q.</span></span> <span data-ttu-id="1af20-209">¿Quiero enmascarar o deshabilitar la identificación de llamadas?</span><span class="sxs-lookup"><span data-stu-id="1af20-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="1af20-210">A. la identificación de llamadas de un usuario se enmascarará al número local de contoso.</span><span class="sxs-lookup"><span data-stu-id="1af20-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="1af20-211">Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1af20-211">Direct Routing</span></span>

<span data-ttu-id="1af20-212">El encendido asistido de Contoso para mantenerse al día en las características de Office 365, incluidas las disponibles con el sistema telefónico y el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="1af20-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="1af20-213">Los arquitectos y el liderazgo técnico usaban las orientaciones proporcionadas durante el encendido 2019 para determinar su dirección.</span><span class="sxs-lookup"><span data-stu-id="1af20-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="1af20-214">Sesiones clave que se usaron:</span><span class="sxs-lookup"><span data-stu-id="1af20-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="1af20-215">Planear el éxito con el enrutamiento directo de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1af20-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="1af20-216">Actualizaciones para enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1af20-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="1af20-217">Configuración</span><span class="sxs-lookup"><span data-stu-id="1af20-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="1af20-218">Sitios de llamadas</span><span class="sxs-lookup"><span data-stu-id="1af20-218">Calling Plans sites</span></span>

<span data-ttu-id="1af20-219">Para obtener licencias y asignar números de teléfono a los usuarios, contoso siguió los pasos de [configurar planes de llamadas](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1af20-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="1af20-220">Debido al número de usuarios a los que se necesitaba asignar números de teléfono, contoso decidió usar PowerShell para asignar los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="1af20-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="1af20-221">Para obtener información sobre cómo asignar números usando PowerShell además de &mdash; otras opciones, &mdash; contoso usó la [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1af20-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="1af20-222">Sitios de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="1af20-222">Direct Routing sites</span></span>

<span data-ttu-id="1af20-223">Para conectar la infraestructura de telefonía local de Contoso con Microsoft Teams, el administrador de Contoso siguió los pasos que se indican en [configurar el enrutamiento directo](direct-routing-configure.md) y revisar el enrutamiento de video [directo en Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1af20-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="1af20-224">Contoso también hace referencia a la documentación de implementación de enrutamiento directo del proveedor de SBC certificado.</span><span class="sxs-lookup"><span data-stu-id="1af20-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="1af20-225">Una vez que se configuró el enrutamiento directo entre el SBC y el sistema telefónico de Microsoft, contoso era necesario para probar la configuración.</span><span class="sxs-lookup"><span data-stu-id="1af20-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="1af20-226">Para ello, los administradores de Contoso han usado el cliente SIP Tester que se analizó en las [actualizaciones para la sesión de enrutamiento directo en el encendido 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="1af20-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="1af20-227">El script de cliente de prueba SIP y la documentación se descargaron desde el script de PowerShell para probar el enrutamiento directo de las conexiones del controlador de borde de sesión.</span><span class="sxs-lookup"><span data-stu-id="1af20-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="1af20-228">Optimización local de medios</span><span class="sxs-lookup"><span data-stu-id="1af20-228">Local Media Optimization</span></span>

<span data-ttu-id="1af20-229">Contoso vio la oportunidad de aprovechar la optimización local de medios en las distintas regiones de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="1af20-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="1af20-230">Los escenarios admitidos para contoso se describen en la [optimización local de medios para el enrutamiento directo](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="1af20-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="1af20-231">La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1af20-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="1af20-232">Los pasos de configuración para la optimización de medios locales son:</span><span class="sxs-lookup"><span data-stu-id="1af20-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="1af20-233">Configurar los sitios de usuario y SBC</span><span class="sxs-lookup"><span data-stu-id="1af20-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="1af20-234">Configurar la SBC según la especificación de proveedor de SBC,</span><span class="sxs-lookup"><span data-stu-id="1af20-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="1af20-235">Agregar direcciones IP de confianza externas a cada sitio usado para la optimización de multimedia local</span><span class="sxs-lookup"><span data-stu-id="1af20-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="1af20-236">Definir la topología de red</span><span class="sxs-lookup"><span data-stu-id="1af20-236">Define the network topology</span></span> 

- <span data-ttu-id="1af20-237">Definir la topología de red virtual</span><span class="sxs-lookup"><span data-stu-id="1af20-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="1af20-238">Determinar el modo: siempre omitir o solo para usuarios locales</span><span class="sxs-lookup"><span data-stu-id="1af20-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="1af20-239">Consideraciones sobre redes</span><span class="sxs-lookup"><span data-stu-id="1af20-239">Networking considerations</span></span>

<span data-ttu-id="1af20-240">Contoso tenía varios usuarios que necesitaban trabajar de forma remota durante un período de tiempo prolongado después de que estuvieran habilitados para el sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="1af20-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="1af20-241">Los usuarios usaron VPN para obtener acceso a determinadas aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="1af20-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="1af20-242">Mientras se encontraba en VPN, los usuarios del sistema telefónico experimentaron una degradación de la calidad de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="1af20-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="1af20-243">Para resolver el problema de calidad, contoso implementó el túnel dividido de VPN, que permitió que su tráfico de Office 365 atravesar Internet mientras la conexión a las aplicaciones internas seguía en la red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="1af20-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="1af20-244">Para implementar túneles divididos de VPN, contoso siguió las instrucciones de [implementación de túneles divididos de VPN para Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="1af20-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





