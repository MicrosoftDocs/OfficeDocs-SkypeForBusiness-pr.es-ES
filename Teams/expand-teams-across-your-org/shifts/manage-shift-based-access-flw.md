---
title: Administrar el acceso basado en turnos para los trabajadores de primera línea en Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso basado en turnos en Teams para los Frontline Workers de su organización.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675222"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Administrar el acceso basado en turnos para los trabajadores de primera línea en Teams
## <a name="overview"></a>Información general

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presencia en Microsoft Teams indica la disponibilidad y el estado actuales de un usuario para otros usuarios. La presencia de los trabajadores de primera línea es a menudo menos predecible que el resto del personal, ya que sus horas de trabajo no suelen ser las mismas cada día. Como administrador, puede configurar Teams para mostrar un conjunto de estados de presencia basados en turnos para que los trabajadores de primera línea de su organización indiquen cuándo están activados y desactivados.

Estos estados de presencia basados en turnos&mdash;![Marca de verificación verde sólido, indica Al cambiar.](../../media/flw-presence-on-shift.png) **En mayús**, ![círculo gris con x, indica Desactivar turno.](../../media/flw-presence-off-shift.png) **Desactivar mayús**, ![Círculo rojo sólido, indica **Que**&mdash;ocupado](../../media/flw-presence-busy.png) está separado del [conjunto predeterminado de estados de presencia](../../presence-admins.md) en Teams. Con estos dos conjuntos de estados de presencia, puede configurar experiencias diferentes para los usuarios de su organización en función de su rol.

Con el acceso basado en turnos, puede administrar el acceso a Teams cuando los trabajadores de primera línea están fuera del turno. Por ejemplo, puede configurar Teams para mostrar un mensaje que los trabajadores de primera línea deben reconocer antes de que puedan usar Teams cuando no están en un turno programado.  

## <a name="scenario"></a>Escenario

Este es un ejemplo de cómo su organización puede administrar el acceso basado en turnos.

Tiene trabajadores de primera línea en su organización que solo deben pagarse por las horas que trabajan en un turno programado y aprobado por su jefe. No deben pagarse por el tiempo invertido trabajando fuera de un turno programado, lo que incluye el uso de la aplicación Teams. Puede configurar un mensaje personalizado que diga "Su tiempo en Teams cuando esté fuera del turno no contará para las horas por pagar", que se muestra cuando los trabajadores de primera línea intentan acceder a Teams cuando están fuera del turno. Si deciden usar Teams, hacen clic en **Acepto**, sprendiendo que no se les pagará por este tiempo.

También tiene trabajadores de información en su organización que tienen salarios y que no tienen turnos de trabajo. Configure los trabajadores de la información para que usen los estados de presencia predeterminados en Teams al tiempo que proporciona presencia basada en turnos a los trabajadores de primera línea.

## <a name="shift-based-presence-states"></a>Estados de presencia basados en turnos

Estos son los estados de presencia basados en turnos.

|Aplicación configurada |Configurado por el usuario  |Más información  |
|---------|---------|---------|
|![Marca de verificación verde continua, indica Al cambiar.](../../media/flw-presence-on-shift.png) En turno     |         |Establecer automáticamente al inicio de un turno         |
|![Círculo gris con x, indica Desactivar turno](../../media/flw-presence-off-shift.png) Desactivar turno     |         |Establecer automáticamente al final de un turno         |
|![Círculo rojo sólido indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Se establece automáticamente. También se puede establecer manualmente cuando el trabajador de primera línea está en turno.|

## <a name="off-shift-access-to-teams"></a>Desactivar el acceso por turnos a Teams

Esta característica le permite administrar el acceso a Teams cuando los trabajadores de primera línea están fuera de turno. Puede configurar Teams para que muestre un mensaje a los trabajadores de primera línea si acceden a Teams cuando están fuera del turno. Los trabajadores de primera línea deben hacer clic en **Acepto** para confirmar el mensaje antes de que puedan usar Teams.

Puede usar el mensaje predeterminado, elegir entre un conjunto de mensajes predefinidos o personalizar el mensaje para que muestre el texto que desee. Este es el mensaje predeterminado:

![Captura de pantalla del mensaje predeterminado.](../../media/shifts-presence-message.png)

También puede establecer la frecuencia con la que se muestra el mensaje y establecer un período de gracia entre el momento en que el primer turno comienza o termina el último turno y cuando está restringido el acceso a Teams.

## <a name="manage-shift-based-access"></a>Administrar el acceso basado en turnos

Como administrador, puede usar directivas para controlar la presencia basada en turnos para los trabajadores de primera línea de su organización. Puede administrar estas directivas con los siguientes cmdlets de PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Use el cmdlet de New-CsTeamsShiftsPolicy para crear una directiva, establezca la configuración de directiva que desee y, después, use el cmdlet Grant-CsTeamsShiftsPolicy para asignar la directiva a los usuarios.

Por ejemplo: Para obtener información detallada sobre cada parámetro y configuración de directiva, incluida la lista de mensajes de turnos desactivados predefinidos entre los que puede elegir, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Ejemplo 1

En este ejemplo, creamos una nueva directiva denominada Desactivar mayús Teams Mensaje predeterminado de Access. En esta directiva, la presencia basada en turnos está activada y el mensaje predeterminado se muestra cada vez que un usuario al que se asigna esta directiva tiene acceso a Teams cuando está desactivado. El usuario puede usar Teams cuando está desactivado si acepta el mensaje y el período de gracia entre el inicio del primer turno o el último turno termina y cuando el acceso está restringido es de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use el **parámetro ShiftNoticeMessageType** para establecer el mensaje que desea mostrar. Para ver una lista de los mensajes predefinidos entre los que puede elegir para este parámetro, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Ejemplo 2 

En este ejemplo, creamos una nueva directiva denominada Desactivar mayús Teams Mensaje personalizado de Access. En esta directiva, la presencia basada en turnos está activada y se muestra un mensaje personalizado cada vez que un usuario al que se asigna esta directiva tiene acceso a Teams cuando está desactivado. El usuario puede usar Teams cuando está desactivado si acepta el mensaje y el período de gracia entre el inicio del primer turno o el último turno termina y cuando el acceso está restringido es de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use el **parámetro ShiftNoticeMessageType** para establecer el mensaje que desea mostrar. Para obtener más información, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Ejemplo 3

En este ejemplo, creamos una nueva directiva denominada Desactivar mayús Teams Mensaje1 de Access. En esta directiva, la presencia basada en turnos está activada y se muestra el siguiente mensaje predefinido cada vez que un usuario al que se le asigna esta directiva tiene acceso a Teams cuando está desactivado.

  "Su empleador no autoriza ni aprueba el uso de su red, aplicaciones, sistemas o herramientas por parte de empleados no exentos o por horas durante sus horas no laborables. Al aceptar, reconoce que el uso de Teams mientras esté fuera del turno no está autorizado y no se le compensará". 

El usuario puede usar Teams cuando está desactivado si acepta el mensaje y el período de gracia entre el inicio del primer turno o el último turno termina y cuando el acceso está restringido es de tres minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use el **parámetro ShiftNoticeMessageType** para establecer el mensaje que desea mostrar. Para ver una lista de los mensajes predefinidos entre los que puede elegir para este parámetro, consulte [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Ejemplo 4

En este ejemplo, asignamos una directiva denominada Desactivar turno Teams Mensaje personalizado de Access a un usuario denominado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Temas relacionados

- [Administrar la aplicación Turnos para su organización en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Descripción de PowerShell para Teams](../../teams-powershell-overview.md)