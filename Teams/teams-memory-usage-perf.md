---
title: Cómo usa Microsoft Teams la memoria
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Obtenga información sobre Microsoft Teams de memoria del sistema y por qué el uso de memoria es el mismo entre la aplicación de escritorio y la aplicación web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878724"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="b3c41-103">Cómo usa Microsoft Teams la memoria</span><span class="sxs-lookup"><span data-stu-id="b3c41-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="b3c41-104">Algunos Microsoft Teams usuarios tienen preguntas sobre cómo usar Teams memoria.</span><span class="sxs-lookup"><span data-stu-id="b3c41-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="b3c41-105">En este artículo se describe cómo Teams usa la memoria y por qué la aplicación de escritorio (aplicación) de Teams y la aplicación web de Teams no impiden que otras aplicaciones y cargas de trabajo del mismo equipo tengan memoria suficiente para ejecutarse de forma óptima.</span><span class="sxs-lookup"><span data-stu-id="b3c41-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="b3c41-106">Teams está diseñado para usar tecnología web moderna.</span><span class="sxs-lookup"><span data-stu-id="b3c41-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="b3c41-107">Para ello, el Teams de escritorio se ha desarrollado en Electron, que usa Chromium para la representación.</span><span class="sxs-lookup"><span data-stu-id="b3c41-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="b3c41-108">Este es el mismo motor de representación detrás de muchos de los exploradores más populares de hoy en día, incluidos Edge y Chrome.</span><span class="sxs-lookup"><span data-stu-id="b3c41-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="b3c41-109">Cómo Teams funciona</span><span class="sxs-lookup"><span data-stu-id="b3c41-109">How Teams works</span></span>

<span data-ttu-id="b3c41-110">Teams diseño en Electron permite un desarrollo más rápido y también mantiene la paridad entre las versiones Teams en diferentes sistemas operativos (Windows, Mac y Linux).</span><span class="sxs-lookup"><span data-stu-id="b3c41-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="b3c41-111">Esta paridad es posible porque Electron y Chromium una base de código similar en todas las versiones.</span><span class="sxs-lookup"><span data-stu-id="b3c41-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="b3c41-112">Otra ventaja de esta arquitectura es que hay un perfil de uso de memoria similar entre la Teams web y la versión de escritorio.</span><span class="sxs-lookup"><span data-stu-id="b3c41-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="b3c41-113">Tanto la aplicación web como las versiones de escritorio usan la memoria de forma similar a como lo usaría un explorador.</span><span class="sxs-lookup"><span data-stu-id="b3c41-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="b3c41-114">Más información sobre Electron está disponible en [su sitio web.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="b3c41-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="b3c41-115">Vea [Chromium uso de memoria](https://www.chromium.org/developers/memory-usage-backgrounder) y [conceptos clave en la memoria chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b3c41-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="b3c41-116">La siguiente imagen muestra los usos de memoria en paralelo de la aplicación de escritorio Teams para Windows y la aplicación web Teams (en este ejemplo, ejecutándose en Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="b3c41-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams de memoria para la aplicación de escritorio y la aplicación web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="b3c41-118">Uso de memoria en Teams</span><span class="sxs-lookup"><span data-stu-id="b3c41-118">Memory usage in Teams</span></span>

<span data-ttu-id="b3c41-119">Es importante comprender  el comportamiento esperado de Teams en lo que respecta a la memoria del sistema y conocer los síntomas de problemas de memoria del sistema realmente problemáticos.</span><span class="sxs-lookup"><span data-stu-id="b3c41-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="b3c41-120">Uso de memoria esperado por Teams</span><span class="sxs-lookup"><span data-stu-id="b3c41-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="b3c41-121">Tanto si ejecuta la aplicación de escritorio Teams como la aplicación web de Teams, Chromium detecta la cantidad de memoria del sistema disponible y usa suficiente memoria para optimizar la experiencia de representación.</span><span class="sxs-lookup"><span data-stu-id="b3c41-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="b3c41-122">Cuando otras aplicaciones o servicios requieren memoria del sistema, Chromium memoria a esos procesos.</span><span class="sxs-lookup"><span data-stu-id="b3c41-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="b3c41-123">Chromium de Teams de memoria de forma continua para optimizar el rendimiento de Teams sin afectar a nada más que se esté ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="b3c41-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="b3c41-124">De este modo, Chromium cargas de trabajo similares pueden usar distintas cantidades de memoria, dependiendo de la cantidad de memoria del sistema disponible.</span><span class="sxs-lookup"><span data-stu-id="b3c41-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="b3c41-125">En el siguiente gráfico se muestra el uso de la memoria Teams en cuatro sistemas independientes, cada uno con diferentes cantidades de memoria disponibles.</span><span class="sxs-lookup"><span data-stu-id="b3c41-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="b3c41-126">Cada uno de los sistemas está procesando cargas de trabajo similares (las mismas aplicaciones abiertas y en ejecución).</span><span class="sxs-lookup"><span data-stu-id="b3c41-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Teams de memoria en diferentes sistemas](media/teams-memory-usage.png)

<span data-ttu-id="b3c41-128">Cuando los equipos tienen más memoria, Teams usarán esa memoria.</span><span class="sxs-lookup"><span data-stu-id="b3c41-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="b3c41-129">En sistemas donde la memoria es escasa, Teams usarán menos.</span><span class="sxs-lookup"><span data-stu-id="b3c41-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="b3c41-130">Síntomas de problemas de memoria del sistema</span><span class="sxs-lookup"><span data-stu-id="b3c41-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="b3c41-131">Si ve uno o varios de los siguientes síntomas en el equipo, podría tener un problema grave de memoria del sistema:</span><span class="sxs-lookup"><span data-stu-id="b3c41-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="b3c41-132">Uso de memoria alta cuando varias aplicaciones de gran tamaño se ejecutan simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="b3c41-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="b3c41-133">Rendimiento del sistema lento o aplicaciones que se cuelgan.</span><span class="sxs-lookup"><span data-stu-id="b3c41-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="b3c41-134">Uso de memoria general del sistema sostenida del 90 % o superior en todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b3c41-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="b3c41-135">Con esta cantidad de uso de memoria, Teams debería devolver la memoria a otras aplicaciones y cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b3c41-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="b3c41-136">El uso de memoria sostenida del 90 % podría significar que Teams no está regresando memoria al sistema, lo que indica un problema.</span><span class="sxs-lookup"><span data-stu-id="b3c41-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="b3c41-137">Las siguientes imágenes muestran ejemplos de vistas en el Administrador de tareas cuando el uso de memoria del sistema es anormalmente alto.</span><span class="sxs-lookup"><span data-stu-id="b3c41-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Teams de uso de memoria en el Administrador de tareas](media/teams-memory-high-mem-process-list.png)

![Teams gráfico de uso de memoria en el Administrador de tareas](media/teams-memory-high-mem-process-list2.png)
