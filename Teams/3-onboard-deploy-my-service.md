---
title: Implementar el servicio de voz de nube de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Descargue la Guía de activación de sitio para planear la implementación de equipos y acelerar y optimizar la adopción de usuario, la percepción de la calidad y la satisfacción.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ddccd9c52e25ae9d0069119641aa7e8a8077d56
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="deploy-my-service"></a><span data-ttu-id="15370-103">Implementar mi servicio</span><span class="sxs-lookup"><span data-stu-id="15370-103">Deploy my service</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="15370-104">Guía de habilitación del sitio para cargas de trabajo de voz de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15370-104">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="15370-105">Utilice esta guía para ayudar a su organización a planear y ejecutar la distribución de las características de voz de Microsoft Teams en el sitio por sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-105">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="15370-106">Incluye actividades necesarios, recomendada escalas de tiempo y vínculos a las instrucciones correspondientes para cada actividad, esta guía cubre Guía de end-to-end para ayudar a garantizar una implementación satisfactoria de voz de equipos para un sitio determinado, centrándose en factores que son importantes para el usuario.</span><span class="sxs-lookup"><span data-stu-id="15370-106">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="15370-107">Al terminar las actividades de esta guía, su organización puede:</span><span class="sxs-lookup"><span data-stu-id="15370-107">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="15370-108">Efectivamente, planear y programar la implementación de equipos.</span><span class="sxs-lookup"><span data-stu-id="15370-108">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="15370-109">Acelerar y optimizar la adopción de usuario.</span><span class="sxs-lookup"><span data-stu-id="15370-109">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="15370-110">Reducir las necesidades de soporte y aumentar la satisfacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="15370-110">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="15370-111">En este artículo y la guía asociada no se pretenden describir cada paso de configuración técnica necesaria para la activación del servicio o proporcionar el tono de marcado a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="15370-111">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="15370-112">En su lugar, se concentran en las actividades y tareas que se recomienda a los usuarios a bordo fácilmente y pedirles que comienzan a consumir cargas de trabajo de equipos voz a través de una transición suave y rápida con una velocidad alta de adopción, mientras minimiza los requerimientos de soporte.</span><span class="sxs-lookup"><span data-stu-id="15370-112">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="15370-113">Para obtener orientación técnica sobre cómo mejorar la configuración de su entorno para la voz de los equipos, vea Resumir listas de comprobación para [configurar las cargas de trabajo de equipos voz](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [capacidades de equipos](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [redes de equipos](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)y [Habilitar Office 365 ](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span><span class="sxs-lookup"><span data-stu-id="15370-113">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [Teams core capabilities](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [networking for Teams](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking), and [enabling Office 365](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="15370-114">Áreas de enfoque de la Guía</span><span class="sxs-lookup"><span data-stu-id="15370-114">Playbook focus areas</span></span>

<span data-ttu-id="15370-115">El enfoque de la guía es tratar los factores que influyen en la percepción del usuario de una implementación de voz de los equipos.</span><span class="sxs-lookup"><span data-stu-id="15370-115">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="15370-116">Las actividades y tareas se agrupan en las siguientes áreas de focalización:</span><span class="sxs-lookup"><span data-stu-id="15370-116">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="15370-117">Validación de la preparación del servicio</span><span class="sxs-lookup"><span data-stu-id="15370-117">Validation of service readiness</span></span>

-   <span data-ttu-id="15370-118">Habilitación de usuario</span><span class="sxs-lookup"><span data-stu-id="15370-118">User enablement</span></span>

-   <span data-ttu-id="15370-119">Puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="15370-119">Endpoints</span></span>

-   <span data-ttu-id="15370-120">Calidad y uso</span><span class="sxs-lookup"><span data-stu-id="15370-120">Usage and quality</span></span>

-   <span data-ttu-id="15370-121">Adopción</span><span class="sxs-lookup"><span data-stu-id="15370-121">Adoption</span></span>

<span data-ttu-id="15370-122">El [Sitio de habilitación de guía de voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) es un libro de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="15370-122">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="15370-123">Cada una de estas áreas de cinco focalización es una hoja independiente del libro y cada actividad y la tarea de despliegue se agrupan en una de estas hojas.</span><span class="sxs-lookup"><span data-stu-id="15370-123">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="15370-124">![Captura de pantalla de la guía] (media/deploy-my-service-image1.png "Captura de pantalla de la guía")</span><span class="sxs-lookup"><span data-stu-id="15370-124">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="15370-125">Creará una instancia independiente de la guía para cada sitio en el ámbito de la implementación de equipos.</span><span class="sxs-lookup"><span data-stu-id="15370-125">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="15370-126">Cómo utilizar la Guía</span><span class="sxs-lookup"><span data-stu-id="15370-126">How to use the playbook</span></span>

<span data-ttu-id="15370-127">Independientemente del tamaño y complejidad de la ubicación, la habilitación de cada sitio requiere planear las tareas y actividades lo bastante pronto y ejecutarlas en el orden óptimo: antes, durante y después de la implantación real del servicio.</span><span class="sxs-lookup"><span data-stu-id="15370-127">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="15370-128">Recomendamos que siga estos pasos como planear y ejecutar su propio viaje a voz de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="15370-128">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="15370-129">Descargue la [Guía de activación de sitio para voz (Guía)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para equipos de Microsoft Voice.</span><span class="sxs-lookup"><span data-stu-id="15370-129">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="15370-130">Crear una copia independiente de la guía para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-130">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="15370-131">En la ficha de la hoja denominada **Guía para {SiteName código}**, reemplace **{SiteName código}** con el nombre de sitio correspondiente o el código de sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-131">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="15370-132">Escriba **el nombre del sitio, código del sitio**y la **fecha de inicio planeada**, tal como se ilustra a continuación.</span><span class="sxs-lookup"><span data-stu-id="15370-132">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="15370-133">Éste es un paso crítico, porque se ajusta los plazos recomendados para todas las actividades en la guía.</span><span class="sxs-lookup"><span data-stu-id="15370-133">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="15370-134">![Ejemplo con nombre del sitio de Nueva York, NY01, el código de sitio y fecha de inicio planeada de 20-Mar-18] (media/deploy-my-service-image2.png "Ejemplo con nombre del sitio de Nueva York, NY01, el código de sitio y fecha de inicio planeada de 20-Mar-18")</span><span class="sxs-lookup"><span data-stu-id="15370-134">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="15370-135">Revise cada actividad, tome las acciones necesarias y actualizar el estado a medida que vaya a través de la línea de tiempo.</span><span class="sxs-lookup"><span data-stu-id="15370-135">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="15370-136">Estado se representa gráficamente, tal como se describe a continuación:</span><span class="sxs-lookup"><span data-stu-id="15370-136">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="15370-137">![Marca de verificación verde](media/deploy-my-service-image3.png) **Sí o no aplicable (verde):** se ha completado la actividad, o no es aplicable para este sitio y no es necesario realizar ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="15370-137">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="15370-138">![Signo de exclamación amarillo](media/deploy-my-service-image4.png) **la actividad no se completa aún (amarillo):** la actividad no ha finalizado todavía y debe actualizarse a sí o No en su programación.</span><span class="sxs-lookup"><span data-stu-id="15370-138">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="15370-139">![X roja](media/deploy-my-service-image5.png) **sin (rojo):** no se puede completar debido a un problema de la actividad y se llevarán a la reunión de estado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="15370-139">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="15370-140">Dentro de cada sección se resume el estado y el título de sección tenga con uno de estos indicadores de estado.</span><span class="sxs-lookup"><span data-stu-id="15370-140">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="15370-141">**Estado semanal** también se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="15370-141">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="15370-142">![Captura de pantalla de la semanal estado resúmenes de la guía] (media/deploy-my-service-image6.png "Captura de pantalla de la semanal estado resúmenes de la guía")</span><span class="sxs-lookup"><span data-stu-id="15370-142">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="15370-143">Repita los pasos anteriores para todas las ubicaciones que usted tiene.</span><span class="sxs-lookup"><span data-stu-id="15370-143">Repeat the steps above for all the locations you have.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="15370-144">Algunos pasos no sería aplicables a todos los sitios y ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="15370-144">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="15370-145">Si una actividad específica no es relevante para un sitio, debe seleccionar **no es aplicable** para esta actividad.</span><span class="sxs-lookup"><span data-stu-id="15370-145">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="15370-146">**No elimine** cualquiera de las filas en la Guía; Si lo hace, no funcionarán las fórmulas de resumen de estado.</span><span class="sxs-lookup"><span data-stu-id="15370-146">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="15370-147">Preste atención a las actividades que podrían tardar más tiempo del planeado, como número de traslado y las actividades de compras.</span><span class="sxs-lookup"><span data-stu-id="15370-147">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="15370-148">Estas actividades pueden afectar negativamente a la escala de tiempo de implementación del sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-148">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="15370-149">Asegúrese de revisar y actualizar la lista de actividades y la escala de tiempo asociado semanalmente y presentarlos en las [reuniones del Comité de dirección](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para asegurarse de que los interesados conozcan el estado de cada sitio y cualquier desviación del plan de implementación de.</span><span class="sxs-lookup"><span data-stu-id="15370-149">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="15370-150">Puntos de decisión</span><span class="sxs-lookup"><span data-stu-id="15370-150">Decision points</span></span></td><td><ul><li><span data-ttu-id="15370-151">Decidir si es necesaria para la implementación de la Guía de habilitación del sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-151">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="15370-152">Decidir quién será responsable de la personalización de la Guía de habilitación del sitio para Microsoft Teams para cada sitio que va a implementar.</span><span class="sxs-lookup"><span data-stu-id="15370-152">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you'll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="15370-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="15370-153">Next steps</span></span></td><td><ul><li><span data-ttu-id="15370-154">Descargue la Guía de habilitación del sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-154">Download the Site Enablement Playbook.</span></span></li><li><span data-ttu-id="15370-155">Personalizar la Guía de habilitación del sitio para su primer sitio.</span><span class="sxs-lookup"><span data-stu-id="15370-155">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="15370-156">Repita según sea necesario para otros sitios.</span><span class="sxs-lookup"><span data-stu-id="15370-156">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->