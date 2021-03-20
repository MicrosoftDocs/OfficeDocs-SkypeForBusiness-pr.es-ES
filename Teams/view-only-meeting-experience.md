---
title: Experiencia de reunión de solo vista
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la experiencia de reunión de solo vista de Teams para administradores, presentadores y asistentes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875060"
---
# <a name="teams-view-only-meeting-experience"></a>Experiencia de reunión de solo vista para Teams

> [!Note]
> Las difusiones de solo vista están disponibles en Microsoft 365 E3/E5 y Microsoft 365 A3/A5. Esta característica se habilitará el 1 de marzo de 2021 como desactivada de forma predeterminada. La característica de Microsoft 365 Government Community Cloud (GCC) comenzará a implantarse a finales de marzo de 2021. Government Community Cloud High (GCCH) y el Departamento de Defensa (DoD) se implementarán en una fecha posterior. Debe cambiar la directiva predeterminada después de esa fecha si quiere que la característica esté ACTIVADA de forma predeterminada. Use PowerShell para habilitar la directiva `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Si la reunión o el seminario web alcanzan su capacidad máxima, Teams escalará sin problemas para dar cabida a una experiencia de difusión de solo vista de 10 000 personas. Además, en estos tiempos de aumento del trabajo remoto, le ofrecemos hasta finales de año la opción de difusiones de hasta 20 000 personas.

Microsoft Teams permite un máximo de 10 000 asistentes en una reunión de Teams. Si se alcanza este límite en la reunión principal, los asistentes adicionales se unirán con una experiencia de solo vista.

Los asistentes que se unan a la reunión antes de alcanzar su capacidad máxima, disfrutarán de la experiencia completa de la reunión de Teams. Podrán compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.

Los asistentes que se unan después de alcanzar la capacidad máxima de la reunión principal tendrán una experiencia de solo vista.

Tenemos compatibilidad completa con dispositivos móviles Android e iOS para que un asistente se una.

> [!Note]
> El límite actual para el número de personas que pueden chatear y llamar a una reunión es de 300 en todo el mundo y 250 en GCC, GCC High y DoD.

La experiencia de solo vista está deshabilitada de forma predeterminada para cualquier organizador que tenga SKU de E3/E5/A3/A5. No es necesario realizar ninguna configuración adicional.

## <a name="disable-teams-view-only-experience"></a>Deshabilitar solo vista en Teams

Los administradores pueden deshabilitar solo vista con PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

En el futuro, también se les permitirá hacerlo desde el Centro de administración de Teams.

## <a name="impact-to-users"></a>Impacto en los usuarios

La experiencia de un usuario puede variar en función de varios factores.

Cuando se alcance la capacidad máxima de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguno de estos requisitos:

- Un administrador ha deshabilitado la experiencia de solo vista de Teams.
- El asistente no tiene permiso para omitir la sala de espera.

Cuando se alcance la capacidad máxima de la reunión principal, se informará de ello al organizador de la reunión y a los presentadores con una pancarta en la que también se les indicará que los nuevos asistentes se unirán a un asistente de solo vista.

  ![el cliente y el mensaje de banner de Teams para organizadores y presentadores](media/chat-and-banner-message.png)

Cuando se alcance la capacidad máxima de la reunión principal, se informará a los asistentes a la reunión en una pantalla previa de que se encuentran en modo de solo vista.

  ![la pantalla previa a unirse a la reunión de Teams y el mensaje para los participantes donde se les indica que se unen en modo de solo vista](media/view-only-pre-join-screen.png)

Siempre que haya espacio, un usuario podrá unirse a la reunión principal. Si la reunión principal alcanza su capacidad máxima y uno o más asistentes la dejan, esta tendrá de nuevo capacidad disponible. Los asistentes que se unan (o vuelvan a unirse) entonces a la reunión, podrán hacerlo hasta que llegue de nuevo a su capacidad máxima. No se transferirá a los asistentes en modo solo vista a la reunión principal automáticamente y, actualmente, tampoco se les puede transferir manualmente.

Si no se han establecido roles de moderador o asistente, los espacios de la reunión principal se ocuparán por orden de llegada. Una vez se haya alcanzado la capacidad máxima de la reunión, el resto de los usuarios se unirán en modo solo vista.

## <a name="impact-to-meeting-presenters"></a>Impacto para los presentadores de reuniones

Estas son las limitaciones para los presentadores de reuniones:

- No tendrá información sobre el asistente de solo vista. eDiscovery no es compatible para los asistentes de solo vista.
- Los usuarios no pueden ver a los asistentes de solo vista.
- No puede quitar a un asistente de solo vista de la reunión.

> [!Note]
> El número de asistentes solo contará a las personas presentes en la reunión y no a las que estén en la sala de solo vista. Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo vista.

## <a name="experience-for-view-only-attendees"></a>Experiencia para asistentes de solo vista

La experiencia de solo vista de Teams permite a los asistentes:

- Escuchar a los participantes de la reunión principal de Teams.
- Consultar la fuente de vídeo del orador activo (si este comparte vídeo).
- Ver el contenido que se comparte con la funcionalidad de compartir el escritorio.

El asistente de solo vista no podrá experimentar las siguientes opciones en las reuniones:

- Unirse a la reunión si el asistente no tiene permiso para omitir la sala de espera según las directivas u opciones de sala de espera establecidas.
- Unirse a la sala de solo vista con Audioconferencia.
- Unirse a la sala de solo vista con el sistema de Sala de Microsoft Teams o los servicios de Interoperabilidad de Vídeo en la Nube (CVI).
- Compartir su audio o vídeo.
- Ver el chat de reunión o participar en él.
- Ver la fuente de vídeo de los participantes de la reunión a menos que el participante sea el orador activo.
- Ver los archivos de PowerPoint que se comparten con la funcionalidad de PowerPoint de recurso compartido nativo o con recursos compartidos de aplicaciones individuales (distintos al uso compartido de escritorio).

## <a name="view-only-feature-limitations"></a>Limitaciones de características de solo vista

- Los asistentes de solo vista siempre verán los subtítulos en directo, independientemente de la configuración de los subtítulos en directo de esa reunión. Actualmente, solo se admiten subtítulos en inglés.
- La tecnología de streaming respaldará a los asistentes de solo vista
- Los asistentes de solo vista no se incluirán en el informe de asistencia.
- Los asistentes de solo vista tendrán una sola experiencia en vídeo. O bien podrán ver al orador activo o podrán ver el contenido que se comparte, pero no ambos.
- Actualmente, no se admite el modo **Galería**, **Galería grande** o **Modo conferencia** para los asistentes de solo vista.  
- Los asistentes de solo vista no tendrán la misma latencia que los asistentes normales. <sup>1</sup>

  <sup>1</sup> Los asistentes de solo vista se reunirán con un retraso de audio y vídeo de 30 segundos en la reunión.  
