---
title: Experiencia de reunión de solo vista
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la experiencia de reunión solo vista de Teams para administradores, presentadores y asistentes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237460"
---
# <a name="teams-view-only-meeting-experience"></a>Experiencia de reunión solo para la vista de Teams

> [!Note]
> La experiencia de reunión de solo lectura estará disponible a principios de marzo de 2021.

> [!Note]
> Hemos aumentado temporalmente la experiencia de solo vista para 20 000 asistentes, pero revertiremos la asistencia a 10 000 asistentes el 30 de junio de 2021.

Microsoft Teams permite que hasta 10 000 asistentes se unan a una reunión de Teams. Una vez que se haya alcanzado la capacidad de la reunión principal, se unirán otros asistentes con una experiencia de solo vista.

Los asistentes que se unan a la reunión en primer lugar, hasta la capacidad de la reunión, recibirán la experiencia de reunión completa de Teams. Pueden compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.

Los asistentes que se unan después de alcanzar la capacidad principal de la reunión tendrán una experiencia de solo lectura.

Tenemos soporte móvil completo para Android y iOS para que un asistente se una.

> [!Note]
> El límite actual para el número de personas que pueden chatear y llamar a una reunión es 300 en EE. UU. y 250 en GCC, GCC High y DoD.

La experiencia de solo vista está habilitada de forma predeterminada para cualquier organizador que tenga SKU E3/E5/A3/A5. No es necesaria ninguna configuración o configuración adicional.

### <a name="disable-teams-view-only-experience"></a>Deshabilitar la experiencia de solo lectura de Teams

Los administradores pueden deshabilitar la experiencia de solo vista con PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

En el futuro, también será posible que los administradores deshabilite la experiencia de solo lectura en el Centro de administración de Teams.

## <a name="impact-to-users"></a>Impacto para los usuarios

La experiencia de un usuario variará en función de varios factores.

Cuando se haya alcanzado la capacidad de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguna de las condiciones siguientes:

- Un administrador ha deshabilitado la experiencia de solo vista de Teams.
- El asistente no tiene permiso para omitir la sala de espera.

Cuando se haya alcanzado la capacidad de la reunión principal, el organizador y los presentadores de la reunión verán un banner que les informará de que se ha alcanzado la capacidad de la reunión y que los nuevos asistentes se unirán a un asistente de solo lectura.

  ![El cliente de Teams y los desordenes de banner para organizadores y presentadores](media/chat-and-banner-message.png)

Cuando se haya alcanzado la capacidad de la reunión principal, los asistentes a la reunión recibirán una información en la pantalla antes de unirse de que se unen en modo de solo lectura.

  ![la pantalla de antes de unirse a Teams y el mensaje para los participantes que les indica que se unirán en modo de solo lectura](media/view-only-pre-join-screen.png)

Si hay espacio, un usuario siempre se unirá a la reunión principal. Si la reunión principal alcanza la capacidad, y uno o más asistentes abandonan la reunión principal, la reunión principal tiene capacidad disponible. Los asistentes que se unan (o vuelvan a unirse) a la reunión se unirán a la reunión principal hasta que llegue de nuevo a su capacidad. Los asistentes que se encuentran en la experiencia de solo lectura no se promoverán automáticamente a la reunión principal y actualmente no pueden promoverse manualmente a la reunión principal.

Si los roles de moderador/asistente no se han establecido, los espacios en la reunión principal se rellenan en función de su nombre. Una vez que se haya alcanzado la capacidad de reunión, todos los demás usuarios se unirán con una experiencia de solo lectura.

## <a name="impact-to-meeting-presenters"></a>Impacto para los presentadores de la reunión

Reservaremos espacio en la reunión normal para los usuarios indicados explícitamente como presentadores en las opciones de la reunión. Si un moderador deja la reunión y, posteriormente, se une de nuevo a la reunión, se le permite entrar en la reunión como moderador.

Entre las limitaciones para los presentadores de reuniones se incluyen:

- No tendrá ninguna información sobre el asistente de solo lectura. No se admite e-discovery para los asistentes solo para visualización.
- Los usuarios no pueden ver solo a los asistentes.
- No puede quitar un asistente de solo vista de la reunión.

> [!Note]
> El número de asistentes solo reflejará las personas de la reunión y no las personas de la sala de desbordamiento. Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo lectura.

## <a name="experience-for-view-only-attendees"></a>Experiencia para asistentes que solo pueden ver

La experiencia de solo vista de Teams permite a los asistentes:

- Escuche a los participantes de la reunión principal de Teams.
- Vea la fuente de vídeo del orador activo (si el orador activo comparte vídeo).
- Ver el contenido que se comparte con la función compartir escritorio.

El asistente que solo ve no podrá experimentar las siguientes opciones en las reuniones:

- Únase a la reunión si el asistente no tiene permiso para omitir la sala de espera en función de las directivas u opciones de la sala de espera.
- Únase a la sala de desbordamiento a través de Audioconferencia.
- Únase a la sala de desbordamiento a través de Microsoft Teams Room system o a través de los servicios cloud Video Interoperabilidad (CVI).
- Únase a la sala de desbordamiento a través de la aplicación móvil Android de Teams.
- Comparta su audio o vídeo.
- Ver o participar en el chat de la reunión.
- Vea la fuente de vídeo de los participantes de la reunión a menos que sea el orador activo.
- Vea los archivos de PowerPoint que se comparten con la funcionalidad de Uso compartido nativo de PowerPoint o con recursos compartidos de aplicaciones individuales (aparte del uso compartido de escritorio).

## <a name="view-only-feature-limitations"></a>Limitaciones de características de solo vista

- Los asistentes que solo ven los subtítulos en directo, independientemente de la configuración de los subtítulos en directo para esa reunión. En este momento, solo se admiten subtítulos en inglés.
- Los asistentes solo para visualización serán compatibles con la tecnología de streaming.
- Los asistentes de solo vista no se incluirán en el informe de asistencia.
- Solo los asistentes a la vista tendrán una única experiencia de vídeo. Pueden ver el orador activo o el contenido que se comparte, pero no ambos.
- Actualmente no se admiten diseños  **de galería,** **galería grande** o modo conjunto para los asistentes que solo pueden verlos.  
- Los asistentes que solo pueden ver no tendrán la misma latencia que un asistente normal. <sup>1</sup>

  <sup>1</sup> Los asistentes que solo pueden ver estarán en una demora de audio y vídeo de 30 segundos en la reunión.  

## <a name="related-topics"></a>Temas relacionados

- [Complemento de comunicaciones avanzado para Teams](teams-add-on-licensing/advanced-communications.md)
- [Especificaciones y límites de Teams](limits-specifications-teams.md)
