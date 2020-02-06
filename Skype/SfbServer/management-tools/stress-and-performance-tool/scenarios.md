---
title: Escenarios de rendimiento para la herramienta de estrés y rendimiento de Skype empresarial Server 2015
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
description: Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar el rendimiento y las pruebas de carga, con la herramienta estrés and performance.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803880"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="503c8-103">Escenarios de rendimiento para la herramienta de estrés y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="503c8-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="503c8-104">Las tareas que debe realizar para configurar Skype empresarial Server 2015 para realizar el rendimiento y las pruebas de carga, con la herramienta estrés and performance.</span><span class="sxs-lookup"><span data-stu-id="503c8-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="503c8-105">Para ejecutar la herramienta Skype empresarial Server 2015 stress and Performance (LyncPerfTool), la topología de Skype empresarial Server 2015 debe estar configurada en primer lugar para los escenarios relevantes para usted.</span><span class="sxs-lookup"><span data-stu-id="503c8-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="503c8-106">Si Skype empresarial Server 2015 no está configurado o no está configurado correctamente, es muy probable que la simulación de carga no se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="503c8-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="503c8-107">Con la herramienta de estrés y rendimiento de Skype empresarial Server 2015, proporcionamos ejemplos de scripts del shell de administración de Skype empresarial y archivos de recursos básicos como parte de la descarga de la [herramienta](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="503c8-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="503c8-108">Se pueden usar como punto de partida para configurar la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="503c8-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="503c8-109">En este artículo se describen los ejemplos de Windows PowerShell proporcionados.</span><span class="sxs-lookup"><span data-stu-id="503c8-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="503c8-110">En general, este tema no le ayudará a describir cómo configurar Skype empresarial Server 2015, tenemos otros temas de planificación e implementación para eso.</span><span class="sxs-lookup"><span data-stu-id="503c8-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="503c8-111">Para obtener más información sobre cómo trabajar con Windows PowerShell en Skype empresarial Server 2015, consulte la documentación del shell de administración de Skype empresarial en Insertar aquí.</span><span class="sxs-lookup"><span data-stu-id="503c8-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="503c8-112">Acerca de la ejecución de scripts de Shell de administración de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="503c8-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="503c8-113">Proporcionamos scripts de PowerShell de ejemplo que puede usar para prepararse para sus simulaciones de carga.</span><span class="sxs-lookup"><span data-stu-id="503c8-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="503c8-114">Debido a que estas secuencias de comandos se han diseñado para la simulación de carga, los encontrarás como simples y permisivos.</span><span class="sxs-lookup"><span data-stu-id="503c8-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="503c8-115">Es posible que no sea adecuado para su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="503c8-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="503c8-116">Nuevamente, hacemos hincapié en que estas secuencias de comandos son muestras, necesitarás revisarlas y, en muchos casos, hacer cambios relevantes para tu entorno antes de poder hacer uso práctico de ellas.</span><span class="sxs-lookup"><span data-stu-id="503c8-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="503c8-117">Como mínimo, esperamos que necesite modificar el script de grupo de servicio de respuesta (RSG) con su topología en mente (para especificar los agentes asignados a los grupos de agentes).</span><span class="sxs-lookup"><span data-stu-id="503c8-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="503c8-118">Pero no tiene que hacerlo, si no lo necesita.</span><span class="sxs-lookup"><span data-stu-id="503c8-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="503c8-119">Ten cuidado al revisar y comprender estas muestras.</span><span class="sxs-lookup"><span data-stu-id="503c8-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="503c8-120">Las secuencias de comandos sobrescribirán cualquier configuración existente en la topología cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="503c8-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="503c8-121">Nombres de versión del cliente de la herramienta de estrés y rendimiento</span><span class="sxs-lookup"><span data-stu-id="503c8-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="503c8-122">Es posible que tenga que configurar la Directiva de comprobación de versión del cliente si ha cambiado previamente la configuración de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="503c8-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="503c8-123">Si no está seguro de esto, Compruebe la documentación de comprobación de la [versión del cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="503c8-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="503c8-124">La herramienta de carga y rendimiento usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Skype empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="503c8-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="503c8-125">LSPT/15.0.0.0 (herramienta de estrés y rendimiento de Skype empresarial Server 2015)</span><span class="sxs-lookup"><span data-stu-id="503c8-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="503c8-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="503c8-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="503c8-127">Para el cliente de movilidad (UCWA) en LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="503c8-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="503c8-128">Herramienta de rendimiento de UCWA y conferencia Web</span><span class="sxs-lookup"><span data-stu-id="503c8-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="503c8-129">Herramienta de Perf de UCWA/móvil</span><span class="sxs-lookup"><span data-stu-id="503c8-129">UCWA Perf Tool/Mobile</span></span>
    

