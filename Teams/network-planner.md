---
title: Usar el planificador de red para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Aprenda a usar el planificador de redes para determinar los requisitos de red para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2920f33417fa640b99a408441be6d3f49c3f078d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573370"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="6c25e-103">Usar el planificador de red para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c25e-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="6c25e-104">Planificador de redes es una herramienta nueva que está disponible en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="6c25e-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="6c25e-105">Puede encontrarla en > \*\*\*\* configuración para **toda la organización**.</span><span class="sxs-lookup"><span data-stu-id="6c25e-105">It can be found by going to **Org-wide settings** > **Network planner**.</span></span> <span data-ttu-id="6c25e-106">En pocos pasos, el planificador de redes puede ayudarle a determinar y organizar los requisitos de red para conectar los usuarios de Microsoft Teams en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="6c25e-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="6c25e-107">Cuando proporciona los detalles de red y el uso de Teams, Network Planner calcula los requisitos de red para implementar equipos y voz en la nube en las ubicaciones físicas de la organización.</span><span class="sxs-lookup"><span data-stu-id="6c25e-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Captura de pantalla de Network Planner](media/network-planner.png)

<span data-ttu-id="6c25e-109">Planificador de redes le permite:</span><span class="sxs-lookup"><span data-stu-id="6c25e-109">Network Planner allows you to:</span></span>

- <span data-ttu-id="6c25e-110">Cree representaciones de su organización con sitios y personas recomendadas de Microsoft (trabajadores de oficina, trabajadores remotos y sistema de sala de equipos).</span><span class="sxs-lookup"><span data-stu-id="6c25e-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6c25e-111">Las personas recomendadas se desarrollaron en función de los datos de los escenarios de mejor uso de Teams y los patrones de uso típicos.</span><span class="sxs-lookup"><span data-stu-id="6c25e-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="6c25e-112">Sin embargo, puede crear hasta tres roles personalizados además de los tres roles recomendados.</span><span class="sxs-lookup"><span data-stu-id="6c25e-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="6c25e-113">Generar informes y calcular los requisitos de ancho de banda para el uso de equipos.</span><span class="sxs-lookup"><span data-stu-id="6c25e-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="6c25e-114">Para usar el planificador de redes, debe ser administrador global, administrador de servicios de equipo o administrador de comunicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="6c25e-114">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="6c25e-115">Crear un rol personalizado</span><span class="sxs-lookup"><span data-stu-id="6c25e-115">Create a custom persona</span></span>

<span data-ttu-id="6c25e-116">Siga estos pasos para crear un rol personalizado:</span><span class="sxs-lookup"><span data-stu-id="6c25e-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="6c25e-117">Vaya a organizador de la red en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6c25e-117">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="6c25e-118">En la pestaña **personas** , haga clic en **personalizar rol**.</span><span class="sxs-lookup"><span data-stu-id="6c25e-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="6c25e-119">En el **nuevo panel personal personalizado** , agregue un nombre y una descripción para el nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="6c25e-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="6c25e-120">Seleccione los permisos que este rol usará dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="6c25e-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="6c25e-121">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="6c25e-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="6c25e-122">Crear su plan</span><span class="sxs-lookup"><span data-stu-id="6c25e-122">Build your plan</span></span>

<span data-ttu-id="6c25e-123">Siga estos pasos para empezar a crear su plan de red:</span><span class="sxs-lookup"><span data-stu-id="6c25e-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="6c25e-124">Vaya a organizador de la red en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6c25e-124">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="6c25e-125">En la pestaña **plan de red** , haga clic en **Agregar un plan de red**.</span><span class="sxs-lookup"><span data-stu-id="6c25e-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="6c25e-126">Escriba un nombre y una descripción para el plan de red.</span><span class="sxs-lookup"><span data-stu-id="6c25e-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="6c25e-127">El plan de red aparecerá en la lista de planes disponibles.</span><span class="sxs-lookup"><span data-stu-id="6c25e-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="6c25e-128">Haga clic en el nombre del plan para seleccionar el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="6c25e-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="6c25e-129">Agregue sitios para crear una representación de la configuración de red de su organización.</span><span class="sxs-lookup"><span data-stu-id="6c25e-129">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="6c25e-130">En función de la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina u otra cosa.</span><span class="sxs-lookup"><span data-stu-id="6c25e-130">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="6c25e-131">Los sitios pueden estar conectados mediante una WAN para permitir el uso compartido de conexiones de Internet o RTC.</span><span class="sxs-lookup"><span data-stu-id="6c25e-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="6c25e-132">Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o a la RTC.</span><span class="sxs-lookup"><span data-stu-id="6c25e-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="6c25e-133">Para crear un sitio:</span><span class="sxs-lookup"><span data-stu-id="6c25e-133">To create a site:</span></span>

    1. <span data-ttu-id="6c25e-134">Agregue un nombre y una descripción para el sitio.</span><span class="sxs-lookup"><span data-stu-id="6c25e-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="6c25e-135">En **configuración de red**, agregue el número de usuarios de red en ese sitio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="6c25e-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="6c25e-136">Agregar detalles de red: habilitada para WAN, capacidad de WAN, salida de Internet (**local** o **remota**) y salida de RTC (ninguna, local o remota).</span><span class="sxs-lookup"><span data-stu-id="6c25e-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="6c25e-137">Debe agregar números de capacidad de WAN y de Internet para ver recomendaciones específicas de ancho de banda cuando genera un informe.</span><span class="sxs-lookup"><span data-stu-id="6c25e-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="6c25e-138">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="6c25e-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="6c25e-139">Crear un informe</span><span class="sxs-lookup"><span data-stu-id="6c25e-139">Create a report</span></span>

<span data-ttu-id="6c25e-140">Después de agregar todos los sitios, puede crear un informe de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="6c25e-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="6c25e-141">En la pestaña **informes** , haga clic en **iniciar un informe**.</span><span class="sxs-lookup"><span data-stu-id="6c25e-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="6c25e-142">Para cada sitio que cree, distribuya el número de usuarios en las personas disponibles.</span><span class="sxs-lookup"><span data-stu-id="6c25e-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="6c25e-143">Si usa las personas recomendadas de Microsoft, el número se distribuirá automáticamente (80% de trabajo de Office y 20% de trabajo remoto).</span><span class="sxs-lookup"><span data-stu-id="6c25e-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="6c25e-144">Una vez completada la distribución, haga clic en **generar informe**.</span><span class="sxs-lookup"><span data-stu-id="6c25e-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="6c25e-145">El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:</span><span class="sxs-lookup"><span data-stu-id="6c25e-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="6c25e-146">Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.</span><span class="sxs-lookup"><span data-stu-id="6c25e-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="6c25e-147">Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="6c25e-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="6c25e-148">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="6c25e-148">Click **Save**.</span></span> <span data-ttu-id="6c25e-149">El informe estará disponible en la lista de informes para verlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="6c25e-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="6c25e-150">Escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c25e-150">Example scenario</span></span>

<span data-ttu-id="6c25e-151">Para obtener un ejemplo de cómo usar el planificador de redes para configurar un plan de red y generar un informe siguiendo estos pasos, descargue el [paquete de PowerPoint "procedimientos de Network Planner"](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).</span><span class="sxs-lookup"><span data-stu-id="6c25e-151">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
