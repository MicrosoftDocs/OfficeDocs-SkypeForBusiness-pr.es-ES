---
title: Experiencia de reunión de solo vista
ms.author: mabond
author: mkbond007
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la experiencia de reunión de solo vista de Teams para administradores, presentadores y asistentes
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7a608132af2807c1fc59e25f7dac39433fe5dc5
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392100"
---
# <a name="teams-view-only-meeting-experience"></a>Experiencia de reunión de solo vista para Teams

> [!Note]
> Las difusiones de solo vista están disponibles en Microsoft 365 E3/E5 y Microsoft 365 A3/A5. Esta característica se habilitará el 1 de marzo de 2021 como desactivada de forma predeterminada. La característica de Microsoft 365 Government Community Cloud (GCC) comenzará a implantarse a finales de marzo de 2021. Government Community Cloud High (GCCH) y el Departamento de Defensa (DoD) se implementarán en una fecha posterior. Debe cambiar la directiva predeterminada después de esa fecha si quiere que la característica esté ACTIVADA de forma predeterminada. Use PowerShell para habilitar la directiva `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Si la reunión alcanza su capacidad máxima, Teams escalará sin problemas para dar cabida a una experiencia de difusión de solo vista de 10 000 personas. Además, en estos tiempos de aumento del trabajo remoto, le ofrecemos hasta finales de año la opción de difusiones de hasta 20 000 personas. Actualmente, los seminarios web no admiten una experiencia de difusión de solo vista.

> [!Note]
> Una reunión de Teams no es un evento en directo de Teams (TLE) y no aprovechará Microsoft eCDN. Para obtener más información, vea [Microsoft lista de comprobación de incorporación de eCDN](/ecdn/integration/onboarding-checklist-for-tle-customers).

Microsoft Teams permite un máximo de 10 000 asistentes en una reunión de Teams. Una vez alcanzada la capacidad de la reunión principal (que es cuando 1 000 usuarios entran en una reunión), se unirán asistentes adicionales con una experiencia de solo vista.

Los asistentes que se unan a la reunión antes de alcanzar su capacidad máxima, disfrutarán de la experiencia completa de la reunión de Teams. Podrán compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.

Los asistentes que se unan después de alcanzar la capacidad máxima de la reunión principal tendrán una experiencia de solo vista.

Los asistentes podrán unirse a la experiencia de solo vista a través del escritorio, la Web y la versión móvil de Teams (Android e iOS).

> [!Note]
> La capacidad límite actual de la "reunión principal" (es decir, el número de usuarios totalmente interactivos) es de 1 000 e incluye GCC y seminarios web.

## <a name="teams-view-only-experience-controls"></a>Controles de experiencia de solo vista de Teams

Habilite la experiencia de solo vista mediante el cmdlet [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy) del [módulo de PowerShell SkypeForBusiness](/powershell/module/skype/) o al menos la versión 2.0.0 del [módulo MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

Para usar el módulo de `MicrosoftTeams` recomendado:

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

Para habilitar la experiencia de solo vista, puede usar el siguiente fragmento de código de PowerShell:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Para deshabilitar la experiencia de solo vista, también puede usar PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

En el futuro, podrá habilitar o deshabilitar la experiencia de solo vista en el Centro de administración de Teams.

## <a name="impact-to-users"></a>Impacto en los usuarios

La experiencia de un usuario puede variar en función de varios factores.

Cuando se alcance la capacidad máxima de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguno de estos requisitos:

- Un administrador ha deshabilitado la experiencia de solo vista de Teams para el organizador o para todo el inquilino.
- El asistente de solo vista no puede omitir la sala de espera. Por ejemplo, si un organizador de una reunión elige que solo **Personas de mi organización** omitan la sala de espera y un asistente que está fuera de la organización intenta unirse como asistente de solo vista, no podrá unirse.

Cuando se alcance la capacidad máxima de la reunión principal, se informará de ello al organizador de la reunión y a los presentadores con una pancarta en la que se les indicará que los nuevos asistentes se unirán como asistentes de solo vista.

  ![el cliente y el mensaje de banner de Teams para organizadores y presentadores.](media/chat-and-banner-message.png)

Cuando se alcance la capacidad máxima de la reunión principal, se informará a los asistentes a la reunión en una pantalla previa de que se encuentran en modo de solo vista.

  ![la pantalla previa a unirse a la reunión de Teams y el mensaje para los participantes donde se les indica que se unen en modo de solo vista.](media/view-only-pre-join-screen.png)

Siempre que haya espacio, un usuario podrá unirse a la reunión principal. Si la reunión principal alcanza su capacidad máxima y uno o más asistentes la dejan, esta tendrá de nuevo capacidad disponible. Los asistentes que se unan (o vuelvan a unirse) entonces a la reunión, podrán hacerlo hasta que llegue de nuevo a su capacidad máxima. No se transferirá a los asistentes en modo solo vista a la reunión principal automáticamente y tampoco se les puede transferir manualmente.

Si se han establecido roles de moderador y asistente y un moderador intenta unirse a una reunión después de que la reunión principal haya alcanzado su capacidad, se unirá como asistente de solo vista y tendrá las mismas limitaciones que otros asistentes de solo vista. El soporte para asegurarse de que todos los moderadores se unan a la reunión principal se implementará más adelante. El organizador siempre tendrá un espacio garantizado en la reunión principal.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Impacto en los moderadores y organizadores de reuniones

Las limitaciones para los moderadores y organizadores de reuniones incluyen:

- No tendrá información sobre el asistente de solo vista. eDiscovery no es compatible para los asistentes de solo vista.
- Los usuarios de la reunión principal no pueden ver los asistentes de solo vista.
- No puede quitar a un asistente de solo vista de la reunión.

> [!Note]
> El número de asistentes solo contará a las personas presentes en la reunión principal y no a las que estén en la sala de solo vista. Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo vista.

## <a name="experience-for-view-only-attendees"></a>Experiencia para asistentes de solo vista

La experiencia de solo vista de Teams permite a los asistentes:

- Escuchar a los participantes de la reunión principal de Teams.
- Consultar la fuente de vídeo del orador activo (si este comparte vídeo).
- Ver el contenido que se comparte con la funcionalidad Compartir escritorio o pantalla.

El asistente de solo vista no podrá experimentar las siguientes opciones en las reuniones:

- Unirse a la reunión si el asistente no tiene permiso para omitir la sala de espera según las directivas u opciones de sala de espera establecidas.
- Unirse a la sala de solo vista con Audioconferencia.
- Unirse a la sala de solo vista con el sistema de Salas de Microsoft Teams o los servicios de Interoperabilidad de Vídeo en la Nube (CVI).
- Compartir su audio o vídeo.
- Ver el chat de reunión o participar en él.
- Ver la fuente de vídeo de los participantes de la reunión a menos que el participante sea el orador activo.
- Ver los archivos de PowerPoint que se comparten con la funcionalidad de PowerPoint Live o los recursos compartidos de aplicaciones individuales (distintos del uso compartido de pantalla o escritorio).
- Levantar la mano en la reunión.
- Enviar o ver reacciones.
- Interactuar con cualquier aplicación 3P que se integre en la reunión de Teams, incluyendo Encuestas.
- Acceso a la grabación de la reunión.

## <a name="view-only-feature-limitations"></a>Limitaciones de características de solo vista

- Los asistentes de solo vista solo podrán ver subtítulos en directo en el escritorio y en la Web. Actualmente, solo se admiten subtítulos en inglés.
- Los asistentes de solo vista no pueden registrarse en seminarios web.
- La tecnología de streaming respaldará a los asistentes de solo vista
- Los asistentes de solo vista no se incluirán en el informe de asistencia.
- Los asistentes de solo vista tendrán una sola experiencia en vídeo. O bien podrán ver al orador activo o podrán ver el contenido que se comparte, pero no ambos.
- Actualmente, no se admite el modo **Galería**, **Galería grande** o **Modo conferencia** para los asistentes de solo vista.
- Solo se admiten asistentes de vista mediante las siguientes directivas de sala de espera: "Personas en mi organización", "Personas en mi organización e invitados", "Personas en mi organización, organizaciones de confianza e invitados" y "Todos". Si usa una directiva de sala de espera que no admite asistentes de solo vista, los asistentes de solo vista se rechazarán para la reunión. 
- Los asistentes de solo vista no tendrán la misma latencia que los asistentes normales. <sup>1</sup>

  <sup>1</sup> Los asistentes de solo vista se reunirán con un retraso de audio y vídeo de 30 segundos en la reunión.  
