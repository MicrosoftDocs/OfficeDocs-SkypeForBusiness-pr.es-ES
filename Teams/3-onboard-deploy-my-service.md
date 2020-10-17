---
title: Implementación de servicios de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Descargue la guía de habilitación de sitios para planificar los lanzamientos de equipos y acelerar y optimizar la adopción de los usuarios, la percepción de su calidad y la satisfacción.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae9a1e6abf7dbf97e625be4eb69a0ef95b1910da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532577"
---
# <a name="deploy-my-service"></a><span data-ttu-id="fd5a6-103">Implementar mis servicios</span><span class="sxs-lookup"><span data-stu-id="fd5a6-103">Deploy my service</span></span>

<span data-ttu-id="fd5a6-104">Este artículo proporciona una descripción general de los requisitos para implementar correctamente los servicios de voz en la nube.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="fd5a6-105">Si sigue una guía prescriptiva para implementar los servicios de voz en la nube, puede asegurarse de que tiene éxito todos los requisitos y de ofrecer resultados repetibles.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="fd5a6-106">Guía de habilitación de sitios para cargas de trabajo de voz de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd5a6-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="fd5a6-107">Use esta guía para ayudar a su organización a planear y ejecutar correctamente la implementación de las características de voz de Microsoft Teams en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="fd5a6-108">Incluye todas las actividades necesarias, las escalas de tiempo recomendadas y los vínculos a la orientación correspondiente para cada actividad, en esta guía se tratan las directrices completas para garantizar una implementación de voz de Teams satisfactoria para un sitio determinado, centrándose en los factores que son importantes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="fd5a6-109">Al completar las actividades de esta guía, su organización puede:</span><span class="sxs-lookup"><span data-stu-id="fd5a6-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="fd5a6-110">Planear y programar de forma eficaz el lanzamiento de Teams.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="fd5a6-111">Acelerar y optimizar la adopción por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="fd5a6-112">Reduzca las necesidades de soporte técnico y aumente la satisfacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="fd5a6-113">Este artículo y la guía relacionada no se destinan a describir todos los pasos de configuración técnica necesarios para la habilitación del servicio o el suministro de tono de marcado a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="fd5a6-114">En su lugar, se concentran en actividades y tareas recomendadas para los usuarios que se incorporan fácilmente y que les permiten comenzar a consumir cargas de trabajo de voz a través de una transición rápida y fluida con una tasa de adopción elevada, a la vez que minimizan los requisitos de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="fd5a6-115">Para obtener orientación técnica sobre cómo configurar mejor su entorno para la voz de Teams, consulte las listas de comprobación de incorporación para [configurar las cargas de trabajo de voz de Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), configurar el [enrutamiento directo en Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), las [capacidades básicas](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)de Teams, las [redes para Teams](prepare-network.md)y [Habilitar Microsoft 365 u Office 365](onboarding-checklist-enable-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fd5a6-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="fd5a6-116">Áreas de concentración de la guía</span><span class="sxs-lookup"><span data-stu-id="fd5a6-116">Playbook focus areas</span></span>

<span data-ttu-id="fd5a6-117">El foco de la guía consiste en tratar los factores que influyen en la percepción del usuario de una implementación de voz de Teams.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="fd5a6-118">Las actividades y las tareas se agrupan en las siguientes áreas de concentración:</span><span class="sxs-lookup"><span data-stu-id="fd5a6-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="fd5a6-119">Validación de la preparación del servicio</span><span class="sxs-lookup"><span data-stu-id="fd5a6-119">Validation of service readiness</span></span>
    - <span data-ttu-id="fd5a6-120">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="fd5a6-120">Audio Conferencing</span></span>
    - <span data-ttu-id="fd5a6-121">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="fd5a6-121">Calling Plans</span></span>
    - <span data-ttu-id="fd5a6-122">Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fd5a6-122">Direct Routing</span></span>

-   <span data-ttu-id="fd5a6-123">Habilitación del usuario</span><span class="sxs-lookup"><span data-stu-id="fd5a6-123">User enablement</span></span>

-   <span data-ttu-id="fd5a6-124">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="fd5a6-124">Endpoints</span></span>

-   <span data-ttu-id="fd5a6-125">Uso y calidad</span><span class="sxs-lookup"><span data-stu-id="fd5a6-125">Usage and quality</span></span>

-   <span data-ttu-id="fd5a6-126">Aprobación</span><span class="sxs-lookup"><span data-stu-id="fd5a6-126">Adoption</span></span>

<span data-ttu-id="fd5a6-127">La [Guía de habilitación de sitios para voz](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="fd5a6-128">Cada una de estas cinco áreas de enfoque es una hoja independiente en el libro, y cada tarea y actividad de implementación se agrupan en una de estas hojas.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="fd5a6-129">![Captura de pantalla de la guía de habilitación de sitios](media/deploy-my-service-image1.png "Captura de pantalla de la guía")</span><span class="sxs-lookup"><span data-stu-id="fd5a6-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="fd5a6-130">Creará una instancia independiente de la guía para cada sitio en el ámbito de la implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="fd5a6-131">Cómo usar la guía</span><span class="sxs-lookup"><span data-stu-id="fd5a6-131">How to use the playbook</span></span>

<span data-ttu-id="fd5a6-132">Independientemente del tamaño y la complejidad de la ubicación, habilitar cada sitio requiere que planee las tareas y las actividades lo antes posible (y las ejecute en orden óptimo) antes, durante y después de la implementación del servicio real.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="fd5a6-133">Le recomendamos que siga estos pasos mientras planea y ejecuta su propio viaje a Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="fd5a6-134">Descargue la [Guía de habilitación de sitios para voz (Guía de voz)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="fd5a6-135">Cree una copia independiente de la guía para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="fd5a6-136">En la pestaña de la hoja denominada **Guía para {siteName-Code}**, reemplaza **{siteName-Code}** por el nombre de sitio correspondiente o el código de sitio.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="fd5a6-137">Escriba el **nombre del sitio, el código de sitio**y la **fecha de lanzamiento planificada**, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="fd5a6-138">Este es un paso crítico, ya que ajusta las fechas límite recomendadas para cada actividad de la guía.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="fd5a6-139">![Ejemplo con nombre de sitio, código de sitio y fecha de lanzamiento planeada](media/deploy-my-service-image2.png "Ejemplo con nombre de sitio de Nueva York, código de sitio NY01 y fecha de lanzamiento planificada de 20 de marzo de 18")</span><span class="sxs-lookup"><span data-stu-id="fd5a6-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="fd5a6-140">Revise cada actividad, lleve a cabo las acciones necesarias y actualice el estado a medida que recorra la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="fd5a6-141">El estado se representa de forma gráfica, como se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="fd5a6-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="fd5a6-142">![Ilustración de una marca de verificación verde ](media/deploy-my-service-image3.png) **sí o no aplicable (verde):** la actividad se ha completado, o no es aplicable para este sitio, y no se necesita ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="fd5a6-143">![Ilustración de un signo de exclamación amarillo ](media/deploy-my-service-image4.png) <strong>la actividad no se ha completado aún (amarillo):</strong> la actividad aún no se ha completado y debe actualizarse a sí o no en su programación.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="fd5a6-144">![Ilustración de una X roja que indica no no ](media/deploy-my-service-image5.png) <strong>(rojo):</strong> la actividad no se puede completar debido a un problema y debe llevarse a la reunión de estado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="fd5a6-145">El estado se resume dentro de cada sección y el título de la sección tiene el formato de uno de estos indicadores de estado.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="fd5a6-146">El **Estado semanal** también se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="fd5a6-147">![Captura de pantalla de los resúmenes de estado semanales en la guía](media/deploy-my-service-image6.png "Captura de pantalla de los resúmenes de estado semanales en la guía")</span><span class="sxs-lookup"><span data-stu-id="fd5a6-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="fd5a6-148">Repita los pasos anteriores para todas las ubicaciones que tiene.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd5a6-149">Es posible que algunos pasos no se apliquen a todas las ubicaciones y sitios.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="fd5a6-150">Si una actividad específica no es relevante para un sitio, debe seleccionar **no aplicable** para esta actividad.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="fd5a6-151">**No elimine** ninguna fila de la guía; Si lo hace, las fórmulas de la imagen de estado no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="fd5a6-152">Preste atención a las actividades que pueden tardar más tiempo del que planeó, como la portabilidad de números y las actividades de compra.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="fd5a6-153">Estas actividades pueden afectar negativamente a la escala de tiempo de la implementación del sitio.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="fd5a6-154">Asegúrese de revisar y actualizar la lista de actividades y la escala de tiempo asociada semanalmente y preséntelas en las [reuniones del Comité de dirección](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para asegurarse de que las partes interesadas conozcan el estado de cada sitio y las posibles desviaciones de la programación de implementación.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="fd5a6-155">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="fd5a6-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="fd5a6-156">Decida si la guía de habilitación de sitios es necesaria para su implementación.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="fd5a6-157">Decida quién será el responsable de personalizar la guía de habilitación del sitio de Microsoft Teams para cada sitio que vaya a implementar.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="fd5a6-158">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="fd5a6-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="fd5a6-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Descargue la guía de habilitación de sitios</a>.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="fd5a6-160">Personalizar la guía de habilitación del sitio para su primer sitio.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="fd5a6-161">Repita los pasos necesarios para los sitios adicionales.</span><span class="sxs-lookup"><span data-stu-id="fd5a6-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->