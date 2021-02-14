---
title: 'Configurar las opciones de red: enrutamiento basado en la ubicación'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y configurar regiones de red, sitios y subredes para el Location-Based de enrutamiento directo.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822950"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="fc8b1-103">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="fc8b1-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="fc8b1-104">Si aún no lo ha hecho, lea Planear el enrutamiento [Location-Based](location-based-routing-plan.md) para enrutamiento directo para revisar otros pasos que deberá realizar antes de configurar las opciones de red para el enrutamiento Location-Based cliente.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="fc8b1-105">En este artículo se describe cómo configurar las opciones de red para Location-Based de distribución.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="fc8b1-106">Después de implementar el enrutamiento directo de Sistema telefónico en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="fc8b1-107">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="fc8b1-107">Define network regions</span></span>

<span data-ttu-id="fc8b1-108">Una región de red contiene una colección de sitios de red e interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="fc8b1-109">Para ver los pasos sobre cómo configurar las regiones de red, vaya a Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b1-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="fc8b1-110">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="fc8b1-110">Define network sites</span></span>

<span data-ttu-id="fc8b1-111">Un sitio de red representa una ubicación donde su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="fc8b1-112">Debe asociar cada sitio de red de la topología a una región de red.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="fc8b1-113">Para obtener información sobre cómo configurar sitios de red, consulte Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b1-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="fc8b1-114">Un procedimiento recomendado para Location-Based es crear un sitio independiente para cada ubicación que tenga conectividad RTC única.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="fc8b1-115">Puede crear un sitio habilitado para el enrutamiento de Location-Based electrónico o un sitio que no esté habilitado para el Location-Based grupo.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="fc8b1-116">Por ejemplo, puede que desee crear un sitio que no esté habilitado para Location-Based Routing para permitir que los usuarios habilitados para Location-Based Routing realicen llamadas RTC cuando se des recorrido a ese sitio.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="fc8b1-117">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="fc8b1-117">Define network subnets</span></span>

<span data-ttu-id="fc8b1-118">Cada subred debe estar asociada a un sitio de red específico.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="fc8b1-119">Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios a la misma subred.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="fc8b1-120">Para ver los pasos sobre cómo configurar subredes de red, vaya a Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b1-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="fc8b1-121">Para Location-Based, las subredes IP en la ubicación donde los puntos de conexión de Teams pueden conectarse a la red deben estar definidas y asociadas a una red definida para exigir la omisión de pago.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="fc8b1-122">Esta asociación de subredes permite Location-Based enrutamiento para localizar los puntos de conexión geográficamente con el fin de determinar si se debe permitir una llamada RTC determinada.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="fc8b1-123">Se admiten subredes IPv6 e IPv4.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="fc8b1-124">Al determinar si un punto de conexión de Teams se encuentra en un sitio, Location-Based enrutamiento comprueba primero si hay una dirección IPv6 que coincida.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="fc8b1-125">Si no hay una dirección IPv6, Location-Based enrutamiento comprueba si hay una dirección IPv4.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="fc8b1-126">Definir direcciones IP de confianza (subredes externas)</span><span class="sxs-lookup"><span data-stu-id="fc8b1-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="fc8b1-127">Las direcciones IP de confianza son las direcciones IP externas a Internet de la red empresarial y se utilizan para determinar si el punto de conexión del usuario se encuentra dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="fc8b1-128">Para ver los pasos sobre cómo configurar direcciones IP de confianza, vaya a Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b1-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="fc8b1-129">Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, Location-Based Routing comprueba la subred interna en la que se encuentra el punto de conexión del usuario.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="fc8b1-130">Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de direcciones IP de confianza, el punto de conexión se clasifica como en una ubicación desconocida y se bloquean las llamadas RTC a un usuario habilitado para Location-Based Routing.</span><span class="sxs-lookup"><span data-stu-id="fc8b1-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc8b1-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fc8b1-131">Next steps</span></span>

<span data-ttu-id="fc8b1-132">Vaya a [Habilitar Location-Based de enrutamiento directo.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b1-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc8b1-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fc8b1-133">Related topics</span></span>

- [<span data-ttu-id="fc8b1-134">Configuración de red para las características de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="fc8b1-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
