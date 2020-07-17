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
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786073"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="57dbd-103">Caso práctico de Contoso: enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="57dbd-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="57dbd-104">El enrutamiento basado en la ubicación (LBR) es una característica que restringe el omisión de peaje según la política y la ubicación física del usuario en el momento de poner o recibir una llamada.</span><span class="sxs-lookup"><span data-stu-id="57dbd-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="57dbd-105">Información general</span><span class="sxs-lookup"><span data-stu-id="57dbd-105">Overview</span></span>

<span data-ttu-id="57dbd-106">Contoso tiene dos oficinas en un país en el que no se puede eludir el proveedor de la red de telefonía pública conmutada (RTC) para reducir los gastos de llamadas de larga distancia.</span><span class="sxs-lookup"><span data-stu-id="57dbd-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="57dbd-107">La oficina principal tiene una conexión a Internet que es utilizada por la oficina principal y por la segunda oficina.</span><span class="sxs-lookup"><span data-stu-id="57dbd-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="57dbd-108">Cada oficina tiene su propio controlador de borde de sesión (SBC) conectado a una portadora RTC.</span><span class="sxs-lookup"><span data-stu-id="57dbd-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="57dbd-109">En este país, contoso tenía LBR configurado para la implementación de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="57dbd-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="57dbd-110">Para determinar cómo configurar LBR para Teams, plan de Contoso read [: enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="57dbd-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="57dbd-111">Contoso determinó que Teams y Skype empresarial siguen los mismos escenarios en los que se puede hacer una llamada, Cuándo se puede recibir, Cuándo se puede transferir una llamada RTC a un usuario de Teams y cuándo se puede transferir otro usuario de Teams a la llamada RTC.</span><span class="sxs-lookup"><span data-stu-id="57dbd-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="57dbd-112">Para Skype empresarial, LBR se configuró con el tronco del SIP del controlador de borde de sesión (SBC) que se conecta a la portadora RTC.</span><span class="sxs-lookup"><span data-stu-id="57dbd-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="57dbd-113">Para este SBC, contoso revisó la [lista de SBCS certificado](direct-routing-border-controllers.md) y determinó que el SBC implementado está certificado para enrutamiento directo, pero no está certificado para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="57dbd-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="57dbd-114">Para admitir LBR, debe configurarse el enrutamiento directo a la SBC en el sitio, debe haber una salida de Internet local y el SBC debe configurarse para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="57dbd-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="57dbd-115">En función de esta información, contoso decidió lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57dbd-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="57dbd-116">Para retrasar la habilitación de Teams LBR hasta que se certifique el SBC existente para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="57dbd-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="57dbd-117">Contoso decidió usar el SBC del sitio principal para la ruta directa a Office 365.</span><span class="sxs-lookup"><span data-stu-id="57dbd-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="57dbd-118">El SBC del sitio principal será el SBC de proxy para el sitio remoto.</span><span class="sxs-lookup"><span data-stu-id="57dbd-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="57dbd-119">Contoso usó un consultor de terceros basado en India para ayudarle con la certificación de la configuración de LBR con la empresa de telefonía en el país.</span><span class="sxs-lookup"><span data-stu-id="57dbd-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="57dbd-120">Para admitir usuarios que trabajan desde fuera de la oficina para realizar llamadas RTC, la empresa emitió el teléfono móvil a sus empleados.</span><span class="sxs-lookup"><span data-stu-id="57dbd-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="57dbd-121">En los siguientes diagramas se muestran las implementaciones antes y después de un país con normativas de telefonía que requieren enrutamiento basado en la ubicación:</span><span class="sxs-lookup"><span data-stu-id="57dbd-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="57dbd-122">**Implementación original**</span><span class="sxs-lookup"><span data-stu-id="57dbd-122">**Original deployment**</span></span>

![Diagrama que muestra antes del estado](media/voice-case-study-5.png)

<span data-ttu-id="57dbd-124">**Implementación con enrutamiento directo**</span><span class="sxs-lookup"><span data-stu-id="57dbd-124">**Deployment with Direct Routing**</span></span>

![Diagrama que muestra antes del estado](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="57dbd-126">Configuración</span><span class="sxs-lookup"><span data-stu-id="57dbd-126">Configuration:</span></span> 

<span data-ttu-id="57dbd-127">Para configurar los componentes de red de Teams, contoso siguió las instrucciones de la [topología de red para características de voz en la nube](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="57dbd-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="57dbd-128">Contoso completó los pasos siguientes para configurar el enrutamiento basado en la ubicación:</span><span class="sxs-lookup"><span data-stu-id="57dbd-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="57dbd-129">Definir regiones de red: se definió una región de red.</span><span class="sxs-lookup"><span data-stu-id="57dbd-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="57dbd-130">Definir sitios de red: se definieron dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="57dbd-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="57dbd-131">Un sitio por cada ubicación de oficina de la región.</span><span class="sxs-lookup"><span data-stu-id="57dbd-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="57dbd-132">Definir subredes de la red: cada planta de una ubicación de la oficina tiene su propia subred para la red cableada y la inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="57dbd-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="57dbd-133">Esta configuración ha dado lugar a 20 subredes para contoso.</span><span class="sxs-lookup"><span data-stu-id="57dbd-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="57dbd-134">Definir direcciones IP fiables: las direcciones IP de dirección externa de la SBC se agregaron a la dirección IP de confianza.</span><span class="sxs-lookup"><span data-stu-id="57dbd-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

