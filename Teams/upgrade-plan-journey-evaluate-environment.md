---
title: Evaluar el entorno antes de actualizar a Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre los requisitos para evaluar correctamente su entorno actual para actualizar a Teams.
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
ms.openlocfilehash: c783934128e2c1d3f971948c41e3481839ff0aa1
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578243"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="d2a6e-103">Evaluar el entorno antes de actualizar a Teams</span><span class="sxs-lookup"><span data-stu-id="d2a6e-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="d2a6e-104">![Diagrama de viaje de actualización, que enfatiza la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Fases del viaje de actualización, con énfasis en la fase De preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="d2a6e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="d2a6e-105">Este artículo forma parte de la fase de preparación técnica del viaje de actualización, una actividad que se completa en paralelo con la fase De disponibilidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="d2a6e-106">Antes de continuar, confirma que has completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="d2a6e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="d2a6e-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="d2a6e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d2a6e-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="d2a6e-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d2a6e-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="d2a6e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d2a6e-110">Ha elegido el viaje de actualización</span><span class="sxs-lookup"><span data-stu-id="d2a6e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="d2a6e-111">En este artículo se ofrece información general sobre los requisitos para evaluar correctamente el entorno actual para el funcionamiento de Teams.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="d2a6e-112">Al evaluar su entorno, identificará los riesgos y requisitos que influirán en la implementación general.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="d2a6e-113">Mediante la identificación previa de estos elementos, puede ajustar la planificación para impulsar el éxito.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="d2a6e-114">Introducción al cuestionario de detección</span><span class="sxs-lookup"><span data-stu-id="d2a6e-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="d2a6e-115">Para lograr los resultados clave objetivo (OKR), previamente ha tomado decisiones clave del servicio.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="d2a6e-116">El siguiente paso es realizar un descubrimiento medioambiental para evaluar todos los aspectos relacionados con su infraestructura de TI, redes y operaciones para confirmar que su organización está lista para implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="d2a6e-117">Descubrir es uno de los primeros pasos clave que debe seguir al planear su viaje a Teams.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="d2a6e-118">El descubrimiento medioambiental debe incluir una evaluación de la preparación de la red para asegurarse de que su red pueda admitir la actualización a Teams.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="d2a6e-119">Realice un descubrimiento detallado del entorno para comprender mejor su estado actual y para revelar cualquier dificultad o, incluso más importante, posibles bloqueadores para la ejecución de la implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="d2a6e-120">Identifique los riesgos técnicos como parte de una evaluación medioambiental y evaluación de la preparación para la adopción, y desarrolle un plan de mitigación para cada riesgo identificado.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="d2a6e-121">Debe incorporar esta información en el registro de riesgos.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="d2a6e-122">Todos los aspectos relacionados con su infraestructura de colaboración existente y la organización de Microsoft 365 u Office 365, redes, puntos de conexión, operaciones, adopción y preparación se incluyen como parte del cuestionario de detección medioambiental.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="d2a6e-123">Trabaje con el equipo del proyecto para proporcionar la información solicitada todos los detalles posibles para facilitar sus actividades de planificación.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="d2a6e-124">[El cuestionario](upgrade-plan-journey-discovery-questionnaire.md) se divide en las siguientes secciones para confirmar la disponibilidad de su organización para la implementación de Teams en varias áreas principales:</span><span class="sxs-lookup"><span data-stu-id="d2a6e-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="d2a6e-125">Detalles de la organización de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d2a6e-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="d2a6e-126">Resumen de la plataforma de colaboración existente</span><span class="sxs-lookup"><span data-stu-id="d2a6e-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="d2a6e-127">Detalles de implementación de la plataforma de colaboración</span><span class="sxs-lookup"><span data-stu-id="d2a6e-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="d2a6e-128">Redes y acceso a servicios de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="d2a6e-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="d2a6e-129">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="d2a6e-129">Endpoints</span></span>
- <span data-ttu-id="d2a6e-130">Operations</span><span class="sxs-lookup"><span data-stu-id="d2a6e-130">Operations</span></span>
- <span data-ttu-id="d2a6e-131">Adopción y preparación</span><span class="sxs-lookup"><span data-stu-id="d2a6e-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="d2a6e-132">Para empezar, copie el cuestionario en un documento de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="d2a6e-133">Intente responder a todas las preguntas y capturar todos los detalles a medida que se desplaza por ellos.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="d2a6e-134">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="d2a6e-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="d2a6e-135">¿Quién será responsable de completar una evaluación del entorno?</span><span class="sxs-lookup"><span data-stu-id="d2a6e-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="d2a6e-136">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d2a6e-136">Next step</span></span></td><td><ul><li><span data-ttu-id="d2a6e-137">Documente los resultados de la evaluación del entorno.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="d2a6e-138">Equipo del proyecto</span><span class="sxs-lookup"><span data-stu-id="d2a6e-138">Project team</span></span>

<span data-ttu-id="d2a6e-139">Asegúrese de que ha comprometido a las personas correctas para su equipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2a6e-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="d2a6e-140">Compruebe los pasos que completó en Dar [la lista a las partes interesadas del proyecto.](upgrade-enlist-stakeholders.md)</span><span class="sxs-lookup"><span data-stu-id="d2a6e-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="d2a6e-141">Después de evaluar su entorno, continúe con el paso siguiente: [Preparar el servicio.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="d2a6e-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
