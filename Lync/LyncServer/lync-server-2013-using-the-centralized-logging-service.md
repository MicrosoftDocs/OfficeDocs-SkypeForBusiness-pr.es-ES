---
title: 'Lync Server 2013: uso del servicio de registro centralizado'
description: 'Lync Server 2013: uso del servicio de registro centralizado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8b9edf839de889e9f0b01c10311f6b5c70ced8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548526"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="d29c7-103">Uso del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-103">Using the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d29c7-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d29c7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d29c7-105">El servicio de registro centralizado es una nueva característica de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d29c7-105">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="d29c7-106">Es un reemplazo mejorado para las herramientas **OCSLogger** y **OCSTracer** que se proporcionaron en las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="d29c7-106">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="d29c7-107">Puede usar el servicio de registro centralizado para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d29c7-107">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="d29c7-108">Comience por iniciar sesión en uno o más PC y grupos desde una sola ubicación y comando.</span><span class="sxs-lookup"><span data-stu-id="d29c7-108">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="d29c7-109">No inicie sesión en una o más PC y grupos desde una sola ubicación y comando.</span><span class="sxs-lookup"><span data-stu-id="d29c7-109">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="d29c7-p102">Busque registros en una o más PC y grupos para una sola ubicación y comando. Puede personalizar el comando de búsqueda para que devuelva toda la suma de registros que se capturaron y almacenaron en todos los PC o devolver un resultado recortado que captura la información específica.</span><span class="sxs-lookup"><span data-stu-id="d29c7-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="d29c7-112">Configurar las sesiones de registro de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d29c7-112">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="d29c7-113">Defina un **Escenario** o use un escenario predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d29c7-113">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="d29c7-114">Un *escenario* en el servicio de registro centralizado se compone de ámbito (global o sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores.</span><span class="sxs-lookup"><span data-stu-id="d29c7-114">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="d29c7-115">Puede ejecutar dos escenarios en cualquier momento en una computadora.</span><span class="sxs-lookup"><span data-stu-id="d29c7-115">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="d29c7-p104">Use un *proveedor* existente o cree un nuevo proveedor. Un *proveedor* define qué sesión de registro recopila, qué nivel de detalle, qué componentes seguirá y qué marcas se aplican.</span><span class="sxs-lookup"><span data-stu-id="d29c7-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="d29c7-118">Si conoce el OCSLogger, el término <EM>proveedores</EM> hace referencia a la colección de <STRONG>componentes</STRONG> (por ejemplo, S4, SIPStack), un <STRONG>tipo de registro</STRONG> (por ejemplo, WPP, EventLog o IIS logfile), un <STRONG>nivel de seguimiento</STRONG> (por ejemplo, Todo, Detallado, depuración) y <STRONG>marcas</STRONG> (por ejemplo, TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="d29c7-118">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="d29c7-119">Estos elementos se definen en el proveedor (una variable de Windows PowerShell) y se pasan al comando del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="d29c7-119">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="d29c7-120">Configurar los PC y grupos desde donde desea recopilar los registros.</span><span class="sxs-lookup"><span data-stu-id="d29c7-120">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="d29c7-121">Defina el ámbito de la sesión de registro desde las opciones **Sitio** (ejecutar las capturas de registro en los PC solo en ese sitio) o **Global** (ejecutar las capturas de registro en todas los PC de la implementación).</span><span class="sxs-lookup"><span data-stu-id="d29c7-121">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="d29c7-122">El servicio de registro centralizado es extremadamente eficaz y puede satisfacer casi todas las necesidades de solución de problemas, tanto grandes como pequeñas.</span><span class="sxs-lookup"><span data-stu-id="d29c7-122">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="d29c7-123">Desde el análisis de causa raíz a problemas de rendimiento, el servicio de registro centralizado puede ser una herramienta importante para los administradores.</span><span class="sxs-lookup"><span data-stu-id="d29c7-123">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="d29c7-124">Todos los ejemplos se muestran con el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d29c7-124">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="d29c7-125">Hay un componente de línea de comandos para el servicio de registro centralizado denominado **CLSController.exe**.</span><span class="sxs-lookup"><span data-stu-id="d29c7-125">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="d29c7-126">Se proporciona ayuda para la herramienta de la línea de comandos a través de la misma herramienta.</span><span class="sxs-lookup"><span data-stu-id="d29c7-126">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="d29c7-127">Sin embargo, existe una cantidad limitada de funciones que puede ejecutar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d29c7-127">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="d29c7-128">Mediante el shell de administración de Lync Server, tiene acceso a un conjunto de características mucho más amplio y mucho más configurable.</span><span class="sxs-lookup"><span data-stu-id="d29c7-128">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="d29c7-129">Debe considerar siempre el shell de administración de Lync Server como el primer y más importante método al usar el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="d29c7-129">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="d29c7-130">En los temas de esta sección se explica cómo usar el servicio de registro centralizado y ejemplos de cómo usar sus numerosas características.</span><span class="sxs-lookup"><span data-stu-id="d29c7-130">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d29c7-131">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d29c7-131">In This Section</span></span>

  - [<span data-ttu-id="d29c7-132">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-132">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="d29c7-133">Administración de las opciones de configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-133">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="d29c7-134">Información sobre las opciones de configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-134">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="d29c7-135">Uso de inicio para el servicio de registro centralizado para capturar registros en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-135">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="d29c7-136">Uso de STOP para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-136">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="d29c7-137">Uso de la búsqueda en registros de captura creados por el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-137">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="d29c7-138">Lectura de registros de captura desde el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d29c7-138">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

