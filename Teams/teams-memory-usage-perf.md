---
title: Cómo usa Microsoft Teams la memoria
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Cómo Microsoft Teams usa la memoria del sistema y por qué el uso de la memoria es idéntico entre la aplicación de escritorio y la aplicación Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05cbd2f4b6691c873393a7ba711e03aadf70a2f2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836990"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="1c785-103">Cómo usa Microsoft Teams la memoria</span><span class="sxs-lookup"><span data-stu-id="1c785-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="1c785-104">Algunos usuarios de Microsoft Teams tienen preguntas sobre cómo usa la memoria los equipos.</span><span class="sxs-lookup"><span data-stu-id="1c785-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="1c785-105">En este artículo se describe cómo se usa la memoria por parte de Teams y por qué la aplicación de escritorio de Teams (aplicación) y la aplicación Web de Teams no evitan que otras aplicaciones y cargas de trabajo del mismo equipo tengan suficiente memoria para funcionar de manera óptima.</span><span class="sxs-lookup"><span data-stu-id="1c785-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="1c785-106">Teams está diseñado para usar la tecnología moderna de Internet.</span><span class="sxs-lookup"><span data-stu-id="1c785-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="1c785-107">Para lograr esto, el cliente de escritorio de Teams se desarrolló en electrones, que usa cromo para la representación.</span><span class="sxs-lookup"><span data-stu-id="1c785-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="1c785-108">Este es el mismo motor de representación tras muchos de los exploradores más populares de hoy, incluidos Edge y Chrome.</span><span class="sxs-lookup"><span data-stu-id="1c785-108">This is the same rendering engine behind many of today’s most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="1c785-109">Cómo funciona Teams</span><span class="sxs-lookup"><span data-stu-id="1c785-109">How Teams works</span></span>

<span data-ttu-id="1c785-110">Los equipos diseñados en electrones permiten un desarrollo más rápido y también mantienen la paridad entre las versiones de Teams en diferentes sistemas operativos (Windows, Mac y Linux).</span><span class="sxs-lookup"><span data-stu-id="1c785-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="1c785-111">Esta paridad es posible porque los electrones y el cromo mantienen una base de código similar en todas las versiones.</span><span class="sxs-lookup"><span data-stu-id="1c785-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="1c785-112">Otra ventaja de esta arquitectura es que hay un perfil de uso de memoria similar entre Team Web App y la versión de escritorio.</span><span class="sxs-lookup"><span data-stu-id="1c785-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="1c785-113">Tanto la aplicación web como las versiones de escritorio usan la memoria de forma similar a como las usaría un explorador.</span><span class="sxs-lookup"><span data-stu-id="1c785-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="1c785-114">Puede obtener más información acerca de electrones en [su sitio web](https://electronjs.org/).</span><span class="sxs-lookup"><span data-stu-id="1c785-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="1c785-115">Para obtener más información, consulta [uso de memoria de cromo](https://www.chromium.org/developers/memory-usage-backgrounder) y [conceptos clave en la memoria de Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) .</span><span class="sxs-lookup"><span data-stu-id="1c785-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="1c785-116">La imagen siguiente muestra usos de memoria en paralelo de la aplicación de escritorio de Teams para Windows y Teams Web App (en este ejemplo, ejecutar Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="1c785-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Uso de memoria de la aplicación de escritorio de Teams y de la aplicación Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="1c785-118">Uso de memoria en Teams</span><span class="sxs-lookup"><span data-stu-id="1c785-118">Memory usage in Teams</span></span>

<span data-ttu-id="1c785-119">Es importante comprender el comportamiento *esperado* de los equipos cuando se trata de la memoria del sistema y conocer los síntomas de problemas de memoria del sistema verdaderamente problemáticos.</span><span class="sxs-lookup"><span data-stu-id="1c785-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="1c785-120">Uso de memoria previsto por los equipos</span><span class="sxs-lookup"><span data-stu-id="1c785-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="1c785-121">Si está ejecutando la aplicación de escritorio de Teams o la aplicación Web de Teams, el cromo detecta la cantidad de memoria disponible en el sistema y usa la suficiente memoria para optimizar la experiencia de representación.</span><span class="sxs-lookup"><span data-stu-id="1c785-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="1c785-122">Cuando otras aplicaciones o servicios requieren memoria del sistema, cromo da memoria a esos procesos.</span><span class="sxs-lookup"><span data-stu-id="1c785-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="1c785-123">Cromo ajusta el uso de memoria de Teams de manera continua para optimizar el rendimiento de los equipos sin afectar a nada que se esté ejecutando en ese momento.</span><span class="sxs-lookup"><span data-stu-id="1c785-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="1c785-124">De esta manera, las cargas de trabajo de cromo similares pueden usar cantidades variables de memoria, según la cantidad de memoria del sistema que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="1c785-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="1c785-125">En el siguiente gráfico se muestra el uso de memoria por parte de Teams en cuatro sistemas diferentes, cada uno con diferentes cantidades de memoria disponibles.</span><span class="sxs-lookup"><span data-stu-id="1c785-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="1c785-126">Cada uno de los sistemas está procesando cargas de trabajo similares (las mismas aplicaciones se abren y se ejecutan).</span><span class="sxs-lookup"><span data-stu-id="1c785-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Uso de memoria de Teams en diferentes sistemas](media/teams-memory-usage.png)

<span data-ttu-id="1c785-128">Cuando los equipos tengan más memoria, Teams usará esa memoria.</span><span class="sxs-lookup"><span data-stu-id="1c785-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="1c785-129">En sistemas en los que la memoria es escasa, Teams usará menos.</span><span class="sxs-lookup"><span data-stu-id="1c785-129">In systems where memory is scarce, Teams will use less.</span></span> 

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="1c785-130">Síntomas de problemas de memoria del sistema</span><span class="sxs-lookup"><span data-stu-id="1c785-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="1c785-131">Si ve uno o varios de los síntomas siguientes en el equipo, puede tener un problema de memoria del sistema grave:</span><span class="sxs-lookup"><span data-stu-id="1c785-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="1c785-132">Uso de memoria alta cuando se ejecutan varias aplicaciones grandes de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="1c785-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="1c785-133">El rendimiento del sistema o las aplicaciones están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="1c785-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="1c785-134">Uso sostenido general de la memoria del sistema de 90% o superior en todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1c785-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="1c785-135">Con esta cantidad de memoria, los equipos deberían devolver memoria a otras aplicaciones y cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1c785-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="1c785-136">El uso sostenido de la memoria de 90% podría significar que los equipos no devuelven memoria al sistema, lo que indica un problema.</span><span class="sxs-lookup"><span data-stu-id="1c785-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="1c785-137">Las siguientes imágenes muestran ejemplos de vistas en el administrador de tareas cuando el uso de memoria del sistema es anormalmente alto.</span><span class="sxs-lookup"><span data-stu-id="1c785-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Vista de uso de memoria de Teams en el administrador de tareas](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso de memoria de Teams en el administrador de tareas](media/teams-memory-high-mem-process-list2.png)
