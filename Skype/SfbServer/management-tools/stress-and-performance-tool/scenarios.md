---
title: Escenarios de rendimiento para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar pruebas de carga y rendimiento, mediante la herramienta stress and performance.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983855"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a409c-103">Escenarios de rendimiento para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a409c-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="a409c-104">Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar pruebas de carga y rendimiento, mediante la herramienta stress and performance.</span><span class="sxs-lookup"><span data-stu-id="a409c-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="a409c-105">Para ejecutar la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015 (LyncPerfTool), la topología de Skype empresarial Server 2015 debe estar configurada primero para los escenarios que le resulten relevantes.</span><span class="sxs-lookup"><span data-stu-id="a409c-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="a409c-106">Si Skype empresarial Server 2015 no está configurado o no está configurado correctamente, es muy probable que la simulación de carga falle.</span><span class="sxs-lookup"><span data-stu-id="a409c-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="a409c-107">Con la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015, proporcionamos ejemplos de secuencias de comandos del shell de administración de Skype empresarial Server y archivos de recursos básicos como parte de la descarga de la [herramienta](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="a409c-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="a409c-108">Se pueden usar como punto de partida para configurar su implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a409c-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="a409c-109">En este artículo se describen los ejemplos de Windows PowerShell proporcionados.</span><span class="sxs-lookup"><span data-stu-id="a409c-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a409c-110">En este tema no se describe cómo configurar Skype empresarial Server 2015 en general, tenemos otros temas de planeación e implementación para ello.</span><span class="sxs-lookup"><span data-stu-id="a409c-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="a409c-111">Para obtener información detallada sobre cómo trabajar con Windows PowerShell en Skype empresarial Server 2015, consulte la documentación del shell de administración de Skype empresarial Server en Insert Introduction aquí.</span><span class="sxs-lookup"><span data-stu-id="a409c-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="a409c-112">Acerca de la ejecución de scripts del shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a409c-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="a409c-113">Proporcionamos scripts de PowerShell de ejemplo que puede usar para preparar sus simulaciones de carga.</span><span class="sxs-lookup"><span data-stu-id="a409c-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="a409c-114">Como estos scripts están diseñados para la simulación de carga, los encontrará sencillos y permisivos.</span><span class="sxs-lookup"><span data-stu-id="a409c-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="a409c-115">Es posible que no sea adecuado para su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="a409c-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="a409c-116">De nuevo, resalte que estos scripts son ejemplos, necesitará revisarlos y, en muchos casos, realizar cambios relevantes para su entorno antes de poder hacer un uso práctico de ellos.</span><span class="sxs-lookup"><span data-stu-id="a409c-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="a409c-117">Como mínimo, esperamos que deba modificar el script de grupo de servicio de respuesta (RSG) con la topología teniendo en cuenta (para especificar los agentes asignados a los grupos de agentes).</span><span class="sxs-lookup"><span data-stu-id="a409c-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="a409c-118">Pero no es necesario que lo ejecute, si no lo necesita.</span><span class="sxs-lookup"><span data-stu-id="a409c-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a409c-119">Tenga cuidado en la revisión y comprensión de estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a409c-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="a409c-120">Los scripts sobrescribirán cualquier configuración existente en la topología cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="a409c-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="a409c-121">Nombres de versión de cliente de la herramienta stress and Performance</span><span class="sxs-lookup"><span data-stu-id="a409c-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="a409c-122">Es posible que deba configurar la Directiva de comprobación de versión de cliente si ha cambiado previamente la configuración de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a409c-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="a409c-123">Si no está seguro de esto, consulte la documentación de comprobación de la [versión de cliente](https://msdn.microsoft.com/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="a409c-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="a409c-124">La herramienta stress and Performance usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Skype empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="a409c-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="a409c-125">LSPT/15.0.0.0 (herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015)</span><span class="sxs-lookup"><span data-stu-id="a409c-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="a409c-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="a409c-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="a409c-127">Para el cliente de movilidad (UCWA) en LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="a409c-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="a409c-128">Conferencia de rendimiento de UCWA Tool/Web</span><span class="sxs-lookup"><span data-stu-id="a409c-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="a409c-129">Herramienta de Perf de UCWA/móvil</span><span class="sxs-lookup"><span data-stu-id="a409c-129">UCWA Perf Tool/Mobile</span></span>
    

