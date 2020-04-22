---
title: Aprendizaje de Microsoft Teams | Problemas de administración del soporte técnico
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Preparar al personal de TI de su organización para implementar y ofrecer soporte técnico a Microsoft Teams.
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
ms.openlocfilehash: 47aef5ceee6daee63683655f167016e4d7ae1cf2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776740"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="b8028-103">Preparar el personal de TI para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8028-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="b8028-104">![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="b8028-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="b8028-105">Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="b8028-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="b8028-106">Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="b8028-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="b8028-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="b8028-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b8028-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="b8028-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="b8028-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="b8028-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="b8028-110">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="b8028-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="b8028-111">Los administradores de su organización de Office 365, sus clientes técnicos y el servicio de asistencia al cliente son responsables de conducir una experiencia de usuario de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="b8028-111">Your Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="b8028-112">Esto incluye asegurarse de que su red está lista para admitir equipos, configurar equipos para los usuarios y ser capaz de solucionar y resolver los problemas que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="b8028-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="b8028-113">Comparta los siguientes recursos con los miembros de su personal de ti y compruebe que estén listos para admitir usuarios antes de empezar la actualización a teams:</span><span class="sxs-lookup"><span data-stu-id="b8028-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="b8028-114">Formación de administradores para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8028-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="b8028-115">Contactar con soporte técnico para productos empresariales: ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="b8028-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="b8028-116">Solucionar problemas de conectividad con el cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8028-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="b8028-117">Usar los archivos de registro para solucionar problemas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8028-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)

[//]: # (Pregunte a Debbie para examinar:)

| | |
|---|---|
| ![Un icono que representa los puntos de decisión](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b8028-120">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="b8028-120">Decision points</span></span>|<ul><li><span data-ttu-id="b8028-121">¿Tiene implicado todo el personal de soporte técnico que pueda estar implicado en la implementación y el soporte técnico de Teams?</span><span class="sxs-lookup"><span data-stu-id="b8028-121">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="b8028-122">¿Ha desarrollado un plan de formación para la incorporación de personal adicional a medida que progresa el upgrade?</span><span class="sxs-lookup"><span data-stu-id="b8028-122">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![Un icono que representa los siguientes pasos](media/audio_conferencing_image9.png)<br/><span data-ttu-id="b8028-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b8028-124">Next steps</span></span>|<ul><li><span data-ttu-id="b8028-125">Verifica que el personal de ti tenga la información que necesitan.</span><span class="sxs-lookup"><span data-stu-id="b8028-125">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="b8028-126">Vuelve a visitar los planes de formación y preparación conforme se publiquen nuevas características.</span><span class="sxs-lookup"><span data-stu-id="b8028-126">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="b8028-127">Una vez que haya preparado el personal de TI para Teams, verifique que su entorno cumpla con todos los [requisitos previos](upgrade-plan-journey-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="b8028-127">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
