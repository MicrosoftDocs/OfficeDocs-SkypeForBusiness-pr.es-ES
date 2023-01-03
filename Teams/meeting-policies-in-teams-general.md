---
title: Administrar directivas generales de reuniones
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
- m365initiative-meetings
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Aprenda a administrar la configuración de directivas de reuniones generales en Teams.
ms.openlocfilehash: cc0d704c5a78d09da4c1332d48f795cdb611d134
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693383"
---
# <a name="meeting-policy-settings---general"></a>Configuración de la directiva de reunión. Aspectos generales

<a name="bkgeneral"> </a>

En este artículo se describen las siguientes configuraciones de directiva general para las reuniones de Teams:

- [Reunirse ahora en canales](#meet-now-in-channels)
- [Complemento de Outlook](#outlook-add-in)
- [Programación de reuniones de canal](#channel-meeting-scheduling)
- [Programación de reuniones privadas](#private-meeting-scheduling)
- [Informe de participación](#engagement-report)
- [Registro de reunión](#meeting-registration)
- [Seminarios web](#webinars)
- [Proveedor de reuniones para el modo Islas](#meeting-provider-for-islands-mode)
- [Reacciones de reuniones](#meeting-reactions)
- [Entrenador de altavoces](#speaker-coach)

## <a name="meet-now-in-channels"></a>Reunirse ahora en canales

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión no planeada en un canal de Teams. Si activa esta configuración, los usuarios pueden hacer clic en el botón **Reunirse** para iniciar una reunión no planeada o programar una reunión en el canal. Esta configuración está activada de forma predeterminada.

[![Captura de pantalla que muestra el icono Reunirse ahora debajo de un mensaje.](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Complemento de Outlook

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si se pueden programar reuniones de Teams desde Outlook (en Windows, Mac, web y dispositivos móviles).

![Captura de pantalla que muestra la posibilidad de programar una nueva reunión.](media/meeting-policies-outlook-add-in.png)

Si desactiva esta opción, los usuarios no podrán programar reuniones de Teams al crear una nueva reunión en Outlook. Por ejemplo, en Outlook en Windows, la opción **Nueva reunión de Teams** no se mostrará en la cinta de opciones.

## <a name="channel-meeting-scheduling"></a>Programación de reuniones de canal

Use la Directiva AllowChannelMeetingScheduling existente para controlar los tipos de eventos que se pueden crear en los calendarios del canal del equipo. Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión en un canal de Teams. Esta configuración está activada de forma predeterminada.

Si esta directiva está desactivada, los usuarios no podrán crear nuevas reuniones de canal. Sin embargo, el organizador del evento puede editar las reuniones de canal existentes.

Programar una reunión se deshabilitará.

![Captura de pantalla que muestra la opción Programar una reunión en Teams.](media/schedule-meeting-option.png)

La selección de canales está desactivada.

[![Captura de pantalla que muestra la opción de calendario para seleccionar un canal en el que desea programar una reunión.](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

En la página de publicaciones del canal, se deshabilitarán las siguientes funcionalidades:

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

![Captura de pantalla que muestra la directiva de permisos de aplicaciones en el Centro de administración de Teams.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Programación de reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo. **La programación de reuniones privadas** está activada de forma predeterminada.

Si desactiva la **configuración de programación de reuniones privada** y de **reunión de canal** , las opciones **Agregar asistentes necesarios** y **Agregar canal** están deshabilitadas para los usuarios de Teams.

## <a name="engagement-report"></a>Informe de participación

Esta es una directiva por usuario. Esta configuración controla si los organizadores de la reunión pueden descargar el [informe de interacción](teams-analytics-and-reports/meeting-attendance-report.md) de la reunión.

Esta directiva está activada de forma predeterminada y permite a los organizadores ver quién registró y asistió a las reuniones y seminarios web que configuró. Para desactivarla en el Centro de administración de Teams, vaya a **Directivas** >  de **reuniones de** reuniones y establezca la configuración del **informe de compromiso** en **Desactivado**.

También puede editar una directiva de reunión de Teams existente mediante el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

De forma predeterminada, el parámetro **AllowEngagementReport** se establece en **Habilitado** en PowerShell. Para evitar que un organizador de la reunión descargue el informe de interacción de la reunión, establezca el parámetro **AllowEngagementReport** en **Deshabilitado**.

Cuando esta directiva está habilitada, la opción para descargar el informe de interacción de la reunión se muestra en el panel **Participantes** .

> [!NOTE]
> Como administrador, no puede ver el informe de asistencia para las reuniones que no organiza. Sin embargo, puede ver los detalles de los participantes de una reunión determinada dentro de las 24 horas posteriores a esa reunión. En el Centro de administración de Teams, vaya a **Usuarios** > **administrar usuarios**. Elija el nombre para mostrar del organizador de la reunión. Seleccione la pestaña **Reuniones & llamadas** y, a continuación, elija el id. de reunión o el identificador de llamada adecuados. A continuación, seleccione **Detalles del participante**.

Para obtener más información, incluidos los límites del informe de participación, consulte [ver y descargar informes de asistencia a reuniones en Teams](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

## <a name="meeting-registration"></a>Registro de reunión

Esta es una directiva por usuario. Si activa esta configuración, los usuarios de su organización pueden agregar el registro a una reunión. Esta directiva está habilitada de forma predeterminada.

Para obtener más información sobre el registro de reuniones, lea [Configurar el registro de reuniones](set-up-webinars.md#configure-meeting-registration).

## <a name="webinars"></a>Seminarios web

Esta es una directiva por usuario. Si habilita seminarios web, los usuarios de su organización pueden crear seminarios web con una sólida administración del registro, sitios de registro y eventos personalizables, y opciones de reunión predeterminadas orientadas a eventos. Esta directiva está habilitada de forma predeterminada.

Obtenga más información sobre seminarios web en [Configurar seminarios web](set-up-webinars.md).

Para obtener más información sobre las diferencias entre reuniones, seminarios web y eventos en directo, vea [Reuniones, seminarios web y eventos en directo](quick-start-meetings-live-events.md).

## <a name="meeting-provider-for-islands-mode"></a>Proveedor de reuniones para el modo Islas

Esta es una directiva por usuario. Esta configuración controla qué complemento de la reunión de Outlook se usa para los *usuarios que están en modo Aplicaciones aisladas*. Puede especificar si los usuarios que se encuentran en modo de aplicaciones aisladas pueden usar solamente el complemento para reunión de Microsoft Teams o los complementos para reunión de Microsoft Teams y Skype Empresarial para programar reuniones en Outlook.

Solo puede aplicar esta directiva a los usuarios que se encuentren en modo Aplicaciones aisladas y tengan el parámetro **AllowOutlookAddIn** establecido en **True** en la directiva de reuniones de Microsoft Teams.

Actualmente, solo puede usar PowerShell para establecer esta directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar qué complemento de la reunión desea que esté disponible para los usuarios, establezca el parámetro **PreferredMeetingProviderForIslandsMode** como se indica a continuación:

- Establezca el parámetro en **TeamsAndSfB** para habilitar tanto el complemento de reuniones de Teams como el complemento de Skype Empresarial en Outlook. **TeamsAndSfB** es el valor predeterminado.
- Establezca el parámetro en **Teams** para habilitar solo el complemento de la reunión de Teams en Outlook. Esta configuración de directiva garantiza que todas las reuniones futuras tengan un vínculo para unirse a una reunión de Teams. No migra a Teams los vínculos existentes para unirse a reuniones de Skype Empresarial. Esta configuración de directiva no afecta a la presencia, el chat, las llamadas RTC ni cualquier otra función en Skype Empresarial, lo que significa que los usuarios seguirán empleando Skype Empresarial para estas funciones.

  Si establece el parámetro como **Teams** y, a continuación, vuelve a **TeamsAndSfB**, se habilitan los complementos de la reunión. Sin embargo, tenga en cuenta que los vínculos existentes para unirse a reuniones de Teams no se migrarán a Skype Empresarial. Solo las reuniones de Skype Empresarial programadas tras el cambio tendrán un vínculo para unirse a reuniones de Skype Empresarial.

## <a name="meeting-reactions"></a>Reacciones de reuniones

La disponibilidad de las reacciones a reuniones se puede configurar a través de la interfaz del Centro de administración de Teams o mediante PowerShell. Las reacciones de reunión están habilitadas de forma predeterminada.

En el Centro de administración de Teams, las reacciones de reunión se pueden habilitar o deshabilitar en las **directivas** >  de reunión de reuniones en **la sección Participantes & invitados** de una directiva de reunión.

Para configurar la configuración en PowerShell, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Para desactivarlo, establezca **AllowMeetingReactions en** **False**.

Desactivar las reacciones de un usuario no significa que un usuario no pueda usar reacciones en las reuniones que programe. El organizador de la reunión puede activar las reacciones desde la página de opciones de la reunión, independientemente de la configuración predeterminada.

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
