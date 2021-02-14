---
title: Escenarios de rendimiento para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Tareas que deberá realizar para configurar Skype Empresarial Server 2015 para realizar pruebas de carga y rendimiento con la Herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814710"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1f57a-103">Escenarios de rendimiento para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="1f57a-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1f57a-104">Tareas que deberá realizar para configurar Skype Empresarial Server 2015 para realizar pruebas de carga y rendimiento con la Herramienta de esfuerzo y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1f57a-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="1f57a-105">Para ejecutar la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015 (LyncPerfTool), la topología de Skype Empresarial Server 2015 debe configurarse primero para escenarios relevantes para usted.</span><span class="sxs-lookup"><span data-stu-id="1f57a-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="1f57a-106">Si Skype Empresarial Server 2015 no está configurado o no está configurado correctamente, es muy probable que la simulación de carga falle.</span><span class="sxs-lookup"><span data-stu-id="1f57a-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="1f57a-107">Con la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, proporcionamos scripts del Shell de administración de Skype Empresarial Server y archivos de recursos básicos como parte de la descarga de la [herramienta.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="1f57a-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="1f57a-108">Se pueden usar como punto de partida para configurar la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1f57a-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="1f57a-109">En este artículo se describen Windows PowerShell ejemplos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="1f57a-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f57a-110">Este tema no le ayudará a describir cómo configurar Skype Empresarial Server 2015 en general, tenemos otros temas de planeación e implementación para ello.</span><span class="sxs-lookup"><span data-stu-id="1f57a-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="1f57a-111">Para obtener más información sobre cómo Windows PowerShell en Skype Empresarial Server 2015, consulte la documentación del Shell de administración de Skype Empresarial Server en Insert introduction HERE.</span><span class="sxs-lookup"><span data-stu-id="1f57a-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="1f57a-112">Acerca de cómo ejecutar scripts de shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1f57a-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="1f57a-113">Proporcionamos scripts de PowerShell de ejemplo que puede usar para prepararse para las simulaciones de carga.</span><span class="sxs-lookup"><span data-stu-id="1f57a-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="1f57a-114">Dado que estos scripts están diseñados para la simulación de carga, encontrará que son simples y permisivos.</span><span class="sxs-lookup"><span data-stu-id="1f57a-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="1f57a-115">Es posible que no sea adecuado para su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="1f57a-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="1f57a-116">Una vez más, destacamos que estos scripts son ejemplos, tendrá que revisarlos y, en muchos casos, realizar cambios relevantes para su entorno antes de poder usarlos de forma práctica.</span><span class="sxs-lookup"><span data-stu-id="1f57a-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="1f57a-117">Como mínimo, esperamos que tenga que modificar el script de Grupo de servicio de respuesta (RSG) pensando en su topología (para especificar los agentes asignados a los grupos de agentes).</span><span class="sxs-lookup"><span data-stu-id="1f57a-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="1f57a-118">Pero no es necesario ejecutarlo, si no es necesario.</span><span class="sxs-lookup"><span data-stu-id="1f57a-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1f57a-119">Tenga cuidado de revisar y comprender estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="1f57a-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="1f57a-120">Los scripts sobrescribirán las configuraciones existentes en la topología cuando se ejecuten.</span><span class="sxs-lookup"><span data-stu-id="1f57a-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="1f57a-121">Nombres de versión de cliente de stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="1f57a-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="1f57a-122">Es posible que deba configurar la directiva de comprobación de versión de cliente si ha cambiado previamente la configuración de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1f57a-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="1f57a-123">Si no está seguro de esto, consulte la documentación de comprobación de [versión de cliente.](https://msdn.microsoft.com/vsto/jj923060)</span><span class="sxs-lookup"><span data-stu-id="1f57a-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="1f57a-124">La herramienta Stress and Performance usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Skype Empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="1f57a-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="1f57a-125">LSPT/15.0.0.0 (Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015)</span><span class="sxs-lookup"><span data-stu-id="1f57a-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="1f57a-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="1f57a-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="1f57a-127">Para el cliente de movilidad (UCWA) en LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="1f57a-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="1f57a-128">Herramienta ucwa perf/conferencia web</span><span class="sxs-lookup"><span data-stu-id="1f57a-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="1f57a-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="1f57a-129">UCWA Perf Tool/Mobile</span></span>
    

