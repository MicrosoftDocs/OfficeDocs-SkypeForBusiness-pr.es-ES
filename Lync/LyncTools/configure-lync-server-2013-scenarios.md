---
title: Configuración de escenarios de 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60da62851580487ea04dd1797ed91a1f8acd251b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="5ef96-102">Configuración de escenarios de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5ef96-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ef96-103">_**Última modificación del tema:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="5ef96-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="5ef96-104">Para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013 (LyncPerfTool), la topología de Lync Server 2013 debe estar configurada primero para los escenarios que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="5ef96-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="5ef96-105">Si Lync Server 2013 no está configurado o está configurado incorrectamente, se producirá un error en la simulación de carga en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="5ef96-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="5ef96-106">Con la herramienta stress and performance de Lync Server 2013, se proporcionan ejemplos de scripts del shell de administración de Lync Server y archivos de recursos básicos que se pueden usar como punto de partida para configurar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ef96-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="5ef96-107">En este tema se describen los ejemplos de Windows PowerShell proporcionados.</span><span class="sxs-lookup"><span data-stu-id="5ef96-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="5ef96-108">Tenga en cuenta que no es el objetivo de este tema describir cómo configurar Lync Server 2013 en general.</span><span class="sxs-lookup"><span data-stu-id="5ef96-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="5ef96-109">Para más detalles sobre cómo trabajar con Windows PowerShell en Lync Server 2013, consulte la documentación del shell de <https://technet.microsoft.com/library/gg398474.aspx>administración de Lync Server en.</span><span class="sxs-lookup"><span data-stu-id="5ef96-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="5ef96-110">Acerca de la ejecución de scripts del shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5ef96-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="5ef96-111">Hemos proporcionado ejemplos de scripts del shell de administración de Lync Server que se pueden usar para preparar la ejecución de la simulación de carga.</span><span class="sxs-lookup"><span data-stu-id="5ef96-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="5ef96-112">Debido a que los scripts están diseñados para la simulación de carga, son sencillos y permisivos y, por lo tanto, no son adecuados para la producción.</span><span class="sxs-lookup"><span data-stu-id="5ef96-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="5ef96-113">Todos los scripts son ejemplos y deben revisarse y, en algunos casos, se pueden modificar para reflejar la topología.</span><span class="sxs-lookup"><span data-stu-id="5ef96-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="5ef96-114">Como mínimo, esperamos que el escenario del servicio de grupo de respuesta (RGS) deba modificarse para especificar los agentes que se asignan a los grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="5ef96-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="5ef96-115">Sin embargo, tiene la opción de no simular esta carga.</span><span class="sxs-lookup"><span data-stu-id="5ef96-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5ef96-116">Tenga cuidado al revisar y comprender los ejemplos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="5ef96-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="5ef96-117">Los scripts sobrescribirán la configuración existente en la topología.</span><span class="sxs-lookup"><span data-stu-id="5ef96-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5ef96-118">Para más información sobre el uso de Windows PowerShell y el shell de administración de Lync Server, vea el blog de <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>lync Server 2013 Windows PowerShell en.</span><span class="sxs-lookup"><span data-stu-id="5ef96-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="5ef96-119">Herramienta de esfuerzo y rendimiento de la versión del cliente de la herramienta</span><span class="sxs-lookup"><span data-stu-id="5ef96-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="5ef96-120">Es posible que tenga que configurar la Directiva de comprobación de versión de cliente si ha cambiado la configuración de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5ef96-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="5ef96-121">Para obtener más información, consulte "configuración de versiones de <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>cliente admitidas" en.</span><span class="sxs-lookup"><span data-stu-id="5ef96-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="5ef96-122">La herramienta stress and performance de Lync Server 2013 usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="5ef96-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="5ef96-123">LSPT/15.0.0.0 (herramienta de esfuerzo y rendimiento de Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="5ef96-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="5ef96-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="5ef96-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="5ef96-125">Estas son para el cliente de movilidad (UCWA) en LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="5ef96-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="5ef96-126">Conferencia de rendimiento de Ucwa Tool/Web</span><span class="sxs-lookup"><span data-stu-id="5ef96-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="5ef96-127">Herramienta de Perf de Ucwa/móvil</span><span class="sxs-lookup"><span data-stu-id="5ef96-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

