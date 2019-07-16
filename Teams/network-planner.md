---
title: Usar el planificador de red para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Aprenda a usar el planificador de redes para determinar los requisitos de red para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c05aa9cba7305b755d4e9290467c92cf71244095
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701570"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="b0d58-103">Usar el planificador de red para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0d58-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="b0d58-104">Bienvenido al organizador de la red.</span><span class="sxs-lookup"><span data-stu-id="b0d58-104">Welcome to the Network Planner.</span></span> <span data-ttu-id="b0d58-105">En pocos pasos, el planificador de redes puede ayudarle a determinar y organizar los requisitos de red para conectar los usuarios de Microsoft Teams en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="b0d58-105">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="b0d58-106">Cuando proporciona los detalles de red y el uso de Teams, Network Planner calcula los requisitos de red para implementar equipos y voz en la nube en las ubicaciones físicas de la organización.</span><span class="sxs-lookup"><span data-stu-id="b0d58-106">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Captura de pantalla de Network Planner](media/network-planner.png)

<span data-ttu-id="b0d58-108">Planificador de redes le permite:</span><span class="sxs-lookup"><span data-stu-id="b0d58-108">Network Planner allows you to:</span></span>

- <span data-ttu-id="b0d58-109">Cree representaciones de su organización con sitios y personas recomendadas de Microsoft (trabajadores de oficina, trabajadores remotos y sistema de sala de equipos).</span><span class="sxs-lookup"><span data-stu-id="b0d58-109">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0d58-110">Las personas recomendadas se desarrollaron en función de los datos de los escenarios de mejor uso de Teams y los patrones de uso típicos.</span><span class="sxs-lookup"><span data-stu-id="b0d58-110">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="b0d58-111">Sin embargo, puede crear hasta tres roles personalizados además de los tres roles recomendados.</span><span class="sxs-lookup"><span data-stu-id="b0d58-111">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="b0d58-112">Generar informes y calcular los requisitos de ancho de banda para el uso de equipos.</span><span class="sxs-lookup"><span data-stu-id="b0d58-112">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="b0d58-113">Para usar el planificador de redes, debe ser administrador global, administrador de servicios de equipo o administrador de comunicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="b0d58-113">To use Network Planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="b0d58-114">Crear un rol personalizado</span><span class="sxs-lookup"><span data-stu-id="b0d58-114">Create a custom persona</span></span>

<span data-ttu-id="b0d58-115">Siga estos pasos para crear un rol personalizado:</span><span class="sxs-lookup"><span data-stu-id="b0d58-115">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="b0d58-116">Vaya a organizador de la red en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0d58-116">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="b0d58-117">En la pestaña **personas** , haga clic en **personalizar rol**.</span><span class="sxs-lookup"><span data-stu-id="b0d58-117">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="b0d58-118">En el **nuevo panel personal personalizado** , agregue un nombre y una descripción para el nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="b0d58-118">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="b0d58-119">Seleccione los permisos que este rol usará dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="b0d58-119">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="b0d58-120">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b0d58-120">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="b0d58-121">Crear su plan</span><span class="sxs-lookup"><span data-stu-id="b0d58-121">Build your plan</span></span>

<span data-ttu-id="b0d58-122">Siga estos pasos para empezar a crear su plan de red:</span><span class="sxs-lookup"><span data-stu-id="b0d58-122">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="b0d58-123">Vaya a organizador de la red en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0d58-123">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="b0d58-124">En la pestaña **plan de red** , haga clic en **Agregar un plan de red**.</span><span class="sxs-lookup"><span data-stu-id="b0d58-124">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="b0d58-125">Escriba un nombre y una descripción para el plan de red.</span><span class="sxs-lookup"><span data-stu-id="b0d58-125">Enter a name and description for your network plan.</span></span> <span data-ttu-id="b0d58-126">El plan de red aparecerá en la lista de planes disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0d58-126">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="b0d58-127">Haga clic en el nombre del plan para seleccionar el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="b0d58-127">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="b0d58-128">Agregue sitios para crear una representación de la configuración de red de su organización.</span><span class="sxs-lookup"><span data-stu-id="b0d58-128">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="b0d58-129">En función de la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina u otra cosa.</span><span class="sxs-lookup"><span data-stu-id="b0d58-129">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="b0d58-130">Los sitios pueden estar conectados mediante una WAN para permitir el uso compartido de conexiones de Internet o RTC.</span><span class="sxs-lookup"><span data-stu-id="b0d58-130">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="b0d58-131">Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o a la RTC.</span><span class="sxs-lookup"><span data-stu-id="b0d58-131">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="b0d58-132">Para crear un sitio:</span><span class="sxs-lookup"><span data-stu-id="b0d58-132">To create a site:</span></span>

    1. <span data-ttu-id="b0d58-133">Agregue un nombre y una descripción para el sitio.</span><span class="sxs-lookup"><span data-stu-id="b0d58-133">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="b0d58-134">En **configuración de red**, agregue el número de usuarios de red en ese sitio (obligatorio).</span><span class="sxs-lookup"><span data-stu-id="b0d58-134">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="b0d58-135">Agregar detalles de red: habilitada para WAN, capacidad de WAN, salida de Internet (**local** o **remota**) y salida de RTC (ninguna, local o remota).</span><span class="sxs-lookup"><span data-stu-id="b0d58-135">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="b0d58-136">Debe agregar números de capacidad de WAN y de Internet para ver recomendaciones específicas de ancho de banda cuando genera un informe.</span><span class="sxs-lookup"><span data-stu-id="b0d58-136">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="b0d58-137">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b0d58-137">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="b0d58-138">Crear un informe</span><span class="sxs-lookup"><span data-stu-id="b0d58-138">Create a report</span></span>

<span data-ttu-id="b0d58-139">Después de agregar todos los sitios, puede crear un informe de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="b0d58-139">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="b0d58-140">En la pestaña **informes** , haga clic en **iniciar un informe**.</span><span class="sxs-lookup"><span data-stu-id="b0d58-140">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="b0d58-141">Para cada sitio que cree, distribuya el número de usuarios en las personas disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0d58-141">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="b0d58-142">Si usa las personas recomendadas de Microsoft, el número se distribuirá automáticamente (80% de trabajo de Office y 20% de trabajo remoto).</span><span class="sxs-lookup"><span data-stu-id="b0d58-142">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="b0d58-143">Una vez completada la distribución, haga clic en **generar informe**.</span><span class="sxs-lookup"><span data-stu-id="b0d58-143">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="b0d58-144">El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:</span><span class="sxs-lookup"><span data-stu-id="b0d58-144">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="b0d58-145">Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.</span><span class="sxs-lookup"><span data-stu-id="b0d58-145">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="b0d58-146">Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="b0d58-146">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="b0d58-147">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b0d58-147">Click **Save**.</span></span> <span data-ttu-id="b0d58-148">El informe estará disponible en la lista de informes para verlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="b0d58-148">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="b0d58-149">Escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0d58-149">Example scenario</span></span>

<span data-ttu-id="b0d58-150">Para obtener un ejemplo de cómo usar el planificador de redes para configurar un plan de red y generar un informe siguiendo estos pasos, descargue el [paquete de PowerPoint "procedimientos de Network Planner"](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).</span><span class="sxs-lookup"><span data-stu-id="b0d58-150">For an example of how to use the Network Planner to set up a network plan and generate a report using these steps, download the [Network Planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
