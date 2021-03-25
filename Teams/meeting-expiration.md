---
title: Directivas de reunión y expiración de la reunión en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Obtenga información sobre cómo usar la configuración de directiva de reunión para controlar la expiración de la reunión en Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 1685da93c90d8d12cc4e8b8f2a92fd4f93391c87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115568"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Directivas de reunión y expiración de la reunión en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Información general

[Las directivas de](meeting-policies-in-teams.md) reunión de Microsoft Teams se usan para controlar si los usuarios de su organización pueden iniciar y programar reuniones y las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Puede administrar directivas de reunión en el centro de administración de Microsoft Teams o mediante [Los](/powershell/module/skype/get-csteamsmeetingpolicy)cmdlets de PowerShell Get , [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell.

La configuración de directiva de reunión que controla si los usuarios pueden iniciar y programar reuniones también controlan la expiración de las reuniones programadas por los usuarios. Cuando un vínculo de unirse a una reunión y el id. de conferencia de una reunión expiran, nadie puede unirse a la reunión. La siguiente configuración de directiva de reunión determina si los usuarios pueden iniciar y programar reuniones en Teams, y nos referimos a ellas en este artículo.

- [Permitir reunirse ahora en canales:](meeting-policies-in-teams.md#allow-meet-now-in-channels)controla si un usuario puede iniciar una reunión improvisada en un canal.
- [Permitir la programación de reuniones del canal:](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)controla si un usuario puede programar una reunión en un canal.
- [Permitir la programación de reuniones privadas:](meeting-policies-in-teams.md#allow-scheduling-private-meetings)controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Permitir el complemento de Outlook:](meeting-policies-in-teams.md#allow-the-outlook-add-in)controla si un usuario puede programar una reunión privada desde Outlook. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Permitir reunirse ahora en reuniones privadas:](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)controla si un usuario puede iniciar una reunión privada improvisada.

De forma predeterminada, esta configuración está en. Cuando cualquiera de estas opciones de configuración está desactivada, cualquier usuario al que se le haya asignado la directiva no puede iniciar ni programar nuevas reuniones de ese tipo. Al mismo tiempo, la reunión une vínculos e id. de conferencia de todas las reuniones existentes de ese tipo que el usuario inició o programó anteriormente expiran.

Por ejemplo, si a un usuario se le asigna una directiva de reunión en  la que esta configuración de directiva de reunión se establece en Activar y, después, desactiva la configuración Permitir reunirse ahora en canales, ese usuario ya no puede iniciar reuniones improvisadas en canales y el canal Reunirse ahora se une a vínculos que el usuario creó anteriormente han expirado. El usuario puede seguir iniciando y programando otros tipos de reunión y unirse a reuniones organizadas por otras personas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>¿Qué sucede cuando expira el vínculo de unirse a la reunión y el id. de conferencia?

Cuando el vínculo de unirse a la reunión y el id. de conferencia de una reunión expiran, nadie puede unirse a la reunión. Cuando un usuario intenta unirse a la reunión a través del vínculo o por teléfono, recibe un mensaje que indica que la reunión ya no está disponible. Las conversaciones, los archivos, las pizarras, las grabaciones, las transcripciones y otros contenidos relacionados con la reunión se conservan y los usuarios pueden seguir accediendo a ellas.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>¿Qué sucede cuando activa y desactiva una configuración de directiva de reunión?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Cambiar una configuración de directiva de reunión de activar a desactivar

Cuando una configuración de directiva de reunión se establece en **On**, los usuarios que tienen asignada la directiva pueden iniciar o programar reuniones de ese tipo y todos pueden unirse. Al cambiar la configuración de directiva de reunión a **Desactivado,** los usuarios a los que se les ha asignado la directiva no pueden iniciar ni programar nuevas reuniones de ese tipo, y los vínculos de combinación de reuniones y los id. de conferencia de las reuniones existentes que el usuario programó previamente expiraron.

Tenga en cuenta que el usuario todavía puede unirse a reuniones organizadas por otras personas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Cambiar una configuración de directiva de reunión de desactivado a encendido

Al cambiar una configuración de directiva de reunión de **Desactivado** a **Activar,** los usuarios que tienen asignada la directiva pueden iniciar o programar reuniones de ese tipo. Si una configuración de directiva de reunión está desactivada y, a continuación, se vuelve a activar para un usuario, todas las reuniones programadas previamente (y expiradas) organizadas por el usuario se activarán y las personas podrán unirse a ellas mediante el vínculo de unirse a la reunión o por teléfono.  

## <a name="meeting-expiration-scenarios"></a>Escenarios de expiración de la reunión

Este es un resumen de cómo funciona la expiración de la reunión para cada una de las configuraciones de directiva de reunión que se debate en este artículo. 

|Si quiere... |Haga esto  |Comportamiento de unirse a la reunión  |
|---------|---------|---------|
|Expire channel Meet now meetings started by a user  |Desactive Permitir **reunirse ahora en canales.**|Nadie puede unirse al canal Reunirse ahora las reuniones iniciadas por el usuario.         |
|Expirar reuniones del canal programadas por un usuario   |Desactive Permitir **la programación de reuniones del canal.**         |Nadie puede unirse a las reuniones del canal programadas por el usuario. Esto impide que las personas se unan a lo siguiente:<ul><li>Reuniones del canal que se produjeron en el pasado.</li> <li>Reuniones de canal que están programadas para el futuro y que aún no se han producido.</li><li>Futuras instancias de reuniones periódicas del canal.</li></ul>       |
|Expirar reuniones privadas programadas por un usuario    |Desactive **Permitir la programación de reuniones privadas** *y* desactive Permitir el complemento **de Outlook.**          |Nadie puede unirse a reuniones privadas programadas por el usuario. Esto impide que las personas se unan a lo siguiente: <ul><li>Reuniones privadas que tuvieron lugar en el pasado.</li> <li>Reuniones privadas programadas para el futuro y que aún no se han producido.</li><li>Futuras instancias de reuniones privadas periódicas.</li></ul> Tanto **Permitir la programación de reuniones privadas** como Permitir el complemento **de Outlook** deben estar desactivados para expirar las reuniones privadas programadas por un usuario. Si una configuración está desactivada y la otra está activada, los vínculos de combinación de reuniones y los IDs de conferencia de las reuniones existentes permanecen activos y no expirarán.      |
|Expirar reuniones privadas de Reunirse ahora iniciadas por un usuario  |Desactive **Permitir reunirse ahora en reuniones privadas.**          |Nadie puede unirse a reuniones privadas de Reunirse ahora iniciadas por el usuario.         |

Si desea que los usuarios accedan a las reuniones programadas o iniciadas previamente por un usuario determinado, puede:

- Active la configuración de directiva de reunión para ese usuario.
- Desactive la configuración de directiva de reunión para ese usuario y haga que otro usuario que tenga habilitada la configuración de directiva cree una nueva reunión para reemplazar la reunión expirada.

> [!NOTE]
> Si la reunión fue enviada por un delegado, a quien se le otorgaron permisos para enviar invitaciones de reunión en nombre de otra persona, como un administrador, la configuración de directiva de reunión se aplica a la persona que ha concedido permiso (el administrador).

## <a name="related-topics"></a>Temas relacionados

[Administración de directivas de reunión en Teams](meeting-policies-in-teams.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)