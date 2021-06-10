---
title: 'Configurar la configuración de red: enrutamiento basado en ubicación'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y configurar regiones de red, sitios y subredes para Location-Based enrutamiento directo.
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
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="10c76-103">Configuración de red de enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="10c76-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="10c76-104">Si aún no lo ha hecho, lea [Plan de enrutamiento Location-Based](location-based-routing-plan.md) para enrutamiento directo para revisar otros pasos que tendrá que seguir antes de configurar la configuración de red para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="10c76-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="10c76-105">En este artículo se describe cómo configurar la configuración de red para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="10c76-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="10c76-106">Después de implementar Sistema telefónico enrutamiento directo en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.</span><span class="sxs-lookup"><span data-stu-id="10c76-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="10c76-107">Definir regiones de red</span><span class="sxs-lookup"><span data-stu-id="10c76-107">Define network regions</span></span>

<span data-ttu-id="10c76-108">Una región de red contiene una colección de sitios de red e interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="10c76-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="10c76-109">Para obtener pasos sobre cómo configurar regiones de red, vaya a Administrar la topología de red para las características de la nube [en Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="10c76-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="10c76-110">Definir sitios de red</span><span class="sxs-lookup"><span data-stu-id="10c76-110">Define network sites</span></span>

<span data-ttu-id="10c76-111">Un sitio de red representa una ubicación donde su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus.</span><span class="sxs-lookup"><span data-stu-id="10c76-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="10c76-112">Debe asociar cada sitio de red de la topología con una región de red.</span><span class="sxs-lookup"><span data-stu-id="10c76-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="10c76-113">Para obtener pasos sobre cómo configurar sitios de red, vea Administrar la topología de red para las características de nube [en Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="10c76-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="10c76-114">Un procedimiento recomendado para Location-Based enrutamiento es crear un sitio independiente para cada ubicación que tenga conectividad RTC única.</span><span class="sxs-lookup"><span data-stu-id="10c76-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="10c76-115">Puede crear un sitio habilitado para Location-Based enrutamiento o un sitio que no esté habilitado para Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="10c76-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="10c76-116">Por ejemplo, es posible que desee crear un sitio que no esté habilitado para el enrutamiento de Location-Based para permitir que los usuarios habilitados para el enrutamiento de Location-Based realicen llamadas RTC cuando se deslomen a ese sitio.</span><span class="sxs-lookup"><span data-stu-id="10c76-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="10c76-117">Definir subredes de red</span><span class="sxs-lookup"><span data-stu-id="10c76-117">Define network subnets</span></span>

<span data-ttu-id="10c76-118">Cada subred debe estar asociada a un sitio de red específico.</span><span class="sxs-lookup"><span data-stu-id="10c76-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="10c76-119">Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios con la misma subred.</span><span class="sxs-lookup"><span data-stu-id="10c76-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="10c76-120">Para obtener pasos sobre cómo configurar subredes de red, vaya a Administrar la topología de red para las características de la [nube en Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="10c76-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="10c76-121">Para Location-Based enrutamiento, las subredes IP en la ubicación donde Teams puntos de conexión pueden conectarse a la red deben definirse y estar asociadas a una red definida para exigir la omisión de pago.</span><span class="sxs-lookup"><span data-stu-id="10c76-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="10c76-122">Esta asociación de subredes permite a Location-Based enrutamiento localizar geográficamente los puntos de conexión para determinar si se debe permitir una llamada RTC determinada.</span><span class="sxs-lookup"><span data-stu-id="10c76-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="10c76-123">Se admiten las subredes IPv6 e IPv4.</span><span class="sxs-lookup"><span data-stu-id="10c76-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="10c76-124">Al determinar si un punto Teams de conexión se encuentra en un sitio, Location-Based enrutamiento primero comprueba si hay una dirección IPv6 que coincida.</span><span class="sxs-lookup"><span data-stu-id="10c76-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="10c76-125">Si una dirección IPv6 no está presente, Location-Based enrutamiento busca una dirección IPv4.</span><span class="sxs-lookup"><span data-stu-id="10c76-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="10c76-126">Definir direcciones IP de confianza (subredes externas)</span><span class="sxs-lookup"><span data-stu-id="10c76-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="10c76-127">Las direcciones IP de confianza son las direcciones IP externas de Internet de la red empresarial y se usan para determinar si el punto de conexión del usuario está dentro de la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="10c76-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="10c76-128">Para ver los pasos sobre cómo configurar direcciones IP de confianza, vaya a Administrar la topología de red para las características de la [nube en Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="10c76-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="10c76-129">Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, Location-Based Enrutamiento comprueba para determinar la subred interna donde se encuentra el punto de conexión del usuario.</span><span class="sxs-lookup"><span data-stu-id="10c76-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="10c76-130">Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de direcciones IP de confianza, el punto de conexión se clasifica como en una ubicación desconocida y las llamadas RTC a o desde un usuario habilitado para Location-Based Enrutamiento se bloquean.</span><span class="sxs-lookup"><span data-stu-id="10c76-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10c76-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="10c76-131">Next steps</span></span>

<span data-ttu-id="10c76-132">Vaya a [Habilitar Location-Based enrutamiento directo.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="10c76-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="10c76-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="10c76-133">Related topics</span></span>

- [<span data-ttu-id="10c76-134">Configuración de red para las características de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="10c76-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
