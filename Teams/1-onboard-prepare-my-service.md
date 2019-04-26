---
title: Preparar la implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usar listas de comprobación de incorporación a preparar Office 365 para los equipos y configurar la funcionalidad básica de los equipos, redes y en la nube cargas de trabajo de voz.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b800dc410eb6a6d506d3c3ad7ad4719485df84c2
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304824"
---
# <a name="prepare-my-service"></a><span data-ttu-id="baf23-103">Preparar mis servicios</span><span class="sxs-lookup"><span data-stu-id="baf23-103">Prepare my service</span></span>

<span data-ttu-id="baf23-104">En este artículo se ofrece una visión general de los requisitos de preparación en la nube de servicios de voz para su organización.</span><span class="sxs-lookup"><span data-stu-id="baf23-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="baf23-105">Preparando correctamente, puede estar seguro de que está listo para proporcionar capacidades de voz a la organización de la nube.</span><span class="sxs-lookup"><span data-stu-id="baf23-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="baf23-106">Listas de comprobación de incorporación de cargas de trabajo de voz de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="baf23-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="baf23-107">Las listas de comprobación siguientes le guiarán a través de los pasos para la implementación de conferencias de Audio, el sistema telefónico con capacidades de teléfono del sistema enrutamiento directo ("enrutamiento directo") y llamar a planes ("llamar a planes de") en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="baf23-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="baf23-108">Preparación de Office 365 para los equipos</span><span class="sxs-lookup"><span data-stu-id="baf23-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="baf23-109">Configurar la funcionalidad básica de los equipos</span><span class="sxs-lookup"><span data-stu-id="baf23-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="baf23-110">Configuración de redes</span><span class="sxs-lookup"><span data-stu-id="baf23-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="baf23-111">Configurar las cargas de trabajo de voz de la nube en los equipos</span><span class="sxs-lookup"><span data-stu-id="baf23-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="baf23-112">Configurar el enrutamiento directo en los equipos</span><span class="sxs-lookup"><span data-stu-id="baf23-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="baf23-113">Las tareas y actividades en estas listas de comprobación son los elementos de "tareas pendientes" principales que se aplican a todas las implementaciones de las capacidades de voz en la nube con los equipos.</span><span class="sxs-lookup"><span data-stu-id="baf23-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="baf23-114">Puede personalizar las listas de comprobación para incluir las actividades y tareas que son específicas de su propio viaje de los equipos.</span><span class="sxs-lookup"><span data-stu-id="baf23-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="baf23-115">Esta guía se centra únicamente en los planes de llamada, conferencias de Audio y el enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="baf23-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="baf23-116">Si está familiarizado con los equipos, revise la [Información general de los equipos de Microsoft](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="baf23-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="baf23-117">Para obtener instrucciones generales para planear la implementación de los equipos, empiece con [chat Deploy, los equipos, los canales y aplicaciones en los equipos de Microsoft](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="baf23-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="baf23-118">Use las listas de comprobación proporcionadas para realizar un seguimiento del estado de cada actividad individual y tareas, y estar seguro de que no ha omitido los pasos más importantes.</span><span class="sxs-lookup"><span data-stu-id="baf23-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="baf23-119">Cada actividad incluye una descripción detallada de las acciones necesarias y las referencias a información adicional que puede usar para llevar a cabo dicha actividad.</span><span class="sxs-lookup"><span data-stu-id="baf23-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="baf23-120">Aunque se recomienda que siga las listas de comprobación en orden, la secuencia exacta dependerá del ámbito de la implementación y la configuración y la complejidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="baf23-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="baf23-121">Para admitir puede ser un "en entorno virgen" en que están organizados los equipos de implementación (uno con ningún Skype anterior de presencia en línea de negocio) o migrar de Skype para profesionales en línea a los equipos.</span><span class="sxs-lookup"><span data-stu-id="baf23-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="baf23-122">Si está migrando desde Skype para profesionales en línea, es posible que algunas de estas actividades ya ha completado y puede omitir ahora.</span><span class="sxs-lookup"><span data-stu-id="baf23-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="baf23-123">Cuando se haya de incorporación a los usuarios en una base por sitio, se recomienda que use la [Guía de habilitación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como una guía adicional a estas listas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="baf23-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="baf23-124">La mayoría de las opciones de configuración es comunes entre los equipos y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="baf23-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="baf23-125">Use el centro de administración del centro de administración de Office 365 y Microsoft Teams para configurar esas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="baf23-125">You use the Office 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="baf23-126">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="baf23-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="baf23-127">¿Quién será responsable de supervisar la finalización de las listas de comprobación de incorporación?</span><span class="sxs-lookup"><span data-stu-id="baf23-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="baf23-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="baf23-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="baf23-129">Descargar las listas de comprobación de incorporación.</span><span class="sxs-lookup"><span data-stu-id="baf23-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="baf23-130">Funciona a través de los elementos de lista de comprobación de incorporación paso a paso de acuerdo con el plan de implementación de la organización.</span><span class="sxs-lookup"><span data-stu-id="baf23-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="baf23-131">Continuar la incorporación de redes</span><span class="sxs-lookup"><span data-stu-id="baf23-131">Continue onboarding</span></span>

<span data-ttu-id="baf23-132">Después de completar estas listas de comprobación, se habrán agregado correctamente las capacidades de voz a su implementación de los equipos.</span><span class="sxs-lookup"><span data-stu-id="baf23-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="baf23-133">Como el siguiente paso, use la [Guía de habilitación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) que le ayudarán a incorporación los usuarios en cada sitio y ayudar a garantizar que planear y ejecutar importantes actividades específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="baf23-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="baf23-134">Plan de implantación de sitio por sitio listo</span><span class="sxs-lookup"><span data-stu-id="baf23-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="baf23-135">Establecer el proceso de administración de servicio</span><span class="sxs-lookup"><span data-stu-id="baf23-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="baf23-136">Ejecutar la prueba y corrección</span><span class="sxs-lookup"><span data-stu-id="baf23-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="baf23-137">Cargas de trabajo de prueba en la nube voz en los equipos</span><span class="sxs-lookup"><span data-stu-id="baf23-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="baf23-138">Después de ha definido y documentado el éxito del negocio de voz de los equipos en la nube y planes de implementación técnica como parte de la fase de previsión y realizada la configuración que desee en el centro de administración, el siguiente paso es validar que la organización se cumplen las expectativas y requisitos a través de la característica, la funcionalidad y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="baf23-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="baf23-139">Debe realizar este paso de validación antes de implementar una implementación piloto o de final en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="baf23-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="baf23-140">Puede aprovechar el plan de éxito empresarial que haya definido durante la fase de previsión para que sirva como base para determinar las actividades, las expectativas, casos de prueba de características y funcionalidades y ámbito global que se deben evaluar durante la fase de pruebas.</span><span class="sxs-lookup"><span data-stu-id="baf23-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="baf23-141">Definir su enfoque de pruebas</span><span class="sxs-lookup"><span data-stu-id="baf23-141">Define your testing approach</span></span>

<span data-ttu-id="baf23-142">En su forma más sencilla, su enfoque de pruebas se basa en la revisión de las capacidades de la característica de las conferencias de Audio, planes de llamada, o tiene previsto de servicio de enrutamiento directo y desarrollar una prueba comprobar que se cumplen los requisitos de funcionalidad para los usuarios en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="baf23-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="baf23-143">El siguiente es un plan de pruebas de ejemplo para la fase de una implementación de conferencias de audio integrado.</span><span class="sxs-lookup"><span data-stu-id="baf23-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="baf23-144">Característica de conferencia de audio para probar</span><span class="sxs-lookup"><span data-stu-id="baf23-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="baf23-145">Resumen de resultados</span><span class="sxs-lookup"><span data-stu-id="baf23-145">Results summary</span></span> | <span data-ttu-id="baf23-146">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="baf23-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="baf23-147">Programar una reunión de los equipos de ad-hoc que contiene información de marcado de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="baf23-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="baf23-148">Superar</span><span class="sxs-lookup"><span data-stu-id="baf23-148">Pass/Fail</span></span>   | <span data-ttu-id="baf23-149">TBD</span><span class="sxs-lookup"><span data-stu-id="baf23-149">TBD</span></span> |
| <span data-ttu-id="baf23-150">Usar un teléfono para el audio de la reunión marcando el número en una reunión desde la RTC con la información de acceso telefónico proporcionada</span><span class="sxs-lookup"><span data-stu-id="baf23-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="baf23-151">Superar</span><span class="sxs-lookup"><span data-stu-id="baf23-151">Pass/Fail</span></span> | <span data-ttu-id="baf23-152">TBD</span><span class="sxs-lookup"><span data-stu-id="baf23-152">TBD</span></span> |
| <span data-ttu-id="baf23-153">Unirse a otras personas a una reunión existente mediante marcación a través de la RTC</span><span class="sxs-lookup"><span data-stu-id="baf23-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="baf23-154">Superar</span><span class="sxs-lookup"><span data-stu-id="baf23-154">Pass/Fail</span></span> | <span data-ttu-id="baf23-155">TBD</span><span class="sxs-lookup"><span data-stu-id="baf23-155">TBD</span></span> |



| <span data-ttu-id="baf23-156">Para probar la característica enrutamiento directa o planes de llamada</span><span class="sxs-lookup"><span data-stu-id="baf23-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="baf23-157">Resumen de resultados</span><span class="sxs-lookup"><span data-stu-id="baf23-157">Results summary</span></span> | <span data-ttu-id="baf23-158">Notas adicionales</span><span class="sxs-lookup"><span data-stu-id="baf23-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="baf23-159">Realizar una llamada de RTC marcando un número RTC</span><span class="sxs-lookup"><span data-stu-id="baf23-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="baf23-160">Superar</span><span class="sxs-lookup"><span data-stu-id="baf23-160">Pass/Fail</span></span>       | <span data-ttu-id="baf23-161">TBD</span><span class="sxs-lookup"><span data-stu-id="baf23-161">TBD</span></span> |
| <span data-ttu-id="baf23-162">Recibir una llamada de RTC marcando el número de RTC desde una línea externa (móvil, teléfono fijo)</span><span class="sxs-lookup"><span data-stu-id="baf23-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="baf23-163">Superar</span><span class="sxs-lookup"><span data-stu-id="baf23-163">Pass/Fail</span></span> | <span data-ttu-id="baf23-164">TBD</span><span class="sxs-lookup"><span data-stu-id="baf23-164">TBD</span></span>|
| <span data-ttu-id="baf23-165">Transferir una llamada de RTC de un usuario de los equipos a otra</span><span class="sxs-lookup"><span data-stu-id="baf23-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="baf23-166">Superar</span><span class="sxs-lookup"><span data-stu-id="baf23-166">Pass/Fail</span></span> | <span data-ttu-id="baf23-167">TBD</span><span class="sxs-lookup"><span data-stu-id="baf23-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="baf23-168">Para ayudar con la creación de caso de prueba como punto de partida, vea la lista de instrucciones de usuario disponibles en [las reuniones de los equipos y las llamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="baf23-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="baf23-169">Configuración de cargas de trabajo de voz en la nube para los equipos</span><span class="sxs-lookup"><span data-stu-id="baf23-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="baf23-170">Ahora que ha definido su enfoque de pruebas, el siguiente paso es la configuración de su entorno de servicio y los usuarios en el ámbito de las características de voz de los equipos en la nube.</span><span class="sxs-lookup"><span data-stu-id="baf23-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="baf23-171">Para obtener información adicional, vea:</span><span class="sxs-lookup"><span data-stu-id="baf23-171">For additional information, see:</span></span>

- [<span data-ttu-id="baf23-172">Planificación técnica de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="baf23-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="baf23-173">Configurar audioconferencias en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="baf23-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="baf23-174">Técnica de planeación para el sistema telefónico con planes de llamada</span><span class="sxs-lookup"><span data-stu-id="baf23-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="baf23-175">Configurar planes de llamada de Skype para empresas y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="baf23-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="baf23-176">Planear el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="baf23-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="baf23-177">Configurar el enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="baf23-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="baf23-178">Ejecutar el plan de pruebas</span><span class="sxs-lookup"><span data-stu-id="baf23-178">Execute the test plan</span></span>

[//]: # (¿Editar bien? "Usuario" parece un poco ambiguo a mí.)
<span data-ttu-id="baf23-180">Después de que se han configurado el entorno del usuario y el servicio, el último paso de prueba incluye la ejecución de planes de prueba con el foco en la validación de características y funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="baf23-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="baf23-181">**Las pruebas de los requisitos previos y supuestos para los usuarios y sitios en el ámbito de conferencia de audio:**</span><span class="sxs-lookup"><span data-stu-id="baf23-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="baf23-182">Empresa utilizar definición de mayúsculas y minúsculas para las conferencias de Audio se ha completado el servicio.</span><span class="sxs-lookup"><span data-stu-id="baf23-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="baf23-183">Licencias necesarias para conferencias de Audio está disponible y se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="baf23-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="baf23-184">La lista de sitios organizativos y grupos de usuarios se han identificado.</span><span class="sxs-lookup"><span data-stu-id="baf23-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="baf23-185">Se han identificado y configurado la lista de conferencias de audio dedicada y compartida marcado en los números con la preferencia de idioma.</span><span class="sxs-lookup"><span data-stu-id="baf23-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="baf23-186">[Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se han configurado para su organización.</span><span class="sxs-lookup"><span data-stu-id="baf23-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="baf23-187">Configuración de puente de conferencia de audio conferencia ha sido identificados y configurado (longitud PIN, las notificaciones de entrada o salida, preferencia de notificación de activación).</span><span class="sxs-lookup"><span data-stu-id="baf23-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="baf23-188">Las directivas de conferencia de inquilinos y que admitan conferencias de Audio de salida de los escenarios se han identificado, configurados y aplica la configuración del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="baf23-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="baf23-189">Requisitos de cumplimiento de conferencia de audio se han identificado y configurado.</span><span class="sxs-lookup"><span data-stu-id="baf23-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="baf23-190">**Llamar a los planes de pruebas de los requisitos previos y supuestos para los usuarios y sitios en el ámbito:**</span><span class="sxs-lookup"><span data-stu-id="baf23-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="baf23-191">Empresa utilizar definición de mayúsculas y minúsculas para la llamada planes de servicio se ha completado.</span><span class="sxs-lookup"><span data-stu-id="baf23-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="baf23-192">Necesario para llamar a los planes de licencias está disponible y se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="baf23-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="baf23-193">La lista de sitios organizativos y grupos de usuarios se han identificado.</span><span class="sxs-lookup"><span data-stu-id="baf23-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="baf23-194">Los números de teléfono que se asignará a los usuarios se han adquirido o trasladado a Microsoft y están disponibles en el portal de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="baf23-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="baf23-195">[Créditos de comunicaciones](what-are-communications-credits.md) (si es necesario) se han configurado para su organización.</span><span class="sxs-lookup"><span data-stu-id="baf23-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="baf23-196">Las directivas de usuario de inquilinos y que admiten una llamada a planes de escenarios se han identificado, configurados y aplica la configuración del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="baf23-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="baf23-197">Llamar a los planes que se han identificado los requisitos de cumplimiento y se ha configurado.</span><span class="sxs-lookup"><span data-stu-id="baf23-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="baf23-198">**Las pruebas de los requisitos previos y supuestos para los usuarios y sitios en el ámbito de enrutamiento directa:**</span><span class="sxs-lookup"><span data-stu-id="baf23-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="baf23-199">Empresa utilizar definición de mayúsculas y minúsculas para el enrutamiento directo de servicio se ha completado.</span><span class="sxs-lookup"><span data-stu-id="baf23-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="baf23-200">Licencias necesarias para el enrutamiento directo está disponible y se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="baf23-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="baf23-201">La lista de sitios organizativos y grupos de usuarios se han identificado.</span><span class="sxs-lookup"><span data-stu-id="baf23-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="baf23-202">Un [certificado de controlador de borde de sesión (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) se ha implementado, configurado y emparejada con el sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="baf23-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="baf23-203">Se ha habilitado la telefonía IP empresarial, y se han asignado los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="baf23-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="baf23-204">Se han identificado, configuradas y asigna las directivas de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="baf23-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="baf23-205">Microsoft Teams se estableció como el cliente llamado preferido para los usuarios en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="baf23-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="baf23-206">Requisitos de cumplimiento de normas de enrutamiento directos se han identificado y configurado.</span><span class="sxs-lookup"><span data-stu-id="baf23-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="baf23-207">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="baf23-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="baf23-208">Decidir qué capacidades de la característica de conferencia de Audio que se van a implementar (Decisión del servicio).</span><span class="sxs-lookup"><span data-stu-id="baf23-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="baf23-209">Identificar los requisitos de la funcionalidad de usuario para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="baf23-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="baf23-210">Identificar los requisitos de configuración de servicios para conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="baf23-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="baf23-211">Decidir si el enrutamiento directo o planes de llamada se implementarán y configurados.</span><span class="sxs-lookup"><span data-stu-id="baf23-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="baf23-212">Decidir qué capacidades de las funciones del sistema de teléfono que se va a implementar (Decisión del servicio).</span><span class="sxs-lookup"><span data-stu-id="baf23-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="baf23-213">Identificar los requisitos de la funcionalidad de usuario para enrutamiento directa o planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="baf23-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="baf23-214">Identificar requisitos de configuración de servicio para enrutamiento directa o planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="baf23-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="baf23-215">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="baf23-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="baf23-216">Desarrollar y documentar el enfoque del plan de pruebas.</span><span class="sxs-lookup"><span data-stu-id="baf23-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="baf23-217">Preparar el entorno de servicio y los usuarios en el ámbito de las características de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="baf23-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="baf23-218">Preparar su entorno de servicio y los usuarios en el ámbito de las características de enrutamiento directa o planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="baf23-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="baf23-219">Ejecutar pruebas de validación para las características de conferencia de Audio que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="baf23-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="baf23-220">Ejecutar pruebas de validación para las características de enrutamiento directa o planes de llamada que se va a habilitar.</span><span class="sxs-lookup"><span data-stu-id="baf23-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="baf23-221">Para cualquier probar errores, confirme que la configuración es correcta, revise los artículos de la Comunidad, y, si es necesario: elevar un caso de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="baf23-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="baf23-222">Para obtener instrucciones detalladas adicionales acerca de cómo realizar las pruebas para conferencias de Audio en los equipos, vea la [detallada de las pruebas de guía para conferencias de Audio](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="baf23-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="baf23-223">Para obtener instrucciones detalladas adicionales acerca de cómo realizar las pruebas para llamar a los planes de en los equipos, vea la [detallada de las pruebas de guía para el sistema telefónico](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="baf23-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
