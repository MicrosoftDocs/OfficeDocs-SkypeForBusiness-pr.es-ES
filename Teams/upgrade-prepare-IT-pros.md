---
title: Preparar al personal de TI para Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo preparar al personal de TI de su organización para implementar y dar soporte técnico a Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 680106618d610d0adc3f93658e3a522d63850e24
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578463"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="8a73e-103">Preparar al personal de TI para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a73e-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="8a73e-104">![Diagrama de viaje de actualización, que enfatiza la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Fases del viaje de actualización, con énfasis en la fase De preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="8a73e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="8a73e-105">Este artículo forma parte de la fase de preparación técnica del viaje de actualización, una actividad que se completa en paralelo con la fase De disponibilidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="8a73e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="8a73e-106">Antes de continuar, confirma que has completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="8a73e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="8a73e-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="8a73e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8a73e-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="8a73e-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8a73e-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="8a73e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8a73e-110">Ha elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="8a73e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="8a73e-111">Los administradores de Microsoft 365 u Office 365, los responsables técnicos y el departamento de soporte técnico son responsables de impulsar una experiencia de usuario de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="8a73e-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="8a73e-112">Esto incluye garantizar que su red esté preparada para admitir Teams, configurar Teams para sus usuarios y poder solucionar de forma eficaz los problemas que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="8a73e-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="8a73e-113">Comparta los siguientes recursos con los miembros del personal de TI y confirme que están listos para ayudar a los usuarios antes de comenzar la actualización a Teams:</span><span class="sxs-lookup"><span data-stu-id="8a73e-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="8a73e-114">Formación de administradores para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a73e-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="8a73e-115">Contactar con el soporte técnico para productos empresariales: ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="8a73e-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="8a73e-116">Solucionar problemas de conectividad con el cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a73e-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="8a73e-117">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a73e-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="8a73e-119">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="8a73e-119">Decision points</span></span>|<ul><li><span data-ttu-id="8a73e-120">¿Ha implicado a todo el personal de soporte técnico que probablemente esté implicado en la implementación y el soporte técnico de Teams?</span><span class="sxs-lookup"><span data-stu-id="8a73e-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="8a73e-121">¿Ha desarrollado un plan de aprendizaje para incorporar personal adicional a medida que avanza la actualización?</span><span class="sxs-lookup"><span data-stu-id="8a73e-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/><span data-ttu-id="8a73e-123">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8a73e-123">Next steps</span></span>|<ul><li><span data-ttu-id="8a73e-124">Compruebe que el personal de IT tenga la información que necesitan.</span><span class="sxs-lookup"><span data-stu-id="8a73e-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="8a73e-125">Revise sus planes de formación y preparación a medida que se van publicando nuevas características.</span><span class="sxs-lookup"><span data-stu-id="8a73e-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="8a73e-126">Una vez que haya preparado el personal de TI para Teams, compruebe que su entorno cumpla todos los [requisitos previos.](upgrade-plan-journey-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="8a73e-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
