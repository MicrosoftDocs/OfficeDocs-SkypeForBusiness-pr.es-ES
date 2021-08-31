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
description: Obtenga información sobre cómo administrar la configuración general de la directiva de reunión en Teams.
ms.openlocfilehash: be28acd1a343988fef94546f405a1f7a3684d4ce
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731669"
---
# <a name="meeting-policy-settings---general"></a>Configuración de la directiva de reunión. Aspectos generales

<a name="bkgeneral"> </a>

En este artículo se describen las siguientes opciones de configuración de directiva general Teams reuniones:

- [Permitir la opción Reunirse ahora en canales](#allow-meet-now-in-channels)
- [Permitir el complemento de Outlook](#allow-the-outlook-add-in)
- [Permitir la programación de reuniones de canal](#allow-channel-meeting-scheduling)
- [Permitir la programación de reuniones privadas](#allow-scheduling-private-meetings)
- [Permitir Reunirse ahora en reuniones privadas](#allow-meet-now-in-private-meetings)
- [Modo de rol moderador designado](#designated-presenter-role-mode)
- [Permitir informe de participación](#allow-engagement-report)
- [Permitir el registro de la reunión](#allow-meeting-registration)
- [Quién registro](#who-can-register)
- [Proveedor de reuniones para el modo Islas](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a>Permitir la opción Reunirse ahora en canales

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión ad hoc en un canal Teams usuario. Si activa esta opción, los  usuarios pueden hacer clic en el botón Reunirse para iniciar una reunión ad hoc o programar una reunión en el canal. El valor predeterminado es True.

[![Captura de pantalla que muestra el icono Reunirse ahora debajo de un mensaje. ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="allow-the-outlook-add-in"></a>Permitir el complemento de Outlook

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si se pueden programar reuniones de Teams desde Outlook (en Windows, Mac, web y dispositivos móviles).

![Captura de pantalla que muestra la capacidad de programar una nueva reunión.](media/meeting-policies-outlook-add-in.png)

Si desactiva esta opción, los usuarios no podrán programar Teams reuniones cuando creen una nueva reunión en Outlook. Por ejemplo, en Outlook en Windows, la opción **Nueva reunión de Teams** no se mostrará en la cinta de opciones.

## <a name="allow-channel-meeting-scheduling"></a>Permitir la programación de reuniones de canal

Use la Directiva AllowChannelMeetingScheduling existente para controlar los tipos de eventos que se pueden crear en los calendarios del canal del equipo. Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión en un canal de Teams. Esta configuración está activada de forma predeterminada. 

Si esta directiva está desactivada, los usuarios no podrán crear nuevas reuniones de canal. Sin embargo, el organizador del evento puede editar las reuniones de canal existentes.

Programar una reunión se deshabilitará.

![Captura de pantalla que muestra la opción Programar una reunión en Teams.](media/schedule-meeting-option.png)

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

![Captura de pantalla que muestra la directiva de permisos de la aplicación en el Teams de administración.](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a>Permitir la programación de reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede programar una reunión privada en Teams. Una reunión es privada cuando no se publica en un canal de un equipo.

Tenga en cuenta que si desactiva **Permitir la programación de reuniones privadas** y **Permitir la programación de reuniones de canal**, las opciones **Agregar los asistentes necesarios** y **Agregar el canal** estarán deshabilitadas para los usuarios de Teams. Esta configuración está activada de forma predeterminada.

## <a name="allow-meet-now-in-private-meetings"></a>Permitir la opción Reunirse ahora en las reuniones privadas

Esta es una directiva por usuario y se aplica antes de que se inicie la reunión. Esta configuración controla si un usuario puede iniciar una reunión privada ad hoc.  Esta configuración está activada de forma predeterminada.

## <a name="designated-presenter-role-mode"></a>Modo de rol moderador designado

Esta es una directiva por usuario. Esta configuración le permite cambiar el valor predeterminado de la configuración **¿Quién puede encargarse de la moderación?** en **Opciones de reunión** en el cliente de Teams. Esta configuración de directiva afecta a todas las reuniones, incluidas las reuniones de Reunirse ahora.

La configuración **¿Quién puede encargarse de la moderación?** permite a los organizadores de reuniones elegir quién puede moderar una reunión. Para obtener más información, consulte [Cambiar la configuración de los participantes para una reunión de Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) y [Roles en una reunión de Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Actualmente, solo puede usar PowerShell para establecer esta configuración de directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar el valor predeterminado de la configuración **¿Quién puede encargarse de la moderación?** de Teams, establezca el parámetro **DesignatedPresenterRoleMode** en una de las siguientes opciones:

- **EveryoneUserOverride**: todos los participantes de la reunión pueden ser moderadores. Este es el valor predeterminado. Este parámetro corresponde a la configuración **Todos** de Teams.
- **EveryoneInCompanyUserOverride**: los usuarios autenticados en la organización, incluidos los invitados, pueden ser moderadores. Este parámetro corresponde a la configuración **Personas de mi organización** de Teams.
- **OrganizerOnlyUserOverride**: solo el organizador de la reunión puede ser moderador y todos los participantes de la reunión se designan como asistentes. Este parámetro corresponde a la configuración **Solo yo** de Teams.

Tenga en cuenta que, después de establecer el valor predeterminado, los organizadores de reuniones aún podrán cambiar esta configuración en Teams y elegir quién puede moderar las reuniones que programen.

## <a name="allow-engagement-report"></a>Permitir informe de participación

Esta es una directiva por usuario. Esta configuración controla si los organizadores de reuniones pueden descargar el [informe de asistencia a reuniones](teams-analytics-and-reports/meeting-attendance-report.md).

Esta directiva está desactivada de forma predeterminada y permite a los organizadores ver quién se registró y asistió a las reuniones y seminarios web que han configurado. Para activar esta opción en el centro Teams de administración, vaya a Directivas de reunión de reuniones y establezca la directiva  >  en **Habilitado.**

Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para permitir que un organizador de la reunión descargue el informe de asistencia a la reunión, establezca el parámetro **AllowEngagementReport** en **Habilitado.** Cuando se habilita, la opción para descargar el informe se muestra en el panel **Participantes**. De forma predeterminada, esta configuración no está habilitada.

Para impedir que el organizador de la reunión descargue el informe, establezca el parámetro en **Deshabilitado**.

## <a name="allow-meeting-registration"></a>Permitir el registro de la reunión

Esta es una directiva por usuario. Si activa esta opción, los usuarios de su organización pueden configurar seminarios web. Esta directiva está habilitada de forma predeterminada.

Para editar esta directiva en el centro Teams de administración, vaya a **Directivas de reunión** de  >  **reuniones.** Para desactivar el registro de la reunión, establezca la directiva en **Desactivado.**

Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para activar el registro de la reunión, establezca el parámetro  **AllowMeetingRegistration** en **True**. Se establece en **True de** forma predeterminada.

Para desactivar el registro de reuniones e impedir que los usuarios programe seminarios web, establezca el parámetro en **Falso.**

## <a name="who-can-register"></a>Quién registro

Esta directiva controla qué usuarios pueden registrarse y asistir a seminarios web. Esta directiva tiene dos opciones, que solo están disponibles si permitir el registro **de reunión** está activado.

- Establezca Quién puede **registrarse**  en Todos si desea permitir que todos los usuarios, incluidos los usuarios anónimos, se registren y asistan a seminarios web que los usuarios de su organización configuren.
- Establezca **Quién puede registrarse**  en Todos los miembros de la organización si desea permitir que solo los usuarios de su organización se registren y asistan a seminarios web.

De forma predeterminada, **Quién puede registrar** se establece en **Todos.** Para editar esta directiva en el centro Teams de administración, vaya a **Directivas de reunión** de  >  **reuniones.**

Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para permitir que todos, incluidos los usuarios anónimos, se registren y asistan a seminarios web, establezca el parámetro **WhoCanRegister** en **Todos.** Se establece en Todos **de** forma predeterminada.

Para permitir que solo los usuarios de su organización se registren y asistan a seminarios web, establezca el parámetro **en EveryoneInCompany**.

## <a name="meeting-provider-for-islands-mode"></a>Proveedor de reuniones para el modo Islas

Esta es una directiva por usuario. Esta configuración controla qué complemento de la reunión de Outlook se usa para los *usuarios que están en modo Aplicaciones aisladas*. Puede especificar si los usuarios solo pueden usar el complemento de la reunión de Teams o los complementos de reuniones de Teams y Skype Empresarial para programar reuniones en Outlook.

Solo puede aplicar esta directiva a los usuarios que se encuentren en modo Aplicaciones aisladas y tengan el parámetro **AllowOutlookAddIn** establecido en **True** en la directiva de reuniones de Microsoft Teams.

Actualmente, solo puede usar PowerShell para establecer esta directiva. Para editar una directiva de reunión de Teams existente, use el cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). También puede crear una nueva directiva de reunión de Teams con el cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) y asignarla a los usuarios.

Para especificar qué complemento de la reunión desea que esté disponible para los usuarios, establezca el parámetro **PreferredMeetingProviderForIslandsMode** como se indica a continuación:

- Establezca el parámetro en **TeamsAndSfB** para habilitar tanto el complemento de reuniones de Teams como el complemento de Skype Empresarial en Outlook. Este es el valor predeterminado.
- Establezca el parámetro en **Teams** para habilitar solo el complemento de la reunión de Teams en Outlook. Esta configuración de directiva garantiza que todas las reuniones futuras tengan un vínculo para unirse a una reunión de Teams. No migra a Teams los vínculos existentes para unirse a reuniones de Skype Empresarial. Esta configuración de directiva no afecta a la presencia, el chat, las llamadas RTC ni cualquier otra función en Skype Empresarial, lo que significa que los usuarios seguirán empleando Skype Empresarial para estas funciones.

  Si establece el parámetro como **Teams** y, a continuación, vuelve a **TeamsAndSfB**, se habilitan los complementos de la reunión. Sin embargo, tenga en cuenta que los vínculos existentes para unirse a reuniones de Teams no se migrarán a Skype Empresarial. Solo las reuniones de Skype Empresarial programadas tras el cambio tendrán un vínculo para unirse a reuniones de Skype Empresarial.

## <a name="meeting-reactions"></a>Reacciones a la reunión

La configuración AllowMeetingReactions solo se puede aplicar con PowerShell. No hay ninguna opción para activar o desactivar AllowMeetingReactions desde el Centro de administración de Teams.

Las reacciones a la reunión están desactivadas de forma predeterminada. Desactivar las reacciones a un usuario no significa que un usuario no pueda usar las reacciones en las reuniones que programe. El organizador de la reunión puede activar las reacciones desde la página de opciones de la reunión, independientemente de la configuración predeterminada.


## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas en Teams](policy-assignment-overview.md)
- [Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess](meeting-policies-restricted-anonymous-access.md)
