---
title: Requisitos previos y dependencias ambientales para actualizar a Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta guía para obtener información sobre los requisitos previos y las dependencias ambientales para implementar Teams en su organización
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282167"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="cdd16-103">Requisitos previos y dependencias ambientales para Teams</span><span class="sxs-lookup"><span data-stu-id="cdd16-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="cdd16-104">![Diagrama de viaje de actualización, haciendo hincapié en la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="cdd16-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="cdd16-105">Este artículo forma parte de la fase preparación técnica del viaje de actualización, una actividad que se completa en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="cdd16-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="cdd16-106">Antes de continuar, confirme que ha completado estas actividades de fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="cdd16-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="cdd16-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="cdd16-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="cdd16-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="cdd16-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="cdd16-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="cdd16-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="cdd16-110">Elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="cdd16-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="cdd16-111">Teams combina varios Microsoft 365 y Office 365 y, por lo tanto, depende de la correcta implementación y funcionamiento de estos servicios.</span><span class="sxs-lookup"><span data-stu-id="cdd16-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="cdd16-112">Estos servicios incluyen, entre otros, SharePoint Online, Exchange Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="cdd16-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="cdd16-113">Aunque no todos los servicios son necesarios, le recomendamos que los implemente todos.</span><span class="sxs-lookup"><span data-stu-id="cdd16-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="cdd16-114">Si decide no implementar determinados servicios, afectará a la funcionalidad que Teams puede ofrecer a su organización.</span><span class="sxs-lookup"><span data-stu-id="cdd16-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="cdd16-115">Por ejemplo, aunque no tiene que implementar SharePoint Online, Teams se basa en SharePoint Online para ciertas funciones, como el uso compartido de archivos en conversaciones de grupo, por lo que no implementar este servicio reducirá la funcionalidad ofrecida a través del cliente.</span><span class="sxs-lookup"><span data-stu-id="cdd16-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="cdd16-116">Vea los artículos siguientes para obtener información sobre los requisitos previos y Teams interactúa con otras tecnologías:</span><span class="sxs-lookup"><span data-stu-id="cdd16-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="cdd16-117">Si su organización no ha implementado ninguna Microsoft 365 o Office 365 de trabajo, vea [Introducción.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="cdd16-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="cdd16-118">Si su organización no ha agregado o configurado un dominio comprobado para Microsoft 365 o Office 365, vea Preguntas más frecuentes sobre [dominios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="cdd16-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="cdd16-119">Si su organización no ha sincronizado identidades para Azure Active Directory, vea Modelos de identidad y [autenticación en Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="cdd16-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="cdd16-120">Si su organización no tiene Exchange Online, vea [Interacción entre Exchange y Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="cdd16-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="cdd16-121">Si su organización no tiene SharePoint Online, vea [Interacción de SharePoint Online y OneDrive para la Empresa con Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="cdd16-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="cdd16-122">Para obtener información [sobre Microsoft 365 grupos y Microsoft Teams interactúan.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="cdd16-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="cdd16-123">Si su organización es una institución educativa y usa un sistema de información para estudiantes, vea Bienvenido a [Microsoft School Data Sync](/schooldatasync) antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cdd16-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="cdd16-124">Si su organización está pensando en las opciones de llamadas de red telefónica conmutada (RTC), vea Voz [: conectividad de Sistema telefónico](cloud-voice-landing-page.md)y RTC , Qué [plan](calling-plan-landing-page.md)de llamadas es adecuado para usted y Sistema telefónico enrutamiento [directo.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="cdd16-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="cdd16-125">Para asegurarse de que se han cumplido todos los requisitos de red antes de Teams, vea Preparar la red de su organización [para Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="cdd16-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="cdd16-126">Si actualmente usa Skype Empresarial Online Connector para administrar sus servicios, tendrá que pasar al módulo de PowerShell de Teams y actualizar los scripts de PowerShell existentes.</span><span class="sxs-lookup"><span data-stu-id="cdd16-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="cdd16-127">Vea [Mover de Skype Empresarial Online Connector al módulo Teams PowerShell para](teams-powershell-move-from-sfbo.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="cdd16-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="cdd16-128">Después de comprobar que el entorno cumple todos los requisitos previos aplicables, [evalúe el entorno actual para Teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cdd16-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>