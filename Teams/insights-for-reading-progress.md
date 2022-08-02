---
title: Obtener información sobre las recomendaciones de progreso de lectura
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Obtenga información sobre cómo se usan los datos de Insights en Progreso de lectura para ayudar a mejorar la capacidad de lectura de los alumnos.
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157900"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>Obtener información sobre las recomendaciones de progreso de lectura

Este artículo está destinado a administradores de TI del sector educativo que quieran comprender cómo se usan los datos de Insights para las recomendaciones de Progreso de lectura.

Insights permite a los profesores realizar un seguimiento de la fluidez de lectura de sus alumnos mediante Progreso de lectura, una herramienta que registra a los alumnos leyendo en voz alta y detecta automáticamente errores.

Progreso de lectura proporciona los siguientes tipos de tareas de desafío de lectura:

- **Palabras contextuales**: practique las palabras recomendadas en función de las palabras que los alumnos pronuncian incorrectamente en tareas anteriores de Progreso de lectura.
- **Palabras correlacionadas**: practique las palabras recomendadas en función de los errores comunes a los alumnos con el mismo tipo de desafíos de lectura.

Para obtener orientación del formador sobre el uso de Insights para el Progreso de lectura, vea [Crear tareas de desafío de Progreso de lectura con Insights](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe).

## <a name="how-does-microsoft-recommend-correlated-words"></a>¿Cómo recomienda Microsoft palabras correlacionadas?

Las palabras correlacionadas son palabras personalizadas y recomendadas que Insights para Educación identificó como difíciles para otros estudiantes que comparten patrones de lectura similares.

Las palabras correlacionadas se basan en una técnica de aprendizaje automático denominada **filtrado colaborativo**.

- Insights analiza los datos de lectura de los alumnos en distintas clases que comparten su área geográfica e idioma, para identificar clústeres de palabras que son difíciles de leer para los alumnos.

- Dado un conjunto de palabras desafiantes, Insights también identifica clústeres similares y los usa para recomendar otras palabras a los alumnos para la práctica personalizada.

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>¿Mantiene Microsoft los datos de los alumnos privados y seguros?

Microsoft se compromete a usar los datos de forma responsable y ética.

Estas son algunas de las medidas adoptadas para crear esta característica:

- Los análisis de datos de los alumnos se crean de una manera oportuna, lo que significa que Microsoft no tiene acceso a los datos de lectura de los alumnos, solo a los resultados del análisis.

- Los administradores de inquilinos pueden optar por no participar en el proceso de análisis de datos desactivando el [botón de alternancia Deducciones avanzadas](class-insights.md#turn-on-and-off-advanced-inferences-in-insights).

- Las palabras inapropiadas se filtran de las listas de recomendaciones de **palabras correlacionadas** . Esto se hace a través de una combinación de técnicas de ciencia de datos y bloqueo de palabras problemáticas conocidas. Sin embargo, este proceso no es prueba de errores. Los formadores deben revisar las recomendaciones.

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>¿Cuáles son las limitaciones de las recomendaciones de palabras de Insights?

- Las recomendaciones de Word para el Progreso de lectura son compatibles actualmente con [estos idiomas](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages).

- Las palabras correlacionadas solo se presentan en clases con al menos cinco alumnos que hayan enviado tareas de Progreso de lectura.

- Es posible que Insights no recomiende palabras nuevas en casos en los que no haya alumnos con patrones de error similares, pero no idénticos.
