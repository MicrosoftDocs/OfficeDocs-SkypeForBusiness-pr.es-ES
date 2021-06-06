---
title: Administrar directivas de reunión para participantes e invitados
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
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
description: Obtenga información sobre cómo administrar la configuración de la directiva de reunión en Teams para participantes e invitados.
ms.openlocfilehash: bec3f82c66984147f109dc68cc97376c502dd9a6
ms.sourcegitcommit: f5b6a0fe055e42e06eee21ce311813b5127474ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52741059"
---
# <a name="meeting-policy-settings---participants--guests"></a>Configuración de la directiva de reuniones: participantes e invitados

<a name="bkmeetingparticipants"> </a>

Esta configuración controla qué participantes de la reunión se quedan en la sala de espera antes de ser admitidos en la reunión y qué nivel de participación se les permite.

- [Permitir que los usuarios anónimos inicien una reunión](#let-anonymous-people-start-a-meeting)
- [Admitir automáticamente usuarios](#automatically-admit-people)
- [Permitir que los usuarios de acceso telefónico omitan la sala de espera](#allow-dial-in-users-to-bypass-the-lobby)
- [Activar subtítulos en directo](#enable-live-captions)
- [Permitir el chat en las reuniones](#allow-chat-in-meetings)

> [!NOTE]
>Las opciones para unirse a una reunión pueden variar en función de la configuración de cada grupo de Teams y del método de conexión. Si el grupo tiene audioconferencia y la usa para conectarse, consulte [Audioconferencia](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Si el grupo de Teams no tiene ninguna Audioconferencia, consulte [Unirse a una reunión en Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-start-a-meeting"></a>Permitir que los usuarios anónimos inicien una reunión

Esta configuración es una directiva por organizador que permite reuniones de conferencias de acceso telefónico local sin líderes. Esta configuración controla si los usuarios de acceso por marcado pueden unirse a la reunión sin que asista un usuario autenticado de la organización. De forma predeterminada, esta configuración está desactivada, lo que significa que los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un usuario autenticado de la organización se una a la reunión.

> [!NOTE]
> Si esta opción está desactivada y un usuario de marcado se une primero a la reunión y se le ubica en la sala de espera, el usuario de la organización debe unirse a la reunión con un cliente de Teams para admitir al usuario de la sala de espera. No hay ningún control de sala de espera disponible para los usuarios con acceso de marcado.

## <a name="automatically-admit-people"></a>Admitir automáticamente usuarios

Esta es una directiva por organizador. Esta configuración controla si los usuarios pueden unirse a una reunión directamente o esperar en la sala de espera hasta que un usuario autenticado los admita. Esta configuración no se aplica a los usuarios de marcado.

![Captura de pantalla que muestra una reunión con un usuario en la sala de espera](media/meeting-policies-lobby.png)

 Los organizadores de la reunión pueden hacer clic en las **Opciones de reunión** en la invitación a la reunión para cambiar esta configuración en cada una de las reuniones programadas.

> [!NOTE]
> En las opciones de reunión, la configuración está etiquetada como "Quién puede omitir la sala de espera". Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y a las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.
  
|Valor de configuración  |Comportamiento para unirse |
|---------|---------|
|**Todos**   |Todos los participantes se unen a la reunión directamente sin tener que esperar en la sala de espera. Esto incluye a los usuarios autenticados, los usuarios externos de organizaciones de confianza (federados), los invitados y los usuarios anónimos.     |
|**Usuarios en mi organización e invitados**     |Los usuarios autenticados de la organización, incluidos los usuarios invitados, se unen a la reunión directamente sin esperar en la sala de espera.  Los usuarios anónimos esperan en la sala de espera.   |
|**Usuarios de mi organización y de organizaciones de confianza e invitados**     |Los usuarios autenticados en la organización, incluidos los usuarios invitados y los usuarios de las organizaciones de confianza, pueden unirse a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios anónimos esperan en la sala de espera.   |
|**Todos los miembros de mi organización**    |Los usuarios autenticados en la organización, incluidos los usuarios invitados, pueden unirse a la reunión directamente sin tener que esperar en la sala de espera.  Los usuarios de organizaciones de confianza y los usuarios anónimos aguardan en la sala de espera. Esta configuración es la predeterminada.           |
|**Solo organizador**    |Solo los organizadores de la reunión se pueden unir a la reunión directamente sin tener que esperar en la sala de espera. Todos los demás, incluidos los usuarios autenticados de la organización, los usuarios invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera.           |
|**Solo usuarios invitados**    |Solo los usuarios invitados y los organizadores de la reunión pueden unirse a la reunión directamente sin esperar en la sala de espera. Todos los demás, incluidos los usuarios autenticados de la organización, los usuarios invitados, los usuarios de organizaciones de confianza y los usuarios anónimos deben esperar en la sala de espera.           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Permitir que los usuarios de acceso telefónico omitan la sala de espera

Esta es una directiva por organizador. Esta opción controla si las personas que llaman por teléfono se unen a la reunión directamente o si aguardan en la sala de espera, independientemente de la configuración de **Admitir participantes automáticamente**. Esta configuración está desactivada de forma predeterminada. Cuando esta opción está desactivada, los usuarios de marcado esperan en la sala de espera hasta que el usuario de la organización se una a la reunión con un cliente de Teams y los acepte. Cuando esta opción está activada, los usuarios de marcado se unirán automáticamente a la reunión cuando un usuario de la organización se una.

> [!NOTE]
> Si un usuario de marcado se une a la reunión antes de que lo haga un usuario de la organización, el primero aguardará en la sala de espera hasta que el usuario de la organización se incorpore a la reunión con un cliente de Teams y le acepte. Si cambia la configuración predeterminada para cualquier usuario, se aplicará a todas las reuniones nuevas organizadas por ese usuario y las reuniones anteriores en las que el usuario no haya modificado las opciones de reunión.

## <a name="enable-live-captions"></a>Activar subtítulos en directo

Esta configuración es una directiva por usuario y se aplica durante una reunión. Esta configuración controla si la opción **Activar los subtítulos en directo** está disponible para que el usuario active y desactive los subtítulos en directo en las reuniones a las que asista.  

![Captura de pantalla que muestra la opción Activar subtítulos en directo](media/meeting-policies-live-captions.png)

|Valor de configuración |Comportamiento  |
|---------|---------|
|**Deshabilitados pero el usuario puede invalidarlos**     | Los subtítulos en directo no se activan automáticamente durante una reunión. El usuario verá la opción **Activar subtítulos en directo** en el menú de desbordamiento **(...)** para activarlos. Esta configuración es la predeterminada. |
|**Deshabilitado**     | Durante una reunión, los subtítulos en directo se deshabilitan para el usuario. El usuario no tiene la opción de activarlos.          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>Permitir el chat en las reuniones

Esta configuración es una configuración por participante. Esta configuración controla si se permite el chat de reunión en la reunión del usuario.

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](assign-policies.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
