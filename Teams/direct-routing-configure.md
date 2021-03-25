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
description: Obtenga información sobre cómo configurar El enrutamiento directo de Microsoft Phone System para conectar su infraestructura de telefonía local a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122244"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="bd478-103">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bd478-103">Configure Direct Routing</span></span>

<span data-ttu-id="bd478-104">El enrutamiento directo de Microsoft Phone System le permite conectar su infraestructura de telefonía local a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bd478-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="bd478-105">En el artículo se enumeran los pasos de alto nivel necesarios para conectar un controlador de borde de sesión (SBC) local compatible con enrutamiento directo y cómo configurar a los usuarios de Teams para que usen enrutamiento directo para conectarse a la red telefónica conmutada (RTC) pública.</span><span class="sxs-lookup"><span data-stu-id="bd478-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="bd478-106">En este artículo se vincula a artículos asociados para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bd478-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="bd478-107">Para obtener información sobre si enrutamiento directo es la solución adecuada para su organización, vea [Enrutamiento directo del sistema telefónico.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bd478-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="bd478-108">Para obtener información sobre los requisitos previos y la planificación de la implementación, vea [Planear enrutamiento directo.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="bd478-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="bd478-109">También puede ver la siguiente sesión para obtener información sobre las ventajas de Enrutamiento directo, cómo planearlo y cómo implementarlo: Enrutamiento directo [en Microsoft Teams.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="bd478-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="bd478-110">Para completar los pasos explicados en este artículo, los administradores necesitan cierta familiaridad con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd478-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="bd478-111">Para obtener más información sobre el uso de PowerShell, vea [Configurar el equipo para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bd478-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="bd478-112">Antes de realizar los pasos de estos artículos, Microsoft recomienda que confirme que su SBC ya se ha configurado según lo recomendado por su proveedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="bd478-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="bd478-113">Documentación de implementación de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="bd478-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="bd478-114">Documentación de implementación de Oracle</span><span class="sxs-lookup"><span data-stu-id="bd478-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="bd478-115">Documentación de implementación de Comunicaciones de la cinta de opciones</span><span class="sxs-lookup"><span data-stu-id="bd478-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="bd478-116">Documentación de implementación de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="bd478-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="bd478-117">Documentación de implementación de Metaswitch</span><span class="sxs-lookup"><span data-stu-id="bd478-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="bd478-118">Para obtener una lista completa de SBC compatibles, vea Lista de controladores de [borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="bd478-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="bd478-119">Para configurar Microsoft Phone System y permitir a los usuarios usar enrutamiento directo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bd478-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="bd478-120">**Paso 1.**</span><span class="sxs-lookup"><span data-stu-id="bd478-120">**Step 1.**</span></span> [<span data-ttu-id="bd478-121">Conectar el SBC con Microsoft Phone System y validar la conexión</span><span class="sxs-lookup"><span data-stu-id="bd478-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="bd478-122">**Paso 2.**</span><span class="sxs-lookup"><span data-stu-id="bd478-122">**Step 2.**</span></span> [<span data-ttu-id="bd478-123">Habilitar usuarios para enrutamiento directo, voz y correo de voz</span><span class="sxs-lookup"><span data-stu-id="bd478-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="bd478-124">**Paso 3.**</span><span class="sxs-lookup"><span data-stu-id="bd478-124">**Step 3.**</span></span> [<span data-ttu-id="bd478-125">Configurar el enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="bd478-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="bd478-126">**Paso 4.**</span><span class="sxs-lookup"><span data-stu-id="bd478-126">**Step 4.**</span></span> [<span data-ttu-id="bd478-127">Traducir números a un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="bd478-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="bd478-128">Si está configurando un SBC para varios inquilinos, también querrá leer Configurar un [SBC para varios inquilinos.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="bd478-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="bd478-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bd478-129">Related topics</span></span>

[<span data-ttu-id="bd478-130">Enrutamiento directo del Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bd478-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="bd478-131">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="bd478-131">Plan Direct Routing</span></span>](direct-routing-plan.md)