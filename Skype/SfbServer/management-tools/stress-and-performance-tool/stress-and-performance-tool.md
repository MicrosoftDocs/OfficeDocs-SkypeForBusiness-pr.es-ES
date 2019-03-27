---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Se usa el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento durante la planeación de la capacidad y la optimización del rendimiento en entornos de prueba o que no sea de producción.
ms.openlocfilehash: 801a18b4c2cb31cad52cf2d57a661361788844f0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875028"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ac7dc-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="ac7dc-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ac7dc-104">Se usa el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento durante la planeación de la capacidad y la optimización del rendimiento en entornos de prueba o que no sea de producción.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="ac7dc-105">El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento incluye herramientas que simplifican la capacidad de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="ac7dc-106">El Skype para Business Server 2015 herramienta de esfuerzo y rendimiento le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="ac7dc-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="ac7dc-107">Simplificar el hardware de planeación de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ac7dc-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="ac7dc-108">Le proporcionan mayor conocimiento y procedimientos recomendados para el ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="ac7dc-109">Medir el rendimiento de su Skype para las implementaciones de Business Server</span><span class="sxs-lookup"><span data-stu-id="ac7dc-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="ac7dc-110">Normalmente, deberá usar esta herramienta después de utilizar el [Skype para la herramienta de planeación de Business Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y perfeccionamiento de la topología con el [Skype para Calculadora de planeación de capacidad de Business Server 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="ac7dc-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="ac7dc-111">Esta herramienta no se actualizarán para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="ac7dc-112">Pruebas</span><span class="sxs-lookup"><span data-stu-id="ac7dc-112">Tests</span></span>

<span data-ttu-id="ac7dc-113">La herramienta de rendimiento y esfuerzo pueden simular estos tipos de carga de usuarios:</span><span class="sxs-lookup"><span data-stu-id="ac7dc-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac7dc-114">Instant Messaging (IM) y presencia</span><span class="sxs-lookup"><span data-stu-id="ac7dc-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="ac7dc-115">Conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="ac7dc-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="ac7dc-116">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ac7dc-116">Application sharing</span></span>  <br/> |<span data-ttu-id="ac7dc-117">Voz sobre IP (VoIP), incluida la red telefónica conmutada simulación (PTSN)</span><span class="sxs-lookup"><span data-stu-id="ac7dc-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="ac7dc-118">Conferencia de acceso cliente Web</span><span class="sxs-lookup"><span data-stu-id="ac7dc-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="ac7dc-119">Operador automático de conferencia</span><span class="sxs-lookup"><span data-stu-id="ac7dc-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="ac7dc-120">Grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ac7dc-120">Response Groups</span></span>  <br/> |<span data-ttu-id="ac7dc-121">Expansión de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="ac7dc-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="ac7dc-122">Descarga de la libreta de direcciones y consulta de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="ac7dc-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="ac7dc-123">Enhanced 911 (E911) las llamadas y perfil de ubicación (plan de marcado)</span><span class="sxs-lookup"><span data-stu-id="ac7dc-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="ac7dc-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="ac7dc-124">MultiView</span></span>  <br/> |<span data-ttu-id="ac7dc-125">Colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="ac7dc-126">Movilidad</span><span class="sxs-lookup"><span data-stu-id="ac7dc-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ac7dc-127">Las aplicaciones y los archivos incluidos con la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="ac7dc-128">Estas aplicaciones son una parte de la Skype para Business Server Stress and Performance Tool:</span><span class="sxs-lookup"><span data-stu-id="ac7dc-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="ac7dc-129">**Herramienta**</span><span class="sxs-lookup"><span data-stu-id="ac7dc-129">**Tool**</span></span>|<span data-ttu-id="ac7dc-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ac7dc-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac7dc-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="ac7dc-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="ac7dc-132">Esta herramienta se utiliza para crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="ac7dc-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="ac7dc-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="ac7dc-134">Se usa para configurar las características de la carga del usuario que está simulando.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="ac7dc-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="ac7dc-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="ac7dc-136">La herramienta que simula la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="ac7dc-137">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="ac7dc-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="ac7dc-138">Necesarios para usar el Skype para la herramienta de registro de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="ac7dc-139">Ejemplos de scripts de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="ac7dc-140">Se usa para configurar la topología para la ejecución de las pruebas de carga, basadas en escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="ac7dc-141">Es probable que necesitará modificarlos para que sean relevantes para su entorno particular.</span><span class="sxs-lookup"><span data-stu-id="ac7dc-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="ac7dc-142">Temas de esta sección</span><span class="sxs-lookup"><span data-stu-id="ac7dc-142">Topics in this section</span></span>

<span data-ttu-id="ac7dc-143">Si necesita saber más debe revisar los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="ac7dc-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="ac7dc-144">Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ac7dc-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="ac7dc-145">Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="ac7dc-146">Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="ac7dc-147">Configuración de directivas para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="ac7dc-148">Uso de la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="ac7dc-149">Preguntas más frecuentes para la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="ac7dc-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

