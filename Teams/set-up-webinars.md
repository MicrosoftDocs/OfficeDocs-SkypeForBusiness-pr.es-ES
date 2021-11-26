---
title: Configurar seminarios web en Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Obtenga información sobre cómo administrar directivas de seminario web para Teams reuniones.
ms.openlocfilehash: 19918d7a32a9a5069dab8dc87011de6112bbe364
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205560"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurar seminarios web en Microsoft Teams

Este artículo le ayudará a configurar su organización para hospedar seminarios web.

## <a name="what-are-webinars"></a>¿Qué son los seminarios web?

Los seminarios web son reuniones estructuradas en las que los presentadores y los participantes tienen roles claros, a menudo usados con fines de aprendizaje o escenarios de generación de clientes potenciales de ventas y marketing.

Después de configurar seminarios web en su organización, los usuarios pueden programar seminarios web y abrir el registro a los asistentes. A diferencia de las reuniones tradicionales que incluyen muchas discusiones y tareas, los seminarios web están diseñados para presentaciones interactivas y proporcionan herramientas para el análisis de los asistentes.

> [!IMPORTANT]
> Para permitir que los usuarios configuren seminarios web, Listas Microsoft deben configurarse en SharePoint habilitando la creación de listas personales. Para obtener más información, vea [Configuración de control para Listas Microsoft](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Permitir a los usuarios programar seminarios web en el Teams de administración

Puede usar el centro de Teams para configurar seminarios web para su organización. Encontrará las directivas para configurar seminarios web en el centro de administración de Teams en **Directivas de reunión** de  >  **reuniones.**

### <a name="meeting-registration"></a>Registro de reunión

Si activa esta opción, los usuarios pueden programar seminarios web. De forma predeterminada, esta opción está activada. Si desea desactivar el registro de la reunión, establezca esta directiva en **Desactivado.**

> [!IMPORTANT]
> **La programación privada de reuniones** debe estar en marcha para que el registro de la reunión funcione. De forma predeterminada, esta directiva está activada en el Teams de administración. Para los alumnos de los inquilinos educativos, esta directiva está desactivada de forma predeterminada. Para obtener más información sobre cómo habilitar la programación de reuniones privadas para los alumnos, vea Teams para Educación [directivas y paquetes de directivas.](policy-packages-edu.md)

### <a name="who-can-register"></a>Quién registro

Si selecciona **Todos, todos** los usuarios, incluidos los usuarios anónimos, pueden registrarse y asistir a seminarios web. Si selecciona **Todos los miembros de la organización,** solo los usuarios de su organización pueden registrarse en seminarios web. Si el registro de la reunión está desactivado, esta opción no estará disponible y nadie podrá registrarse en seminarios web.

> [!NOTE]
> El valor predeterminado de **Quién puede registrar** es Todos los miembros de la **organización** en inquilinos educativos. Para obtener más información, [vea Teams para Educación de directivas](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Informe de participación

Si activa esta opción, los organizadores pueden ver informes de quién se registró y asistió a los seminarios web que configuraron. Esta directiva está desactivada de forma predeterminada. Para obtener más información, vea [Directivas de reunión en Teams - Informe de participación.](meeting-policies-in-teams-general.md#engagement-report) Para obtener información sobre la experiencia del usuario final, vea [Ver y descargar informes de asistencia a reuniones.](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir a los usuarios programar seminarios web con PowerShell

Puede usar los siguientes atributos dentro del cmdlet **Set-CsTeamsMeetingPolicy de Windows PowerShell set-CsTeamsMeetingPolicy** para configurar seminarios web en Teams.

- MeetingRegistration
- WhoCanRegister
- PrivateMeetingScheduling

Lea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener más información sobre el cmdlet.

> [!NOTE]
> Antes de poder ejecutar estos cmdlets, debe estar conectado a Microsoft Teams PowerShell. Para obtener más información, vea [Administrar Teams con Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Permitir a los usuarios programar seminarios web

Puede restringir el registro solo a los usuarios de su organización o abrirlo a todos los usuarios, tanto dentro como fuera de su inquilino. De forma predeterminada, **WhoCanRegister** está habilitado y establecido en **Todos** para la **directiva global (predeterminada para** toda la organización). Si desea desactivar el registro de la reunión, establezca **MeetingRegistration en** **False**.

> [!IMPORTANT]
> **PrivateMeetingScheduling** debe establecerse en **True** para **que MeetingRegistration** funcione.

1. Activar el registro de la reunión

```powershell
Set-CsTeamsMeetingPolicy -MeetingRegistration $True
```

2. Activar la programación de reuniones privadas

```powershell
Set-CsTeamsMeetingPolicy -PrivateMeetingScheduling $True
```

3. Configurar quién puede registrarse en seminarios web

**Permitir *que solo* los usuarios de su organización se registren en seminarios web**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Para permitir que cualquier usuario, incluidos los usuarios anónimos, se registre en seminarios web, ejecute:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Si la combinación anónima está desactivada en la configuración de la reunión, los usuarios anónimos no pueden unirse a seminarios web. Para obtener más información y habilitar esta configuración, vea [Configuración de la reunión en Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Recopilar asistencia a la reunión

Si desea que los organizadores analicen quién se registró y asistió a seminarios web, tendrá que activar la directiva **EngagementReport.** Para ello, ejecute el siguiente comando en PowerShell.

```powershell
Set-CsTeamsMeetingPolicy -EngagementReport Enabled
```

## <a name="configure-webinar-settings"></a>Configurar la configuración del seminario web

Después de habilitar su entorno para seminarios web, no se requiere más administración de administradores. La directiva controla qué opciones se muestran para los organizadores de seminarios web.

## <a name="related-topics"></a>Temas relacionados

- [Directivas de reunión en Teams - General](meeting-policies-in-teams-general.md)
- [Documentación de Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams para Educación de directivas](easy-policy-setup-edu.md)
