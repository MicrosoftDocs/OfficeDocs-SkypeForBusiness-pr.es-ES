---
title: Administrar directivas de reunión para participantes e invitados
ms.author: mabond
author: mkbond007
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
description: Aprenda a administrar la configuración de directivas de reunión en Teams para participantes e invitados.
ms.openlocfilehash: 26d2fd24d8b241b8f79276148ed27abd3e5412b1
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693393"
---
# <a name="meeting-policy-settings---participants--guests"></a>Configuración de la directiva de reuniones: participantes e invitados

<a name="bkmeetingparticipants"> </a>

Esta configuración controla qué participantes de la reunión esperan en la sala de espera antes de ser admitidos en la reunión y el nivel de participación que se les permite en una reunión.

- [Permitir que personas anónimas se unan a una reunión](#let-anonymous-people-join-a-meeting)
- [Permitir que los usuarios anónimos inicien una reunión](#let-anonymous-people-start-a-meeting)
- [Quién puede presentar en reuniones](#who-can-present-in-meetings)
- [Admitir automáticamente usuarios](#automatically-admit-people)
- [Los usuarios de acceso telefónico local pueden omitir la sala de espera](#dial-in-users-can-bypass-the-lobby)
- [Reunirse ahora en reuniones privadas](#meet-now-in-private-meetings)
- [Subtítulos en directo](#live-captions)
- [Chatear en reuniones](#chat-in-meetings)
- [Teams Q&A](#teams-qa)
- [Reacciones de reuniones](#meeting-reactions)

Esta configuración se encuentra en el Centro de administración de Teams, en **Directivas** >  de **reunión** de reuniones, en la sección **Participantes & invitados**.

> [!NOTE]
> Las opciones para unirse a una reunión pueden variar en función de la configuración de cada grupo de Teams y del método de conexión. Si el grupo tiene audioconferencia y la usa para conectarse, consulte [Audioconferencia](/microsoftteams/audio-conferencing-in-office-365). Si el grupo de Teams no tiene ninguna Audioconferencia, consulte [Unirse a una reunión en Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Permitir que personas anónimas se unan a una reunión

Esta configuración por organizador permite a cualquier persona unirse a las reuniones como usuario anónimo seleccionando el vínculo en la invitación a la reunión. Para más información, consulte[Únase a una reunión sin una cuenta de Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508). La capacidad de los usuarios anónimos para unirse a reuniones también se controla en el nivel de su organización, la configuración más restrictiva será eficaz. Para obtener más información, consulte [Uso del Centro de administración de Microsoft Teams para configurar directivas para toda la organización](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Permitir que los usuarios anónimos inicien una reunión

Esta configuración es una directiva por organizador que permite reuniones de conferencia de acceso telefónico local sin coordinadores. Esta configuración controla si los usuarios anónimos y los autores de llamadas de acceso telefónico pueden unirse a la reunión sin un usuario autenticado de la organización que participe. De forma predeterminada, esta configuración está desactivada, lo que significa que los usuarios anónimos y los autores de llamadas de acceso telefónico local esperarán en la sala de espera hasta que un usuario autenticado de la organización se una a la reunión.

> [!NOTE]
> Si esta opción está desactivada y un usuario de marcado se une primero a la reunión y se le ubica en la sala de espera, el usuario de la organización debe unirse a la reunión con un cliente de Teams para admitir al usuario de la sala de espera. No hay ningún control de sala de espera disponible para los usuarios con acceso de marcado.

## <a name="who-can-present-in-meetings"></a>Quién puede presentar en reuniones

Esta configuración es una directiva por usuario que le permite cambiar el valor predeterminado de la configuración **¿Quién puede presentar?** en **Opciones de reunión** del cliente de Teams. La configuración de directiva **Quién puede presentar en las reuniones** afecta a todas las reuniones, incluidas las reuniones de Reunirse ahora.

La configuración **¿Quién puede encargarse de la moderación?** permite a los organizadores de reuniones elegir quién puede moderar una reunión. Para obtener más información, consulte [Cambiar la configuración de los participantes para una reunión de Teams](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) y [Roles en una reunión de Teams](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Para especificar el valor predeterminado de la configuración **¿Quién puede presentar?** en Teams, establezca una de las siguientes opciones en la directiva **¿Quién puede presentar en las reuniones** ?:

- **Organizadores, pero los usuarios pueden invalidarlo**: solo el organizador de la reunión puede ser moderador y todos los participantes de la reunión se designan como asistentes. Este parámetro corresponde a la configuración **Solo yo** de Teams.
- **Todos los usuarios de la organización, pero el usuario pueden invalidarlo**: los usuarios autenticados de la organización, incluidos los invitados, pueden ser moderadores. Esta configuración corresponde a la **configuración de Personas en mi organización** en Teams.
- **Todos, excepto el usuario, pueden invalidarlo**: todos los participantes de la reunión pueden ser moderadores. Este es el valor predeterminado. Esta configuración corresponde a la configuración **Todos** en Teams.

Tenga en cuenta que, después de establecer el valor predeterminado, los organizadores de reuniones aún podrán cambiar esta configuración en Teams y elegir quién puede moderar las reuniones que programen.

## <a name="automatically-admit-people"></a>Admitir automáticamente usuarios

Esta es una directiva por organizador. Esta configuración controla si las personas se unen a una reunión directamente o esperan en la sala de espera hasta que un usuario autenticado las admita. Esta configuración no se aplica a los usuarios de acceso telefónico local.

![Captura de pantalla que muestra una reunión con un usuario en la sala de espera.](media/meeting-policies-lobby.png)

 Los organizadores de la reunión pueden hacer clic en las **Opciones de reunión** en la invitación a la reunión para cambiar esta configuración en cada una de las reuniones programadas.

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|Valor de configuración  |Comportamiento para unirse |
|---------|---------|
|**Todos**   |Todos los participantes se unen a la reunión directamente sin tener que esperar en la sala de espera. Esto incluye usuarios autenticados, usuarios de organizaciones de confianza, invitados y usuarios anónimos.     |
|**Usuarios en mi organización e invitados**     |Los usuarios autenticados de la organización, incluidos los invitados, se unen a la reunión directamente sin tener que esperar en la sala de espera. Los usuarios de organizaciones de confianza y los usuarios anónimos aguardan en la sala de espera. Esta configuración es la predeterminada.    |
|**Usuarios de mi organización y de organizaciones de confianza e invitados**     |Los usuarios autenticados de la organización, incluidos los invitados y los usuarios de organizaciones de confianza, se unen a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios anónimos esperan en la sala de espera.   |
|**Usuarios en mi organización**    |Los usuarios autenticados de la organización se unen a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios de organizaciones de confianza, invitados y usuarios anónimos esperan en la sala de espera.          |
|**Solo organizador**    |Solo los organizadores de la reunión se pueden unir a la reunión directamente sin tener que esperar en la sala de espera. Todos los demás usuarios, incluidos los usuarios autenticados de la organización, los invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera. En la página de opciones de reunión de cliente de Teams, aparece como "Solo yo".          |
|**Solo usuarios invitados**    |Solo los usuarios invitados y los organizadores de la reunión pueden unirse a la reunión directamente sin tener que esperar en la sala de espera. Todos los demás usuarios, incluidos los usuarios autenticados de la organización, los invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera. En la página de opciones de reunión de cliente de Teams, aparece como "Personas invito". Los usuarios agregados como parte de un grupo de distribución tendrán que pasar por la sala de espera.      |

 > [!NOTE]
> Las organizaciones de confianza son dominios con los que se permiten las comunicaciones federadas en Teams. Si habilita **Permitir el acceso externo a todos los dominios externos** en el Centro de administración de Teams, cualquier usuario autenticado dentro de cualquier organización de Teams será de confianza. Si elige especificar dominios externos permitidos y bloquear todos los demás, los dominios permitidos se convertirán en organizaciones de confianza. Se considera que cualquier dominio bloqueado no es una organización de confianza.

## <a name="dial-in-users-can-bypass-the-lobby"></a>Los usuarios de acceso telefónico local pueden omitir la sala de espera

Esta es una directiva por organizador. Esta opción controla si las personas que llaman por teléfono se unen a la reunión directamente o si aguardan en la sala de espera, independientemente de la configuración de **Admitir participantes automáticamente**. Esta configuración está desactivada de forma predeterminada. Cuando esta opción está desactivada, los usuarios de marcado esperan en la sala de espera hasta que el usuario de la organización se una a la reunión con un cliente de Teams y los acepte. Cuando esta configuración está activada, los usuarios de acceso telefónico local se unirán automáticamente a la reunión cuando un usuario de la organización se una a la reunión con un cliente de Teams.

> [!NOTE]
> Si un usuario de marcado se une a la reunión antes de que lo haga un usuario de la organización, el primero aguardará en la sala de espera hasta que el usuario de la organización se incorpore a la reunión con un cliente de Teams y le acepte. Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.

## <a name="meet-now-in-private-meetings"></a>Reunirse ahora en reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión privada no planeada. Esta configuración está activada de forma predeterminada.

## <a name="live-captions"></a>Subtítulos en directo

Esta configuración es una directiva por usuario y se aplica durante una reunión. Esta configuración controla si la opción **Activar los subtítulos en directo** está disponible para que el usuario active y desactive los subtítulos en directo en las reuniones a las que asista.  

![Captura de pantalla que muestra la opción Activar subtítulos en directo.](media/meeting-policies-live-captions.png)

|Valor de configuración |Comportamiento  |
|---------|---------|
|**No está habilitado, pero el usuario puede invalidarlo**     | Los subtítulos en directo no se activan automáticamente durante una reunión. El usuario verá la opción **Activar subtítulos en directo** en el menú de desbordamiento **(...)** para activarlos. Esta configuración es la predeterminada. |
|**No habilitado**     | Durante una reunión, los subtítulos en directo se deshabilitan para el usuario. El usuario no tiene la opción de activarlos.          |

Para obtener más información sobre cómo los usuarios finales pueden activar **los subtítulos en directo**, vea [Usar subtítulos en directo en una reunión de Teams](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260).

### <a name="live-translated-captions"></a>Subtítulos traducidos en directo

> [!NOTE]
> Esta característica está disponible temporalmente en la versión preliminar pública. Después de la vista previa, el organizador de la reunión debe tener una licencia de Teams Premium para que los asistentes usen subtítulos traducidos en directo.

De forma predeterminada, **los subtítulos en directo** se muestran en el idioma que se habla durante una reunión. **Los subtítulos traducidos en directo** permiten a los usuarios ver los subtítulos traducidos al idioma con el que se sientan más cómodos.

Para habilitar **los subtítulos traducidos en directo**, los **subtítulos** en directo deben establecerse en **No habilitado, pero el usuario puede reemplazarlo** en el Centro de administración de Teams. Para desactivar los **subtítulos traducidos en directo**, establezca esta opción en **No habilitado**.

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chatear en reuniones

Se trata de una directiva por usuario y por organizador. Esta configuración controla si se permite el chat de reunión en la reunión del usuario. Esta configuración no se aplica a las reuniones del canal.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Actígalo para todos los usuarios**     | Todos los participantes pueden escribir y ver mensajes de chat. |
|**Desactívala para todos los usuarios**     | El chat de la reunión está desactivado para todos los participantes.  |
|**Actígalo para todos los usuarios excepto los anónimos**     | El acceso de escritura por chat de la reunión está desactivado solo para participantes anónimos.  |

Una vez que esta directiva de **Chat en reuniones** se aplica a los usuarios, un organizador no puede invalidar esta directiva a través de **las Opciones de reunión**.

La directiva aplicada al organizador de la reunión puede afectar a otros usuarios de la reunión. Por ejemplo:

- Si el organizador tiene la opción **Chat en reuniones establecida en** **Activar para todos los** usuarios o **Activarla para todos los usuarios excepto anónimos**, se aplicará la directiva individual de un usuario y los usuarios que tengan **la opción Desactivar para todos** los usuarios establecida no podrán chatear en la reunión.
- Si el organizador tiene la opción **Chat en reuniones establecida en** **Desactivarla para todos los usuarios**, se aplica la directiva del organizador y nadie podrá chatear en la reunión.

<a name="bkparticipantsandguests"> </a>

## <a name="teams-qa"></a>Teams Q&A

Esta es una directiva por organizador. Esta configuración activa o desactiva la experiencia preguntas & respuestas (Q&A).

La configuración se aplica cuando los organizadores crean o actualizan una reunión. Esta configuración está desactivada de forma predeterminada. Obtenga más información sobre [Q&A en Reuniones de Teams](/manage-qna-for-teams).

Teams Q&A se puede ajustar dentro del centro de administración de Teams en **Directivas** >  de **reunión** de reuniones en la sección **Participantes & invitados**. El parámetro `-QnAEngagementMode` controla esta directiva en PowerShell.

|Valor de configuración |Comportamiento  |
|---------|---------|
|**On**     | Los organizadores pueden agregar Q&A al crear reuniones. |
|**Desactivado**     | Los organizadores no tendrán la opción de agregar Q&A al crear reuniones.  |

## <a name="meeting-reactions"></a>Reacciones de reuniones

Las reacciones de reunión están activadas de forma predeterminada. Desactivar las reacciones a un usuario no significa que un usuario no pueda usar las reacciones en las reuniones que programe. El organizador de la reunión puede activar las reacciones desde la página de opciones de la reunión, independientemente de la configuración predeterminada.

## <a name="enable-meeting-policy-settings"></a>Habilitar la configuración de la directiva de reunión

Para habilitar la configuración de la directiva de reunión, puede usar el [Centro de administración de Teams](https://admin.teams.microsoft.com/policies/meetings) (Directivas de **reunión** > **Editar una directiva** > **Participantes & invitados**) o el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) en Teams PowerShell.

En este ejemplo, usamos PowerShell para modificar la directiva de reunión global para permitir que cualquier persona pueda iniciar una reunión o unirse a ella.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Una vez que haya configurado una directiva, debe aplicarla a los usuarios. Si ha modificado la directiva global (predeterminada para toda la organización), se aplicará automáticamente a los usuarios. Debe esperar al menos 4 horas para que los cambios de directiva surtan efecto, pero pueden tardar hasta 24 horas.

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
