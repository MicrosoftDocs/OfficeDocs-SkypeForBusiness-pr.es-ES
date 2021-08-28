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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bb4eb1c1c681e0c2089ec1258f7729727fdb77f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586304"
---
# <a name="teams-view-only-meeting-experience"></a>Experiencia de reunión de solo vista para Teams

> [!Note]
> Las difusiones de solo vista están disponibles en Microsoft 365 E3/E5 y Microsoft 365 A3/A5. Esta característica se habilitará el 1 de marzo de 2021 como desactivada de forma predeterminada. La característica de Microsoft 365 Government Community Cloud (GCC) comenzará a implantarse a finales de marzo de 2021. Government Community Cloud High (GCCH) y el Departamento de Defensa (DoD) se implementarán en una fecha posterior. Debe cambiar la directiva predeterminada después de esa fecha si quiere que la característica esté ACTIVADA de forma predeterminada. Use PowerShell para habilitar la directiva `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Si la reunión alcanza la capacidad, Teams escalará sin problemas para dar cabida a una experiencia de difusión solo para 10 000 personas. Además, en estos tiempos de aumento del trabajo remoto, le ofrecemos hasta finales de año la opción de difusiones de hasta 20 000 personas. Actualmente, los seminarios web no admiten una experiencia de difusión solo vista.

Microsoft Teams permite un máximo de 10 000 asistentes en una reunión de Teams. Una vez que se haya alcanzado la capacidad de la reunión principal (que es cuando 1000 usuarios entran en una reunión), los asistentes adicionales se unirán con una experiencia de solo vista.

Los asistentes que se unan a la reunión en primer lugar, hasta la capacidad de la reunión principal, recibirán la experiencia Teams reunión. Podrán compartir audio y vídeo, ver vídeos compartidos y participar en el chat de la reunión.

Los asistentes que se unan después de alcanzar la capacidad máxima de la reunión principal tendrán una experiencia de solo vista.

Los asistentes podrán unirse a la experiencia de solo visualización a través de escritorio, web y Teams móvil (Android e iOS).

> [!Note]
> La capacidad límite actual de la "reunión principal" o, en otras palabras, el número de usuarios totalmente interactivos es de 1000 e incluye GCC seminarios web.

## <a name="teams-view-only-experience-controls"></a>Teams de experiencia de solo vista

Puede habilitar la experiencia de solo vista con el cmdlet desde el módulo [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) [de PowerShell de SkypeForBusiness](/powershell/module/skype/?view=skype-ps) o al menos la versión 2.0.0 del módulo [MicrosoftTeams.](https://www.powershellgallery.com/packages/MicrosoftTeams)

Para usar el módulo `MicrosoftTeams` recomendado:

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

Para habilitar la experiencia de solo vista, puede usar el siguiente fragmento de PowerShell:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Para deshabilitar la experiencia de solo vista, también puede usar PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

En el futuro, podrá habilitar o deshabilitar la experiencia de solo vista en el centro de administración Teams vista.

## <a name="impact-to-users"></a>Impacto en los usuarios

La experiencia de un usuario puede variar en función de varios factores.

Cuando se alcance la capacidad máxima de la reunión principal, un asistente no podrá unirse a la reunión si se cumple alguno de estos requisitos:

- Un administrador ha deshabilitado la Teams solo vista para el organizador o para todo el espacio empresarial.
- El asistente de solo vista no puede omitir la sala de espera. Como ejemplo, si un organizador de una  reunión elige que solo personas de mi organización omitan la sala de espera y un asistente que está fuera de la organización intenta unirse como asistente de solo vista, no podrá unirse.

Cuando se haya alcanzado la capacidad de la reunión principal, el organizador de la reunión y los presentadores verán una pancarta en la que se les informará de que los nuevos asistentes se unirán como asistentes de solo visualización.

  ![el cliente y el mensaje de banner de Teams para organizadores y presentadores](media/chat-and-banner-message.png)

Cuando se alcance la capacidad máxima de la reunión principal, se informará a los asistentes a la reunión en una pantalla previa de que se encuentran en modo de solo vista.

  ![la pantalla previa a unirse a la reunión de Teams y el mensaje para los participantes donde se les indica que se unen en modo de solo vista](media/view-only-pre-join-screen.png)

Siempre que haya espacio, un usuario podrá unirse a la reunión principal. Si la reunión principal alcanza su capacidad máxima y uno o más asistentes la dejan, esta tendrá de nuevo capacidad disponible. Los asistentes que se unan (o vuelvan a unirse) entonces a la reunión, podrán hacerlo hasta que llegue de nuevo a su capacidad máxima. Los asistentes que se encuentran en la experiencia de solo visualización no se promoverán automáticamente a la reunión principal y no se pueden promover manualmente a la reunión principal.

Si se han establecido roles de moderador y asistente y un moderador intenta unirse a una reunión después de que la reunión principal haya alcanzado la capacidad, se unirán como asistentes de solo vista y tendrán las mismas limitaciones que otros asistentes de solo vista. Soporte técnico para garantizar que todos los presentadores se unan a la reunión principal se llevará a cabo más adelante. El organizador siempre tendrá garantizado el espacio en la reunión principal.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Impacto para los presentadores y organizadores de la reunión

Entre las limitaciones para los organizadores y los organizadores de la reunión se incluyen:

- No tendrá información sobre el asistente de solo vista. eDiscovery no es compatible para los asistentes de solo vista.
- Los usuarios de la reunión principal no pueden ver a los asistentes de solo vista.
- No puede quitar a un asistente de solo vista de la reunión.

> [!Note]
> El recuento de asistentes solo reflejará las personas de la reunión principal y no las personas de la sala de solo vista. Por lo tanto, los presentadores no pueden obtener un recuento exacto de quién está en la experiencia de solo vista.

## <a name="experience-for-view-only-attendees"></a>Experiencia para asistentes de solo vista

La experiencia de solo vista de Teams permite a los asistentes:

- Escuchar a los participantes de la reunión principal de Teams.
- Consultar la fuente de vídeo del orador activo (si este comparte vídeo).
- Vea el contenido que se comparte con la funcionalidad compartir escritorio o pantalla.

El asistente de solo vista no podrá experimentar las siguientes opciones en las reuniones:

- Unirse a la reunión si el asistente no tiene permiso para omitir la sala de espera según las directivas u opciones de sala de espera establecidas.
- Unirse a la sala de solo vista con Audioconferencia.
- Únase a la sala de solo vista con Salas de Microsoft Teams o con los servicios de interoperabilidad de vídeo en la nube (CVI).
- Compartir su audio o vídeo.
- Ver el chat de reunión o participar en él.
- Ver la fuente de vídeo de los participantes de la reunión a menos que el participante sea el orador activo.
- Vea PowerPoint que se comparten con la funcionalidad PowerPoint Live o recursos compartidos de aplicaciones individuales (distintos del uso compartido de pantalla o escritorio).
- Levante la mano en la reunión.
- Enviar o ver reacciones.
- Interactúe con cualquier aplicación 3P que se integre en la Teams, incluidos sondeos.

## <a name="view-only-feature-limitations"></a>Limitaciones de características de solo vista

- Los asistentes de solo visualización solo podrán ver los subtítulos en directo en escritorio y web. Actualmente, solo se admiten subtítulos en inglés.
- Los asistentes de solo vista no pueden registrarse en seminarios web.
- La tecnología de streaming respaldará a los asistentes de solo vista
- Los asistentes de solo vista no se incluirán en el informe de asistencia.
- Los asistentes de solo vista tendrán una sola experiencia en vídeo. O bien podrán ver al orador activo o podrán ver el contenido que se comparte, pero no ambos.
- Actualmente, no se admite el modo **Galería**, **Galería grande** o **Modo conferencia** para los asistentes de solo vista.
- Los asistentes de solo visualización solo son compatibles con las siguientes directivas de la sala de espera: "Solo usted", "Personas de mi organización e invitados", "Personas de mi organización y organizaciones de confianza, e invitados" y "Todos los usuarios". Si usa una directiva de sala de espera que no admite asistentes de solo vista, los asistentes de solo vista se rechazarán de la reunión. 
- Los asistentes de solo vista no tendrán la misma latencia que los asistentes normales. <sup>1</sup>

  <sup>1</sup> Los asistentes de solo vista se reunirán con un retraso de audio y vídeo de 30 segundos en la reunión.  
