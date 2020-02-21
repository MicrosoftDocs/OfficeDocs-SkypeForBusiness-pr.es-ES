---
title: Configurar el enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System.
ms.openlocfilehash: 9c56078a6d016967e518746e3567373404d1c486
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157878"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="50535-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="50535-103">Configure Direct Routing</span></span>

<span data-ttu-id="50535-104">El enrutamiento directo de Microsoft Phone System le permite conectar su infraestructura de telefonía local con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="50535-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="50535-105">En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión local compatible (SBC) con el enrutamiento directo y cómo configurar los usuarios de Teamtes para que usen el enrutamiento directo para conectarse a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="50535-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="50535-106">Este artículo contiene vínculos a artículos asociados para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="50535-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="50535-107">Para obtener información sobre si el enrutamiento directo es la solución adecuada para su organización, consulte [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="50535-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="50535-108">Para obtener información sobre los requisitos previos y la planificación de la implementación, consulte [planear el enrutamiento directo](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="50535-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="50535-109">También puede ver la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearla y cómo implementarla: el [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="50535-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="50535-110">Para completar los pasos que se explican en este artículo, los administradores deben estar familiarizados con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50535-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="50535-111">Para obtener más información sobre cómo usar PowerShell, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="50535-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="50535-112">Antes de realizar los pasos de estos artículos, Microsoft le recomienda que confirme que su SBC ya se ha configurado de la manera recomendada por su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="50535-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="50535-113">Documentación de la implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="50535-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="50535-114">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="50535-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="50535-115">Documentación de implementación de comunicaciones de la cinta</span><span class="sxs-lookup"><span data-stu-id="50535-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="50535-116">Documentación de la implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="50535-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="50535-117">Para obtener una lista completa de SBCs admitidos, vea [lista de controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="50535-117">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="50535-118">Para configurar Microsoft Phone System y permitir que los usuarios usen el enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="50535-118">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="50535-119">**Paso 1.**</span><span class="sxs-lookup"><span data-stu-id="50535-119">**Step 1.**</span></span> [<span data-ttu-id="50535-120">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="50535-120">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="50535-121">**Paso 2.**</span><span class="sxs-lookup"><span data-stu-id="50535-121">**Step 2.**</span></span> [<span data-ttu-id="50535-122">Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="50535-122">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="50535-123">**Paso 3.**</span><span class="sxs-lookup"><span data-stu-id="50535-123">**Step 3.**</span></span> [<span data-ttu-id="50535-124">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="50535-124">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="50535-125">**Paso 4.**</span><span class="sxs-lookup"><span data-stu-id="50535-125">**Step 4.**</span></span> [<span data-ttu-id="50535-126">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="50535-126">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="50535-127">Si está configurando un SBC para varios inquilinos, también deberá leer [configurar un SBC para varios inquilinos](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="50535-127">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="50535-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="50535-128">See also</span></span>

[<span data-ttu-id="50535-129">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="50535-129">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="50535-130">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="50535-130">Plan Direct Routing</span></span>](direct-routing-plan.md)

