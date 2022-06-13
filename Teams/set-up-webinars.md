---
title: Configurar seminarios web en Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Obtenga información sobre cómo administrar directivas de seminario web para reuniones de Teams.
ms.openlocfilehash: 247d5c560075dfd0498ea76b476d5515d0fc6f07
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045709"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurar seminarios web en Microsoft Teams

Este artículo le ayudará a configurar su organización para hospedar seminarios web.

## <a name="what-are-webinars"></a>¿Qué son los seminarios web?

Los seminarios web son reuniones estructuradas en las que los moderadores y participantes tienen roles claros, que se usan a menudo para fines de aprendizaje o escenarios de generación de líderes de ventas y marketing.

Después de configurar seminarios web en su organización, los usuarios pueden programar seminarios web y abrir el registro a los asistentes. A diferencia de las reuniones tradicionales que incluyen muchas discusiones y tareas, los seminarios web están diseñados para presentaciones interactivas y proporcionan herramientas para el análisis de los asistentes.

> [!IMPORTANT]
> Para permitir a los usuarios configurar seminarios web, Listas Microsoft deben configurarse en SharePoint habilitando la creación de listas personales. Para obtener más información, consulta [Configuración de control de Listas Microsoft](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Permitir a los usuarios programar seminarios web en el centro de administración de Teams

Puede usar el centro de administración de Teams para configurar seminarios web para su organización. Encontrará las directivas para configurar seminarios web en el Teams centro de administración en **Directivas** >  de **reuniones de reuniones**.

### <a name="meeting-registration"></a>Registro de reunión

Si lo activa, los usuarios pueden programar seminarios web. De forma predeterminada, esta opción está activada. Si desea desactivar el registro de reuniones, establezca esta directiva en **Desactivado**.

> [!IMPORTANT]
> **La programación de reuniones privadas** debe estar activada para que funcione el registro de la reunión. De forma predeterminada, esta directiva está activada en el centro de administración de Teams. Para los estudiantes de inquilinos educativos, esta directiva está desactivada de forma predeterminada. Para obtener más información sobre cómo habilitar la programación de reuniones privadas para los alumnos, vea [Teams para Educación directivas y paquetes de directivas](policy-packages-edu.md).

### <a name="who-can-register"></a>Quién pueden registrarse

Si selecciona **Todos** los usuarios, todos los usuarios, incluidos los usuarios anónimos, pueden registrarse y asistir a seminarios web. Si selecciona **Todos los usuarios de la organización**, solo los usuarios de su organización pueden registrarse en seminarios web. Si el registro de reuniones está desactivado, esta opción no estará disponible y nadie podrá registrarse en seminarios web.

> [!NOTE]
> El valor predeterminado de **Quién pueden registrarse** es **Todos los usuarios de la organización** en inquilinos educativos. Para obtener más información, consulte [Asistente para directivas de Teams para Educación](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Informe de participación

Cuando esto está activado, los organizadores pueden ver los informes de las personas que se registraron y asistieron a los seminarios web que configuraron. Esta directiva está activada de forma predeterminada. Para obtener más información, vea [Directivas de reunión en Teams - Informe de interacción](meeting-policies-in-teams-general.md#engagement-report). Para obtener información sobre la experiencia del usuario final, vea [Ver y descargar informes de asistencia a reuniones](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir a los usuarios programar seminarios web con PowerShell

Puede usar los siguientes atributos dentro del cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** para configurar seminarios web en Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Lea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener más información sobre el cmdlet.

> [!NOTE]
> Para poder ejecutar estos cmdlets, debe estar conectado a Microsoft Teams PowerShell. Para obtener más información, vea [Administrar Teams con Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Permitir a los usuarios programar seminarios web

Puede restringir el registro a los usuarios solo de su organización o abrirlos a todos los usuarios, tanto dentro como fuera de su inquilino. De forma predeterminada, **WhoCanRegister** está habilitado y establecido en **Todos** para la **directiva Global (predeterminada para toda** la organización). Si quiere desactivar el registro de reuniones, establezca **AllowMeetingRegistration** en **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** debe establecerse en **True** para **que AllowMeetingRegistration** funcione.

1. Activar el registro de reuniones

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Activar la programación de reuniones privadas

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
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
> Si la opción de unión anónima está desactivada en la configuración de la reunión, los usuarios anónimos no podrán unirse a seminarios web. Para obtener más información y habilitar esta configuración, consulte [Configuración de la reunión en Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Recopilar la asistencia a la reunión

El parámetro **AllowEngagementReport** le permite ver quién registró y asistió a seminarios web. Esta directiva está activada de forma predeterminada. Para desactivarlo, ejecute el siguiente comando en PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Configurar las opciones de seminario web

Después de habilitar el entorno para seminarios web, no es necesario administrar más administradores. La directiva controla qué opciones se muestran para los organizadores del seminario web.

## <a name="related-topics"></a>Temas relacionados

- [Directivas de reunión en Teams : General](meeting-policies-in-teams-general.md)
- [Documentación de Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Asistente para directivas de Teams para Educación](easy-policy-setup-edu.md)
