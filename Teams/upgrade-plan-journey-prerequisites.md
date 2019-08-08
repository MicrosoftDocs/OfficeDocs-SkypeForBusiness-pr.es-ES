---
title: Requisitos previos de Microsoft Teams | Actualización de adopción de dependencias
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Use esta guía para obtener información sobre los requisitos previos y las dependencias ambientales para implementar equipos de su organización.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0da49178a55cc14b98946beb7212a1627829c13e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236080"
---
<span data-ttu-id="87102-103">![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica] (media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="87102-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="87102-104">Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="87102-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="87102-105">Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="87102-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="87102-106">Inventar a los participantes del proyecto</span><span class="sxs-lookup"><span data-stu-id="87102-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="87102-107">Definió el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="87102-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="87102-108">La coexistencia y la interoperabilidad de Skype para empresas y equipos</span><span class="sxs-lookup"><span data-stu-id="87102-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="87102-109">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="87102-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="87102-110">Requisitos previos y dependencias medioambientales de los equipos</span><span class="sxs-lookup"><span data-stu-id="87102-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="87102-111">Teams combina varios servicios de Office 365 y, por lo tanto, depende de la implementación y el funcionamiento correctos de estos servicios.</span><span class="sxs-lookup"><span data-stu-id="87102-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="87102-112">Estos servicios incluyen, entre otros, SharePoint Online, Exchange Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="87102-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="87102-113">Aunque no se necesitan todos los servicios, se recomienda implementarlos todos.</span><span class="sxs-lookup"><span data-stu-id="87102-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="87102-114">Si decide no implementar determinados servicios, esta afectará a la funcionalidad que los equipos pueden ofrecer a su organización.</span><span class="sxs-lookup"><span data-stu-id="87102-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="87102-115">Por ejemplo, aunque no tiene que implementar SharePoint Online, los equipos dependen de SharePoint Online para determinadas funciones, como el uso compartido de archivos en las conversaciones grupales, por lo que si no implementa este servicio, disminuirá la funcionalidad ofrecida a través de la Client.</span><span class="sxs-lookup"><span data-stu-id="87102-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="87102-116">Consulte los artículos siguientes para obtener información sobre los requisitos previos y cómo Teams interactúa con otras tecnologías:</span><span class="sxs-lookup"><span data-stu-id="87102-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="87102-117">Si su organización no ha implementado ninguna carga de trabajo de Office 365, consulte [Introducción a office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="87102-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="87102-118">Si su organización no ha agregado ni configurado un dominio verificado para Office 365, consulte [comprobar el dominio de office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="87102-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="87102-119">Si su organización no ha sincronizado las identidades con Azure Active Directory, consulte [modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="87102-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="87102-120">Si su organización no tiene Exchange Online, consulte [comprender cómo interactúan Exchange y Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="87102-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="87102-121">Si su organización no tiene SharePoint Online, consulte [comprender cómo SharePoint Online y OneDrive para la empresa interactúan con Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="87102-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="87102-122">Obtenga información sobre cómo interactúan los [grupos de Office 365 y Microsoft Teams](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="87102-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="87102-123">Si su organización es un centro educativo y usa un sistema de información de estudiante, [implemente School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="87102-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="87102-124">Una vez que haya verificado que su entorno cumple con todos los requisitos previos vigentes, [evalúe su entorno actual para Teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="87102-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
