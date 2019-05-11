---
title: Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tareas que necesitará realizar para configurar Skype para Business Server 2015 hacer pruebas de rendimiento y carga-, mediante la herramienta de rendimiento y esfuerzo.
ms.openlocfilehash: 06ca34717080421129fc03475103b34804ef280a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901700"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="6c1ef-103">Escenarios de rendimiento para el Skype para Business Server 2015 herramienta de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="6c1ef-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="6c1ef-104">Tareas que necesitará realizar para configurar Skype para Business Server 2015 hacer pruebas de rendimiento y carga-, mediante la herramienta de rendimiento y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="6c1ef-105">Para ejecutar la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento (LyncPerfTool), en primer lugar debe configurarse la Skype para topología empresarial Server 2015 para escenarios relevantes para usted.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="6c1ef-106">Si Skype para Business Server 2015 no está configurado o no está configurado correctamente, es muy probable que se lleve a cabo la simulación de carga.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="6c1ef-107">Con Skype para Business Server 2015 herramienta de esfuerzo y rendimiento, ofrecemos ejemplo Skype para las secuencias de comandos de Shell de administración de servidor empresarial y archivos de recursos básicos como parte de la [descarga de la herramienta](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="6c1ef-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="6c1ef-108">Estos se pueden usar como punto de partida para configurar su Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="6c1ef-109">En este artículo se describe los ejemplos de Windows PowerShell proporcionados.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c1ef-110">En este tema no le ayudará a describen cómo configurar Skype para Business Server 2015, por lo general, tenemos otros temas de planeación e implementación para.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="6c1ef-111">Para obtener información detallada sobre cómo trabajar con Windows PowerShell en Skype para Business Server 2015, vea el Skype para la documentación del Shell de administración de servidor empresarial en Insertar aquí la introducción.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="6c1ef-112">Acerca de la ejecución de Skype para la administración de Business Server secuencias de comandos de shell</span><span class="sxs-lookup"><span data-stu-id="6c1ef-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="6c1ef-113">Nos permite proporcionar scripts de PowerShell de ejemplo que puede usar para preparar sus simulaciones de carga.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="6c1ef-114">Debido a que estas secuencias de comandos están diseñados para la simulación de carga, encontrará que sean sencilla y permissive.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="6c1ef-115">Puede que no sea apropiado para su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="6c1ef-116">Vuelva a se hace hincapié en que estas secuencias de comandos son ejemplos, que necesitará para revisarlos y en muchos casos realice cambios relevantes para su entorno antes de poder hacer un uso práctico de ellos.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="6c1ef-117">Como mínimo, que esperábamos que necesita modificar la secuencia de comandos del grupo de servicio de respuesta (RSG) con su topología en cuenta (para especificar a los agentes asignados a los grupos de agentes).</span><span class="sxs-lookup"><span data-stu-id="6c1ef-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="6c1ef-118">Pero no es necesario ejecutar, si no es necesario.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6c1ef-119">Por favor, tenga cuidado al revisar y descripción de estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="6c1ef-120">Las secuencias de comandos sobrescribe cualquier configuración existente en la topología cuando ejecuta.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="6c1ef-121">Herramienta de esfuerzo y rendimiento nombres de versión de cliente</span><span class="sxs-lookup"><span data-stu-id="6c1ef-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="6c1ef-122">Es posible que necesite configurar la directiva de comprobación de la versión de cliente si anteriormente se ha cambiado la configuración de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="6c1ef-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="6c1ef-123">Si no está seguro acerca de esto, consulte la [documentación de comprobación de la versión de cliente](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="6c1ef-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="6c1ef-124">La herramienta Stress and Performance utiliza las siguientes versiones de agente de usuario de forma predeterminada cuando se comunica con Skype para Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="6c1ef-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="6c1ef-125">LSPT/15.0.0.0 (Skype para Business Server 2015 herramienta de esfuerzo y rendimiento)</span><span class="sxs-lookup"><span data-stu-id="6c1ef-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="6c1ef-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="6c1ef-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="6c1ef-127">Para el cliente de movilidad (UCWA) en LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="6c1ef-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="6c1ef-128">Conferencia Web de la herramienta rendimiento UCWA</span><span class="sxs-lookup"><span data-stu-id="6c1ef-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="6c1ef-129">Herramienta de rendimiento UCWA o móvil</span><span class="sxs-lookup"><span data-stu-id="6c1ef-129">UCWA Perf Tool/Mobile</span></span>
    

