---
title: 'Lync Server 2013: Inicio del proceso de planeación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e5bea18abe11a6d88e07e5f8a1cd4da3d0eca0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="286bd-102">Inicio del proceso de planeación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="286bd-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="286bd-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="286bd-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="286bd-104">Aunque parece intimidar a la planeación de una implementación local de comunicaciones unificadas, Lync Server ofrece dos herramientas valiosas que le ayudarán a:</span><span class="sxs-lookup"><span data-stu-id="286bd-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="286bd-105">**La herramienta de planeación** es un asistente que presenta una serie de preguntas sobre la organización, las características de Lync Server que desea habilitar y las necesidades de planeación de la capacidad.</span><span class="sxs-lookup"><span data-stu-id="286bd-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="286bd-106">A continuación, se crea una topología de implementación recomendada en función de las respuestas y se genera un diagrama de Microsoft Visio de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="286bd-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="286bd-107">El **generador de topologías** es un componente de instalación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="286bd-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="286bd-108">Puede usar el generador de topologías para crear, ajustar y publicar la topología planeada.</span><span class="sxs-lookup"><span data-stu-id="286bd-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="286bd-109">Asimismo, valida la topología antes de comenzar a realizar las instalaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="286bd-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="286bd-110">Al instalar Lync Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación, y el programa de instalación implementa el servidor tal como se indicó en la topología.</span><span class="sxs-lookup"><span data-stu-id="286bd-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="286bd-111">Herramienta de planeación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="286bd-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="286bd-112">La herramienta de planeación toma sus respuestas a las preguntas de la herramienta y genera una topología en función de las instrucciones y los procedimientos recomendados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="286bd-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="286bd-113">También proporciona varias vistas de una implementación en función de las respuestas.</span><span class="sxs-lookup"><span data-stu-id="286bd-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="286bd-114">Muestra una vista global de todos los sitios (es decir, tanto sitios centrales como sucursales) y vistas detalladas que muestran los servidores y otros componentes en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="286bd-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="286bd-115">La ejecución de la herramienta de planeación no le compromete a ninguna implementación específica ni inicia ningún proceso.</span><span class="sxs-lookup"><span data-stu-id="286bd-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="286bd-116">De hecho, ejecutar la herramienta de planeación incluso antes de tener en cuenta un plan de empresa puede ser una forma muy instructiva de comprender los tipos de preguntas que debe considerar en el proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="286bd-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="286bd-117">Puede ejecutar la herramienta de planeación varias veces, responder a las preguntas de manera diferente y comparar los resultados.</span><span class="sxs-lookup"><span data-stu-id="286bd-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="286bd-118">Si tiene un diseño con el que está satisfecho principalmente pero que necesita realizar cambios en, puede volver a la herramienta de planeación, cargar el diseño y realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="286bd-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="286bd-119">La herramienta de planeación tarda unos 15 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="286bd-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="286bd-120">Cuando esté satisfecho, puede usar la herramienta de planeación para crear un diagrama de la implementación planeada.</span><span class="sxs-lookup"><span data-stu-id="286bd-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="286bd-121">Puede usar este diagrama mientras crea la implementación en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="286bd-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="286bd-122">La herramienta de planeación que se incluye con esta versión de Lync Server 2013 es una versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="286bd-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="286bd-123">Tenga en cuenta que los números de planeación de la capacidad de la herramienta de planeación son preliminares y no se admiten en la versión final.</span><span class="sxs-lookup"><span data-stu-id="286bd-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="286bd-124">Generador de topologías de Lync Server</span><span class="sxs-lookup"><span data-stu-id="286bd-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="286bd-125">Una vez que haya decidido el plan de implementación, use el generador de topologías para empezar a implementar.</span><span class="sxs-lookup"><span data-stu-id="286bd-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="286bd-126">Cuando termine, use el generador de topologías para validar la topología y, si es así, puede publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="286bd-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="286bd-127">Al publicar la topología, Lync Server coloca la topología en el almacén de administración central, que se crea en este momento si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="286bd-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="286bd-128">Al instalar Lync Server en cada servidor de la implementación, el servidor lee la topología del almacén de administración central y se instala para ajustarse a su rol en la implementación.</span><span class="sxs-lookup"><span data-stu-id="286bd-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="286bd-129">Como alternativa, si está familiarizado con Lync Server y necesita menos instrucciones preceptivas, puede omitir la herramienta de planeación y usar los asistentes en el generador de topologías para el diseño inicial de la implementación y también para los pasos de validación y publicación.</span><span class="sxs-lookup"><span data-stu-id="286bd-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="286bd-130">Es un paso necesario usar el generador de topologías para planear y publicar una topología.</span><span class="sxs-lookup"><span data-stu-id="286bd-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="286bd-131">No se puede omitir el generador de topología e instalar Lync Server individualmente en los servidores de la implementación.</span><span class="sxs-lookup"><span data-stu-id="286bd-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="286bd-132">Cada servidor debe leer la topología desde una topología validada y publicada en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="286bd-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="286bd-133">Proceso de planeación de alto nivel</span><span class="sxs-lookup"><span data-stu-id="286bd-133">High-Level Planning Process</span></span>

<span data-ttu-id="286bd-134">Se recomienda el siguiente proceso general para usar la documentación y la herramienta de planeación para planear la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="286bd-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="286bd-135">Si está familiarizado con las versiones anteriores de Lync Server, lea [nuevas características en Lync server 2013](lync-server-2013-new-features.md) para familiarizarse con las nuevas características y requisitos en lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="286bd-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="286bd-136">Lea los otros temas de esta sección de la documentación: [aspectos básicos de las topologías que debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md), [decisiones iniciales de planeación para](lync-server-2013-initial-planning-decisions.md)Lync Server 2013 y [clientes para Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="286bd-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="286bd-137">Tenga en cuenta las decisiones de planeación representadas en las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="286bd-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="286bd-138">Ahora que está más familiarizado con las características de Lync Server y los tipos de preguntas que deben responderse, ejecute la herramienta de planeación y vea la topología resultante y sus detalles.</span><span class="sxs-lookup"><span data-stu-id="286bd-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="286bd-139">Asegúrese de que la topología cumple los requisitos únicos para su organización.</span><span class="sxs-lookup"><span data-stu-id="286bd-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="286bd-140">Si hay cargas de trabajo o características específicas en las que está interesado o necesita aprender sobre, lea las secciones correspondientes de [Planning para Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="286bd-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="286bd-141">Vuelva a ejecutar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="286bd-141">Run the Planning Tool again.</span></span> <span data-ttu-id="286bd-142">Puede comenzar con la implementación que ha creado en el paso 3 y modificar los resultados o comenzar de nuevo desde el principio.</span><span class="sxs-lookup"><span data-stu-id="286bd-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="286bd-143">Si es necesario, ejecute la herramienta de planeación una tercera vez y repita hasta que quede satisfecho con el resultado.</span><span class="sxs-lookup"><span data-stu-id="286bd-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="286bd-144">Cuando haya finalizado el plan de topología, use la herramienta de planeación para crear e imprimir un diagrama de Visio de la topología.</span><span class="sxs-lookup"><span data-stu-id="286bd-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="286bd-145">Puede usar esta copia impresa mientras trabaja con Topology Builder para introducir su topología.</span><span class="sxs-lookup"><span data-stu-id="286bd-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="286bd-146">Antes de comenzar con la implementación, lea la determinación de los [requisitos del sistema para Lync server 2013](lync-server-2013-determining-your-system-requirements.md) y la determinación de los [requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para familiarizarse con los requisitos previos y la infraestructura necesaria para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="286bd-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="286bd-147">Además, asegúrese de que ha leído todas las secciones de [planeación de Lync Server 2013](lync-server-2013-planning.md) que se aplican a las cargas de trabajo y las características que tiene previsto implementar.</span><span class="sxs-lookup"><span data-stu-id="286bd-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="286bd-148">Migración desde versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="286bd-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="286bd-149">Si va a migrar a Lync Server desde una versión anterior, consulte la documentación de la [migración](migration.md) para obtener instrucciones específicas para la migración y la implementación.</span><span class="sxs-lookup"><span data-stu-id="286bd-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

