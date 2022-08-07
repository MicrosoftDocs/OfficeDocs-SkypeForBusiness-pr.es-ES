---
title: Cómo usa Microsoft Teams la memoria
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Obtenga información sobre el uso de memoria del sistema de Microsoft Teams y por qué el uso de memoria es el mismo entre la aplicación de escritorio y la aplicación web.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: cb2405c50d758c5879bcc44451a0ce9c50a7d614
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268145"
---
# <a name="how-microsoft-teams-uses-memory"></a>Cómo usa Microsoft Teams la memoria

Algunos usuarios de Microsoft Teams tienen preguntas sobre cómo Teams usa la memoria. En este artículo se describe cómo usa Teams la memoria y por qué la aplicación de escritorio (aplicación) de Teams y la aplicación web de Teams no impiden que otras aplicaciones y cargas de trabajo del mismo equipo tengan suficiente memoria para ejecutarse de forma óptima. Teams está diseñado para usar la tecnología web moderna. Para conseguirlo, el cliente de escritorio de Teams se desarrolló en Electron, que utiliza Chromium para la representación. Este es el mismo motor de representación detrás de muchos de los exploradores más populares de hoy en día, como Edge y Chrome.

## <a name="how-teams-works"></a>Cómo funciona Teams

El diseño de Teams en Electrones permite un desarrollo más rápido y también mantiene la paridad entre las versiones de Teams en diferentes sistemas operativos (Windows, Mac y Linux). Esta paridad es posible porque Electron y Chromium mantener una base de código similar en todas las versiones. Otra ventaja de esta arquitectura es que hay un perfil de uso de memoria similar entre la aplicación web de Teams y la versión de escritorio. Tanto la aplicación web como las versiones de escritorio usan la memoria de forma similar a como la usaría un explorador. Más información sobre Electron está disponible en [su sitio web](https://electronjs.org/).

Consulta [Chromium uso de memoria](https://www.chromium.org/developers/memory-usage-backgrounder) y [conceptos clave en la memoria de Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obtener más información.

La imagen siguiente muestra los usos de memoria en paralelo de la aplicación de escritorio de Teams para Windows y la aplicación web de Teams (en este ejemplo, que se ejecuta en Google Chrome).

![Uso de memoria de Teams para la aplicación de escritorio y la aplicación web.](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a>Uso de memoria en Teams

Es importante comprender el comportamiento *esperado* de Teams en lo que respecta a la memoria del sistema y conocer los síntomas de los problemas verdaderamente problemáticos de la memoria del sistema.

### <a name="expected-memory-usage-by-teams"></a>Uso de memoria esperado por Teams

Tanto si está ejecutando la aplicación de escritorio de Teams como la aplicación web de Teams, Chromium detecta la cantidad de memoria del sistema disponible y usa suficiente memoria para optimizar la experiencia de representación. Cuando otras aplicaciones o servicios requieren memoria del sistema, Chromium entrega memoria a esos procesos. Chromium sintoniza el uso de memoria de Teams de forma continua con el fin de optimizar el rendimiento de Teams sin afectar a nada más que se esté ejecutando actualmente.

De esta forma, las cargas de trabajo de Chromium similares pueden utilizar distintas cantidades de memoria, dependiendo de la cantidad de memoria del sistema disponible.

El siguiente gráfico muestra el uso de memoria por parte de Teams en cuatro sistemas independientes, cada uno con diferentes cantidades de memoria disponible. Cada uno de los sistemas procesa cargas de trabajo similares (las mismas aplicaciones abiertas y en ejecución).

![Uso de memoria de Teams en diferentes sistemas.](media/teams-memory-usage.png)

Cuando los equipos tengan más memoria, Teams usará esa memoria. En sistemas en los que la memoria es escasa, Teams usará menos.

### <a name="symptoms-of-system-memory-issues"></a>Síntomas de problemas de memoria del sistema

Si ves uno o varios de los siguientes síntomas en el equipo, podrías tener un problema grave de memoria del sistema:

- Uso de memoria elevada cuando se ejecutan varias aplicaciones de gran tamaño al mismo tiempo.
- Rendimiento lento del sistema o aplicaciones que se cuelgan.
- Se ha mantenido el uso de memoria general del sistema del 90 % o superior en todas las aplicaciones. Con esta cantidad de uso de memoria, Teams debería devolver memoria a otras aplicaciones y cargas de trabajo. Un uso sostenido de la memoria del 90 % podría significar que Teams no está devolviendo memoria al sistema, lo que indica un problema.

Las siguientes imágenes muestran ejemplos de vistas en el Administrador de tareas cuando el uso de memoria del sistema es anormalmente alto.

![Vista uso de memoria de Teams en el Administrador de tareas.](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso de memoria de Teams en el Administrador de tareas.](media/teams-memory-high-mem-process-list2.png)
