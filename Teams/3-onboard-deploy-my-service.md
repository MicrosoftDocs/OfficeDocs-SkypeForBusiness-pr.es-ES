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
description: Descargue el Libro de reproducción de habilitación del sitio para planear la implementación de Teams y acelerar y optimizar la adopción del usuario, la percepción de calidad y la satisfacción.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112636"
---
# <a name="deploy-my-service"></a><span data-ttu-id="430ac-103">Implementar mis servicios</span><span class="sxs-lookup"><span data-stu-id="430ac-103">Deploy my service</span></span>

<span data-ttu-id="430ac-104">En este artículo se proporciona información general sobre los requisitos para implementar correctamente los servicios de voz en la nube.</span><span class="sxs-lookup"><span data-stu-id="430ac-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="430ac-105">Siguiendo instrucciones prescriptivas para implementar servicios de voz en la nube, puede asegurarse de que cumple correctamente todos los requisitos y ofrece resultados repetibles.</span><span class="sxs-lookup"><span data-stu-id="430ac-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="430ac-106">Libro de reproducción de habilitación del sitio para cargas de trabajo de voz de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="430ac-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="430ac-107">Use este libro de juegos para ayudar a su organización a planear y ejecutar correctamente la implementación de las características de voz de Microsoft Teams de forma individual.</span><span class="sxs-lookup"><span data-stu-id="430ac-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="430ac-108">Incluyendo todas las actividades necesarias, las escalas de tiempo recomendadas y los vínculos a las instrucciones correspondientes para cada actividad, este libro de reproducción trata las instrucciones de extremo a extremo para ayudar a garantizar una implementación de voz de Teams correcta para un sitio determinado, centrándose en los factores que son importantes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="430ac-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="430ac-109">Al completar las actividades de este libro de juegos, su organización puede:</span><span class="sxs-lookup"><span data-stu-id="430ac-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="430ac-110">Planee y programe su implementación de Teams de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="430ac-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="430ac-111">Acelere y optimice la adopción de usuarios.</span><span class="sxs-lookup"><span data-stu-id="430ac-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="430ac-112">Reduzca las necesidades de soporte técnico y aumente la satisfacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="430ac-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="430ac-113">Este artículo y el libro de juegos asociados no están diseñados para describir todos los pasos de configuración técnica necesarios para la habilitación del servicio o proporcionar tono de marcado a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="430ac-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="430ac-114">En su lugar, se centran en las actividades y tareas recomendadas para incorporar a los usuarios fácilmente y hacer que empiecen a consumir cargas de trabajo de voz de Teams mediante una transición rápida y fluida con una alta tasa de adopción, al tiempo que minimizan los requisitos de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="430ac-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="430ac-115">Para obtener instrucciones técnicas sobre cómo configurar mejor su entorno para la voz de Teams, vea las listas de comprobación de incorporación para configurar las cargas de trabajo de voz de [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)configurar el enrutamiento directo en [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)las capacidades principales de [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)las redes para [Teams](prepare-network.md)y habilitar [Microsoft 365 u Office 365.](onboarding-checklist-enable-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="430ac-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="430ac-116">Áreas de foco de Playbook</span><span class="sxs-lookup"><span data-stu-id="430ac-116">Playbook focus areas</span></span>

<span data-ttu-id="430ac-117">El foco del libro de reproducción es abordar los factores que influyen en la percepción del usuario de una implementación de voz de Teams.</span><span class="sxs-lookup"><span data-stu-id="430ac-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="430ac-118">Las actividades y tareas se agrupan en las siguientes áreas de enfoque:</span><span class="sxs-lookup"><span data-stu-id="430ac-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="430ac-119">Validación de la preparación del servicio</span><span class="sxs-lookup"><span data-stu-id="430ac-119">Validation of service readiness</span></span>
    - <span data-ttu-id="430ac-120">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="430ac-120">Audio Conferencing</span></span>
    - <span data-ttu-id="430ac-121">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="430ac-121">Calling Plans</span></span>
    - <span data-ttu-id="430ac-122">Enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="430ac-122">Direct Routing</span></span>

-   <span data-ttu-id="430ac-123">Habilitación de usuario</span><span class="sxs-lookup"><span data-stu-id="430ac-123">User enablement</span></span>

-   <span data-ttu-id="430ac-124">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="430ac-124">Endpoints</span></span>

-   <span data-ttu-id="430ac-125">Uso y calidad</span><span class="sxs-lookup"><span data-stu-id="430ac-125">Usage and quality</span></span>

-   <span data-ttu-id="430ac-126">Adopción</span><span class="sxs-lookup"><span data-stu-id="430ac-126">Adoption</span></span>

<span data-ttu-id="430ac-127">El [Libro de reproducción de habilitación del sitio para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="430ac-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="430ac-128">Cada una de estas cinco áreas de enfoque es una hoja independiente en el libro y cada tarea y actividad de implementación se agrupa en una de estas hojas.</span><span class="sxs-lookup"><span data-stu-id="430ac-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="430ac-129">![Captura de pantalla del libro de reproducción de habilitación del sitio](media/deploy-my-service-image1.png "Captura de pantalla del libro de reproducción")</span><span class="sxs-lookup"><span data-stu-id="430ac-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="430ac-130">Creará una instancia independiente del libro de juegos para cada sitio en el ámbito de la implementación de Teams.</span><span class="sxs-lookup"><span data-stu-id="430ac-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="430ac-131">Cómo usar el libro de reproducción</span><span class="sxs-lookup"><span data-stu-id="430ac-131">How to use the playbook</span></span>

<span data-ttu-id="430ac-132">Independientemente del tamaño y la complejidad de la ubicación, la habilitación de cada sitio requiere que planee sus tareas y actividades lo suficientemente pronto como para ejecutarlas en orden óptimo, antes, durante y después de la implementación real del servicio.</span><span class="sxs-lookup"><span data-stu-id="430ac-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="430ac-133">Le recomendamos que siga estos pasos a medida que planee y ejecute su propio viaje a La voz de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="430ac-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="430ac-134">Descargue el Libro de reproducción de habilitación [del sitio para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="430ac-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="430ac-135">Cree una copia independiente del libro de reproducción para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="430ac-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="430ac-136">En la pestaña de la hoja denominada **Playbook para {SiteName-Code},** reemplace **{SiteName-Code}** por el nombre del sitio o el código de sitio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="430ac-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="430ac-137">Escriba el **nombre del sitio, el código del** sitio y la fecha de inicio **planificada,** como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="430ac-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="430ac-138">Este es un paso crítico, ya que ajusta las fechas límite recomendadas para cada actividad del libro de reproducción.</span><span class="sxs-lookup"><span data-stu-id="430ac-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="430ac-139">![Ejemplo con nombre de sitio, código de sitio y fecha de inicio planeada](media/deploy-my-service-image2.png "Ejemplo con el nombre del sitio de Nueva York, el código de sitio NY01 y la fecha de lanzamiento planeada del 20 de marzo al 18")</span><span class="sxs-lookup"><span data-stu-id="430ac-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="430ac-140">Revise cada actividad, haga las acciones necesarias y actualice el estado a medida que pase por la escala de tiempo.</span><span class="sxs-lookup"><span data-stu-id="430ac-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="430ac-141">El estado se representa gráficamente, como se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="430ac-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="430ac-142">![Ilustración de una marca de verificación verde Sí o no aplicable ](media/deploy-my-service-image3.png) **(verde):** la actividad se ha completado o no es aplicable para este sitio y no se necesita ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="430ac-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="430ac-143">![Ilustración de un signo de exclamación amarillo La actividad aún no se ha completado (amarillo): la actividad aún no se ha completado y debe actualizarse a Sí o No en ](media/deploy-my-service-image4.png) <strong></strong> su programación.</span><span class="sxs-lookup"><span data-stu-id="430ac-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="430ac-144">![Ilustración de una X roja que indica que no ](media/deploy-my-service-image5.png) <strong>(rojo):</strong> la actividad no se puede completar debido a un problema y debe llevarse a la reunión de estado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="430ac-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="430ac-145">El estado se incluye en cada sección y el encabezado de sección tiene formato con uno de estos indicadores de estado.</span><span class="sxs-lookup"><span data-stu-id="430ac-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="430ac-146">**El estado semanal** también se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="430ac-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="430ac-147">![Captura de pantalla de las actualizaciones semanales de estado en el libro de reproducción](media/deploy-my-service-image6.png "Captura de pantalla de las actualizaciones semanales de estado en el libro de reproducción")</span><span class="sxs-lookup"><span data-stu-id="430ac-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="430ac-148">Repita los pasos anteriores para todas las ubicaciones que tiene.</span><span class="sxs-lookup"><span data-stu-id="430ac-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="430ac-149">Es posible que algunos pasos no sean aplicables a todas las ubicaciones y sitios.</span><span class="sxs-lookup"><span data-stu-id="430ac-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="430ac-150">Si una actividad específica no es relevante para un sitio, debe seleccionar **No aplicable** a esta actividad.</span><span class="sxs-lookup"><span data-stu-id="430ac-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="430ac-151">**DO NOT DELETE** any rows in the playbook; si lo hace, las fórmulas de succión de estado no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="430ac-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="430ac-152">Preste atención a las actividades que pueden llevar más tiempo de lo planeado, como porción de números y actividades de compras.</span><span class="sxs-lookup"><span data-stu-id="430ac-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="430ac-153">Estas actividades pueden afectar negativamente a la escala de tiempo de implementación del sitio.</span><span class="sxs-lookup"><span data-stu-id="430ac-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="430ac-154">Asegúrese de revisar y actualizar la lista de actividades y [](./envision-steering-committee-complete-guide.md) la escala de tiempo asociada semanalmente y presentarlas en reuniones del comité de dirección para asegurarse de que las partes interesadas son conscientes del estado de cada sitio y de las posibles desviaciones de la programación de implementación.</span><span class="sxs-lookup"><span data-stu-id="430ac-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="430ac-155">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="430ac-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="430ac-156">Decida si el Playbook de habilitación del sitio es necesario para su implementación.</span><span class="sxs-lookup"><span data-stu-id="430ac-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="430ac-157">Decida quién será el responsable de personalizar el Playbook de habilitación del sitio para Microsoft Teams para cada sitio que implemente.</span><span class="sxs-lookup"><span data-stu-id="430ac-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="430ac-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="430ac-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="430ac-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Descargue el Libro de reproducción de habilitación del sitio.</a></span><span class="sxs-lookup"><span data-stu-id="430ac-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="430ac-160">Personalice el Libro de reproducción de habilitación del sitio para el primer sitio.</span><span class="sxs-lookup"><span data-stu-id="430ac-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="430ac-161">Repita el procedimiento según sea necesario para sitios adicionales.</span><span class="sxs-lookup"><span data-stu-id="430ac-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->