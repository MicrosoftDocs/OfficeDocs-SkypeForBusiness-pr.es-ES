---
title: Guía ancho de banda bajo de Microsoft Teams para EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Artículo de Microsoft Teams para EDU que le ayudará con los problemas de reunión y vídeo relacionados con el ancho de banda bajo. Tanto si es un padre, un formador o un administrador de TI, tiene opciones para mejorar la experiencia con Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111086"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Ayuda para las situaciones de ancho de banda bajo para Teams para EDU

Hay muchos elementos de red cuando se trata de trabajar con Microsoft Teams que pueden afectar el rendimiento, y el ancho de banda bajo es una de las situaciones que pueden resultar completamente fuera de su control. Tenga en cuenta lo siguiente:

- Una conexión a Internet de baja velocidad para la escuela.
- Una conexión a Internet de baja velocidad para uno o más alumnos.
- Horas del día en que el ancho de banda se reduce debido al uso de la red en un área.
- Períodos de ancho de banda bajo causados por interrupciones locales no por las escuelas ni por los alumnos, pero que afecta negativamente al rendimiento.
- Problemas que no son de ancho de banda (por ejemplo, problema con el hardware) que se hacen pasar por problemas de ancho de banda bajo.

Este artículo le proporcionará las mejores prácticas para realizar una amplia variedad de actividades de Teams cuando se enfrente a un problema de ancho de banda bajo.

> [!IMPORTANT]
> Aquí encontrará información sobre [Cómo Microsoft Teams usa la memoria](teams-memory-usage-perf.md), porque además de los problemas de ancho de banda bajo, es posible que tenga problemas de recursos en su dispositivo. Si está buscando una guía de red para Microsoft Teams, consulte [Preparar la red de la organización para Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>Resolver problemas de ancho de banda bajo para administradores de TI

Lo más importante que debe recordar, como administrador de TI, es que, aunque tenga soluciones para problemas de ancho de banda bajo que sean de amplia difusión y que resolverán los problemas rápidamente, esto debe considerarse con cuidado, ya que algunos problemas pueden resolverse con un enfoque más limitado tomado a nivel del formador o incluso del alumno/padre.

Es decir, si se produce un problema de ancho de banda bajo para un amplio grupo de alumnos, tomar medidas como un administrador de TI tiene sentido y también tiene sentido si las acciones emprendidas en el nivel de alumno/formador no le han sido útiles.

> [!NOTE]
> Si tiene tiempo, inviértalo leyendo la [guía de revisión de la calidad de la experiencia](quality-of-experience-review-guide.md), es una lectura valiosa (que aunque no es específica de EDU, aún tendrá información valiosa). De esta forma, los administradores de TI experimentados podrán profundizar en la experiencia de los formadores y alumnos.

### <a name="meetings-and-video"></a>Reuniones y vídeo

Un enfoque principal para los problemas de ancho de banda bajo son las reuniones y específicamente el vídeo en las reuniones. A continuación, tenemos algunas de las acciones que un administrador de TI debe considerar cuando se trata de problemas informados por alumnos o formadores con respecto a tener la mejor experiencia de reunión en un entorno educativo.

#### <a name="meeting-policies"></a>Directivas de reunión

En lo que respecta a las reuniones, una de las áreas más relacionadas para las situaciones de ancho de banda baja tiene que ver con los vídeos. Por fortuna, además de que Teams puede escalar el ancho de banda detectado automáticamente, usted, como administrador de TI dispone de opciones de directiva que puede establecer en el nivel de organizador y/o usuario, para brindar a todos la mejor experiencia considerando el ancho de banda que tienen para trabajar en un momento dado.

Entre las cosas que puede establecer mediante la directiva se incluyen:

- Deshabilitar el vídeo completamente, para que nadie pueda habilitarlo.
- Tasa de bits multimedia (se define por usuario).

Para obtener más información sobre sus opciones, y para ver las especificaciones específicas de las directivas que necesitaría establecer para las reuniones y el vídeo, consulte [Configuración de la directiva de reuniones en Teams: audio y vídeo](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) para obtener información detallada.

#### <a name="screen-sharing-policies"></a>Directivas de uso compartido de pantalla

En otros casos, los formadores pueden compartir toda la pantalla con los alumnos, cuando el uso compartido debe limitarse a una aplicación relevante para la lección que se está impartiendo. Esto también puede establecerse con una directiva, si esa es una forma más deseable de hacerlo que hacer que los formadores tomen esa decisión individualmente.

Para tener una buena idea de lo que puede hacer para limitar la pantalla el uso compartido de la pantalla con la configuración de directivas, consulte [Configuración de la directiva de reuniones en Teams: uso compartido de la pantalla](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).

#### <a name="dial-in-number-for-meetings"></a>Número de acceso telefónico para una reunión

Puede ser más fácil para algunos alumnos intentar llamar en algunas sesiones de clase. Puede proporcionar un número de acceso telefónico para reuniones de Teams, de modo que los alumnos que tienen problemas pueden llamar como alternativa para asistir a una reunión de vídeo.

Para obtener más información sobre esto, puede leer [Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Escenarios de ancho de banda bajo como formador

Los formadores deben sentirse capacitados para tomar medidas para resolver problemas de ancho de banda bajo y puede ser una mejor opción que la acción del administrador de TI en las situaciones siguientes:

- Si el problema es intermitente o relativamente transitorio.
- Si hay un momento específico del día, puede anticiparse a un problema o el ancho de banda bajo tiene alguna previsibilidad.

En estas situaciones, puede llevar a cabo algunas acciones.

Para obtener más información, consulte [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Escenarios de ancho de banda bajo como padre o alumno

También hay situaciones, y debe analizarlas de manera proactiva con los formadores, donde el problema de ancho de banda se encuentra en el lado del alumno (por ejemplo, un gran número de alumnos pueden ver las lecciones de vídeo sin problemas, pero un pequeño número de alumnos tienen dificultades).

Es poco probable que sean muchos los padres que puedan solucionar estos problemas. Los problemas de ancho de banda bajo pueden estar fuera del control de un alumno o de los padres (su hogar puede no tener acceso a un ancho de banda alto, pueden que haya muchas personas en el área de consumo inmediato consumiendo ancho de banda y afectando lo que pueden hacer, probablemente el Internet es inestable, etc.).

Hemos incorporado una guía en nuestro artículo [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para padres y alumnos, también puede revisar y probar estas recomendaciones si tiene algún problema.