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
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786073"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="52884-103">Caso práctico de Contoso: Location-Based enrutamiento</span><span class="sxs-lookup"><span data-stu-id="52884-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="52884-104">Location-Based enrutamiento (LBR) es una característica que restringe la omisión de pago en función de la directiva y la ubicación física del usuario en el momento de realizar o recibir una llamada.</span><span class="sxs-lookup"><span data-stu-id="52884-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="52884-105">Información general</span><span class="sxs-lookup"><span data-stu-id="52884-105">Overview</span></span>

<span data-ttu-id="52884-106">Contoso tiene dos oficinas en un país donde es ilegal omitir el proveedor de red telefónica conmutada (RTC) para reducir los costos de llamadas de larga distancia.</span><span class="sxs-lookup"><span data-stu-id="52884-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="52884-107">La oficina principal tiene una conexión a Internet que usa la oficina principal y la segunda oficina.</span><span class="sxs-lookup"><span data-stu-id="52884-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="52884-108">Cada oficina tiene su propio controlador de borde de sesión (SBC) conectado a un operador RTC.</span><span class="sxs-lookup"><span data-stu-id="52884-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="52884-109">En este país, Contoso tenía LBR configurado para su Skype Empresarial implementación.</span><span class="sxs-lookup"><span data-stu-id="52884-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="52884-110">Para determinar cómo configurar LBR para Teams, Contoso leyó [Planear Location-Based enrutamiento directo](location-based-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="52884-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="52884-111">Contoso determinó que Teams y Skype Empresarial siguen los mismos escenarios en los que se puede realizar una llamada, cuando se puede recibir, cuando una llamada RTC se puede transferir a un usuario de Teams y cuando puede transferir otro usuario de Teams a la llamada RTC.</span><span class="sxs-lookup"><span data-stu-id="52884-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="52884-112">Por Skype Empresarial, LBR se configuró con el tronco SIP del controlador de borde de sesión (SBC) que se conecta al operador RTC.</span><span class="sxs-lookup"><span data-stu-id="52884-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="52884-113">Para este SBC, Contoso [](direct-routing-border-controllers.md) revisó la lista de SBC certificados y determinó que el SBC implementado está certificado para enrutamiento directo, pero no está certificado para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="52884-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="52884-114">Para admitir LBR, el enrutamiento directo debe configurarse en el SBC en el sitio, debe haber una salida de Internet local y el SBC debe configurarse para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="52884-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="52884-115">Basándose en esta información, Contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52884-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="52884-116">Para retrasar la habilitación de Teams LBR hasta que el SBC existente esté certificado para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="52884-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="52884-117">Contoso decidió usar el sitio principal SBC para la ruta directa para Office 365.</span><span class="sxs-lookup"><span data-stu-id="52884-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="52884-118">El SBC del sitio principal será el SBC proxy para el sitio remoto.</span><span class="sxs-lookup"><span data-stu-id="52884-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="52884-119">Contoso usó un consultor de terceros con sede en india para ayudar a certificar la configuración de LBR con la compañía de telefonía del país.</span><span class="sxs-lookup"><span data-stu-id="52884-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="52884-120">Para ayudar a los usuarios que trabajan desde fuera de la oficina a realizar llamadas RTC, la empresa emitió teléfonos móviles a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="52884-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="52884-121">En los diagramas siguientes se muestran las implementaciones antes y después de un país con normativas de telefonía que requieren Location-Based enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="52884-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="52884-122">**Implementación original**</span><span class="sxs-lookup"><span data-stu-id="52884-122">**Original deployment**</span></span>

![Diagrama que se muestra antes del estado](media/voice-case-study-5.png)

<span data-ttu-id="52884-124">**Implementación con enrutamiento directo**</span><span class="sxs-lookup"><span data-stu-id="52884-124">**Deployment with Direct Routing**</span></span>

![Diagrama que se muestra antes del estado](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="52884-126">Configuración:</span><span class="sxs-lookup"><span data-stu-id="52884-126">Configuration:</span></span> 

<span data-ttu-id="52884-127">Para configurar los componentes de red en Teams, Contoso siguió las instrucciones de Administrar la topología de red para las características [de voz en la nube.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="52884-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="52884-128">Contoso completó los pasos siguientes para configurar Location-Based enrutamiento:</span><span class="sxs-lookup"><span data-stu-id="52884-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="52884-129">Definir regiones de red: se ha definido una región de red.</span><span class="sxs-lookup"><span data-stu-id="52884-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="52884-130">Definir sitios de red: se han definido dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="52884-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="52884-131">Un sitio para cada ubicación de oficina de la región.</span><span class="sxs-lookup"><span data-stu-id="52884-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="52884-132">Definir subredes de red: cada planta de una ubicación de oficina tiene su propia subred para la red cableada e inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="52884-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="52884-133">Esta configuración dio como resultado 20 subredes para Contoso.</span><span class="sxs-lookup"><span data-stu-id="52884-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="52884-134">Definir direcciones IP de confianza: las direcciones IP externas del SBC se agregaron a la dirección IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="52884-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

