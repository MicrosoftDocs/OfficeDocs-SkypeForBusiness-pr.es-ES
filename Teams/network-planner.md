---
title: Use el Planificador de red para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: El administrador puede aprender a usar Network Planner para determinar los requisitos de red para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240483"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="6d0db-103">Use el Planificador de red para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d0db-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="6d0db-104">Network Planner es una nueva herramienta que está disponible en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="6d0db-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="6d0db-105">Puede encontrarla yendo a Planificador **de** red  >  **de planificación.**</span><span class="sxs-lookup"><span data-stu-id="6d0db-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="6d0db-106">En tan solo unos pocos pasos, Network Planner puede ayudarle a determinar y organizar los requisitos de red para conectar a Microsoft Teams usuarios de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="6d0db-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="6d0db-107">Cuando proporciona el uso de Teams y los detalles de la red, el Planeamiento de red calcula los requisitos de red para implementar Teams y voz en la nube en las ubicaciones físicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="6d0db-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Captura de pantalla de Planificador de red](media/network-planner.png)

<span data-ttu-id="6d0db-109">El planificador de red le permite:</span><span class="sxs-lookup"><span data-stu-id="6d0db-109">Network planner allows you to:</span></span>

- <span data-ttu-id="6d0db-110">Cree representaciones de su organización con sitios y personas recomendadas por Microsoft (trabajadores de oficina, trabajadores remotos y Teams de sala).</span><span class="sxs-lookup"><span data-stu-id="6d0db-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6d0db-111">Las personas recomendadas se desarrollaron basándose en datos Teams escenarios de mejor uso y patrones de uso típicos.</span><span class="sxs-lookup"><span data-stu-id="6d0db-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="6d0db-112">Sin embargo, puede crear hasta tres personas personalizadas además de las tres personas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="6d0db-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="6d0db-113">Genere informes y calcule los requisitos de ancho de banda Teams uso.</span><span class="sxs-lookup"><span data-stu-id="6d0db-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="6d0db-114">Para usar El planificador de red, debe ser administrador global, Teams administrador o Teams de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="6d0db-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="6d0db-115">Crear una persona personalizada</span><span class="sxs-lookup"><span data-stu-id="6d0db-115">Create a custom persona</span></span>

<span data-ttu-id="6d0db-116">Siga estos pasos para crear una persona personalizada:</span><span class="sxs-lookup"><span data-stu-id="6d0db-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="6d0db-117">Vaya al Planificador de red en el Microsoft Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="6d0db-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="6d0db-118">En la **pestaña Personas,** haga clic **en + Persona personalizada.**</span><span class="sxs-lookup"><span data-stu-id="6d0db-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="6d0db-119">En el **panel Nuevo carácter personalizado,** agregue un nombre y una descripción para la nueva persona.</span><span class="sxs-lookup"><span data-stu-id="6d0db-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="6d0db-120">Seleccione los permisos que usará esta persona dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="6d0db-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="6d0db-121">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="6d0db-122">Crear un plan</span><span class="sxs-lookup"><span data-stu-id="6d0db-122">Build your plan</span></span>

<span data-ttu-id="6d0db-123">Siga estos pasos para empezar a crear su plan de red:</span><span class="sxs-lookup"><span data-stu-id="6d0db-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="6d0db-124">Vaya al Planificador de red en el Microsoft Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="6d0db-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="6d0db-125">En la pestaña **Plan de** red, haga clic en Agregar un plan **de red.**</span><span class="sxs-lookup"><span data-stu-id="6d0db-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="6d0db-126">Escriba un nombre y una descripción para el plan de red.</span><span class="sxs-lookup"><span data-stu-id="6d0db-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="6d0db-127">El plan de red aparecerá en la lista de planes disponibles.</span><span class="sxs-lookup"><span data-stu-id="6d0db-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="6d0db-128">Haga clic en el nombre del plan para seleccionar el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="6d0db-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="6d0db-129">Agregue sitios para crear una representación de la configuración de red de su organización.</span><span class="sxs-lookup"><span data-stu-id="6d0db-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="6d0db-130">Según la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina u otra cosa.</span><span class="sxs-lookup"><span data-stu-id="6d0db-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="6d0db-131">Es posible que los sitios estén conectados mediante una WAN para permitir el uso compartido de conexiones de Internet y/o RTC.</span><span class="sxs-lookup"><span data-stu-id="6d0db-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="6d0db-132">Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o RTC.</span><span class="sxs-lookup"><span data-stu-id="6d0db-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="6d0db-133">Para crear un sitio:</span><span class="sxs-lookup"><span data-stu-id="6d0db-133">To create a site:</span></span>

    1. <span data-ttu-id="6d0db-134">Agregue un nombre y una descripción para el sitio.</span><span class="sxs-lookup"><span data-stu-id="6d0db-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="6d0db-135">En **Configuración de red,** agregue el número de usuarios de red en ese sitio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="6d0db-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="6d0db-136">Agregar detalles de red: capacidad WAN habilitada, salida de Internet **(local** o **remota)** y salida RTC (ninguna, local o remota).</span><span class="sxs-lookup"><span data-stu-id="6d0db-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="6d0db-137">Debe agregar números de wan e capacidad de Internet para ver recomendaciones específicas de ancho de banda al generar un informe.</span><span class="sxs-lookup"><span data-stu-id="6d0db-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="6d0db-138">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="6d0db-139">Crear un informe</span><span class="sxs-lookup"><span data-stu-id="6d0db-139">Create a report</span></span>

<span data-ttu-id="6d0db-140">Después de agregar todos los sitios, puede crear un informe, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="6d0db-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="6d0db-141">En la **pestaña Informes,** haga clic **en Iniciar un informe.**</span><span class="sxs-lookup"><span data-stu-id="6d0db-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="6d0db-142">Para cada sitio que cree, distribuya el número de usuarios entre las personas disponibles.</span><span class="sxs-lookup"><span data-stu-id="6d0db-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="6d0db-143">Si usa las personas recomendadas por Microsoft, el número se distribuirá automáticamente (80% trabajador de oficina y 20 % trabajador remoto).</span><span class="sxs-lookup"><span data-stu-id="6d0db-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="6d0db-144">Después de completar la distribución, haga clic **en Generar informe.**</span><span class="sxs-lookup"><span data-stu-id="6d0db-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="6d0db-145">El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:</span><span class="sxs-lookup"><span data-stu-id="6d0db-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="6d0db-146">Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.</span><span class="sxs-lookup"><span data-stu-id="6d0db-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="6d0db-147">Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="6d0db-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="6d0db-148">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d0db-148">Click **Save**.</span></span> <span data-ttu-id="6d0db-149">El informe estará disponible en la lista de informes para su visualización posterior.</span><span class="sxs-lookup"><span data-stu-id="6d0db-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="6d0db-150">Ejemplo ficticio</span><span class="sxs-lookup"><span data-stu-id="6d0db-150">Example scenario</span></span>

<span data-ttu-id="6d0db-151">Para ver un ejemplo de cómo usar el planificador de red para configurar un plan de red y generar un informe con estos pasos, descargue el planificador de [red How-To PowerPoint presentación](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).</span><span class="sxs-lookup"><span data-stu-id="6d0db-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
