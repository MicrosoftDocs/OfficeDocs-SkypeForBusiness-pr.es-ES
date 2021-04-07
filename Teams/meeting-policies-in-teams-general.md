---
title: Administrar directivas generales de reuniones
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
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Obtenga información sobre cómo administrar la configuración general de la directiva de reunión en Teams.
ms.openlocfilehash: fb5f537e5cc96ba363fb4aa68bbfff2af513db6b
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598764"
---
# <a name="meeting-policy-settings---general"></a>Configuración de la directiva de reunión. Aspectos generales

<a name="bkgeneral"> </a>

En este artículo se describen las siguientes opciones de configuración de directiva general para las reuniones de Teams:

- [Permitir la opción Reunirse ahora en canales](#allow-meet-now-in-channels)
- [Permitir el complemento de Outlook](#allow-the-outlook-add-in)
- [Permitir la programación de reuniones de canal](#allow-channel-meeting-scheduling)
- [Permitir la programación de reuniones privadas](#allow-scheduling-private-meetings)
- [Permitir Reunirse ahora en reuniones privadas](#allow-meet-now-in-private-meetings)
- [Modo de rol moderador designado](#designated-presenter-role-mode)
- [Informe de asistencia a la reunión](#meeting-attendance-report)
- [Proveedor de reuniones para el modo Islas](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a>Permitir la opción Reunirse ahora en canales

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión ad hoc en un canal de Teams. Si activa esta opción, los  usuarios pueden hacer clic en el botón Reunirse para iniciar una reunión ad hoc o programar una reunión en el canal. El valor predeterminado es True.

[![Captura de pantalla que muestra el icono Reunirse ahora debajo de un mensaje ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="allow-the-outlook-add-in"></a>Permitir el complemento de Outlook

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si se pueden programar reuniones de Teams desde Outlook (en Windows, Mac, web y dispositivos móviles).

![Captura de pantalla que muestra la posibilidad de programar una nueva reunión](media/meeting-policies-outlook-add-in.png)

Si desactiva esta opción, los usuarios no podrán programar reuniones de Teams cuando creen una nueva reunión en Outlook. Por ejemplo, en Outlook en Windows, la opción **Nueva reunión de Teams** no se mostrará en la cinta de opciones.

## <a name="allow-channel-meeting-scheduling"></a>Permitir la programación de reuniones de canal

Use la Directiva AllowChannelMeetingScheduling existente para controlar los tipos de eventos que se pueden crear en los calendarios del canal del equipo. Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión en un canal de Teams. Esta configuración está activada de forma predeterminada. 

Si esta directiva está desactivada, los usuarios no podrán crear nuevas reuniones de canal. Sin embargo, el organizador del evento puede editar las reuniones de canal existentes.

Programar una reunión se deshabilitará.

![Captura de pantalla que muestra la opción Programar una reunión en Teams](media/schedule-meeting-option.png)

La selección de canales está desactivada.

[Captura de pantalla que muestra la opción de calendario para seleccionar un canal en el que ![ desea programar una reunión. ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

En la página de publicaciones del canal, se deshabilitará lo siguiente:

- El botón **Programar una reunión** en el cuadro de redactar respuesta del canal.
  ![Captura de pantalla que muestra la opción de calendario para seleccionar un canal en el que desea programar una reunión.](media/schedule-meeting-disabled-in-chat2.png)
  
- El botón **Programar una reunión** en el encabezado del canal.
  ![Captura de pantalla que muestra la opción de calendario para seleccionar un canal a través del cual desea programar una reunión.](media/schedule-now-in-header.png)

En el calendario del canal:

- El botón **Agregar nuevo evento** en el encabezado del calendario del canal se deshabilitará.
  ![Captura de pantalla que muestra la opción de calendario para seleccionar un canal que le permitirá programar una reunión.](media/add-new-event-disabled.png)

- Los usuarios no podrán arrastrar y seleccionar un bloque de tiempo en el calendario del canal para crear una reunión de canal.

- Los usuarios no pueden usar métodos abreviados de teclado para crear una reunión en el calendario del canal.

En el Centro de administración:

La aplicación Calendario de canal se mostrará en la sección **Aplicaciones de Microsoft** en la página de directivas de permisos de la aplicación.

![Captura de pantalla que muestra la directiva de permisos de la aplicación en el Centro de administración de Teams.](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a>Permitir la programación de reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.

Tenga en cuenta que si desactiva **Permitir la programación de reuniones privadas** y **Permitir la programación de reuniones de canal**, las opciones **Agregar los asistentes necesarios** y **Agregar el canal** estarán deshabilitadas para los usuarios de Teams. Esta configuración está activada de forma predeterminada.

## <a name="allow-meet-now-in-private-meetings"></a>Permitir la opción Reunirse ahora en las reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión privada ad hoc.  Esta configuración está activada de forma predeterminada.

## <a name="designated-presenter-role-mode"></a>Modo de rol moderador designado

Esta es una directiva por usuario. Esta configuración le permite cambiar el valor predeterminado de la configuración **¿Quién puede encargarse de la moderación?** en **Opciones de reunión** en el cliente de Teams. Esta configuración de directiva afecta a todas las reuniones, incluidas las reuniones de Reunirse ahora.

La configuración **¿Quién puede encargarse de la moderación?** permite a los organizadores de reuniones elegir quién puede moderar una reunión. Para obtener más información, consulte [Cambiar la configuración de los participantes para una reunión de Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) y [Roles en una reunión de Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Actualmente, solo puede usar PowerShell para establecer esta configuración de directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar el valor predeterminado de la configuración **¿Quién puede encargarse de la moderación?** de Teams, establezca el parámetro **DesignatedPresenterRoleMode** en una de las siguientes opciones:

- **EveryoneUserOverride**: todos los participantes de la reunión pueden ser moderadores. Este es el valor predeterminado. Este parámetro corresponde a la configuración **Todos** de Teams.
- **EveryoneInCompanyUserOverride**: los usuarios autenticados en la organización, incluidos los invitados, pueden ser moderadores. Este parámetro corresponde a la configuración **Personas de mi organización** de Teams.
- **OrganizerOnlyUserOverride**: solo el organizador de la reunión puede ser moderador y todos los participantes de la reunión se designan como asistentes. Este parámetro corresponde a la configuración **Solo yo** de Teams.

Tenga en cuenta que, después de establecer el valor predeterminado, los organizadores de reuniones aún podrán cambiar esta configuración en Teams y elegir quién puede moderar las reuniones que programen.

## <a name="meeting-attendance-report"></a>Informe de asistencia a la reunión

Esta es una directiva por usuario. Esta configuración controla si los organizadores de reuniones pueden descargar el [informe de asistencia a reuniones](teams-analytics-and-reports/meeting-attendance-report.md).

Actualmente, solo puede usar PowerShell para establecer esta configuración de directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para permitir que el organizador de la reunión descargue el informe de asistencia a reuniones, establezca el parámetro **AllowEngagementReport** en **Habilitado**. Cuando se habilita, la opción para descargar el informe se muestra en el panel **Participantes**.

Para impedir que el organizador de la reunión descargue el informe, establezca el parámetro en **Deshabilitado**. De forma predeterminada, esta opción está deshabilitada y la opción para descargar el informe no está disponible.

## <a name="meeting-provider-for-islands-mode"></a>Proveedor de reuniones para el modo Islas

Esta es una directiva por usuario. Esta configuración controla qué complemento de la reunión de Outlook se usa para los *usuarios que están en modo Aplicaciones aisladas*. Puede especificar si los usuarios solo pueden usar el complemento de la reunión de Teams o los complementos de reuniones de Teams y Skype Empresarial para programar reuniones en Outlook.

Solo puede aplicar esta directiva a los usuarios que se encuentren en modo Aplicaciones aisladas y tengan el parámetro **AllowOutlookAddIn** establecido en **True** en la directiva de reuniones de Microsoft Teams.

Actualmente, solo puede usar PowerShell para establecer esta directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar qué complemento de la reunión desea que esté disponible para los usuarios, establezca el parámetro **PreferredMeetingProviderForIslandsMode** como se indica a continuación:

- Establezca el parámetro en **TeamsAndSfB** para habilitar tanto el complemento de reuniones de Teams como el complemento de Skype Empresarial en Outlook. Este es el valor predeterminado.
- Establezca el parámetro en **Teams** para habilitar solo el complemento de la reunión de Teams en Outlook. Esta configuración de directiva garantiza que todas las reuniones futuras tengan un vínculo para unirse a una reunión de Teams. No migra a Teams los vínculos existentes para unirse a reuniones de Skype Empresarial. Esta configuración de directiva no afecta a la presencia, el chat, las llamadas RTC ni cualquier otra función en Skype Empresarial, lo que significa que los usuarios seguirán empleando Skype Empresarial para estas funciones.

  Si establece el parámetro como **Teams** y, a continuación, vuelve a **TeamsAndSfB**, se habilitan los complementos de la reunión. Sin embargo, tenga en cuenta que los vínculos existentes para unirse a reuniones de Teams no se migrarán a Skype Empresarial. Solo las reuniones de Skype Empresarial programadas tras el cambio tendrán un vínculo para unirse a reuniones de Skype Empresarial.

## <a name="meeting-reactions"></a>Reacciones a la reunión

La configuración AllowMeetingReactions solo se puede aplicar con PowerShell. No hay ninguna opción para activar o desactivar AllowMeetingReactions desde el Centro de administración de Teams.

Las reacciones a las reuniones están desactivadas de forma predeterminada. Desactivar las reacciones de un usuario no significa que un usuario no pueda usar las reacciones en las reuniones que programe. El organizador de la reunión puede activar las reacciones desde la página de opciones de reunión, independientemente de la configuración predeterminada.


## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](assign-policies.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
