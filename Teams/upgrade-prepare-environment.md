---
title: Preparar el entorno para la actualización a teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Valide el entorno y la preparación de la red antes de empezar la actualización de Skype empresarial a teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb736a0398d1ab77ed67919f02a80400bd2ae19e
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578253"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="ae951-103">Preparar el entorno para la actualización a teams</span><span class="sxs-lookup"><span data-stu-id="ae951-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="ae951-104">![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")</span><span class="sxs-lookup"><span data-stu-id="ae951-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ae951-105">Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario.</span><span class="sxs-lookup"><span data-stu-id="ae951-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ae951-106">Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:</span><span class="sxs-lookup"><span data-stu-id="ae951-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ae951-107">Ha incorporado a las partes interesadas del proyecto</span><span class="sxs-lookup"><span data-stu-id="ae951-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ae951-108">Ha definido el ámbito del proyecto</span><span class="sxs-lookup"><span data-stu-id="ae951-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ae951-109">Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="ae951-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ae951-110">Eligió la actualización del viaje</span><span class="sxs-lookup"><span data-stu-id="ae951-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="ae951-111">Para impulsar una actualización correcta de los equipos de su organización, es importante que valide su entorno actual de Skype empresarial y su disponibilidad en la red.</span><span class="sxs-lookup"><span data-stu-id="ae951-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="ae951-112">Preparar el entorno actual le ayudará a garantizar una experiencia de usuario de alta calidad ahora, además de mejorar la calidad de la experiencia de usuario en Teams.</span><span class="sxs-lookup"><span data-stu-id="ae951-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="ae951-113">Tomarse el tiempo para planificar pasos individuales puede ayudarle a acelerar la implementación y a asegurarse de que no haya omitido ningún elemento importante de acción.</span><span class="sxs-lookup"><span data-stu-id="ae951-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="ae951-114">Complete estas actividades en paralelo con la preparación de la preparación del usuario:</span><span class="sxs-lookup"><span data-stu-id="ae951-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="ae951-115">[Prepare su personal de ti](upgrade-prepare-IT-pros.md) para asegurarse de que tienen lo que necesitan para que el viaje de actualización se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae951-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="ae951-116">Compruebe que su entorno cumple con todos los [requisitos previos](upgrade-plan-journey-prerequisites.md)y comprenda las dependencias entre Microsoft 365 u Office 365 Services y Teams.</span><span class="sxs-lookup"><span data-stu-id="ae951-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="ae951-117">[Evalúe el entorno](upgrade-plan-journey-evaluate-environment.md) mediante el descubrimiento ambiental con un cuestionario de ejemplo para confirmar que la disponibilidad de la organización lleva a cabo un viaje correcto de actualización a teams.</span><span class="sxs-lookup"><span data-stu-id="ae951-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="ae951-118">[Prepare su red mediante la](prepare-network.md) planeación, la preparación y la realización de los pasos de corrección necesarios para que la red admita las cargas de trabajo de Teams.</span><span class="sxs-lookup"><span data-stu-id="ae951-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="ae951-119">[Prepare su servicio](upgrade-prepare-environment-prepare-service.md) para el despliegue mediante listas de comprobación de incorporación para asegurarse de que la configuración de equipos está lista para permitir la migración de los usuarios de Skype empresarial a teams.</span><span class="sxs-lookup"><span data-stu-id="ae951-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
