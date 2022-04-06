---
title: Administrar directivas generales de reuniones
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
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de directivas de reuniones generales en Teams.
ms.openlocfilehash: 2582327261e52f1d834cd3b368c79aa55ca7f103
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686347"
---
# <a name="meeting-policy-settings---general"></a>Configuración de la directiva de reunión. Aspectos generales

<a name="bkgeneral"> </a>

En este artículo se describen las siguientes configuraciones de directiva general para las reuniones de Teams:

- [Reunirse ahora en canales](#meet-now-in-channels)
- [Outlook complemento](#outlook-add-in)
- [Programación de reuniones de canal](#channel-meeting-scheduling)
- [Programación de reuniones privadas](#private-meeting-scheduling)
- [Reunirse ahora en reuniones privadas](#meet-now-in-private-meetings)
- [Modo de rol de moderador designado](#designated-presenter-role-mode)
- [Informe de participación](#engagement-report)
- [Registro de reunión](#meeting-registration)
- [Quién pueden registrarse](#who-can-register)
- [Proveedor de reuniones para el modo Islas](#meeting-provider-for-islands-mode)
- [Entrenador de altavoces](#speaker-coach)

## <a name="meet-now-in-channels"></a>Reunirse ahora en canales

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión ad hoc en un canal Teams. Si lo activa, los usuarios pueden hacer clic en el botón **Reunirse** para iniciar una reunión ad hoc o programar una reunión en el canal. El valor predeterminado es True.

[![Captura de pantalla que muestra el icono Reunirse ahora debajo de un mensaje.](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook complemento

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si se pueden programar reuniones de Teams desde Outlook (en Windows, Mac, web y dispositivos móviles).

![Captura de pantalla que muestra la posibilidad de programar una nueva reunión.](media/meeting-policies-outlook-add-in.png)

Si desactiva esta opción, los usuarios no podrán programar reuniones Teams al crear una nueva reunión en Outlook. Por ejemplo, en Outlook en Windows, la opción **Nueva reunión de Teams** no se mostrará en la cinta de opciones.

## <a name="channel-meeting-scheduling"></a>Programación de reuniones de canal

Use la Directiva AllowChannelMeetingScheduling existente para controlar los tipos de eventos que se pueden crear en los calendarios del canal del equipo. Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión en un canal de Teams. Esta configuración está activada de forma predeterminada.

Si esta directiva está desactivada, los usuarios no podrán crear nuevas reuniones de canal. Sin embargo, el organizador del evento puede editar las reuniones de canal existentes.

Programar una reunión se deshabilitará.

![Captura de pantalla que muestra la opción Programar una reunión en Teams.](media/schedule-meeting-option.png)

La selección de canales está desactivada.

[![Captura de pantalla que muestra la opción de calendario para seleccionar un canal en el que desea programar una reunión.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

En la página de publicaciones del canal, se deshabilitarán las siguientes opciones:

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

![Captura de pantalla que muestra la directiva de permisos de aplicaciones en el centro de administración de Teams.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Programación de reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.

Tenga en cuenta que si desactiva **Permitir la programación de reuniones privadas** y **Permitir la programación de reuniones de canal**, las opciones **Agregar los asistentes necesarios** y **Agregar el canal** estarán deshabilitadas para los usuarios de Teams. Esta configuración está activada de forma predeterminada.

## <a name="meet-now-in-private-meetings"></a>Reunirse ahora en reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión privada ad hoc.  Esta configuración está activada de forma predeterminada.

## <a name="designated-presenter-role-mode"></a>Modo de rol de moderador designado

Esta es una directiva por usuario. Esta configuración le permite cambiar el valor predeterminado de la configuración **¿Quién puede encargarse de la moderación?** en **Opciones de reunión** en el cliente de Teams. Esta configuración de directiva afecta a todas las reuniones, incluidas las reuniones de Reunirse ahora.

La configuración **¿Quién puede encargarse de la moderación?** permite a los organizadores de reuniones elegir quién puede moderar una reunión. Para obtener más información, consulte [Cambiar la configuración de los participantes para una reunión de Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) y [Roles en una reunión de Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Actualmente, solo puede usar PowerShell para establecer esta configuración de directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar el valor predeterminado de la configuración **¿Quién puede encargarse de la moderación?** de Teams, establezca el parámetro **DesignatedPresenterRoleMode** en una de las siguientes opciones:

- **EveryoneUserOverride**: todos los participantes de la reunión pueden ser moderadores. Este es el valor predeterminado. Este parámetro corresponde a la configuración **Todos** de Teams.
- **EveryoneInCompanyUserOverride**: los usuarios autenticados en la organización, incluidos los invitados, pueden ser moderadores. Este parámetro corresponde a la configuración **Personas de mi organización** de Teams.
- **OrganizerOnlyUserOverride**: solo el organizador de la reunión puede ser moderador y todos los participantes de la reunión se designan como asistentes. Este parámetro corresponde a la configuración **Solo yo** de Teams.

Tenga en cuenta que, después de establecer el valor predeterminado, los organizadores de reuniones aún podrán cambiar esta configuración en Teams y elegir quién puede moderar las reuniones que programen.

## <a name="engagement-report"></a>Informe de participación

Esta es una directiva por usuario. Esta configuración controla si los organizadores de reuniones pueden descargar el [informe de asistencia a reuniones](teams-analytics-and-reports/meeting-attendance-report.md).

Esta directiva está activada de forma predeterminada y permite a los organizadores ver quién registró y asistió a las reuniones y seminarios web que configuró. Para desactivarla en el centro de administración de Teams, vaya a **Directivas de MeetingsMeeting** >  y establezca la configuración del **informe de interacción** en **Desactivado**.

También puede editar una directiva de reunión de Teams existente mediante el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

De forma predeterminada, el parámetro **AllowEngagementReport** se establece en **Habilitado** en PowerShell. Para evitar que un organizador de la reunión descargue el informe de asistencia a la reunión, establezca el parámetro **AllowEngagementReport** en **Deshabilitado**.

Cuando esta directiva está habilitada, la opción para descargar el informe de asistencia a la reunión se muestra en el panel **Participantes** .

> [!NOTE]
> Como administrador, no puede ver el informe de asistencia para las reuniones que no organiza. Sin embargo, puede ver los detalles de los participantes de una reunión determinada dentro de las 24 horas posteriores a esa reunión. En el centro de administración de Teams, vaya a **UsuariosAdministrar** >  usuarios. Elija el nombre para mostrar del organizador de la reunión. Seleccione la pestaña **Reuniones & llamadas** y, a continuación, elija el id. de reunión o el identificador de llamada adecuados. A continuación, seleccione **Detalles del participante**.

Para obtener más información, incluidos los límites del informe de participación, consulte [ver y descargar informes de asistencia a reuniones en Teams](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310).

## <a name="meeting-registration"></a>Registro de reunión

Esta es una directiva por usuario. Si lo activa, los usuarios de su organización pueden configurar seminarios web. Esta directiva está habilitada de forma predeterminada.

Para editar esta directiva en el centro de administración de Teams, vaya a **Directivas de MeetingsMeeting** > . Para desactivar el registro de reuniones, establezca la directiva en **Desactivado**.

Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para activar el registro de la reunión, establezca el parámetro  **MeetingRegistration** en **True**. De forma predeterminada, se establece en **True** .

Para desactivar el registro de reuniones e impedir que los usuarios programen seminarios web, establezca el parámetro en **False**.

## <a name="who-can-register"></a>Quién pueden registrarse

Esta directiva controla qué usuarios pueden registrar y asistir a seminarios web. Esta directiva tiene dos opciones, que solo están disponibles si el **registro de la reunión** está activado.

- Establezca **Quién puede registrarse** en **Todos** los usuarios si desea permitir que todos los usuarios, incluidos los usuarios anónimos, registren y asistan a seminarios web que configuren los usuarios de su organización.
- Establezca **Quién puede registrarse** **en Todos los usuarios de la organización** si desea permitir que solo los usuarios de su organización se registren y asistan a seminarios web.

De forma predeterminada, **Quién pueden registrarse** se establece en **Todos**. Para editar esta directiva en el centro de administración de Teams, vaya a **Directivas de MeetingsMeeting** > .

Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para permitir que todos los usuarios, incluidos los usuarios anónimos, puedan registrarse y asistir a seminarios web, establezca el parámetro **WhoCanRegister** en **Everyone**. Esta opción está establecida en **Todos de** forma predeterminada.

Para permitir que solo los usuarios de su organización puedan registrarse y asistir a seminarios web, establezca el parámetro en **EveryoneInCompany**.

## <a name="meeting-provider-for-islands-mode"></a>Proveedor de reuniones para el modo Islas

Esta es una directiva por usuario. Esta configuración controla qué complemento de la reunión de Outlook se usa para los *usuarios que están en modo Aplicaciones aisladas*. Puede especificar si los usuarios que se encuentran en modo de aplicaciones aisladas pueden usar solamente el complemento para reunión de Microsoft Teams o los complementos para reunión de Microsoft Teams y Skype Empresarial para programar reuniones en Outlook.

Solo puede aplicar esta directiva a los usuarios que se encuentren en modo Aplicaciones aisladas y tengan el parámetro **AllowOutlookAddIn** establecido en **True** en la directiva de reuniones de Microsoft Teams.

Actualmente, solo puede usar PowerShell para establecer esta directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar qué complemento de la reunión desea que esté disponible para los usuarios, establezca el parámetro **PreferredMeetingProviderForIslandsMode** como se indica a continuación:

- Establezca el parámetro en **TeamsAndSfB** para habilitar tanto el complemento de reuniones de Teams como el complemento de Skype Empresarial en Outlook. Este es el valor predeterminado.
- Establezca el parámetro en **Teams** para habilitar solo el complemento de la reunión de Teams en Outlook. Esta configuración de directiva garantiza que todas las reuniones futuras tengan un vínculo para unirse a una reunión de Teams. No migra a Teams los vínculos existentes para unirse a reuniones de Skype Empresarial. Esta configuración de directiva no afecta a la presencia, el chat, las llamadas RTC ni cualquier otra función en Skype Empresarial, lo que significa que los usuarios seguirán empleando Skype Empresarial para estas funciones.

  Si establece el parámetro como **Teams** y, a continuación, vuelve a **TeamsAndSfB**, se habilitan los complementos de la reunión. Sin embargo, tenga en cuenta que los vínculos existentes para unirse a reuniones de Teams no se migrarán a Skype Empresarial. Solo las reuniones de Skype Empresarial programadas tras el cambio tendrán un vínculo para unirse a reuniones de Skype Empresarial.

## <a name="meeting-reactions"></a>Reacciones de reuniones

La configuración AllowMeetingReactions solo se puede aplicar con PowerShell. No hay ninguna opción para activar o desactivar AllowMeetingReactions desde el Centro de administración de Teams.

Las reacciones a la reunión están desactivadas de forma predeterminada. Desactivar las reacciones a un usuario no significa que un usuario no pueda usar las reacciones en las reuniones que programe. El organizador de la reunión puede activar las reacciones desde la página de opciones de la reunión, independientemente de la configuración predeterminada.

## <a name="speaker-coach"></a>Entrenador de altavoces

Esta configuración permite a los usuarios activar el Asesor de oradores durante una reunión de Teams. El Asesor para oradores escucha el audio del usuario mientras presenta y proporciona comentarios privados en tiempo real y sugerencias para mejorar. El usuario también obtiene un informe resumido de sus comentarios después de la reunión.

> [!NOTE]
> El usuario que activó el Asesor para oradores durante la reunión es el único que puede ver el informe resumido de los comentarios. Los administradores no tendrán acceso a ninguno de estos datos.

Actualmente, solo puede establecer y editar esta directiva en PowerShell. mediante el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Esta configuración está habilitada de forma predeterminada. Para desactivarlo, establezca **AllowMeetingCoach** en **False**.

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas en Teams](policy-assignment-overview.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
