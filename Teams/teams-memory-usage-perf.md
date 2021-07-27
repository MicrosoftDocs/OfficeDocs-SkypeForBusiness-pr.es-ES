---
title: Cómo usa Microsoft Teams la memoria
author: msdmaguire
ms.author: serdars
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
ms.openlocfilehash: d3e694dcba73cd90b2faa131776210c5d3faf4d5
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587319"
---
# <a name="how-microsoft-teams-uses-memory"></a>Cómo usa Microsoft Teams la memoria

Algunos Microsoft Teams usuarios tienen preguntas sobre cómo usar Teams memoria. En este artículo se describe cómo Teams usa la memoria y por qué la aplicación de escritorio (aplicación) de Teams y la aplicación web de Teams no impiden que otras aplicaciones y cargas de trabajo del mismo equipo tengan memoria suficiente para ejecutarse de forma óptima. Teams está diseñado para usar tecnología web moderna. Para ello, el Teams de escritorio se ha desarrollado en Electron, que usa Chromium para la representación. Este es el mismo motor de representación detrás de muchos de los exploradores más populares de hoy en día, incluidos Edge y Chrome.

## <a name="how-teams-works"></a>Cómo Teams funciona

Teams diseño en Electron permite un desarrollo más rápido y también mantiene la paridad entre las versiones Teams en diferentes sistemas operativos (Windows, Mac y Linux). Esta paridad es posible porque Electron y Chromium una base de código similar en todas las versiones. Otra ventaja de esta arquitectura es que hay un perfil de uso de memoria similar entre la Teams web y la versión de escritorio. Tanto la aplicación web como las versiones de escritorio usan la memoria de forma similar a como lo usaría un explorador. Más información sobre Electron está disponible en [su sitio web.](https://electronjs.org/)

Vea [Chromium uso de memoria](https://www.chromium.org/developers/memory-usage-backgrounder) y [conceptos clave en la memoria chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obtener más información.

La siguiente imagen muestra los usos de memoria en paralelo de la aplicación de escritorio Teams para Windows y la aplicación web Teams (en este ejemplo, ejecutándose en Google Chrome).

![Teams de memoria para la aplicación de escritorio y la aplicación web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso de memoria en Teams

Es importante comprender  el comportamiento esperado de Teams en lo que respecta a la memoria del sistema y conocer los síntomas de problemas de memoria del sistema realmente problemáticos.

### <a name="expected-memory-usage-by-teams"></a>Uso de memoria esperado por Teams

Tanto si ejecuta la aplicación de escritorio Teams como la aplicación web de Teams, Chromium detecta la cantidad de memoria del sistema disponible y usa suficiente memoria para optimizar la experiencia de representación. Cuando otras aplicaciones o servicios requieren memoria del sistema, Chromium memoria a esos procesos. Chromium de Teams de memoria de forma continua para optimizar el rendimiento de Teams sin afectar a nada más que se esté ejecutando actualmente.

De este modo, Chromium cargas de trabajo similares pueden usar distintas cantidades de memoria, dependiendo de la cantidad de memoria del sistema disponible.

En el siguiente gráfico se muestra el uso de la memoria Teams en cuatro sistemas independientes, cada uno con diferentes cantidades de memoria disponibles. Cada uno de los sistemas está procesando cargas de trabajo similares (las mismas aplicaciones abiertas y en ejecución).

![Teams de memoria en diferentes sistemas](media/teams-memory-usage.png)

Cuando los equipos tienen más memoria, Teams usarán esa memoria. En sistemas donde la memoria es escasa, Teams usarán menos.

### <a name="symptoms-of-system-memory-issues"></a>Síntomas de problemas de memoria del sistema

Si ve uno o varios de los siguientes síntomas en el equipo, podría tener un problema grave de memoria del sistema:

- Uso de memoria alta cuando varias aplicaciones de gran tamaño se ejecutan simultáneamente.
- Rendimiento del sistema lento o aplicaciones que se cuelgan.
- Uso de memoria general del sistema sostenida del 90 % o superior en todas las aplicaciones. Con esta cantidad de uso de memoria, Teams debería devolver la memoria a otras aplicaciones y cargas de trabajo. El uso de memoria sostenida del 90 % podría significar que Teams no está regresando memoria al sistema, lo que indica un problema.

Las siguientes imágenes muestran ejemplos de vistas en el Administrador de tareas cuando el uso de memoria del sistema es anormalmente alto.

![Teams de uso de memoria en el Administrador de tareas](media/teams-memory-high-mem-process-list.png)

![Teams gráfico de uso de memoria en el Administrador de tareas](media/teams-memory-high-mem-process-list2.png)
