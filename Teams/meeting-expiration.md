---
title: Directivas de reunión y expiración de reuniones en Microsoft Teams
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
description: Obtenga información sobre cómo usar la configuración de la directiva de reunión para controlar la expiración de una reunión en Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827530"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Directivas de reunión y expiración de reuniones en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Descripción general

[Las](meeting-policies-in-teams.md) directivas de reuniones de Microsoft Teams se usan para controlar si los usuarios de su organización pueden iniciar y programar reuniones, así como las características que están disponibles para los participantes de las reuniones programadas por los usuarios. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Puede administrar las directivas de reuniones en el Centro de administración de Microsoft Teams o mediante los cmdlets [Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy), [New,](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) [Remove,](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy) [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell.

La configuración de la directiva de reunión que controla si los usuarios pueden iniciar y programar reuniones también controlan la expiración de las reuniones programadas por los usuarios. Cuando el vínculo y el id. de conferencia para unirse a una reunión expiran, nadie puede unirse a la reunión. La siguiente configuración de directiva de reunión determina si los usuarios pueden iniciar y programar reuniones en Teams, como se muestra en este artículo.

- [Permitir reunirse ahora en canales:](meeting-policies-in-teams.md#allow-meet-now-in-channels)controla si un usuario puede iniciar una reunión improvisada en un canal.
- [Permitir la programación de reuniones del canal:](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)controla si un usuario puede programar una reunión en un canal.
- [Permitir la programación de reuniones privadas:](meeting-policies-in-teams.md#allow-scheduling-private-meetings)controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Permitir la adición de Outlook:](meeting-policies-in-teams.md#allow-the-outlook-add-in)controla si un usuario puede programar una reunión privada desde Outlook. Una reunión es privada cuando no se publica en un canal de un equipo.
- [Permitir reunirse ahora en reuniones privadas:](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)controla si un usuario puede iniciar una reunión privada no improvisada.

Esta configuración está predeterminada de manera predeterminada. Cuando cualquiera de estas configuraciones está desactivada, cualquier usuario al que se le asigne la directiva no podrá iniciar o programar reuniones nuevas de ese tipo. Al mismo tiempo, las reuniones se unen a vínculos e id. de conferencia de todas las reuniones existentes de ese tipo que el usuario ha iniciado o programado expirado previamente.

Por ejemplo, si se asigna a un usuario una directiva de reunión en la  que esta configuración de directiva de reunión está establecida en Activar y, a continuación, desactiva la opción Permitir reunirse ahora en los canales, dicho usuario ya no podrá iniciar reuniones impares en los canales y el canal Reunirse ahora expirará. El usuario aún puede iniciar y programar otros tipos de reuniones y unirse a reuniones organizadas por otras personas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>¿Qué sucede cuando expira el vínculo para unirse a la reunión y el id. de conferencia?

Cuando el vínculo para unirse a la reunión y el id. de conferencia para una reunión expiran, nadie puede unirse a la reunión. Cuando un usuario intenta unirse a la reunión a través del vínculo o por teléfono, recibe un mensaje que indica que la reunión ya no está disponible. Las conversaciones, los archivos, las pizarras, las grabaciones, las transcripciones y otros contenidos relacionados con la reunión se conservan y los usuarios aún pueden acceder a ellos.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>¿Qué sucede cuando activa y desactiva una configuración de directiva de reunión?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Cambiar la configuración de una directiva de reunión de activarla a desactivarla

Cuando la configuración de la directiva de reunión está establecida en **"On",** los usuarios a los que se les asigne la directiva podrán iniciar o programar reuniones de ese tipo y todos podrán unirse. Cuando cambia la configuración de la directiva de reunión a **Desactivado,** los usuarios a los que se asigna la directiva no pueden iniciar o programar reuniones nuevas de ese tipo, y los vínculos para unirse a la reunión e id. de conferencia de las reuniones existentes que el usuario programó previamente expirarán.

Tenga en cuenta que el usuario aún puede unirse a reuniones organizadas por otras personas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Cambiar la configuración de una directiva de reunión de desactivado a activar

Cuando cambia la configuración  de directiva de reunión de Desactivado a **Desactivado,** los usuarios a los que se les asigne la directiva podrán iniciar o programar reuniones de ese tipo. Si una configuración de directiva de reunión está desactivada y activada de nuevo para un usuario, todas las reuniones programadas previamente (y expiradas) organizadas por el usuario se activarán y las personas podrán unirse a ellas mediante el vínculo para unirse a la reunión o por teléfono.  

## <a name="meeting-expiration-scenarios"></a>Escenarios de expiración de la reunión

Este es un resumen de cómo funciona la expiración de la reunión para cada una de las configuraciones de directiva de reunión analizadas en este artículo. 

|Si quiere... |Haga lo siguiente  |Comportamiento de unión a reuniones  |
|---------|---------|---------|
|Expirar las reuniones del canal Reunirse ahora iniciadas por un usuario  |Desactive Permitir **reunirse ahora en canales.**|Nadie puede unirse al canal Reunirse ahora las reuniones iniciadas por el usuario.         |
|Expirar las reuniones del canal programadas por un usuario   |Desactive permitir la **programación de reuniones del canal.**         |Nadie puede unirse a las reuniones del canal programadas por el usuario. Esto evita que las personas se unan a lo siguiente:<ul><li>Reuniones de canal que tuvieron lugar en el pasado.</li> <li>Reuniones de canal que están programadas para el futuro y aún no se han producido.</li><li>Futuras instancias de reuniones periódicas del canal.</li></ul>       |
|Expirar reuniones privadas programadas por un usuario    |Desactive **Permitir la programación de reuniones privadas** *y* desactive Permitir el complemento **de Outlook.**          |Nadie puede unirse a reuniones privadas programadas por el usuario. Esto evita que las personas se unan a lo siguiente: <ul><li>Reuniones privadas que tuvieron lugar en el pasado.</li> <li>Reuniones privadas que están programadas para el futuro y aún no se han producido.</li><li>Futuras instancias de reuniones privadas periódicas.</li></ul> Tanto **Permitir la programación de reuniones privadas** como Permitir el complemento de **Outlook** deben estar desactivadas para expirar las reuniones privadas programadas por un usuario. Si una configuración está desactivada y la otra activada, los vínculos para unirse a reuniones y los ID de conferencia de las reuniones existentes seguirán activos y no expirarán.      |
|Expirar las reuniones privadas de Reunirse ahora iniciadas por un usuario  |Desactive Permitir **reunirse ahora en reuniones privadas.**          |Nadie puede unirse a reuniones privadas de Reunirse ahora iniciadas por el usuario.         |

Si desea que los usuarios accedan a reuniones previamente programadas o iniciadas por un usuario determinado, puede:

- Active la configuración de directiva de reunión para ese usuario.
- Desactive la configuración de directiva de reunión para ese usuario y haga que otro usuario que tenga habilitada la configuración de directiva habilite la creación de una nueva reunión para reemplazar la reunión expirada.

> [!NOTE]
> Si la reunión la envió un delegado, al que se le han concedido permisos para enviar invitaciones a reuniones en nombre de otra persona, como un jefe, la configuración de la directiva de reunión se aplica a la persona que ha concedido permiso (el administrador).

## <a name="related-topics"></a>Temas relacionados

[Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)

[Descripción de PowerShell para Teams](teams-powershell-overview.md)