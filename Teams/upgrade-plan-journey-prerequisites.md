---
title: Requisitos previos de los equipos de Microsoft | Actualización de adopción de dependencias
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use esta guía para obtener más información acerca de los requisitos previos y las dependencias del entorno para implementar los equipos de la organización
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 784c2ac08ca6dbfece5cdc8c99fee2b308325576
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895936"
---
<span data-ttu-id="d477c-103">![Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica] (media/upgrade-banner-tech-readiness.png "Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="d477c-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="d477c-104">En este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad completar en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="d477c-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="d477c-105">Antes de continuar, confirme que ha realizado estas actividades de fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="d477c-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="d477c-106">Los participantes en el proyecto de alta</span><span class="sxs-lookup"><span data-stu-id="d477c-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d477c-107">Define el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="d477c-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d477c-108">Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos</span><span class="sxs-lookup"><span data-stu-id="d477c-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d477c-109">Elegido su viaje por la actualización</span><span class="sxs-lookup"><span data-stu-id="d477c-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="d477c-110">Requisitos previos y las dependencias del entorno para los equipos</span><span class="sxs-lookup"><span data-stu-id="d477c-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="d477c-111">Los equipos combina varios servicios de Office 365 y, por lo tanto, depende de la correcta implementación y el funcionamiento de estos servicios.</span><span class="sxs-lookup"><span data-stu-id="d477c-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="d477c-112">Estos servicios incluyen, pero no está limitado a: Exchange Online, SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="d477c-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="d477c-113">Aunque no todos los servicios son necesarios, se recomienda encarecidamente implementar todos ellos.</span><span class="sxs-lookup"><span data-stu-id="d477c-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="d477c-114">Si decide no implementar determinados servicios, afectará a la funcionalidad que los equipos pueden ofrecer a su organización.</span><span class="sxs-lookup"><span data-stu-id="d477c-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="d477c-115">Por ejemplo, aunque no tiene que implementar SharePoint Online, los equipos se basan en SharePoint Online para determinadas funciones, como compartir archivos de las conversaciones en grupo, por lo que no se implementa este servicio reducirán la funcionalidad que ofrece a través de la cliente.</span><span class="sxs-lookup"><span data-stu-id="d477c-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="d477c-116">Vea los siguientes artículos para obtener más información acerca de los requisitos previos y cómo los equipos interactúa con otras tecnologías:</span><span class="sxs-lookup"><span data-stu-id="d477c-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="d477c-117">Si la organización no ha implementado las cargas de trabajo de Office 365, vea [Introducción a Office 365 para la empresa](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="d477c-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="d477c-118">Si la organización no ha agregado o se ha configurado un dominio comprobado para Office 365, vea [Verify su dominio de Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="d477c-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="d477c-119">Si su organización no sincronizado las identidades de Azure Active Directory, vea [modelos de identidad y la autenticación en los equipos de Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d477c-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="d477c-120">Si su organización doesn¹t tiene Exchange Online, vea [comprender cómo interactúan los equipos de Microsoft y de Exchange](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="d477c-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="d477c-121">Si su organización no tiene SharePoint Online, consulte [comprender cómo SharePoint Online y OneDrive para la empresa interactúan con los equipos de Microsoft](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="d477c-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="d477c-122">Obtenga información sobre cómo [interactúan los grupos de Office 365 y equipos de Microsoft](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d477c-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="d477c-123">Si la organización es una institución de enseñanza y usar un sistema de información de estudiantes, [implementar la sincronización de datos de escuela](https://docs.microsoft.com/schooldatasync) antes de implementar Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d477c-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="d477c-124">Una vez que se haya comprobado que su entorno cumple todos los requisitos previos aplicables, [evaluar su entorno actual para los equipos](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d477c-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
