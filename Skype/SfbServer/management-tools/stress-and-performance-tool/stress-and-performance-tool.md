---
title: Skype para Business Server 2015 Stress y la herramienta de rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: El Skype para Business Server 2015 Stress y la herramienta de rendimiento se utiliza durante la planificación de la capacidad y la optimización del rendimiento en entornos de prueba o ajeno a la producción.
ms.openlocfilehash: 0a0a5b17a6e45b2e8944e0e0dd4b3840fc62e102
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="82bff-103">Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="82bff-104">El Skype para Business Server 2015 Stress y la herramienta de rendimiento se utiliza durante la planificación de la capacidad y la optimización del rendimiento en entornos de prueba o ajeno a la producción.</span><span class="sxs-lookup"><span data-stu-id="82bff-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="82bff-105">El Skype para la herramienta Business Server 2015 Stress and Performance incluye herramientas que simplificarán la capacidad planificación de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="82bff-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="82bff-106">El Skype para Business Server 2015 Stress y la herramienta de rendimiento le ayudarán:</span><span class="sxs-lookup"><span data-stu-id="82bff-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="82bff-107">Simplificar el hardware planear Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="82bff-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="82bff-108">Le proporcionan mayor conocimiento y mejores prácticas para optimizar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="82bff-109">Medir el rendimiento de su Skype para implementaciones de servidores empresariales</span><span class="sxs-lookup"><span data-stu-id="82bff-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="82bff-110">Normalmente utilizaría esta herramienta después de utilizar el [Skype para la herramienta de planeación de Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y refinar la topología con el [Skype para Calculadora de planeación de capacidad de Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="82bff-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 
  
## <a name="tests"></a><span data-ttu-id="82bff-111">Pruebas</span><span class="sxs-lookup"><span data-stu-id="82bff-111">Tests</span></span>

<span data-ttu-id="82bff-112">La herramienta de rendimiento y esfuerzo pueden simular estos tipos de carga de usuarios:</span><span class="sxs-lookup"><span data-stu-id="82bff-112">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82bff-113">Instant Messaging (IM) y presencia</span><span class="sxs-lookup"><span data-stu-id="82bff-113">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="82bff-114">Conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="82bff-114">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="82bff-115">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="82bff-115">Application sharing</span></span>  <br/> |<span data-ttu-id="82bff-116">Voz sobre IP (VoIP), incluyendo la red telefónica pública conmutada simulación (PTSN)</span><span class="sxs-lookup"><span data-stu-id="82bff-116">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="82bff-117">Conferencias de cliente de acceso Web</span><span class="sxs-lookup"><span data-stu-id="82bff-117">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="82bff-118">Operador automático de conferencia</span><span class="sxs-lookup"><span data-stu-id="82bff-118">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="82bff-119">Grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="82bff-119">Response Groups</span></span>  <br/> |<span data-ttu-id="82bff-120">Expansión de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="82bff-120">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="82bff-121">Descarga de la libreta de direcciones y consulta de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="82bff-121">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="82bff-122">Enhanced 911 (E911) las llamadas y perfil de ubicación (plan de marcado)</span><span class="sxs-lookup"><span data-stu-id="82bff-122">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="82bff-123">MultiView</span><span class="sxs-lookup"><span data-stu-id="82bff-123">MultiView</span></span>  <br/> |<span data-ttu-id="82bff-124">Colaboración de datos</span><span class="sxs-lookup"><span data-stu-id="82bff-124">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="82bff-125">Movilidad</span><span class="sxs-lookup"><span data-stu-id="82bff-125">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="82bff-126">Aplicaciones y archivos incluidos con el Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-126">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="82bff-127">Estas aplicaciones son parte de la Skype para la herramienta Business Server Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="82bff-127">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="82bff-128">**Herramienta**</span><span class="sxs-lookup"><span data-stu-id="82bff-128">**Tool**</span></span>|<span data-ttu-id="82bff-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="82bff-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82bff-130">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="82bff-130">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="82bff-131">Esta herramienta se utiliza para crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="82bff-131">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="82bff-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="82bff-132">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="82bff-133">Se utiliza para configurar las características de la carga de usuarios que está simulando.</span><span class="sxs-lookup"><span data-stu-id="82bff-133">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="82bff-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="82bff-134">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="82bff-135">La herramienta que simula la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="82bff-135">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="82bff-136">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="82bff-136">Default.tmx</span></span>  <br/> |<span data-ttu-id="82bff-137">Necesario para utilizar el Skype para la herramienta de registro de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="82bff-137">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="82bff-138">Ejemplos de secuencias de comandos de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="82bff-138">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="82bff-139">Permite configurar la topología para ejecutar pruebas de carga, basadas en escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="82bff-139">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="82bff-140">Probablemente necesitará modificarlos para que sean relevantes para su entorno particular.</span><span class="sxs-lookup"><span data-stu-id="82bff-140">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="82bff-141">Temas de esta sección</span><span class="sxs-lookup"><span data-stu-id="82bff-141">Topics in this section</span></span>

<span data-ttu-id="82bff-142">Si necesita saber más debe revisar los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="82bff-142">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="82bff-143">Requisitos previos y el programa de instalación para el Skype para Busines herramienta de carga y rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-143">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="82bff-144">Escenarios de rendimiento para el Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-144">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="82bff-145">Aprovisionamiento de la topología para ejecutar la carga en situaciones de estrés y rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-145">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="82bff-146">Configuración de directivas para el Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-146">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="82bff-147">Usando el Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-147">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="82bff-148">Preguntas más frecuentes sobre el Skype para Business Server 2015 Stress y la herramienta de rendimiento</span><span class="sxs-lookup"><span data-stu-id="82bff-148">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

