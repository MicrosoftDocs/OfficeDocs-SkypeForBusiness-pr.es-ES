---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: La herramienta de estrés y rendimiento de Skype empresarial Server 2015 se usa durante la planificación de la capacidad y en el ajuste del rendimiento en entornos ajenos a la producción o pruebas.
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816159"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="aa092-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="aa092-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="aa092-104">La herramienta de estrés y rendimiento de Skype empresarial Server 2015 se usa durante la planificación de la capacidad y en el ajuste del rendimiento en entornos ajenos a la producción o pruebas.</span><span class="sxs-lookup"><span data-stu-id="aa092-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="aa092-105">La herramienta de estrés y rendimiento de Skype empresarial Server 2015 incluye herramientas que simplificarán la planificación de la capacidad de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aa092-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="aa092-106">La herramienta de estrés y rendimiento de Skype empresarial Server 2015 le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="aa092-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="aa092-107">Simplificar la planificación de hardware para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="aa092-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="aa092-108">Obtener un mayor conocimiento y procedimientos recomendados para ajustar el rendimiento</span><span class="sxs-lookup"><span data-stu-id="aa092-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="aa092-109">Medir el rendimiento de las implementaciones de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="aa092-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="aa092-110">Normalmente usaría esta herramienta después de usar la herramienta de [planeación de Skype empresarial Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y refinar la topología con la calculadora de [planeación de capacidad de Skype empresarial 2015](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="aa092-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="aa092-111">Esta herramienta no se actualizará en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aa092-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="aa092-112">Pruebas</span><span class="sxs-lookup"><span data-stu-id="aa092-112">Tests</span></span>

<span data-ttu-id="aa092-113">La herramienta estrés and performance puede simular estos tipos de carga de usuarios:</span><span class="sxs-lookup"><span data-stu-id="aa092-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aa092-114">Mensajería instantánea (mi) y presencia</span><span class="sxs-lookup"><span data-stu-id="aa092-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="aa092-115">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="aa092-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="aa092-116">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="aa092-116">Application sharing</span></span>  <br/> |<span data-ttu-id="aa092-117">Voz sobre IP (VoIP), incluida una simulación de red de telefonía pública conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="aa092-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="aa092-118">Conferencia de cliente de Web Access</span><span class="sxs-lookup"><span data-stu-id="aa092-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="aa092-119">Operador automático de la Conferencia</span><span class="sxs-lookup"><span data-stu-id="aa092-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="aa092-120">Grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="aa092-120">Response Groups</span></span>  <br/> |<span data-ttu-id="aa092-121">Expansión de la lista de distribución</span><span class="sxs-lookup"><span data-stu-id="aa092-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="aa092-122">Consulta de la libreta de direcciones y descarga de la libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="aa092-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="aa092-123">Llamadas y perfiles de ubicación de 911 (E911) mejorados (plan de marcado)</span><span class="sxs-lookup"><span data-stu-id="aa092-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="aa092-124">Multivista</span><span class="sxs-lookup"><span data-stu-id="aa092-124">MultiView</span></span>  <br/> |<span data-ttu-id="aa092-125">Colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="aa092-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="aa092-126">Movilidad</span><span class="sxs-lookup"><span data-stu-id="aa092-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="aa092-127">Aplicaciones y archivos incluidos con la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa092-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="aa092-128">Estas aplicaciones forman parte de la herramienta de estrés y rendimiento de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="aa092-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="aa092-129">**Utilidad**</span><span class="sxs-lookup"><span data-stu-id="aa092-129">**Tool**</span></span>|<span data-ttu-id="aa092-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aa092-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa092-131">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="aa092-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="aa092-132">Esta herramienta se usa para crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="aa092-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="aa092-133">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="aa092-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="aa092-134">Se usa para configurar las características de la carga de usuarios que se está simulando.</span><span class="sxs-lookup"><span data-stu-id="aa092-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="aa092-135">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="aa092-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="aa092-136">La herramienta que simula la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="aa092-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="aa092-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="aa092-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="aa092-138">Necesario para usar la herramienta de registro de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aa092-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="aa092-139">Ejemplos de scripts de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="aa092-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="aa092-140">Se usa para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="aa092-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="aa092-141">Es probable que deba modificarlos para que sean relevantes para su entorno en particular.</span><span class="sxs-lookup"><span data-stu-id="aa092-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="aa092-142">Temas de esta sección</span><span class="sxs-lookup"><span data-stu-id="aa092-142">Topics in this section</span></span>

<span data-ttu-id="aa092-143">Debe revisar los artículos siguientes si necesita más información:</span><span class="sxs-lookup"><span data-stu-id="aa092-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="aa092-144">Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="aa092-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="aa092-145">Escenarios de rendimiento para la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa092-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="aa092-146">Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento</span><span class="sxs-lookup"><span data-stu-id="aa092-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="aa092-147">Configuración de directivas para la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa092-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="aa092-148">Usar la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa092-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="aa092-149">Preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa092-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

