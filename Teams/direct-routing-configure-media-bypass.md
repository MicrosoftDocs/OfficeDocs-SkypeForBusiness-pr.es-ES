---
title: Configurar el desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a configurar la omisión de medios con el enrutamiento directo de Sistema telefónico para Microsoft Teams cambiando todos los usuarios a la vez o implementando un enfoque por fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416900"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="de5dd-103">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="de5dd-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="de5dd-104">Antes de configurar la omisión de medios con enrutamiento directo, asegúrese de haber leído plan de omisión [de medios con enrutamiento directo.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="de5dd-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="de5dd-105">Para activar la omisión de medios, deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="de5dd-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="de5dd-106">Asegúrese de que el proveedor del controlador de borde de sesión (SBC) admite la omisión de medios y proporciona instrucciones sobre cómo configurar la omisión en la SBC.</span><span class="sxs-lookup"><span data-stu-id="de5dd-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="de5dd-107">Consulta la página de certificación para obtener información sobre los SBC, que admiten el omisión de medios, y para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="de5dd-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="de5dd-108">Debe activar la omisión de medios en el tronco usando el comando siguiente:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="de5dd-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="de5dd-109">Asegúrese de que los puertos necesarios estén abiertos.</span><span class="sxs-lookup"><span data-stu-id="de5dd-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="de5dd-110">Migrar desde troncos no omitados a troncos no habilitados para omisión</span><span class="sxs-lookup"><span data-stu-id="de5dd-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="de5dd-111">Puede cambiar todos los usuarios a la vez o implementar un enfoque por fases (recomendado).</span><span class="sxs-lookup"><span data-stu-id="de5dd-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="de5dd-112">**Cambiar todos los usuarios a la vez.**</span><span class="sxs-lookup"><span data-stu-id="de5dd-112">**Switch all users at once.**</span></span> <span data-ttu-id="de5dd-113">Si se cumplen todas las condiciones, puede activar el modo de omisión.</span><span class="sxs-lookup"><span data-stu-id="de5dd-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="de5dd-114">Sin embargo, todos los usuarios de producción se cambiarán al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="de5dd-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="de5dd-115">Como es posible que experimente algunos problemas inicialmente al configurar troncos y puertos, es posible que la experiencia del usuario de producción se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="de5dd-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="de5dd-116">**Enfoque por fases. (Recomendado).**</span><span class="sxs-lookup"><span data-stu-id="de5dd-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="de5dd-117">Cree un tronco nuevo para el mismo SBC (con un puerto diferente), pruebe y cambie la directiva de enrutamiento de voz en línea para que los usuarios apunten al nuevo tronco.</span><span class="sxs-lookup"><span data-stu-id="de5dd-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="de5dd-118">Este es el enfoque recomendado porque permite una transición más fluida y una experiencia de usuario sin interrupciones.</span><span class="sxs-lookup"><span data-stu-id="de5dd-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="de5dd-119">Este método requiere la configuración de la SBC, un nuevo nombre DE FQDN y la configuración del firewall.</span><span class="sxs-lookup"><span data-stu-id="de5dd-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="de5dd-120">Tenga en cuenta que necesitará asegurarse de que el certificado admite ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="de5dd-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="de5dd-121">En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="de5dd-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrar desde troncos no omitados a troncos habilitados para omisión)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="de5dd-123">Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación de su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="de5dd-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="de5dd-124">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="de5dd-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="de5dd-125">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="de5dd-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="de5dd-126">Documentación de implementación de comunicaciones de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="de5dd-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="de5dd-127">Documentación de implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="de5dd-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="de5dd-128">Para obtener una lista de controladores de borde de sesión (SBCs) certificados para enrutamiento directo, consulta la lista de controladores de controlador de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="de5dd-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="de5dd-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="de5dd-129">Related topics</span></span>

[<span data-ttu-id="de5dd-130">Planear la omisión de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="de5dd-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



