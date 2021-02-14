---
title: Usar el organizador de red para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: El administrador puede obtener información sobre cómo usar el planificador de red para determinar los requisitos de red para Microsoft Teams.
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
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611804"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="d6b89-103">Usar el organizador de red para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6b89-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="d6b89-104">Network Planner es una nueva herramienta que está disponible en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="d6b89-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="d6b89-105">Puede encontrarla yendo al Planificador **de red de**  >  **planificación.**</span><span class="sxs-lookup"><span data-stu-id="d6b89-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="d6b89-106">En solo unos pasos, el organizador de red puede ayudarle a determinar y organizar los requisitos de red para conectar los usuarios de Microsoft Teams en toda su organización.</span><span class="sxs-lookup"><span data-stu-id="d6b89-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="d6b89-107">Cuando proporciona los detalles de la red y el uso de Teams, el planificador de red calcula los requisitos de red para implementar Teams y la voz en la nube en las ubicaciones físicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="d6b89-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Captura de pantalla del organizador de red](media/network-planner.png)

<span data-ttu-id="d6b89-109">El planificador de red le permite:</span><span class="sxs-lookup"><span data-stu-id="d6b89-109">Network planner allows you to:</span></span>

- <span data-ttu-id="d6b89-110">Cree representaciones de su organización con sitios y personas recomendadas por Microsoft (trabajadores de oficina, trabajadores remotos y sistema de sala de Teams).</span><span class="sxs-lookup"><span data-stu-id="d6b89-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6b89-111">Los roles recomendados se desarrollaron basándose en los datos de los escenarios de mejor uso de Teams y en los patrones de uso típicos.</span><span class="sxs-lookup"><span data-stu-id="d6b89-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="d6b89-112">Sin embargo, puede crear hasta tres personas personalizadas además de las tres personas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="d6b89-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="d6b89-113">Genere informes y calcule requisitos de ancho de banda para el uso de Teams.</span><span class="sxs-lookup"><span data-stu-id="d6b89-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="d6b89-114">Para usar el planificador de red, debe ser administrador global, administrador de servicios de Teams o administrador de comunicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="d6b89-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="d6b89-115">Crear un rol personalizado</span><span class="sxs-lookup"><span data-stu-id="d6b89-115">Create a custom persona</span></span>

<span data-ttu-id="d6b89-116">Siga estos pasos para crear un rol personalizado:</span><span class="sxs-lookup"><span data-stu-id="d6b89-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="d6b89-117">Vaya al Organizador de red en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6b89-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="d6b89-118">En la **pestaña Personas,** haga clic **en + Rol personalizado.**</span><span class="sxs-lookup"><span data-stu-id="d6b89-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="d6b89-119">En el **panel Nuevo rol personalizado,** agregue un nombre y una descripción para el nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="d6b89-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="d6b89-120">Seleccione los permisos que usará esta persona dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="d6b89-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="d6b89-121">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6b89-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="d6b89-122">Cree su plan</span><span class="sxs-lookup"><span data-stu-id="d6b89-122">Build your plan</span></span>

<span data-ttu-id="d6b89-123">Siga estos pasos para comenzar a crear su plan de red:</span><span class="sxs-lookup"><span data-stu-id="d6b89-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="d6b89-124">Vaya al Organizador de red en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d6b89-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="d6b89-125">En la pestaña **Plan de** red, haga clic en Agregar un plan **de red.**</span><span class="sxs-lookup"><span data-stu-id="d6b89-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="d6b89-126">Escriba un nombre y una descripción para su plan de red.</span><span class="sxs-lookup"><span data-stu-id="d6b89-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="d6b89-127">El plan de red aparecerá en la lista de planes disponibles.</span><span class="sxs-lookup"><span data-stu-id="d6b89-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="d6b89-128">Haga clic en el nombre del plan para seleccionar el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="d6b89-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="d6b89-129">Agregue sitios para crear una representación de la configuración de red de su organización.</span><span class="sxs-lookup"><span data-stu-id="d6b89-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="d6b89-130">Según la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina o cualquier otra cosa.</span><span class="sxs-lookup"><span data-stu-id="d6b89-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="d6b89-131">Es posible que los sitios estén conectados mediante una WAN para permitir el uso compartido de conexiones de Internet o RTC.</span><span class="sxs-lookup"><span data-stu-id="d6b89-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="d6b89-132">Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o RTC.</span><span class="sxs-lookup"><span data-stu-id="d6b89-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="d6b89-133">Para crear un sitio:</span><span class="sxs-lookup"><span data-stu-id="d6b89-133">To create a site:</span></span>

    1. <span data-ttu-id="d6b89-134">Agregue un nombre y una descripción para el sitio.</span><span class="sxs-lookup"><span data-stu-id="d6b89-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="d6b89-135">En **Configuración de** red, agregue el número de usuarios de red en ese sitio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="d6b89-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="d6b89-136">Agregue detalles de red: habilitada para WAN, capacidad de WAN, salida de Internet **(local** o **remota)** y salida RTC (ninguna, local o remota).</span><span class="sxs-lookup"><span data-stu-id="d6b89-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="d6b89-137">Debe agregar wan y números de capacidad de Internet para ver recomendaciones específicas de ancho de banda al generar un informe.</span><span class="sxs-lookup"><span data-stu-id="d6b89-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="d6b89-138">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6b89-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="d6b89-139">Crear un informe</span><span class="sxs-lookup"><span data-stu-id="d6b89-139">Create a report</span></span>

<span data-ttu-id="d6b89-140">Después de agregar todos los sitios, puede crear un informe del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6b89-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="d6b89-141">En la **pestaña Informes,** haga clic **en Iniciar un informe.**</span><span class="sxs-lookup"><span data-stu-id="d6b89-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="d6b89-142">Para cada sitio que cree, distribuya el número de usuarios entre las personas disponibles.</span><span class="sxs-lookup"><span data-stu-id="d6b89-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="d6b89-143">Si usa los roles recomendados por Microsoft, el número se distribuirá automáticamente (el 80 % de trabajador de oficina y el 20 % de trabajador remoto).</span><span class="sxs-lookup"><span data-stu-id="d6b89-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="d6b89-144">Después de completar la distribución, haga clic **en Generar informe.**</span><span class="sxs-lookup"><span data-stu-id="d6b89-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="d6b89-145">El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:</span><span class="sxs-lookup"><span data-stu-id="d6b89-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="d6b89-146">Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.</span><span class="sxs-lookup"><span data-stu-id="d6b89-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="d6b89-147">Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="d6b89-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="d6b89-148">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d6b89-148">Click **Save**.</span></span> <span data-ttu-id="d6b89-149">El informe estará disponible en la lista de informes para verlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="d6b89-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="d6b89-150">Escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6b89-150">Example scenario</span></span>

<span data-ttu-id="d6b89-151">Para obtener un ejemplo de cómo usar el planificador de red para configurar un plan de red y generar un informe con estos pasos, descargue el planificador de red How-To conjunto de diapositivas de [PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).</span><span class="sxs-lookup"><span data-stu-id="d6b89-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
