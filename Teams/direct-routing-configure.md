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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a configurar el enrutamiento directo de Microsoft Phone System para conectar su infraestructura de telefonía local con Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701298"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="b1a18-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b1a18-103">Configure Direct Routing</span></span>

<span data-ttu-id="b1a18-104">El enrutamiento directo de Microsoft Phone System le permite conectar su infraestructura de telefonía local con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b1a18-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="b1a18-105">En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión local compatible (SBC) con el enrutamiento directo y cómo configurar los usuarios de Teamtes para que usen el enrutamiento directo para conectarse a la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="b1a18-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="b1a18-106">Este artículo contiene vínculos a artículos asociados para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b1a18-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="b1a18-107">Para obtener información sobre si el enrutamiento directo es la solución adecuada para su organización, consulte [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b1a18-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="b1a18-108">Para obtener información sobre los requisitos previos y la planificación de la implementación, consulte [planear el enrutamiento directo](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="b1a18-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="b1a18-109">También puede ver la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearla y cómo implementarla: el [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="b1a18-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="b1a18-110">Para completar los pasos que se explican en este artículo, los administradores deben estar familiarizados con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1a18-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b1a18-111">Para obtener más información sobre cómo usar PowerShell, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b1a18-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="b1a18-112">Antes de realizar los pasos de estos artículos, Microsoft le recomienda que confirme que su SBC ya se ha configurado de la manera recomendada por su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="b1a18-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="b1a18-113">Documentación de la implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="b1a18-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="b1a18-114">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="b1a18-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="b1a18-115">Documentación de implementación de comunicaciones de la cinta</span><span class="sxs-lookup"><span data-stu-id="b1a18-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="b1a18-116">Documentación de la implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="b1a18-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="b1a18-117">Documentación de implementación de MetaSwitch</span><span class="sxs-lookup"><span data-stu-id="b1a18-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="b1a18-118">Para obtener una lista completa de SBCs admitidos, vea [lista de controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="b1a18-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="b1a18-119">Para configurar Microsoft Phone System y permitir que los usuarios usen el enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b1a18-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="b1a18-120">**Paso 1.**</span><span class="sxs-lookup"><span data-stu-id="b1a18-120">**Step 1.**</span></span> [<span data-ttu-id="b1a18-121">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="b1a18-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="b1a18-122">**Paso 2.**</span><span class="sxs-lookup"><span data-stu-id="b1a18-122">**Step 2.**</span></span> [<span data-ttu-id="b1a18-123">Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz</span><span class="sxs-lookup"><span data-stu-id="b1a18-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="b1a18-124">**Paso 3.**</span><span class="sxs-lookup"><span data-stu-id="b1a18-124">**Step 3.**</span></span> [<span data-ttu-id="b1a18-125">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="b1a18-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="b1a18-126">**Paso 4.**</span><span class="sxs-lookup"><span data-stu-id="b1a18-126">**Step 4.**</span></span> [<span data-ttu-id="b1a18-127">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="b1a18-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="b1a18-128">Si está configurando un SBC para varios inquilinos, también deberá leer [configurar un SBC para varios inquilinos](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="b1a18-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="b1a18-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b1a18-129">Related topics</span></span>

[<span data-ttu-id="b1a18-130">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b1a18-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="b1a18-131">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="b1a18-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

