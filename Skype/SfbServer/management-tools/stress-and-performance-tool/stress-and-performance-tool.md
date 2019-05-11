---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Se usa el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento durante la planeación de la capacidad y la optimización del rendimiento en entornos de prueba o que no sea de producción.
ms.openlocfilehash: 7705e92c8389e0377e805bd7d8e09aee454d9160
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904576"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1edfc-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="1edfc-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1edfc-104">Se usa el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento durante la planeación de la capacidad y la optimización del rendimiento en entornos de prueba o que no sea de producción.</span><span class="sxs-lookup"><span data-stu-id="1edfc-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="1edfc-105">El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento incluye herramientas que simplifican la capacidad de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1edfc-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="1edfc-106">El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="1edfc-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="1edfc-107">Simplificar el hardware de planeación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1edfc-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="1edfc-108">Le proporcionan mayor conocimiento y procedimientos recomendados para el ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="1edfc-109">Medir el rendimiento de su Skype para las implementaciones de Business Server</span><span class="sxs-lookup"><span data-stu-id="1edfc-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="1edfc-110">Normalmente, deberá usar esta herramienta después de utilizar el [Skype para la herramienta de planeación de Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y perfeccionamiento de la topología con el [Skype para Calculadora de planeación de capacidad de Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="1edfc-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="1edfc-111">Esta herramienta no se actualizarán para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1edfc-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="1edfc-112">Pruebas</span><span class="sxs-lookup"><span data-stu-id="1edfc-112">Tests</span></span>

<span data-ttu-id="1edfc-113">La herramienta de rendimiento y esfuerzo pueden simular estos tipos de carga de usuarios:</span><span class="sxs-lookup"><span data-stu-id="1edfc-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1edfc-114">Instant Messaging (IM) y presencia</span><span class="sxs-lookup"><span data-stu-id="1edfc-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="1edfc-115">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="1edfc-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="1edfc-116">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1edfc-116">Application sharing</span></span>  <br/> |<span data-ttu-id="1edfc-117">Voz sobre IP (VoIP), incluida la red telefónica conmutada simulación (PTSN)</span><span class="sxs-lookup"><span data-stu-id="1edfc-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="1edfc-118">Conferencia de acceso cliente Web</span><span class="sxs-lookup"><span data-stu-id="1edfc-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="1edfc-119">Operador automático de conferencia</span><span class="sxs-lookup"><span data-stu-id="1edfc-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="1edfc-120">Grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="1edfc-120">Response Groups</span></span>  <br/> |<span data-ttu-id="1edfc-121">Expansión de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="1edfc-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="1edfc-122">Descarga de la libreta de direcciones y consulta de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="1edfc-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="1edfc-123">Enhanced 911 (E911) las llamadas y perfil de ubicación (plan de marcado)</span><span class="sxs-lookup"><span data-stu-id="1edfc-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="1edfc-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="1edfc-124">MultiView</span></span>  <br/> |<span data-ttu-id="1edfc-125">Colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="1edfc-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="1edfc-126">Movilidad</span><span class="sxs-lookup"><span data-stu-id="1edfc-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1edfc-127">Las aplicaciones y los archivos incluidos con la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="1edfc-128">Estas aplicaciones son una parte de la Skype para Business Server Stress and Performance Tool:</span><span class="sxs-lookup"><span data-stu-id="1edfc-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="1edfc-129">**Herramienta**</span><span class="sxs-lookup"><span data-stu-id="1edfc-129">**Tool**</span></span>|<span data-ttu-id="1edfc-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1edfc-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1edfc-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="1edfc-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="1edfc-132">Esta herramienta se utiliza para crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="1edfc-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="1edfc-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="1edfc-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="1edfc-134">Se usa para configurar las características de la carga del usuario que está simulando.</span><span class="sxs-lookup"><span data-stu-id="1edfc-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="1edfc-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="1edfc-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="1edfc-136">La herramienta que simula la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1edfc-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="1edfc-137">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="1edfc-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="1edfc-138">Necesarios para usar el Skype para la herramienta de registro de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1edfc-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="1edfc-139">Ejemplos de scripts de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="1edfc-140">Se usa para configurar la topología para la ejecución de las pruebas de carga, basadas en escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="1edfc-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="1edfc-141">Es probable que necesitará modificarlos para que sean relevantes para su entorno particular.</span><span class="sxs-lookup"><span data-stu-id="1edfc-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="1edfc-142">Temas de esta sección</span><span class="sxs-lookup"><span data-stu-id="1edfc-142">Topics in this section</span></span>

<span data-ttu-id="1edfc-143">Si necesita saber más debe revisar los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="1edfc-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="1edfc-144">Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="1edfc-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="1edfc-145">Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="1edfc-146">Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="1edfc-147">Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="1edfc-148">Uso de la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="1edfc-149">Preguntas más frecuentes para la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1edfc-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

