---
title: Administrar el acceso anónimo de participantes a las reuniones de Teams (administradores de TI)
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 'Para profesionales de TI: obtenga información sobre cómo funciona la participación anónima en las reuniones en Microsoft Teams.'
ms.openlocfilehash: a4f1833059febf2f8481cba9f1b3716519613e89
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983738"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a>Administrar el acceso anónimo de participantes a las reuniones de Teams (administradores de TI)

Los participantes anónimos en reuniones hospedadas por su organización son aquellos cuya identidad no se puede comprobar. Esto podría incluir:

- Personas que no han iniciado sesión en Teams con una cuenta profesional o educativa 
- Personas de organizaciones que no son de confianza (configuradas en [acceso externo](manage-external-access.md)) y de organizaciones en las que confía pero que no confían en su organización.

Unirse a una reunión anónima se controla mediante una configuración de nivel de organización y directivas de nivel de usuario. Para que funcione unirse a una reunión anónima:
- La configuración **Usuarios anónimos pueden unirse a una reunión** de Teams (nivel de organización) debe estar activada.
- Al organizador de la reunión se le debe asignar una directiva de reunión de Teams en la que el control **Permitir que personas anónimas se unan a una reunión** está activado.

Unirse a una reunión anónima está activado de forma predeterminada para la organización y en la directiva de reunión global predeterminada. Se recomienda mantener la configuración de nivel de organización activada y usar las directivas de reunión para activar o desactivar la unión anónima a la reunión para diferentes usuarios (organizadores de la reunión).

Tenga en cuenta que si está habilitada la opción de unirse a una reunión anónima, las directivas de la sala de espera afectan a la forma en que los participantes anónimos se unen a las reuniones. Para obtener más información, consulte [Controlar quién puede omitir la sala de espera de la reunión en Microsoft Teams](who-can-bypass-meeting-lobby.md).

#### <a name="meetings-with-trusted-organizations"></a>Reuniones con organizaciones de confianza

Al configurar organizaciones de confianza para reuniones externas y chats, los asistentes a las reuniones de esas organizaciones pueden considerarse anónimos si la configuración de acceso externo no está configurada correctamente para ambas organizaciones. Para obtener más información, consulte [Organizaciones de confianza para reuniones y chats externos](manage-external-access.md).

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>Administrar unirse a una reunión anónima para la organización

La configuración de unión anónima a una reunión de nivel de organización debe estar activada para que cualquier persona de la organización pueda crear reuniones que permitan participantes anónimos.

> [!Important]
> Los **participantes anónimos pueden unirse a una reunión** de toda la organización se quitarán en el futuro. Se recomienda dejar activada **esta opción y** usar el control **de directiva Permitir que personas anónimas se unan a una reunión** de nivel de usuario para permitir o evitar la unión anónima a una reunión.

Para configurar unirse a una reunión anónima para la organización
1. Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com).

1. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de la reunión**.

1. En **Participantes**, establezca **Participantes anónimos pueden unirse a una reunión** **en Activado** (recomendado) o **Desactivado**.

    ![Captura de pantalla de la configuración de los participantes para las reuniones en el centro de administración.](media/meeting-settings-participants.png "Captura de pantalla de la configuración de los participantes para las reuniones de Teams en el centro de administración de Microsoft Teams.")

1. Seleccione **Guardar**.

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>Administrar qué organizadores de reuniones pueden permitir unirse a la reunión de forma anónima

Puede controlar qué usuarios o grupos pueden hospedar reuniones que incluyan participantes anónimos. Para ello, asigne una directiva de reunión con unirse a una reunión anónimo activado a cada organizador de la reunión que necesite hospedar reuniones con participantes anónimos.

Para configurar unirse a una reunión anónima para organizadores específicos de la reunión
1. Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com).

1. En el panel de navegación izquierdo, vaya a **Directivas** > **de reunión de reuniones**.

1. Seleccione la directiva que desea modificar.

1. Establezca **Permitir que personas anónimas se unan a una reunión** **en Activado**.

1. Seleccione **Guardar**.

Los cambios en las directivas de reuniones pueden tardar hasta 24 horas en surtir efecto.

## <a name="configure-anonymous-meeting-join-using-powershell"></a>Configurar unirse a una reunión anónima con PowerShell

Puede controlar si los participantes anónimos pueden unirse a las reuniones mediante:

- El `-DisableAnonymousJoin` parámetro de [Set-CsTeamsMeetingConfiguration](/powershell/module/skype/set-csteamsmeetingconfiguration) para configurar la configuración de nivel de organización. (Se recomienda dejar esta opción establecida en False y usar Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting para controlar la unión anónima a la reunión en el nivel de usuario o grupo).
- El `-AllowAnonymousUsersToJoinMeeting` parámetro [de Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para configurar una directiva de reunión a nivel de usuario

Para permitir que participantes anónimos se unan a reuniones, debe configurar ambos para permitir la unión anónima a la reunión estableciendo los siguientes valores:

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin` establecido en **$false**
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting` establecido en **$true** para los organizadores de la reunión relevantes

## <a name="block-anonymous-meeting-join-for-specific-client-types"></a>Bloquear la unión anónima a una reunión para tipos de cliente específicos

Cuando los participantes anónimos pueden unirse a reuniones, pueden usar el cliente de Teams o un cliente personalizado creado con [Azure Communication Services](/azure/communication-services/). 

Los administradores pueden bloquear cualquiera de estos tipos de cliente mediante el `-BlockedAnonymousJoinClientTypes` parámetro [en Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes).

## <a name="anonymous-participants-meeting-experience"></a>Experiencia de reunión de participantes anónimos

Los participantes anónimos no tienen todas las mismas capacidades que otros participantes de la reunión. Por ejemplo, participantes anónimos:

- No tener acceso al chat de la reunión antes y después de la reunión
- No tiene acceso a las tarjetas de perfil (tarjetas de perfil en Microsoft 365 Soporte técnico de Microsoft)

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>Cómo interactúan los participantes anónimos con las aplicaciones en las reuniones

De forma predeterminada, está habilitada la configuración para permitir que participantes anónimos interactúen con aplicaciones en reuniones.

Para configurar el acceso de aplicaciones para participantes anónimos de la reunión

1. Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com).

1. En la navegación izquierda, diríjase a **Reuniones** > **Configuración de la reunión**.

1. En **Participantes**, establezca  **Participantes anónimos pueden interactuar con aplicaciones en reuniones en** **Activado** o **Desactivado**.

También puede controlar esto con PowerShell mediante `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers`.

Los participantes anónimos heredan la directiva de permisos global (predeterminada para toda la organización) de Teams. Los participantes anónimos pueden interactuar con aplicaciones en las reuniones de Teams siempre que la aplicación esté habilitada en esa directiva y **los participantes anónimos puedan interactuar con las aplicaciones en las reuniones** esté **Activada**.

Tenga en cuenta que los participantes anónimos solo pueden interactuar con aplicaciones que ya están disponibles en una reunión y no pueden adquirir ni administrar estas aplicaciones.

## <a name="related-topics"></a>Temas relacionados

[Unirse a una reunión sin una cuenta de Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Usar el Centro de administración de Microsoft Teams para configurar la directiva de toda la organización](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[Los participantes externos reciben "Iniciar sesión en Teams para unirse o ponerse en contacto con el organizador de la reunión"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[Asignar directivas en Teams: introducción](policy-assignment-overview.md)