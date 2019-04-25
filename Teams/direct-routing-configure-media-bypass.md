---
title: Configurar el desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo configurar el desvío de medios con el enrutamiento directo teléfono del sistema.
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232701"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="8074b-103">Configurar el desvío de medios con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8074b-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="8074b-104">Antes de desvío de medios de configuración con el enrutamiento directo, asegúrese de que ha leído [Plan para los medios de desvío con el enrutamiento directo](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="8074b-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="8074b-105">Para activar el desvío de medios, se deben cumplir las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="8074b-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="8074b-106">Asegúrese de que su proveedor de controlador de borde de sesión (SBC) de elección es compatible con el desvío de medios y proporciona instrucciones acerca de cómo configurar el desvío en el SBC.</span><span class="sxs-lookup"><span data-stu-id="8074b-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="8074b-107">Consulte la página de certificación para obtener más información acerca de SBCs, el desvío de los medios de soporte técnico, y para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8074b-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="8074b-108">Debe activar el desvío de medios en el tronco mediante el siguiente comando: **Set-CSOnlinePSTNGateway-<sbc_FQDN> Identity - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="8074b-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="8074b-109">Asegúrese de que se abren los puertos requeridos.</span><span class="sxs-lookup"><span data-stu-id="8074b-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="8074b-110">Migración de troncos no pasó a habilitados para el desvío de troncos</span><span class="sxs-lookup"><span data-stu-id="8074b-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="8074b-111">Puede cambiar todos los usuarios a la vez o puede implementar por fases lleva a cabo (recomendado).</span><span class="sxs-lookup"><span data-stu-id="8074b-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="8074b-112">**Cambiar todos los usuarios a la vez.**</span><span class="sxs-lookup"><span data-stu-id="8074b-112">**Switch all users at once.**</span></span> <span data-ttu-id="8074b-113">Si se cumplen todas las condiciones, puede activar el modo de omisión.</span><span class="sxs-lookup"><span data-stu-id="8074b-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="8074b-114">Sin embargo, todos los usuarios de producción cambiará al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8074b-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="8074b-115">Debido a que podrían experimentar algunos problemas inicialmente al configurar troncos y puertos, la experiencia de usuario de producción podría verse afectada.</span><span class="sxs-lookup"><span data-stu-id="8074b-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="8074b-116">Enfoque de **Phased. (Recomendado)**.</span><span class="sxs-lookup"><span data-stu-id="8074b-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="8074b-117">Crear un nuevo tronco para la misma SBC (con un puerto diferente), ponerlo a prueba y cambiar la directiva de enrutamiento de voz en línea para los usuarios para que apunte al nuevo tronco.</span><span class="sxs-lookup"><span data-stu-id="8074b-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="8074b-118">Éste es el enfoque recomendado porque permite una transición más suave y la experiencia del usuario sin interrupciones.</span><span class="sxs-lookup"><span data-stu-id="8074b-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="8074b-119">Este método requiere la configuración de la SBC, un nuevo nombre FQDN y la configuración del servidor de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8074b-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="8074b-120">Tenga en cuenta que tendrá para asegurarse de que su certificado admite tanto los troncos.</span><span class="sxs-lookup"><span data-stu-id="8074b-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="8074b-121">En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado de comodín.</span><span class="sxs-lookup"><span data-stu-id="8074b-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migración de troncos no pasó a habilitados para el desvío de troncos)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="8074b-123">Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación de su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="8074b-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="8074b-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8074b-124">AudioCodes</span></span>
- <span data-ttu-id="8074b-125">Cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="8074b-125">Ribbon</span></span>
- <span data-ttu-id="8074b-126">TE-Systems (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="8074b-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="8074b-127">Para obtener una lista de controladores de borde de sesión (SBCs) certificados para el enrutamiento directo, vea la [lista de controladores de Broder sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="8074b-127">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="8074b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8074b-128">See also</span></span>

[<span data-ttu-id="8074b-129">Planear el desvío de medios con el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="8074b-129">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



