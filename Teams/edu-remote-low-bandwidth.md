---
title: Solucionar problemas de escenarios de ancho de banda bajo para Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Obtenga ayuda con problemas de reunión y vídeo relacionados con problemas de ancho de banda bajo en Teams. Tanto si es un padre, un educador o un Administración de TI, tiene opciones para mejorar la experiencia con Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426817"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>Solucionar problemas de escenarios de ancho de banda bajo para Teams

Este artículo ofrecerá a los administradores de TI los procedimientos recomendados para solucionar problemas de ancho de banda bajo en Teams.

Numerosos elementos de red pueden afectar al rendimiento al trabajar con Microsoft Teams.

- Conexión a Internet de baja velocidad para la escuela.
- Conexión a Internet de baja velocidad para uno o más estudiantes.
- Horas del día en que el ancho de banda se reduce debido al uso de la red en un área.
- Las interrupciones no son locales para la escuela o los alumnos, pero afectan al rendimiento.
- Problemas con el hardware que causan problemas de ancho de banda bajo.

> [!IMPORTANT]
> Lea [Cómo Microsoft Teams usa la memoria](teams-memory-usage-perf.md) para las limitaciones de recursos en los dispositivos.
>
>Para obtener instrucciones sobre la red de Teams, consulte [Preparar la red de su organización para Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>Resolver problemas de ancho de banda bajo para administradores de TI

Es posible que algunos problemas solo se resuelvan con un enfoque limitado en el nivel de usuario individual.

Si se producen problemas de ancho de banda para muchos usuarios o si las acciones realizadas en el nivel de usuario no han sido útiles, la acción para toda la escuela es el siguiente paso.

> [!NOTE]
> También puede leer la [Guía de revisión de calidad de la experiencia](quality-of-experience-review-guide.md). No es específica de la educación, pero tiene información valiosa.

### <a name="meetings-and-video"></a>Reuniones y vídeo

Tenga en cuenta las siguientes acciones al tratar los problemas de reunión relacionados con el bajo ancho de banda de red.

#### <a name="meeting-video-policies"></a>Directivas de vídeo de reunión

Teams escala automáticamente la calidad de las reuniones al ancho de banda detectado por un usuario. Sin embargo, puede establecer más restricciones para conservar el ancho de banda.

Entre algunas restricciones que puede establecer a través de la directiva se incluyen:

- Desactivación del vídeo por completo para que nadie pueda usar vídeo.
- Limitación de la velocidad de bits multimedia, que se establece por usuario.

Para ver más directivas que debe establecer para reuniones y vídeo, lea [Configuración de directivas de reunión en Teams: audio y vídeo](meeting-policies-audio-and-video.md).

#### <a name="screen-sharing-policies"></a>Directivas de uso compartido de pantalla

En Teams, los usuarios pueden compartir toda la pantalla o ventanas individuales.

Compartir una pantalla completa usa más ancho de banda que simplemente compartir una ventana.

- Impedir que los usuarios compartan toda la pantalla a través de la directiva.
- Indique a los formadores que solo compartan aplicaciones, no toda la pantalla.

Obtenga más información sobre las directivas de uso compartido de la pantalla [en Configuración de directivas de reunión en Teams: Audio y vídeo](meeting-policies-audio-and-video.md).

#### <a name="dial-in-number-for-meetings"></a>Número de acceso telefónico para una reunión

Puede que sea más fácil para algunos alumnos llamar a las sesiones de clase.

- Proporcione un número de acceso telefónico local para las reuniones de Teams como alternativa a asistir a una reunión de vídeo.

Para obtener más información, lea [Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Escenarios de ancho de banda bajo como formador

Hacer que los formadores solucione los problemas de ancho de banda puede ser una mejor opción que la acción de TI en las situaciones siguientes:

- El problema es intermitente.
- Hay una hora específica del día que puede anticipar que hay un problema.

Para conocer los pasos que un formador puede tomar para resolver problemas de ancho de banda, lea [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Escenarios de ancho de banda bajo como padre o alumno

A veces, el problema de ancho de banda está del lado de un alumno.

- Es posible que su casa no tenga acceso a un ancho de banda alto.
- Pueden tener muchas personas en su área inmediata también consumiendo ancho de banda.
- Puede haber inestabilidad en Internet.

Hemos recopilado instrucciones en nuestro artículo [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para padres y alumnos.
