---
title: Configurar escenarios de 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ad7a3be8b69c956b1cca0f1d1554a5fa288f17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34843055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="8c748-102">Configurar escenarios de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="8c748-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c748-103">_**Última modificación del tema:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="8c748-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="8c748-104">Para ejecutar la herramienta Lync Server 2013 stress and Performance (LyncPerfTool), la topología de Lync Server 2013 debe estar configurada en primer lugar para los escenarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="8c748-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="8c748-105">Si Lync Server 2013 no está configurado o no está configurado correctamente, la simulación de carga fallará en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="8c748-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="8c748-106">Con la herramienta Lync Server 2013 stress and performance, hemos proporcionado ejemplos de scripts del shell de administración de Lync Server y archivos de recursos básicos que se pueden usar como punto de partida para configurar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c748-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="8c748-107">En este tema se describen los ejemplos de Windows PowerShell proporcionados.</span><span class="sxs-lookup"><span data-stu-id="8c748-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="8c748-108">Tenga en cuenta que no es el objetivo de este tema describir cómo configurar Lync Server 2013 en general.</span><span class="sxs-lookup"><span data-stu-id="8c748-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="8c748-109">Para obtener más información sobre cómo trabajar con Windows PowerShell en Lync Server 2013, consulte la documentación del shell <https://technet.microsoft.com/en-us/library/gg398474.aspx>de administración de Lync Server en.</span><span class="sxs-lookup"><span data-stu-id="8c748-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/en-us/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="8c748-110">Acerca de la ejecución de scripts de Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="8c748-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="8c748-111">Proporcionamos ejemplos de scripts del shell de administración de Lync Server que se pueden usar en la preparación de la ejecución de la simulación de carga.</span><span class="sxs-lookup"><span data-stu-id="8c748-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="8c748-112">Dado que los scripts están pensados para la simulación de carga, son sencillos y permisivos, por lo que es posible que no sean adecuados para la producción.</span><span class="sxs-lookup"><span data-stu-id="8c748-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="8c748-113">Todos los scripts son ejemplos y deben revisarse y, en algunos casos, modificarse para reflejar su topología.</span><span class="sxs-lookup"><span data-stu-id="8c748-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="8c748-114">Como mínimo, esperamos que el escenario del servicio de grupo de respuesta (RGS) deba modificarse para especificar los agentes que se asignan a los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="8c748-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="8c748-115">Sin embargo, tiene la opción de no simular esta carga.</span><span class="sxs-lookup"><span data-stu-id="8c748-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8c748-116">Preste atención en la revisión y la comprensión de los ejemplos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="8c748-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="8c748-117">Los scripts sobrescribirán cualquier configuración existente en la topología.</span><span class="sxs-lookup"><span data-stu-id="8c748-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8c748-118">Para obtener más información sobre el uso de Windows PowerShell y el shell de administración de Lync Server, consulte el blog <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>de lync Server 2013 de Windows PowerShell en.</span><span class="sxs-lookup"><span data-stu-id="8c748-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="8c748-119">Herramienta de carga y rendimiento del cliente de la versión del cliente</span><span class="sxs-lookup"><span data-stu-id="8c748-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="8c748-120">Es posible que tenga que configurar la Directiva de comprobación de versión del cliente si ha cambiado la configuración de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8c748-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="8c748-121">Para obtener más información, consulte "configurar versiones de cliente <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>admitidas" en.</span><span class="sxs-lookup"><span data-stu-id="8c748-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="8c748-122">La herramienta de estrés y rendimiento de Lync Server 2013 usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="8c748-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="8c748-123">LSPT/15.0.0.0 (herramienta Lync Server 2013 stress and Performance)</span><span class="sxs-lookup"><span data-stu-id="8c748-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="8c748-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="8c748-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="8c748-125">Estos son para el cliente de Mobility (UCWA) en LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="8c748-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="8c748-126">Herramienta de rendimiento de Ucwa y conferencia Web</span><span class="sxs-lookup"><span data-stu-id="8c748-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="8c748-127">Herramienta de Perf de Ucwa/móvil</span><span class="sxs-lookup"><span data-stu-id="8c748-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

