---
title: Preparar la implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use listas de comprobación de incorporación para preparar Office 365 para equipos y configurar las capacidades básicas de Teams, las redes y las cargas de trabajo de voz de nube.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 653b5cf46e0b079af47c282b4110b181e76be915
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516499"
---
# <a name="prepare-my-service"></a><span data-ttu-id="c26dd-103">Preparar mis servicios</span><span class="sxs-lookup"><span data-stu-id="c26dd-103">Prepare my service</span></span>

<span data-ttu-id="c26dd-104">Este artículo proporciona una descripción general de los requisitos para preparar los servicios de voz en la nube para su organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="c26dd-105">Si se prepara correctamente, puede estar seguro de que está listo para proporcionar funcionalidades de voz en la nube a su organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="c26dd-106">Listas de comprobación de incorporación para las cargas de trabajo de voz de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="c26dd-107">La siguiente lista de comprobación le guiará a través de los pasos para implementar audioconferencias, sistemas telefónicos con planes de llamadas ("planes de llamadas") y capacidades de enrutamiento directo del sistema telefónico ("enrutamiento directo") en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c26dd-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="c26dd-108">Preparar Office 365 para equipos</span><span class="sxs-lookup"><span data-stu-id="c26dd-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="c26dd-109">Configurar capacidades básicas de Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="c26dd-110">Configurar redes</span><span class="sxs-lookup"><span data-stu-id="c26dd-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="c26dd-111">Configurar cargas de trabajo de voz de nube en Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="c26dd-112">Configurar el enrutamiento directo en Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="c26dd-113">Las tareas y actividades de estas listas de comprobación son los elementos básicos de "tareas pendientes" que se aplican a cada implementación de las capacidades de voz en la nube con Teams.</span><span class="sxs-lookup"><span data-stu-id="c26dd-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="c26dd-114">Puede personalizar las listas de comprobación para incluir las actividades y las tareas específicas de su propio viaje de equipos.</span><span class="sxs-lookup"><span data-stu-id="c26dd-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="c26dd-115">Esta guía se centra únicamente en los planes de llamadas, las conferencias de audio y el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="c26dd-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="c26dd-116">Si es nuevo en Teams, revise la [información general de Microsoft Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c26dd-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="c26dd-117">Para obtener instrucciones generales sobre el planeamiento de la implementación de Teams, comience con la [implementación de chat, equipos, canales y aplicaciones en Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c26dd-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="c26dd-118">Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada una de las actividades y tareas, y para asegurarse de que no ha omitido ningún paso importante.</span><span class="sxs-lookup"><span data-stu-id="c26dd-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="c26dd-119">Cada actividad incluye una descripción detallada de las acciones y referencias necesarias para la información adicional que puede usar para completar esa actividad.</span><span class="sxs-lookup"><span data-stu-id="c26dd-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="c26dd-120">Aunque le recomendamos que siga las listas de comprobación en orden, la secuencia exacta dependerá del alcance de la implementación, así como de la configuración y la complejidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="c26dd-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="c26dd-121">Están organizados para admitir una implementación de equipos de "Greenfield" (uno sin presencia anterior de Skype empresarial online) o de Skype empresarial online a teams.</span><span class="sxs-lookup"><span data-stu-id="c26dd-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="c26dd-122">Si va a migrar desde Skype empresarial online, es posible que ya haya completado algunas de estas actividades y las pueda ignorar ahora.</span><span class="sxs-lookup"><span data-stu-id="c26dd-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="c26dd-123">Cuando incorpora usuarios en función de cada sitio, le recomendamos encarecidamente que use la guía [de habilitación de sitios para voz (guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como una guía complementaria a estas listas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c26dd-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="c26dd-124">La mayoría de las opciones de configuración son comunes entre equipos y Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="c26dd-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="c26dd-125">Use el centro de administración de Microsoft 365 y el centro de administración de Microsoft Teams para configurar estas opciones.</span><span class="sxs-lookup"><span data-stu-id="c26dd-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="c26dd-126">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="c26dd-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="c26dd-127">¿Quién será el responsable de supervisar la finalización de las listas de comprobación de incorporación?</span><span class="sxs-lookup"><span data-stu-id="c26dd-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="c26dd-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c26dd-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="c26dd-129">Descargue las listas de comprobación de incorporación.</span><span class="sxs-lookup"><span data-stu-id="c26dd-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="c26dd-130">Trabaje paso a paso en la lista de comprobación de complementos de acuerdo con el plan de implementación de su organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="c26dd-131">Continuar con la incorporación</span><span class="sxs-lookup"><span data-stu-id="c26dd-131">Continue onboarding</span></span>

<span data-ttu-id="c26dd-132">Después de completar estas listas de comprobación, habrá agregado correctamente capacidades de voz a la implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="c26dd-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="c26dd-133">Como paso siguiente, use la [Guía de habilitación de sitios para voz (Guía de servicio)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para que le resulte más fácil incorporar a los usuarios de cada sitio y asegurarse de que planea y ejecuta actividades importantes específicas del sitio.</span><span class="sxs-lookup"><span data-stu-id="c26dd-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="c26dd-134">Plan de lanzamiento de sitio preparado por sitio</span><span class="sxs-lookup"><span data-stu-id="c26dd-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="c26dd-135">Establecer el proceso de administración de servicios</span><span class="sxs-lookup"><span data-stu-id="c26dd-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="c26dd-136">Ejecutar pruebas y correcciones</span><span class="sxs-lookup"><span data-stu-id="c26dd-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="c26dd-137">Probar las cargas de trabajo de voz en la nube en Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="c26dd-138">Una vez que haya definido y documentado los planes de implementación técnica y de éxito de su equipo de voz en la nube como parte de la fase de previsión y haya realizado la configuración que desea en el centro de administración, el siguiente paso es validar que la organización las expectativas y los requisitos se cumplen mediante características, funcionalidad y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="c26dd-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="c26dd-139">Debe realizar este paso de validación antes de implementar una implementación piloto o final en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="c26dd-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="c26dd-140">Puede aprovechar el plan de éxito empresarial que definió durante la fase de enVision para servir como base para determinar las actividades, expectativas, casos de pruebas de características/funcionalidades y ámbito general que se evaluará durante la fase de pruebas.</span><span class="sxs-lookup"><span data-stu-id="c26dd-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="c26dd-141">Definir el método de prueba</span><span class="sxs-lookup"><span data-stu-id="c26dd-141">Define your testing approach</span></span>

<span data-ttu-id="c26dd-142">En su forma más simple, el método de pruebas se basa en la revisión de las capacidades de las características de la audioconferencia, los planes de llamadas o el servicio de enrutamiento directo y el desarrollo de un plan de pruebas para comprobar que se cumplen los requisitos de funcionalidad para los usuarios en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c26dd-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="c26dd-143">A continuación se encuentra un plan de prueba de ejemplo para la fase integrada de una implementación de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c26dd-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="c26dd-144">Característica de audioconferencia para probar</span><span class="sxs-lookup"><span data-stu-id="c26dd-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="c26dd-145">Resumen de resultados</span><span class="sxs-lookup"><span data-stu-id="c26dd-145">Results summary</span></span> | <span data-ttu-id="c26dd-146">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="c26dd-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="c26dd-147">Programar una reunión de equipos ad-hoc que contenga información de acceso telefónico de las conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="c26dd-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="c26dd-148">Superado/suspenso</span><span class="sxs-lookup"><span data-stu-id="c26dd-148">Pass/Fail</span></span>   | <span data-ttu-id="c26dd-149">DETERMINADO</span><span class="sxs-lookup"><span data-stu-id="c26dd-149">TBD</span></span> |
| <span data-ttu-id="c26dd-150">Usar un teléfono para el audio de la reunión mediante el marcado a una reunión desde la RTC con la información de acceso telefónico proporcionada</span><span class="sxs-lookup"><span data-stu-id="c26dd-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="c26dd-151">Superado/suspenso</span><span class="sxs-lookup"><span data-stu-id="c26dd-151">Pass/Fail</span></span> | <span data-ttu-id="c26dd-152">DETERMINADO</span><span class="sxs-lookup"><span data-stu-id="c26dd-152">TBD</span></span> |
| <span data-ttu-id="c26dd-153">Unirse a otras personas a una reunión existente mediante la llamada a través de la RTC</span><span class="sxs-lookup"><span data-stu-id="c26dd-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="c26dd-154">Superado/suspenso</span><span class="sxs-lookup"><span data-stu-id="c26dd-154">Pass/Fail</span></span> | <span data-ttu-id="c26dd-155">DETERMINADO</span><span class="sxs-lookup"><span data-stu-id="c26dd-155">TBD</span></span> |



| <span data-ttu-id="c26dd-156">Planes de llamadas o característica de enrutamiento directo para probar</span><span class="sxs-lookup"><span data-stu-id="c26dd-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="c26dd-157">Resumen de resultados</span><span class="sxs-lookup"><span data-stu-id="c26dd-157">Results summary</span></span> | <span data-ttu-id="c26dd-158">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="c26dd-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="c26dd-159">Hacer una llamada RTC marcando un número de RTC</span><span class="sxs-lookup"><span data-stu-id="c26dd-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="c26dd-160">Superado/suspenso</span><span class="sxs-lookup"><span data-stu-id="c26dd-160">Pass/Fail</span></span>       | <span data-ttu-id="c26dd-161">DETERMINADO</span><span class="sxs-lookup"><span data-stu-id="c26dd-161">TBD</span></span> |
| <span data-ttu-id="c26dd-162">Recibir una llamada RTC marcando su número de RTC desde una línea externa (móvil, teléfono fijo)</span><span class="sxs-lookup"><span data-stu-id="c26dd-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="c26dd-163">Superado/suspenso</span><span class="sxs-lookup"><span data-stu-id="c26dd-163">Pass/Fail</span></span> | <span data-ttu-id="c26dd-164">DETERMINADO</span><span class="sxs-lookup"><span data-stu-id="c26dd-164">TBD</span></span>|
| <span data-ttu-id="c26dd-165">Transferir una llamada RTC de un usuario de un equipo a otro</span><span class="sxs-lookup"><span data-stu-id="c26dd-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="c26dd-166">Superado/suspenso</span><span class="sxs-lookup"><span data-stu-id="c26dd-166">Pass/Fail</span></span> | <span data-ttu-id="c26dd-167">DETERMINADO</span><span class="sxs-lookup"><span data-stu-id="c26dd-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="c26dd-168">Para obtener ayuda con la creación de casos de prueba como punto de partida, consulte la lista de instrucciones para el usuario disponible en las [reuniones y las llamadas de Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="c26dd-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="c26dd-169">Configurar cargas de trabajo de voz en la nube para equipos</span><span class="sxs-lookup"><span data-stu-id="c26dd-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="c26dd-170">Ahora que ha definido el método de prueba, el siguiente paso es configurar su entorno de servicio y los usuarios en ámbito para las características de voz en la nube de Teams.</span><span class="sxs-lookup"><span data-stu-id="c26dd-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="c26dd-171">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="c26dd-171">For additional information, see:</span></span>

- [<span data-ttu-id="c26dd-172">Planificación técnica de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="c26dd-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="c26dd-173">Configurar audioconferencias en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="c26dd-174">Planificación técnica para el sistema telefónico con planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="c26dd-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="c26dd-175">Configurar planes de llamadas para Skype empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c26dd-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="c26dd-176">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="c26dd-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="c26dd-177">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="c26dd-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="c26dd-178">Ejecutar el plan de pruebas</span><span class="sxs-lookup"><span data-stu-id="c26dd-178">Execute the test plan</span></span>

[//]: # (¿Modificar? "El usuario" parecía algo ambiguo para mí.)
<span data-ttu-id="c26dd-180">Después de configurar el entorno de usuario y el servicio, el último paso de las pruebas incluye la ejecución del plan de pruebas con el foco en la validación de características y funciones.</span><span class="sxs-lookup"><span data-stu-id="c26dd-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="c26dd-181">**Pruebas de las conferencias de audio y requisitos previos para usuarios y sitios en el ámbito:**</span><span class="sxs-lookup"><span data-stu-id="c26dd-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c26dd-182">Se ha completado la definición del caso de uso empresarial para el servicio audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c26dd-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="c26dd-183">Las licencias necesarias para las conferencias de audio están disponibles y se han asignado.</span><span class="sxs-lookup"><span data-stu-id="c26dd-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="c26dd-184">Se ha identificado la lista de sitios y grupos de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c26dd-185">Se ha identificado y configurado la lista de números de marcado de audioconferencias dedicados y compartidos con preferencias de idioma.</span><span class="sxs-lookup"><span data-stu-id="c26dd-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="c26dd-186">Se han configurado [créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) para su organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="c26dd-187">La configuración del puente de conferencia de conferencia de audio ha sido identificada y configurada (longitud del PIN, notificaciones de entrada/salida, preferencia de notificación de habilitación).</span><span class="sxs-lookup"><span data-stu-id="c26dd-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="c26dd-188">Las directivas de conferencia de inquilino y la configuración del plan de marcado que admiten escenarios de llamada de conferencias de audio se han identificado, configurado y aplicado.</span><span class="sxs-lookup"><span data-stu-id="c26dd-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="c26dd-189">Se han identificado y configurado los requisitos de cumplimiento de las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="c26dd-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="c26dd-190">**Planes de llamadas que prueban los requisitos previos y los supuestos de los usuarios y los sitios en el ámbito:**</span><span class="sxs-lookup"><span data-stu-id="c26dd-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c26dd-191">Se ha completado la definición del caso de uso empresarial para el servicio de planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="c26dd-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="c26dd-192">La licencia necesaria para los planes de llamadas está disponible y se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="c26dd-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="c26dd-193">Se ha identificado la lista de sitios y grupos de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c26dd-194">Los números de teléfono que se asignarán a los usuarios se han adquirido o trasladado a Microsoft y están disponibles en el portal del inquilino.</span><span class="sxs-lookup"><span data-stu-id="c26dd-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="c26dd-195">Se han configurado [créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) para su organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="c26dd-196">Las directivas de usuario de inquilino y la configuración del plan de marcado que admiten escenarios de llamadas se han identificado, configurado y aplicado.</span><span class="sxs-lookup"><span data-stu-id="c26dd-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="c26dd-197">Se han identificado y configurado los requisitos de cumplimiento de planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c26dd-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="c26dd-198">**Enrutamiento directo pruebe las suposiciones y los requisitos previos de los usuarios y los sitios en el ámbito:**</span><span class="sxs-lookup"><span data-stu-id="c26dd-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="c26dd-199">Se ha completado la definición del caso de uso empresarial para el servicio de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="c26dd-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="c26dd-200">La licencia necesaria para el enrutamiento directo está disponible y se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="c26dd-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="c26dd-201">Se ha identificado la lista de sitios y grupos de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="c26dd-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="c26dd-202">Un [controlador de borde de sesión (SBC) certificado](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) se ha implementado, configurado y emparejado con el sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="c26dd-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="c26dd-203">Se ha habilitado la telefonía IP empresarial y se han asignado los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="c26dd-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="c26dd-204">Se han identificado, configurado y asignado las directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="c26dd-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="c26dd-205">Microsoft Teams se ha configurado como el cliente de llamadas preferido para los usuarios en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="c26dd-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="c26dd-206">Los requisitos de cumplimiento de enrutamiento directo se han identificado y configurado.</span><span class="sxs-lookup"><span data-stu-id="c26dd-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="c26dd-207">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="c26dd-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="c26dd-208">Decidir qué capacidades de características de audioconferencia se implementarán (decisión de servicio).</span><span class="sxs-lookup"><span data-stu-id="c26dd-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="c26dd-209">Identifique los requisitos de funcionalidad de usuario para audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c26dd-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="c26dd-210">Identifique los requisitos de configuración del servicio para audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c26dd-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="c26dd-211">Decidir si los planes de llamadas o enrutamiento directos se implementarán y configurarán.</span><span class="sxs-lookup"><span data-stu-id="c26dd-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="c26dd-212">Decidir qué funcionalidades de características del sistema telefónico se implementarán (decisión de servicio).</span><span class="sxs-lookup"><span data-stu-id="c26dd-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="c26dd-213">Identifique los requisitos de funcionalidad de usuario para los planes de llamadas o el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="c26dd-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="c26dd-214">Identifique los requisitos de configuración del servicio para los planes de llamadas o el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="c26dd-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="c26dd-215">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c26dd-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="c26dd-216">Desarrolle y documente el método de su plan de pruebas.</span><span class="sxs-lookup"><span data-stu-id="c26dd-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="c26dd-217">Preparar el entorno de servicio y los usuarios en el ámbito de las características de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="c26dd-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="c26dd-218">Preparar el entorno de servicio y los usuarios en el ámbito de los planes de llamadas o de las características de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="c26dd-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="c26dd-219">Ejecute la validación de prueba para las características de audioconferencia que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="c26dd-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="c26dd-220">Ejecute la validación de prueba para los planes de llamadas o las características de enrutamiento directo que desee habilitar.</span><span class="sxs-lookup"><span data-stu-id="c26dd-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="c26dd-221">Para cualquier error de prueba, confirme que la configuración es correcta, revise los artículos de la comunidad y, si es necesario, aumente un caso de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c26dd-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="c26dd-222">Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas de conferencias de audio en Teams, consulte la [Guía de pruebas detallada de audioconferencia](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="c26dd-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="c26dd-223">Para obtener instrucciones detalladas adicionales sobre cómo realizar pruebas de planes de llamadas en Teams, consulte la [Guía de pruebas detallada para el sistema telefónico](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="c26dd-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
