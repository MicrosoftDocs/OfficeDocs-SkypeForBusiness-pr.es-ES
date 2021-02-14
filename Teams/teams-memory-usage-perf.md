---
title: Cómo usa Microsoft Teams la memoria
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Obtenga información sobre el uso de memoria del sistema de Microsoft Teams y por qué el uso de memoria es el mismo entre la aplicación de escritorio y la aplicación web.
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
# <a name="how-microsoft-teams-uses-memory"></a>Cómo usa Microsoft Teams la memoria

Algunos usuarios de Microsoft Teams tienen preguntas sobre cómo Teams usa la memoria. En este artículo se describe cómo teams usa la memoria y por qué la aplicación de escritorio (aplicación) de Teams y la aplicación web de Teams no impiden que otras aplicaciones y cargas de trabajo en el mismo equipo tengan suficiente memoria para ejecutarse de forma óptima. Teams está diseñado para usar la tecnología web moderna. Para ello, el cliente de escritorio de Teams se ha desarrollado en Electron, que usa Chromium para la representación. Se trata del mismo motor de representación que está detrás de muchos de los exploradores más populares de hoy en día, como Edge y Chrome.

## <a name="how-teams-works"></a>Cómo funciona Teams

Teams diseñado en Electron permite un desarrollo más rápido y también mantiene la paridad entre las versiones de Teams en diferentes sistemas operativos (Windows, Mac y Linux). Esta paridad es posible porque Electron y Chromium mantienen una base de código similar en todas las versiones. Otra ventaja de esta arquitectura es que hay un perfil de uso de memoria similar entre la aplicación web de Teams y la versión de escritorio. Tanto la aplicación web como las versiones de escritorio usan memoria de forma similar a como la usaría un explorador. Puede obtener más información sobre Electron en [su sitio web.](https://electronjs.org/)

Para [obtener más información,](https://www.chromium.org/developers/memory-usage-backgrounder) consulta Conceptos clave y uso de memoria de Chromium en la memoria de [Chrome.](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)

La imagen siguiente muestra los usos de memoria en paralelo de la aplicación de escritorio de Teams para Windows y la aplicación web de Teams (en este ejemplo, en Google Chrome).

![Uso de memoria de Teams para la aplicación de escritorio y la aplicación web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso de memoria en Teams

Es importante comprender  el comportamiento esperado de Teams en lo que respecta a la memoria del sistema y conocer los síntomas de problemas de memoria del sistema realmente problemáticos.

### <a name="expected-memory-usage-by-teams"></a>Uso de memoria esperado por Teams

Tanto si ejecuta la aplicación de escritorio de Teams como la aplicación web de Teams, Chromium detecta la cantidad de memoria del sistema disponible y utiliza suficiente memoria para optimizar la experiencia de representación. Cuando otras aplicaciones o servicios requieren memoria del sistema, Chromium entrega memoria a esos procesos. Chromium canda el uso de memoria de Teams de forma continua con el fin de optimizar el rendimiento de Teams sin que nada más se esté ejecutando actualmente.

De esta forma, las cargas de trabajo similares de Chromium pueden usar diferentes cantidades de memoria, dependiendo de la cantidad de memoria del sistema que esté disponible.

El siguiente gráfico muestra el uso de memoria de Teams en cuatro sistemas independientes, cada uno con diferentes cantidades de memoria disponibles. Cada uno de los sistemas está procesando cargas de trabajo similares (las mismas aplicaciones se abren y se ejecutan).

![Uso de memoria de Teams en diferentes sistemas](media/teams-memory-usage.png)

Cuando los equipos tengan más memoria, Teams usará esa memoria. En los sistemas en los que la memoria es dinámica, Teams usará menos.

### <a name="symptoms-of-system-memory-issues"></a>Síntomas de problemas de memoria del sistema

Si ve uno o varios de los síntomas siguientes en el equipo, podría tener un problema grave de memoria del sistema:

- Uso de alta memoria cuando se ejecutan varias aplicaciones de gran tamaño al mismo tiempo.
- Rendimiento lento del sistema o aplicaciones que se cuelgan.
- Uso de memoria general sostenida del sistema del 90 % o superior en todas las aplicaciones. Con esta cantidad de uso de memoria, Teams debería devolver memoria a otras aplicaciones y cargas de trabajo. El uso de memoria sostenida del 90 % podría significar que Teams no está dando memoria al sistema, lo que indica un problema.

Las siguientes imágenes muestran ejemplos de vistas en el Administrador de tareas cuando el uso de memoria del sistema es anormalmente alto.

![Vista uso de memoria de Teams en el Administrador de tareas](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso de memoria de Teams en el Administrador de tareas](media/teams-memory-high-mem-process-list2.png)
