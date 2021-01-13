---
title: Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 se usa durante la planeación de capacidad y el ajuste del rendimiento en entornos de prueba o no producción.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814930"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="98ddd-103">Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="98ddd-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="98ddd-104">La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 se usa durante la planeación de capacidad y el ajuste del rendimiento en entornos de prueba o no producción.</span><span class="sxs-lookup"><span data-stu-id="98ddd-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="98ddd-105">La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 incluye herramientas que simplificarán la planeación de la capacidad para Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="98ddd-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="98ddd-106">La Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="98ddd-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="98ddd-107">Simplificar la planeación del hardware para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="98ddd-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="98ddd-108">Proporcionar mayor conocimiento y procedimientos recomendados para el ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="98ddd-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="98ddd-109">Medir el rendimiento de las implementaciones de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="98ddd-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="98ddd-110">Normalmente, esta herramienta se usa después de usar la Herramienta de planeación de Skype Empresarial [Server 2015](../../management-tools/planning-tool/planning-tool.md) para diseñar la topología y refinar la topología con la calculadora de planeación de capacidad de [Skype Empresarial Server 2015.](../../management-tools/capacity-planning-calculator.md)</span><span class="sxs-lookup"><span data-stu-id="98ddd-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="98ddd-111">Esta herramienta no se actualizará para Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="98ddd-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="98ddd-112">Pruebas</span><span class="sxs-lookup"><span data-stu-id="98ddd-112">Tests</span></span>

<span data-ttu-id="98ddd-113">La herramienta Stress and Performance puede simular estos tipos de carga de usuario:</span><span class="sxs-lookup"><span data-stu-id="98ddd-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="98ddd-114">Mensajería instantánea (MI) y presencia</span><span class="sxs-lookup"><span data-stu-id="98ddd-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="98ddd-115">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="98ddd-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="98ddd-116">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="98ddd-116">Application sharing</span></span>  <br/> |<span data-ttu-id="98ddd-117">Voz sobre IP (VoIP), incluida la simulación de red telefónica conmutada (PTSN)</span><span class="sxs-lookup"><span data-stu-id="98ddd-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="98ddd-118">Conferencia de cliente de acceso web</span><span class="sxs-lookup"><span data-stu-id="98ddd-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="98ddd-119">Operador automático de conferencia</span><span class="sxs-lookup"><span data-stu-id="98ddd-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="98ddd-120">Grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="98ddd-120">Response Groups</span></span>  <br/> |<span data-ttu-id="98ddd-121">Expansión de listas de distribución</span><span class="sxs-lookup"><span data-stu-id="98ddd-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="98ddd-122">Descarga de libreta de direcciones y consulta de libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="98ddd-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="98ddd-123">Perfil de ubicación y llamadas mejoradas al 911 (E911) (plan de marcado)</span><span class="sxs-lookup"><span data-stu-id="98ddd-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="98ddd-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="98ddd-124">MultiView</span></span>  <br/> |<span data-ttu-id="98ddd-125">Colaboración de datos</span><span class="sxs-lookup"><span data-stu-id="98ddd-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="98ddd-126">Movilidad</span><span class="sxs-lookup"><span data-stu-id="98ddd-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="98ddd-127">Aplicaciones y archivos incluidos con la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="98ddd-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="98ddd-128">Estas aplicaciones forman parte de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="98ddd-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="98ddd-129">**Herramienta**</span><span class="sxs-lookup"><span data-stu-id="98ddd-129">**Tool**</span></span>|<span data-ttu-id="98ddd-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="98ddd-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98ddd-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="98ddd-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="98ddd-132">Esta herramienta se usa para crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="98ddd-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="98ddd-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="98ddd-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="98ddd-134">Se usa para configurar las características de la carga de usuario que está simulando.</span><span class="sxs-lookup"><span data-stu-id="98ddd-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="98ddd-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="98ddd-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="98ddd-136">Herramienta que simula la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="98ddd-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="98ddd-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="98ddd-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="98ddd-138">Necesario para usar la herramienta de registro de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="98ddd-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="98ddd-139">Ejemplos de script de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="98ddd-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="98ddd-140">Se usa para configurar la topología para ejecutar pruebas de carga, en función de escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="98ddd-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="98ddd-141">Es probable que deba modificarlos para que sean relevantes para su entorno en particular.</span><span class="sxs-lookup"><span data-stu-id="98ddd-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="98ddd-142">Temas de esta sección</span><span class="sxs-lookup"><span data-stu-id="98ddd-142">Topics in this section</span></span>

<span data-ttu-id="98ddd-143">Debe revisar los siguientes artículos si necesita más información:</span><span class="sxs-lookup"><span data-stu-id="98ddd-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="98ddd-144">Requisitos previos y configuración de la Herramienta de esfuerzo y rendimiento de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="98ddd-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="98ddd-145">Escenarios de rendimiento para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="98ddd-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="98ddd-146">Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="98ddd-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="98ddd-147">Configuración de directivas para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="98ddd-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="98ddd-148">Uso de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="98ddd-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="98ddd-149">Preguntas más frecuentes sobre la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="98ddd-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

