---
title: Directivas de reunión y expiración de la reunión en Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Aprenda a usar la configuración de la Directiva de reunión para controlar la expiración de la reunión en Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46641002"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Directivas de reunión y expiración de la reunión en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Información general

[Las directivas de reunión](meeting-policies-in-teams.md) de Microsoft Teams se usan para controlar si los usuarios de su organización pueden iniciar y programar reuniones y las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Las directivas de reunión se administran en el centro de administración de Microsoft Teams o mediante los cmdlets de PowerShell [Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy), [New](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy), [set](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy)y [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

La configuración de la Directiva de reunión que controla si los usuarios pueden iniciar y programar reuniones, también controlar el vencimiento de las reuniones programadas por los usuarios. Cuando expira un vínculo de unirse a una reunión e identificador de conferencia para una reunión, nadie puede unirse a la reunión. La siguiente configuración de la Directiva de reunión determina si los usuarios pueden iniciar y programar reuniones en Teams y hacemos referencia a ellas en este artículo.

- [Permitir reunirse ahora en canales](meeting-policies-in-teams.md#allow-meet-now-in-channels): controla si un usuario puede iniciar una reunión no planeada en un canal.
- [Permitir programación de reuniones de canal](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): controla si un usuario puede programar una reunión en un canal.
- [Permitir la programación de reuniones privadas](meeting-policies-in-teams.md#allow-scheduling-private-meetings): controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Permitir el complemento de Outlook](meeting-policies-in-teams.md#allow-the-outlook-add-in): controla si un usuario puede programar una reunión privada desde Outlook. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Permitir reunirse ahora en reuniones privadas](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings): controla si un usuario puede iniciar una reunión privada improvisada.

De forma predeterminada, esta configuración está activada. Cuando se desactiva cualquiera de estas opciones de configuración, cualquier usuario que tenga asignada la Directiva no puede iniciar ni programar nuevas reuniones de ese tipo. Al mismo tiempo, los vínculos de la combinación de reuniones y los identificadores de conferencia de todas las reuniones existentes de ese tipo que el usuario haya comenzado o programado previamente.

Por ejemplo, si se **asigna a un**usuario una directiva de reunión en la que se establece esta configuración de directiva de reunión y, después, desactiva la opción **permitir reunirse ahora en los canales** , ese usuario ya no podrá iniciar reuniones espontáneas en los canales, y los vínculos de unirse a Channel que el usuario ha creado previamente han expirado. El usuario aún puede iniciar y programar otros tipos de reunión y unirse a reuniones organizadas por otras personas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>¿Qué sucede cuando el vínculo de la Unión a la reunión y el identificador de la Conferencia vencen?

Cuando el vínculo de la Unión a la reunión y el identificador de conferencia expiren, nadie podrá unirse a la reunión. Cuando un usuario intenta unirse a la reunión a través del vínculo o por teléfono, recibirá un mensaje que indica que la reunión ya no está disponible. Las conversaciones, los archivos, las pizarras, las grabaciones, transcripciones y otros contenidos relacionados con la reunión se conservan y los usuarios pueden seguir teniendo acceso a ellas.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>¿Qué sucede cuando se activa y se desactiva una configuración de directiva de reunión?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Cambiar la configuración de una directiva de reunión de activada a desactivada

Cuando una configuración de directiva de reunión se establece **en activado**, los usuarios a los que se les asigna la Directiva pueden iniciar o programar reuniones de ese tipo y todos pueden unirse. Al cambiar la configuración de la Directiva de la reunión a **desactivada**, los usuarios que tienen asignada la Directiva no pueden iniciar ni programar nuevas reuniones de ese tipo, así como los vínculos de la Unión a la reunión y los identificadores de conferencia de las reuniones existentes que el usuario ha programado anteriormente.

Tenga en cuenta que el usuario aún puede unirse a reuniones organizadas por otras personas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Cambiar la configuración de una directiva de reunión de desactivada a activada

Al cambiar la configuración de una directiva de reunión de **desactivada** **, los**usuarios que tienen asignada la Directiva pueden iniciar o programar reuniones de ese tipo. Si la configuración de la Directiva de reunión está desactivada y, después, se activa de nuevo para un usuario, todas las reuniones programadas (y vencidas) organizadas por el usuario se activan y las personas pueden unirse a ellas mediante el vínculo para unirse a la reunión o por teléfono.  

## <a name="meeting-expiration-scenarios"></a>Escenarios de expiración de reuniones

Este es un resumen de cómo funciona la caducidad de la reunión para cada una de las configuraciones de la Directiva de reunión descritas en este artículo. 

|Si desea... |Haga lo siguiente  |Comportamiento de unirse a una reunión  |
|---------|---------|---------|
|Hacer que las reuniones del canal expiren ahora reuniones iniciadas por un usuario  |Desactive **permitir reunirse ahora en canales**.|Nadie puede unirse a las reuniones iniciadas por el canal.         |
|Hacer reuniones de canal vencidas programadas por un usuario   |Desactive **permitir programación de reuniones de canal**.         |Nadie puede unirse a las reuniones de canal programadas por el usuario. Esto impide que las personas se unan a lo siguiente:<ul><li>Reuniones de canal que tuvieron lugar en el pasado.</li> <li>Reuniones de canal que se programan para el futuro y que aún no se han producido.</li><li>Instancias futuras de reuniones de canales periódicas.</li></ul>       |
|Expirar las reuniones privadas programadas por un usuario    |Desactive la **opción permitir la programación de reuniones privadas** *y* desactivar **permitir el complemento de Outlook**.          |Nadie puede unirse a las reuniones privadas programadas por el usuario. Esto impide que las personas se unan a lo siguiente: <ul><li>Reuniones privadas que tuvieron lugar en el pasado.</li> <li>Reuniones privadas que se programan para el futuro y que aún no se han producido.</li><li>Instancias futuras de reuniones privadas periódicas.</li></ul> Ambos **permiten la programación de reuniones privadas** y **permiten que el complemento de Outlook** esté desactivado para que las reuniones privadas estén programadas por un usuario. Si una configuración está desactivada y la otra es activada, los vínculos de unirse a la reunión y los identificadores de conferencia de las reuniones existentes seguirán activos y no expirarán.      |
|Hacer que las reuniones privadas reunirse ahora sean iniciadas por un usuario  |Desactive **permitir reunirse ahora en reuniones privadas**.          |Nadie puede unirse a reuniones privadas reunirse ahora que haya iniciado el usuario.         |

Si desea que los usuarios tengan acceso a las reuniones programadas o iniciadas previamente por un usuario concreto, puede hacer lo siguiente:

- Active la configuración de la Directiva de reunión para ese usuario.
- Desactive la configuración de directiva de reunión de ese usuario y asegúrese de que otro usuario con la configuración de directiva permite crear una nueva reunión para reemplazar la reunión expirada.

> [!NOTE]
> Si un delegado envió la reunión, a quién se le han concedido permisos para enviar invitaciones a reuniones en nombre de otra persona, como un administrador, la configuración de la Directiva de reunión se aplica a la persona que concedió el permiso (el jefe).

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)

[Asignar directivas a los usuarios de Teams](assign-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)