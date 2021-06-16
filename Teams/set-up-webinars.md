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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Obtenga información sobre cómo administrar directivas de seminario web para Teams reuniones.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926752"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurar seminarios web en Microsoft Teams

Este artículo le ayudará a configurar su organización para hospedar seminarios web.

## <a name="what-are-webinars"></a>¿Qué son los seminarios web?

Los seminarios web son reuniones estructuradas en las que los presentadores y los participantes tienen roles claros, a menudo usados con fines de aprendizaje o escenarios de generación de clientes potenciales de ventas y marketing.

Después de configurar seminarios web en su organización, los usuarios pueden programar seminarios web y abrir el registro a los asistentes. A diferencia de las reuniones tradicionales que incluyen muchas discusiones y tareas, los seminarios web están diseñados para presentaciones interactivas y proporcionan herramientas para el análisis de los asistentes.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir a los usuarios programar seminarios web con PowerShell

Puede usar los siguientes atributos dentro del cmdlet **Set-CsTeamsMeetingPolicy de Windows PowerShell set-CsTeamsMeetingPolicy** para configurar seminarios web en Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Lea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener más información sobre el cmdlet.

> [!NOTE]
> Antes de poder ejecutar estos cmdlets, debe estar conectado a Microsoft Teams PowerShell. Para obtener más información, vea [Administrar Teams con Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Permitir a los usuarios programar seminarios web

Puede restringir el registro solo a los usuarios de su organización o abrirlo a todos los usuarios, tanto dentro como fuera de su inquilino. De forma predeterminada, **WhoCanRegister** está habilitado y establecido en **Todos.** Si desea desactivar el registro de la reunión, establezca **AllowMeetingRegistration** en **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** debe establecerse en **True** para **que AllowMeetingRegistration** funcione. Además, las listas de Microsoft deben configurarse en SharePoint. Para obtener más información, vea [Configuración de control de listas de Microsoft.](/sharepoint/control-lists)

1. Activar el registro de la reunión

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
> Si la combinación anónima está desactivada en la configuración de la reunión, los usuarios anónimos no pueden unirse a seminarios web. Para obtener más información y habilitar esta configuración, vea [Configuración de la reunión en Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Recopilar asistencia a la reunión

Si desea que los organizadores analicen quién se registró y asistió a seminarios web, tendrá que activar la directiva **AllowEngagementReport.** Para ello, ejecute el siguiente comando en PowerShell.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>Configurar la configuración del seminario web

Después de habilitar su entorno para seminarios web, no se requiere más administración de administradores. La directiva controla qué opciones se muestran para los organizadores de seminarios web.

## <a name="related-topics"></a>Temas relacionados

- [Directivas de reunión en Teams - General](meeting-policies-in-teams-general.md)
- [Documentación de Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
