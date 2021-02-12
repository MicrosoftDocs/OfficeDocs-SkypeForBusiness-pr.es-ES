---
title: Requisitos previos y dependencias medioambientales para actualizar a Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta guía para obtener información sobre los requisitos previos y las dependencias medioambientales para implementar Teams en su organización
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578283"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="75cde-103">Requisitos previos y dependencias medioambientales para Teams</span><span class="sxs-lookup"><span data-stu-id="75cde-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="75cde-104">![Diagrama de viaje de actualización, que enfatiza la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Fases del viaje de actualización, con énfasis en la fase De preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="75cde-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="75cde-105">Este artículo forma parte de la fase de preparación técnica del viaje de actualización, una actividad que se completa en paralelo con la fase De disponibilidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="75cde-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="75cde-106">Antes de continuar, confirma que has completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="75cde-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="75cde-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="75cde-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="75cde-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="75cde-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="75cde-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="75cde-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="75cde-110">Ha elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="75cde-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="75cde-111">Teams combina varios servicios de Microsoft 365 y Office 365, y, por tanto, depende de la correcta implementación y funcionamiento de estos servicios.</span><span class="sxs-lookup"><span data-stu-id="75cde-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="75cde-112">Estos servicios incluyen, pero no están limitados a, SharePoint Online, Exchange Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="75cde-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="75cde-113">Aunque no todos los servicios son necesarios, recomendamos encarecidamente que los implemente todos.</span><span class="sxs-lookup"><span data-stu-id="75cde-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="75cde-114">Si decide no implementar determinados servicios, afectará a la funcionalidad que Teams puede ofrecer a su organización.</span><span class="sxs-lookup"><span data-stu-id="75cde-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="75cde-115">Por ejemplo, aunque no tenga que implementar SharePoint Online, Teams sí confía en SharePoint Online para ciertas funciones como el uso compartido de archivos en conversaciones de grupo, por lo que no implementar este servicio reducirá la funcionalidad que se ofrece a través del cliente.</span><span class="sxs-lookup"><span data-stu-id="75cde-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="75cde-116">Consulte los artículos siguientes para obtener información sobre los requisitos previos y cómo Teams interactúa con otras tecnologías:</span><span class="sxs-lookup"><span data-stu-id="75cde-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="75cde-117">Si su organización no ha implementado ninguna carga de trabajo de Microsoft 365 u Office 365, vea [Introducción.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="75cde-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="75cde-118">Si su organización no ha agregado o configurado un dominio comprobado para Microsoft 365 u Office 365, consulte Preguntas más frecuentes [sobre dominios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="75cde-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="75cde-119">Si su organización no ha sincronizado las identidades con Azure Active Directory, consulte Modelos de identidad [y autenticación en Microsoft Teams.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="75cde-120">Si su organización no tiene Exchange Online, consulte [Comprender cómo interactúan Exchange y Microsoft Teams.](Exchange-Teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="75cde-121">Si su organización no tiene SharePoint Online, consulte Comprender cómo SharePoint Online y OneDrive para la [Empresa interactúan con Microsoft Teams.](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="75cde-122">Para obtener información sobre [cómo interactúan los grupos de Microsoft 365 y Microsoft Teams.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="75cde-123">Si su organización es una institución educativa y usa un sistema de información de estudiantes, consulte Bienvenido a [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75cde-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="75cde-124">Si su organización está pensando en las opciones de llamadas a la red telefónica conmutada (RTC), consulte [Voz:](cloud-voice-landing-page.md)conectividad de sistema telefónico y RTC, qué [plan](calling-plan-landing-page.md)de llamadas es el adecuado para usted y enrutamiento directo de sistema [telefónico.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="75cde-125">Para asegurarse de que se han cumplido todos los requisitos de red antes de implementar Teams, vea Preparar la [red de su organización para Microsoft Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

<span data-ttu-id="75cde-126">Una vez que haya comprobado que su entorno cumple todos los requisitos previos aplicables, [evalúe su entorno actual para Teams.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="75cde-126">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
