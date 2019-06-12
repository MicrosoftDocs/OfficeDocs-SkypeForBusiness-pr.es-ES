---
title: 'Lync Server 2013: usar el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b5e4e2582c7b1738f0a6072197643f4df99238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="89f6d-102">Usar el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89f6d-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="89f6d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="89f6d-104">El servicio de registro centralizado es una nueva característica de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89f6d-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="89f6d-105">Se trata de una sustitución mejorada para las herramientas **OCSLogger** y **OCSTracer** que se proporcionaron en versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="89f6d-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="89f6d-106">Puede usar el servicio de registro centralizado para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="89f6d-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="89f6d-107">Iniciar el registro en uno o más equipos y grupos de repositorios desde una sola ubicación y un mismo comando.</span><span class="sxs-lookup"><span data-stu-id="89f6d-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="89f6d-108">Detener el registro de uno o varios equipos y grupos desde una única ubicación y comando.</span><span class="sxs-lookup"><span data-stu-id="89f6d-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="89f6d-109">Buscar registros en uno o más equipos y grupos para una única ubicación y un comando.</span><span class="sxs-lookup"><span data-stu-id="89f6d-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="89f6d-110">Puede personalizar el comando de búsqueda para que devuelva toda la agregación de registros que se han capturado y almacenado en todos los equipos, o bien devolver un resultado recortado que captura datos específicos.</span><span class="sxs-lookup"><span data-stu-id="89f6d-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="89f6d-111">Configure las sesiones de registro de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="89f6d-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="89f6d-112">Defina un **Escenario** o use un escenario predeterminado.</span><span class="sxs-lookup"><span data-stu-id="89f6d-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="89f6d-113">Un *escenario* en el servicio de registro centralizado está formado por ámbito (global o sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores.</span><span class="sxs-lookup"><span data-stu-id="89f6d-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="89f6d-114">Puede ejecutar dos escenarios en cualquier momento en un equipo.</span><span class="sxs-lookup"><span data-stu-id="89f6d-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="89f6d-p104">Use un *proveedor* existente o cree uno. Un *proveedor* define qué recopila la sesión de registro, su nivel de detalle, qué componentes seguirá y qué marcas se aplican.</span><span class="sxs-lookup"><span data-stu-id="89f6d-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="89f6d-117">Si conoce OCSLogger, el término <EM>proveedores</EM> hace referencia a la colección de <STRONG>componentes</STRONG> (por ejemplo, S4, SIPStack), un <STRONG>tipo de registro</STRONG> (por ejemplo, WPP, EventLog o IIS logfile), un <STRONG>nivel de seguimiento</STRONG> (por ejemplo, Todo, Detallado, Depuración) y las <STRONG>marcas</STRONG> (por ejemplo, TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="89f6d-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="89f6d-118">Estos elementos se definen en el proveedor (una variable de Windows PowerShell) y se pasan al comando del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="89f6d-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="89f6d-119">Configure los equipos y grupos de los que desea recopilar registros.</span><span class="sxs-lookup"><span data-stu-id="89f6d-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="89f6d-120">Defina el ámbito de la sesión de registro en el **sitio** de opciones (ejecutar registro de capturas en equipos de ese sitio solo) o **global** (ejecutar captura de registro en todos los equipos de la implementación).</span><span class="sxs-lookup"><span data-stu-id="89f6d-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="89f6d-121">El servicio de registro centralizado es extremadamente eficaz y puede cumplir casi todas las necesidades de solución de problemas de solución de problemas: grande o pequeño.</span><span class="sxs-lookup"><span data-stu-id="89f6d-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="89f6d-122">Desde el análisis de causa raíz hasta problemas de rendimiento, el servicio de registro centralizado puede ser una herramienta importante para cualquier administrador.</span><span class="sxs-lookup"><span data-stu-id="89f6d-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="89f6d-123">Se muestran todos los ejemplos con el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f6d-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="89f6d-124">Hay un componente de línea de comandos para el servicio de registro centralizado denominado **CLSController. exe**.</span><span class="sxs-lookup"><span data-stu-id="89f6d-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="89f6d-125">La herramienta de línea de comandos proporciona ayuda a través de la propia herramienta.</span><span class="sxs-lookup"><span data-stu-id="89f6d-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="89f6d-126">Sin embargo, hay un conjunto limitado de funciones que puede ejecutar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="89f6d-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="89f6d-127">Mediante el shell de administración de Lync Server, tiene acceso a un conjunto de características mucho más amplio y configurable.</span><span class="sxs-lookup"><span data-stu-id="89f6d-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="89f6d-128">Siempre debe considerar el shell de administración de Lync Server como el primer y más importante método al usar el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="89f6d-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="89f6d-129">En los temas de esta sección se explica cómo usar el servicio de registro centralizado y ejemplos de uso de sus numerosas características.</span><span class="sxs-lookup"><span data-stu-id="89f6d-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89f6d-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="89f6d-130">In This Section</span></span>

  - [<span data-ttu-id="89f6d-131">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="89f6d-132">Administración de la configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="89f6d-133">Descripción de la configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="89f6d-134">Uso de iniciar para el servicio de registro centralizado para capturar registros en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="89f6d-135">Usar detener para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="89f6d-136">Usar la búsqueda en registros de captura creados por el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="89f6d-137">Lectura de registros de captura del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f6d-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

