---
title: Actualización de Microsoft Teams | Evaluación del entorno, preguntas sobre descubrimiento
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Use esta guía para obtener información sobre los requisitos para evaluar correctamente su entorno actual para actualizar a teams.
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
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158748"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="84b24-103">Evaluar el entorno antes de actualizar a teams</span><span class="sxs-lookup"><span data-stu-id="84b24-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="84b24-104">![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="84b24-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="84b24-105">Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="84b24-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="84b24-106">Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="84b24-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="84b24-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="84b24-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="84b24-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="84b24-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="84b24-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="84b24-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="84b24-110">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="84b24-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="84b24-111">Este artículo proporciona una descripción general de los requisitos para evaluar correctamente su entorno actual para equipos operativos.</span><span class="sxs-lookup"><span data-stu-id="84b24-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="84b24-112">Al evaluar su entorno, usted identifica los riesgos y los requisitos que influirán en la implementación general.</span><span class="sxs-lookup"><span data-stu-id="84b24-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="84b24-113">Al identificar estos elementos previamente, puede ajustar la planificación para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="84b24-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="84b24-114">Introducción al cuestionario de detección</span><span class="sxs-lookup"><span data-stu-id="84b24-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="84b24-115">Para lograr los resultados clave objetivo (OKRs), ya has tomado decisiones clave sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="84b24-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="84b24-116">El siguiente paso es realizar el descubrimiento medioambiental para evaluar todos los aspectos relacionados con la infraestructura de ti, las redes y las operaciones para confirmar que su organización está lista para implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="84b24-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="84b24-117">El descubrimiento es uno de los primeros pasos clave que debe tomar al planear su viaje a teams.</span><span class="sxs-lookup"><span data-stu-id="84b24-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="84b24-118">El descubrimiento medioambiental debe incluir una evaluación de la disponibilidad de red para asegurarse de que su red pueda admitir la actualización a teams.</span><span class="sxs-lookup"><span data-stu-id="84b24-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="84b24-119">Puede realizar un descubrimiento detallado de su entorno para comprender mejor su estado actual y revelar cualquier dificultad o, aún más importante, los posibles bloqueadores para la ejecución de la implementación de su equipo.</span><span class="sxs-lookup"><span data-stu-id="84b24-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="84b24-120">Identifique los riesgos técnicos como parte de una evaluación del medio ambiente y de la evaluación de la preparación de la adopción, y desarrolle un plan de mitigación por cada riesgo identificado.</span><span class="sxs-lookup"><span data-stu-id="84b24-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="84b24-121">Debes incorporar esta información en el registro de riesgos.</span><span class="sxs-lookup"><span data-stu-id="84b24-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="84b24-122">Todos los temas relacionados con su infraestructura de colaboración existente y Microsoft 365 u Office 365 organización, redes, puntos de conexión, operaciones, adopción y preparación se incluyen como parte del cuestionario de descubrimiento ambiental.</span><span class="sxs-lookup"><span data-stu-id="84b24-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="84b24-123">Trabaje con su equipo de proyecto para proporcionar la información solicitada con la mayor cantidad de detalles posible para facilitar sus actividades de planificación.</span><span class="sxs-lookup"><span data-stu-id="84b24-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="84b24-124">[El cuestionario](upgrade-plan-journey-discovery-questionnaire.md) se divide en las siguientes secciones para confirmar la preparación de su organización para la implementación de equipos en varias áreas principales:</span><span class="sxs-lookup"><span data-stu-id="84b24-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="84b24-125">Detalles de la organización de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="84b24-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="84b24-126">Resumen de la plataforma de colaboración existente</span><span class="sxs-lookup"><span data-stu-id="84b24-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="84b24-127">Detalles de implementación de la plataforma de colaboración</span><span class="sxs-lookup"><span data-stu-id="84b24-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="84b24-128">Redes y acceso a Microsoft 365 u Office 365 Services</span><span class="sxs-lookup"><span data-stu-id="84b24-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="84b24-129">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="84b24-129">Endpoints</span></span>
- <span data-ttu-id="84b24-130">Operations</span><span class="sxs-lookup"><span data-stu-id="84b24-130">Operations</span></span>
- <span data-ttu-id="84b24-131">Adopción y preparación</span><span class="sxs-lookup"><span data-stu-id="84b24-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="84b24-132">Puede empezar copiando el cuestionario en un documento de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="84b24-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="84b24-133">Intenta contestar todas las preguntas y captura todos los detalles a medida que te desplazas.</span><span class="sxs-lookup"><span data-stu-id="84b24-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="84b24-134">Punto de decisión</span><span class="sxs-lookup"><span data-stu-id="84b24-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="84b24-135">¿Quién será el responsable de completar una evaluación del entorno?</span><span class="sxs-lookup"><span data-stu-id="84b24-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="84b24-136">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="84b24-136">Next step</span></span></td><td><ul><li><span data-ttu-id="84b24-137">Documente los resultados de la evaluación del entorno.</span><span class="sxs-lookup"><span data-stu-id="84b24-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="84b24-138">Equipo del proyecto</span><span class="sxs-lookup"><span data-stu-id="84b24-138">Project team</span></span>

<span data-ttu-id="84b24-139">Asegúrese de que ha contratado a las personas adecuadas para el equipo de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="84b24-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="84b24-140">Compruebe los pasos completados para [dar de alta a los participantes del proyecto](upgrade-enlist-stakeholders.md).</span><span class="sxs-lookup"><span data-stu-id="84b24-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="84b24-141">Después de evaluar su entorno, continúe con el siguiente paso: [preparar el servicio](upgrade-prepare-environment-prepare-service.md).</span><span class="sxs-lookup"><span data-stu-id="84b24-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
