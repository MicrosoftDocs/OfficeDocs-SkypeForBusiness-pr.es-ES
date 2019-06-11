---
title: 'Lync Server 2013: Iniciar el proceso de planeación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="730d7-102">Iniciar el proceso de planeación para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730d7-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="730d7-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="730d7-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="730d7-104">Aunque la planeación de una implementación de comunicaciones unificadas locales puede intimidar, Lync Server ofrece dos valiosas herramientas para ayudarle:</span><span class="sxs-lookup"><span data-stu-id="730d7-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="730d7-105">**La herramienta de planeación** es un asistente que presenta una serie de preguntas sobre su organización, las características de Lync Server que desea habilitar y sus necesidades de planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="730d7-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="730d7-106">A continuación, crea una topología de implementación recomendada en función de sus respuestas y genera un diagrama de Microsoft Visio de esta implementación.</span><span class="sxs-lookup"><span data-stu-id="730d7-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="730d7-107">El **generador de topología** es un componente de instalación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="730d7-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="730d7-108">El generador de topología se usa para crear, ajustar y publicar la topología planeada.</span><span class="sxs-lookup"><span data-stu-id="730d7-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="730d7-109">También valida su topología antes de empezar con las instalaciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="730d7-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="730d7-110">Al instalar Lync Server en servidores individuales, los servidores leen la topología publicada como parte del proceso de instalación y el programa de instalación implementa el servidor tal como se indica en la topología.</span><span class="sxs-lookup"><span data-stu-id="730d7-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="730d7-111">Herramienta de planeación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="730d7-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="730d7-112">La herramienta de planeación toma sus respuestas a las preguntas de la herramienta y genera una topología basada en las directrices y procedimientos recomendados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="730d7-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="730d7-113">También proporciona varias vistas de una implementación en función de las respuestas.</span><span class="sxs-lookup"><span data-stu-id="730d7-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="730d7-114">Muestra una vista global de todos los sitios (es decir, tanto los sitios centrales como las sucursales) y las vistas detalladas que muestran los servidores y otros componentes de cada sitio.</span><span class="sxs-lookup"><span data-stu-id="730d7-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="730d7-115">La ejecución de la herramienta de planeación no le compromete a ninguna implementación específica ni inicia ningún proceso.</span><span class="sxs-lookup"><span data-stu-id="730d7-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="730d7-116">De hecho, ejecutar la herramienta de planeación incluso antes de tener un plan para empresas puede ser una forma muy instructiva de comprender los tipos de preguntas que debe considerar en su proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="730d7-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="730d7-117">Puede ejecutar la herramienta de planeación varias veces, responder a las preguntas de manera diferente y comparar los resultados.</span><span class="sxs-lookup"><span data-stu-id="730d7-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="730d7-118">Si tiene un diseño que está más satisfecho pero que necesita realizar cambios, puede volver a la herramienta de planificación, cargar el diseño y realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="730d7-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="730d7-119">La herramienta de planificación tarda aproximadamente 15 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="730d7-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="730d7-120">Una vez que esté satisfecho, puede usar la herramienta de planeación para crear un diagrama de la implementación planeada.</span><span class="sxs-lookup"><span data-stu-id="730d7-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="730d7-121">Puede usar este diagrama mientras crea la implementación en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="730d7-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="730d7-122">La herramienta de planeación que se incluye en esta versión de Lync Server 2013 es una versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="730d7-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="730d7-123">Tenga en cuenta que las cifras de la planificación de capacidad de la Herramienta de planeación son preliminares y no son compatibles con la versión final.</span><span class="sxs-lookup"><span data-stu-id="730d7-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="730d7-124">Generador de topología de Lync Server</span><span class="sxs-lookup"><span data-stu-id="730d7-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="730d7-125">Una vez que haya decidido su plan de implementación, use el generador de topología para empezar a implementarlo.</span><span class="sxs-lookup"><span data-stu-id="730d7-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="730d7-126">Cuando termine, use el generador de topología para validar la topología y, a continuación, si se supera, puede publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="730d7-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="730d7-127">Al publicar la topología, Lync Server coloca la topología en el almacén de administración central, que se crea en este momento si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="730d7-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="730d7-128">Al instalar Lync Server en cada servidor de la implementación, el servidor lee la topología del almacén central de administración y se instala para adaptarse a su rol en la implementación.</span><span class="sxs-lookup"><span data-stu-id="730d7-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="730d7-129">Como alternativa, si está familiarizado con Lync Server y necesita menos instrucciones preceptivas, puede omitir la herramienta de planeación y usar los asistentes en el generador de topología para el diseño inicial de la implementación y también para los pasos de validación y publicación.</span><span class="sxs-lookup"><span data-stu-id="730d7-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="730d7-130">El uso del generador de topología para planear y publicar una topología es un paso obligatorio.</span><span class="sxs-lookup"><span data-stu-id="730d7-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="730d7-131">No se puede omitir el generador de topología e instalar Lync Server individualmente en los servidores de la implementación.</span><span class="sxs-lookup"><span data-stu-id="730d7-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="730d7-132">Cada servidor debe leer la topología desde una topología validada Publicada en el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="730d7-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="730d7-133">Proceso de planificación de alto nivel</span><span class="sxs-lookup"><span data-stu-id="730d7-133">High-Level Planning Process</span></span>

<span data-ttu-id="730d7-134">Recomendamos el siguiente proceso general para usar la documentación y la herramienta de planeación para planear la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="730d7-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="730d7-135">Si está familiarizado con las versiones anteriores de Lync Server, lea [nuevas características de Lync server 2013](lync-server-2013-new-features.md) para familiarizarse con las nuevas características y requisitos de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="730d7-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="730d7-136">Lea el resto de temas de esta sección de la documentación: [aspectos básicos de topología que debe conocer antes de planear Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md), [decisiones iniciales de planeación para Lync Server 2013](lync-server-2013-initial-planning-decisions.md)y [ Clientes para Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="730d7-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="730d7-137">Observe las decisiones de planeación representadas en las [topologías de referencia en Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="730d7-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="730d7-138">Ahora que está más familiarizado con las características de Lync Server y los tipos de preguntas que deben responderse, ejecute la herramienta de planeación y vea la topología resultante y sus detalles.</span><span class="sxs-lookup"><span data-stu-id="730d7-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="730d7-139">Asegúrese de que la topología cumpla con los requisitos únicos de su organización.</span><span class="sxs-lookup"><span data-stu-id="730d7-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="730d7-140">Si hay cargas de trabajo o características específicas en las que está interesado o necesita conocer, lea las secciones correspondientes de la [planificación de Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="730d7-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="730d7-141">Vuelva a ejecutar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="730d7-141">Run the Planning Tool again.</span></span> <span data-ttu-id="730d7-142">Puede comenzar con la implementación que creó en el paso 3 y modificar los resultados o comenzar de nuevo desde el principio.</span><span class="sxs-lookup"><span data-stu-id="730d7-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="730d7-143">Si es necesario, ejecute la herramienta de planeación una tercera vez y repita hasta que esté satisfecho con la salida.</span><span class="sxs-lookup"><span data-stu-id="730d7-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="730d7-144">Cuando haya finalizado el plan de topología, use la herramienta de planeación para crear e imprimir un diagrama de Visio de su topología.</span><span class="sxs-lookup"><span data-stu-id="730d7-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="730d7-145">Puede usar esta copia impresa mientras trabaja con Topology Builder para introducir su topología.</span><span class="sxs-lookup"><span data-stu-id="730d7-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="730d7-146">Antes de comenzar la implementación, lea la determinación de los [requisitos del sistema para Lync server 2013](lync-server-2013-determining-your-system-requirements.md) y la determinación de los [requisitos de infraestructura de Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para familiarizarse con los requisitos previos y la infraestructura necesaria para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="730d7-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="730d7-147">Además, asegúrese de que ha leído todas las secciones de [planeación de Lync Server 2013](lync-server-2013-planning.md) que se aplican a las cargas de trabajo y las características que planea implementar.</span><span class="sxs-lookup"><span data-stu-id="730d7-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="730d7-148">Migrar desde versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="730d7-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="730d7-149">Si va a migrar a Lync Server desde una versión anterior, consulte la documentación de la [migración](migration.md) para obtener instrucciones específicas para la migración y la implementación.</span><span class="sxs-lookup"><span data-stu-id="730d7-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

