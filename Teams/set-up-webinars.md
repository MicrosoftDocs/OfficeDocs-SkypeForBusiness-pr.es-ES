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
ms.openlocfilehash: 739c0b5494b0ecc5b9a20fd8db4756313848325b
ms.sourcegitcommit: e5d6a2c3ad45c1285016b93ec4c7afea907d71a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275528"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurar seminarios web en Microsoft Teams

Este artículo le ayudará a configurar su organización para hospedar seminarios web.

## <a name="what-are-webinars"></a>¿Qué son los seminarios web?

Los seminarios web son reuniones estructuradas en las que los instructores y los participantes tienen roles claros, a menudo usados con fines de aprendizaje o escenarios de generación de clientes potenciales de ventas y marketing.

Después de configurar seminarios web en su organización, los usuarios pueden programar seminarios web y abrir el registro a los asistentes. A diferencia de las reuniones tradicionales que incluyen muchas discusiones y tareas, los seminarios web están diseñados para presentaciones interactivas y proporcionan herramientas para el análisis de los asistentes.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Permitir a los usuarios programar seminarios web con PowerShell

Puede usar los siguientes atributos dentro del cmdlet **Set-CsTeamsMeetingPolicy de Windows PowerShell set-CsTeamsMeetingPolicy** para configurar seminarios web en Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Lea [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para obtener más información sobre el cmdlet.

> [!NOTE]
> Antes de poder ejecutar estos cmdlets, debe estar conectado a Skype Empresarial PowerShell en línea. Para obtener más información, vea [Administrar Skype Empresarial Online con Microsoft 365 o Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

### <a name="allow-users-to-schedule-webinars"></a>Permitir a los usuarios programar seminarios web

Para permitir que los usuarios de su organización programe seminarios web, ejecute:

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a>Configurar quién puede registrarse en seminarios web

Puede restringir el registro solo a los usuarios de su organización o abrirlo a todos los usuarios, tanto dentro como fuera de su inquilino. De forma predeterminada, **WhoCanRegister** está habilitado y establecido en **Todos.** Si desea desactivar el registro de la reunión, establezca **WhoCanRegister** en **False**.

> [!IMPORTANT]
> Tenga en cuenta que **AllowPrivateMeetingScheduling** debe establecerse en **True** para **que WhoCanRegister** funcione. Además, las listas de Microsoft deben configurarse en SharePoint. Para obtener más información, vea [Configuración de control de listas de Microsoft.](/sharepoint/control-lists)

**Para permitir *que solo* los usuarios de su organización se registren en seminarios web, ejecute:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

A continuación, ejecute:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Para permitir que cualquier usuario, incluidos los usuarios anónimos, se registre en seminarios web, ejecute:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

A continuación, ejecute:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
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
