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
description: Lea este tema para aprender a configurar la omisión de medios con enrutamiento directo de sistema telefónico.
ms.openlocfilehash: 2931194783e2055c468ec2d7ad1286b9fe1940ae
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572239"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="37523-103">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="37523-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="37523-104">Antes de configurar la omisión de medios con enrutamiento directo, asegúrese de que tiene un [plan de lectura de multimedia con enrutamiento directo](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="37523-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="37523-105">Para activar la omisión de elementos multimedia, se deben cumplir las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="37523-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="37523-106">Asegúrese de que el proveedor del controlador de borde (SBC) de la sesión que elija admita la omisión de medios y proporciona instrucciones sobre cómo configurar el omisión en la SBC.</span><span class="sxs-lookup"><span data-stu-id="37523-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="37523-107">Consulte la página de certificación para obtener información sobre SBCs, que admiten la omisión de elementos multimedia y para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="37523-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="37523-108">Para activar la omisión de elementos multimedia en el tronco, use el siguiente comando: **set-CSOnlinePSTNGateway-Identity <> sbc_FQDN-MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="37523-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="37523-109">Asegúrese de que los puertos necesarios estén abiertos.</span><span class="sxs-lookup"><span data-stu-id="37523-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="37523-110">Migrar desde troncos no omitidos a troncos habilitados para omitir</span><span class="sxs-lookup"><span data-stu-id="37523-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="37523-111">Puede cambiar todos los usuarios a la vez o puede implementar un enfoque por fases (recomendado).</span><span class="sxs-lookup"><span data-stu-id="37523-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="37523-112">**Cambiar todos los usuarios a la vez.**</span><span class="sxs-lookup"><span data-stu-id="37523-112">**Switch all users at once.**</span></span> <span data-ttu-id="37523-113">Si se cumplen todas las condiciones, puede activar el modo de omisión.</span><span class="sxs-lookup"><span data-stu-id="37523-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="37523-114">Sin embargo, todos los usuarios de producción se cambiarán al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="37523-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="37523-115">Dado que es posible que al principio experimente algunos problemas al configurar los troncos y los puertos, su experiencia con el usuario de producción podría verse afectada.</span><span class="sxs-lookup"><span data-stu-id="37523-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="37523-116">**Enfoque por fases. (Recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="37523-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="37523-117">Cree un nuevo tronco para el mismo SBC (con un puerto diferente), pruébelo y cambie la Directiva de enrutamiento de voz en línea para que los usuarios apunten al nuevo tronco.</span><span class="sxs-lookup"><span data-stu-id="37523-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="37523-118">Este es el método recomendado porque permite una transición más fluida y una experiencia de usuario ininterrumpida.</span><span class="sxs-lookup"><span data-stu-id="37523-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="37523-119">Este enfoque requiere la configuración de SBC, un nuevo nombre FQDN y la configuración del firewall.</span><span class="sxs-lookup"><span data-stu-id="37523-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="37523-120">Nota tendrá que asegurarse de que su certificado admite ambos troncos.</span><span class="sxs-lookup"><span data-stu-id="37523-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="37523-121">En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado comodín.</span><span class="sxs-lookup"><span data-stu-id="37523-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrar desde troncos no omitidos a troncos habilitados para omitir)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="37523-123">Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación del proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="37523-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="37523-124">Documentación de la implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="37523-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="37523-125">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="37523-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="37523-126">Documentación de implementación de comunicaciones de la cinta</span><span class="sxs-lookup"><span data-stu-id="37523-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="37523-127">Documentación de la implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="37523-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="37523-128">Para obtener una lista de los controladores de borde de sesión (SBCs) certificados para enrutamiento directo, consulte [List of Session borde Controllers Certified for Direct Routing](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="37523-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="37523-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="37523-129">See also</span></span>

[<span data-ttu-id="37523-130">Planear la omisión de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="37523-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



