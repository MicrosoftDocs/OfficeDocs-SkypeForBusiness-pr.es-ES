---
title: Administrar directivas de reunión para participantes e invitados
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de la directiva de reunión en Teams para participantes e invitados.
ms.openlocfilehash: 05408ade76aa96b64f07899881beb68fa52c74b4
ms.sourcegitcommit: a31c02892e35babbbcf5e7c303c7f14d7ba5cb52
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64784704"
---
# <a name="meeting-policy-settings---participants--guests"></a>Configuración de la directiva de reuniones: participantes e invitados

<a name="bkmeetingparticipants"> </a>

Esta configuración controla qué participantes de la reunión se quedan en la sala de espera antes de ser admitidos en la reunión y qué nivel de participación se les permite.

- [Permitir que los usuarios anónimos inicien una reunión](#let-anonymous-people-start-a-meeting)
- [Admitir automáticamente usuarios](#automatically-admit-people)
- [Permitir que los usuarios de acceso telefónico omitan la sala de espera](#allow-dial-in-users-to-bypass-the-lobby)
- [Subtítulos en directo](#live-captions)
- [Chatear en reuniones](#chat-in-meetings)

> [!NOTE]
>Las opciones para unirse a una reunión pueden variar en función de la configuración de cada grupo de Teams y del método de conexión. Si el grupo tiene audioconferencia y la usa para conectarse, consulte [Audioconferencia](/microsoftteams/audio-conferencing-in-office-365). Si el grupo de Teams no tiene ninguna Audioconferencia, consulte [Unirse a una reunión en Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).


## <a name="let-anonymous-people-start-a-meeting"></a>Permitir que los usuarios anónimos inicien una reunión

Esta configuración es una directiva por organizador que permite reuniones de conferencia de acceso telefónico local sin coordinadores. Esta configuración controla si los usuarios de acceso por marcado pueden unirse a la reunión sin que asista un usuario autenticado de la organización. De forma predeterminada, esta configuración está desactivada, lo que significa que los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un usuario autenticado de la organización se una a la reunión.

> [!NOTE]
> Si esta opción está desactivada y un usuario de marcado se une primero a la reunión y se le ubica en la sala de espera, el usuario de la organización debe unirse a la reunión con un cliente de Teams para admitir al usuario de la sala de espera. No hay ningún control de sala de espera disponible para los usuarios con acceso de marcado.

## <a name="automatically-admit-people"></a>Admitir automáticamente usuarios

Esta es una directiva por organizador. Esta configuración controla si los usuarios pueden unirse a una reunión directamente o esperar en la sala de espera hasta que un usuario autenticado los admita. Esta configuración no se aplica a los usuarios de marcado.

![Captura de pantalla que muestra una reunión con un usuario en la sala de espera.](media/meeting-policies-lobby.png)

 Los organizadores de la reunión pueden hacer clic en las **Opciones de reunión** en la invitación a la reunión para cambiar esta configuración en cada una de las reuniones programadas.

> [!NOTE]
> En las opciones de reunión, la configuración está etiquetada como "Quién puede omitir la sala de espera". Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y a las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.
  
|Valor de configuración  |Comportamiento para unirse |
|---------|---------|
|**Todos**   |Todos los participantes se unen a la reunión directamente sin tener que esperar en la sala de espera. Esto incluye a los usuarios autenticados, los usuarios externos de organizaciones de confianza (federados), los invitados y los usuarios anónimos.     |
|**Usuarios en mi organización e invitados**     |Los usuarios autenticados de la organización, incluidos los usuarios invitados, se unen a la reunión directamente sin tener que esperar en la sala de espera. Los usuarios de organizaciones de confianza y los usuarios anónimos esperan en la sala de espera. Esta configuración es la predeterminada.    |
|**Usuarios de mi organización y de organizaciones de confianza e invitados**     |Los usuarios autenticados en la organización, incluidos los usuarios invitados y los usuarios de las organizaciones de confianza, pueden unirse a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios anónimos esperan en la sala de espera.   |
|**Usuarios en mi organización**    |Los usuarios autenticados de la organización se unen a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios de organizaciones de confianza, los usuarios invitados y los usuarios anónimos esperan en la sala de espera.          |
|**Solo organizador**    |Solo los organizadores de la reunión se pueden unir a la reunión directamente sin tener que esperar en la sala de espera. Todos los demás usuarios, incluidos los usuarios autenticados de la organización, los usuarios invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera. En la página Teams opciones de reunión de cliente, aparece como "Solo yo".          |
|**Solo usuarios invitados**    |Solo los usuarios invitados y los organizadores de la reunión pueden unirse a la reunión directamente sin tener que esperar en la sala de espera. Todos los demás usuarios, incluidos los usuarios autenticados de la organización, los usuarios invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera. En la página Teams opciones de reunión del cliente, aparece como "Personas a las que invito". Los usuarios agregados como parte de un grupo de distribución tendrán que pasar por la sala de espera.      |

 > [!NOTE]
> Las organizaciones de confianza son dominios con los que se permiten las comunicaciones federadas en Teams. Si habilita **Permitir todos los dominios externos** para el acceso externo en el centro de administración de Teams, cualquier usuario autenticado dentro de cualquier Teams organización será de confianza. Si elige especificar dominios externos permitidos y bloquear todos los demás, los dominios permitidos se convertirán en organizaciones de confianza. Se considera que cualquier dominio bloqueado no es una organización de confianza.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Permitir que los usuarios de acceso telefónico omitan la sala de espera

Esta es una directiva por organizador. Esta opción controla si las personas que llaman por teléfono se unen a la reunión directamente o si aguardan en la sala de espera, independientemente de la configuración de **Admitir participantes automáticamente**. Esta configuración está desactivada de forma predeterminada. Cuando esta opción está desactivada, los usuarios de marcado esperan en la sala de espera hasta que el usuario de la organización se una a la reunión con un cliente de Teams y los acepte. Cuando esta configuración está activada, los usuarios de acceso telefónico local se unirán automáticamente a la reunión cuando un usuario de la organización se una a la reunión con un cliente de Teams.

> [!NOTE]
> Si un usuario de marcado se une a la reunión antes de que lo haga un usuario de la organización, el primero aguardará en la sala de espera hasta que el usuario de la organización se incorpore a la reunión con un cliente de Teams y le acepte. Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.

## <a name="live-captions"></a>Subtítulos en directo

Esta configuración es una directiva por usuario y se aplica durante una reunión. Esta configuración controla si la opción **Activar los subtítulos en directo** está disponible para que el usuario active y desactive los subtítulos en directo en las reuniones a las que asista.  

![Captura de pantalla que muestra la opción Activar subtítulos en directo.](media/meeting-policies-live-captions.png)

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Deshabilitados pero el usuario puede invalidarlos**     | Los subtítulos en directo no se activan automáticamente durante una reunión. El usuario verá la opción **Activar subtítulos en directo** en el menú de desbordamiento **(...)** para activarlos. Esta configuración es la predeterminada. |
|**No habilitado**     | Durante una reunión, los subtítulos en directo se deshabilitan para el usuario. El usuario no tiene la opción de activarlos.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chatear en reuniones

Esta configuración es una configuración por participante. Esta configuración controla si se permite el chat de reunión en la reunión del usuario.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Habilitado**     | Todos los participantes pueden escribir y ver mensajes de chat. |
|**No habilitado**     | El chat de la reunión está desactivado para todos los participantes.  |

<a name="bkparticipantsandguests"> </a>

## <a name="enable-meeting-policy-settings"></a>Habilitar la configuración de la directiva de reunión

Para habilitar la configuración de la directiva de reunión, puede usar el [centro de administración de Teams](https://admin.teams.microsoft.com/policies/meetings) (**Directivas** >  de **reuniónEditar una** **directivaParticipants** >  & invitados) o el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) en Teams PowerShell. 

En este ejemplo, usamos PowerShell para modificar la directiva de reunión global para permitir que cualquier persona pueda iniciar una reunión o unirse a ella.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Una vez que haya configurado una directiva, debe aplicarla a los usuarios. Si ha modificado la directiva global (predeterminada para toda la organización), se aplicará automáticamente a los usuarios. Debe esperar al menos 4 horas para que los cambios de directiva surtan efecto, pero pueden tardar hasta 24 horas.


## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
