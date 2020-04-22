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
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f340146225d7e386233e727bb8c5d181db7f15fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776725"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="f1dc1-103">Requisitos previos y dependencias medioambientales de los equipos</span><span class="sxs-lookup"><span data-stu-id="f1dc1-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="f1dc1-104">![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="f1dc1-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="f1dc1-105">Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="f1dc1-106">Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="f1dc1-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="f1dc1-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="f1dc1-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f1dc1-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="f1dc1-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="f1dc1-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="f1dc1-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="f1dc1-110">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="f1dc1-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="f1dc1-111">Teams combina varios servicios de Office 365 y, por lo tanto, depende de la implementación y el funcionamiento correctos de estos servicios.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="f1dc1-112">Estos servicios incluyen, entre otros, SharePoint Online, Exchange Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="f1dc1-113">Aunque no se necesitan todos los servicios, se recomienda implementarlos todos.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="f1dc1-114">Si decide no implementar determinados servicios, esta afectará a la funcionalidad que los equipos pueden ofrecer a su organización.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="f1dc1-115">Por ejemplo, aunque no tiene que implementar SharePoint Online, los equipos dependen de SharePoint Online para ciertas funciones, como el uso compartido de archivos en las conversaciones de grupo, por lo que si no implementa este servicio, disminuirá la funcionalidad que se ofrece a través del cliente.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="f1dc1-116">Consulte los artículos siguientes para obtener información sobre los requisitos previos y cómo Teams interactúa con otras tecnologías:</span><span class="sxs-lookup"><span data-stu-id="f1dc1-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="f1dc1-117">Si su organización no ha implementado ninguna carga de trabajo de Office 365, consulte [Introducción a office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-117">If your organization hasn't deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="f1dc1-118">Si su organización no ha agregado ni configurado un dominio verificado para Office 365, consulte [comprobar el dominio de office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-118">If your organization hasn't added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="f1dc1-119">Si su organización no ha sincronizado las identidades con Azure Active Directory, consulte [modelos de identidad y autenticación en Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="f1dc1-120">Si su organización no tiene<sup>1</sup>Exchange Online, consulte [comprender cómo interactúan Exchange y Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="f1dc1-121">Si su organización no tiene SharePoint Online, consulte [comprender cómo SharePoint Online y OneDrive para la empresa interactúan con Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="f1dc1-122">Obtenga información sobre cómo [interactúan microsoft 365 Groups y Microsoft Teams](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="f1dc1-123">Si su organización es un centro educativo y usa un sistema de información de estudiante, [implemente School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f1dc1-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="f1dc1-124">Una vez que haya verificado que su entorno cumple con todos los requisitos previos vigentes, [evalúe su entorno actual para Teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f1dc1-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
