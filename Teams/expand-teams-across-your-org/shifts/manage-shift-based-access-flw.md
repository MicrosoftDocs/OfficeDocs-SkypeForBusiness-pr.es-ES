---
title: Administrar el acceso basado en turnos para los trabajadores de primera línea en Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso basado en turnos en Teams para los trabajadores de frontline de su organización.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1d8ed8e964d1ffeda8e862992335560c9a6aab
ms.sourcegitcommit: 330b5c3e299ddad5168958e4722d1e0b987372e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53536846"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Administrar el acceso basado en turnos para los trabajadores de primera línea en Teams

> [!IMPORTANT]
> Desde el 30 de junio de 2020 Microsoft StaffHub ha sido retirado. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación Turnos para la administración de la programación y a medida que pase el tiempo se implementarán funciones adicionales StaffHub dejó de proveer servicios a todos los usuarios el 30 de junio de 2020. A cualquier usuario que intente abrir StaffHub se mostrará un mensaje en el que se le indicará que descargue Teams. Para obtener más información, consulte [Microsoft StaffHub se ha retirado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Información general

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presencia en Microsoft Teams indica la disponibilidad y el estado actuales de un usuario a otros usuarios. La presencia de los trabajadores de primera línea suele ser menos predecible que el resto del personal, ya que su horario laboral normalmente no es el mismo cada día. Como administrador, puede configurar Teams para mostrar un conjunto de estados de presencia basados en turnos para que los trabajadores de la primera línea de su organización indiquen cuándo están en o fuera del turno.

Estos estados de presencia basados en turnos Marca de verificación Verde sólido, indica En turno En turno, Círculo gris con x, indica Desactivado mayús, Círculo rojo sólido, indica que Ocupado ocupado son independientes del conjunto predeterminado de estados de &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ presencia en ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Con estos dos conjuntos de estados de presencia, puede configurar experiencias diferentes para los usuarios de su organización en función de su rol.

Con el acceso basado en turnos, puede administrar el acceso a Teams cuando los trabajadores de primera línea están fuera del turno. Por ejemplo, puede establecer Teams mostrar un mensaje que los trabajadores de primera línea deben reconocer antes de que puedan usar Teams cuando no están en un turno programado.  

## <a name="scenario"></a>Escenario

Este es un ejemplo de cómo su organización puede administrar el acceso basado en turnos.

Tiene trabajadores de primera línea en su organización a los que solo se les debe pagar por horas que trabajan en un turno que su jefe programó y aprobó. No se les debe pagar por el tiempo invertido trabajando fuera de un turno programado, lo que incluye el uso de la Teams aplicación. Configure un mensaje personalizado que diga "Su tiempo en Teams cuando está fuera del turno no contará para las horas por pagar", que se muestra cuando los trabajadores de primera línea intentan acceder Teams cuando están fuera del turno. Si deciden usar Teams, hacen clic en **Acepto** con la idea de que no se les pagará por este tiempo.

También tiene trabajadores de la información de su organización que tienen salarios y que no trabajan por turnos. Configure a los trabajadores de la información para que usen los estados de presencia predeterminados en Teams mientras proporciona a los trabajadores de primera línea presencia basada en turnos.

## <a name="shift-based-presence-states"></a>Estados de presencia basados en turnos

Estos son los estados de presencia basados en turnos.

|Aplicación configurada |Configurado por el usuario  |Más información  |
|---------|---------|---------|
|![Marca de verificación verde sólida, indica En turno](../../media/flw-presence-on-shift.png) En turno     |         |Se establece automáticamente al principio de un turno         |
|![Círculo gris con x, indica Desactivado mayús](../../media/flw-presence-off-shift.png) Desactivar turno     |         |Se establece automáticamente al final de un turno         |
|![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Establecer automáticamente. También se puede establecer manualmente cuando el trabajador de primera línea está en turno.|

## <a name="off-shift-access-to-teams"></a>Desactivar el acceso por turnos a Teams

Esta característica le permite administrar el acceso a Teams cuando los trabajadores de primera línea están fuera del turno. Puede establecer Teams mostrar un mensaje a los trabajadores de primera línea si acceden a Teams cuando están fuera del turno. Los trabajadores de primera línea deben hacer **clic en Acepto** para confirmar el mensaje antes de que puedan usar Teams.

Puede usar el mensaje predeterminado, elegir entre un conjunto de mensajes predefinidos o personalizar el mensaje para mostrar el texto que desee. Este es el mensaje predeterminado:

![Captura de pantalla del mensaje predeterminado](../../media/shifts-presence-message.png)

También puede establecer la frecuencia cuando se muestra el mensaje y establecer un período de gracia entre cuando se inicia el primer turno o finaliza el último turno y cuando el acceso a Teams está restringido.

## <a name="manage-shift-based-access"></a>Administrar el acceso basado en turnos

Como administrador, usa directivas para controlar la presencia basada en turnos para los trabajadores de primera línea de su organización. Puede administrar estas directivas mediante los siguientes cmdlets de PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Use el cmdlet New-CsTeamsShiftsPolicy para crear una nueva directiva, establezca la configuración de directiva que desee y, a continuación, use el cmdlet Grant-CsTeamsShiftsPolicy para asignar la directiva a los usuarios.

Por ejemplo: Para obtener información detallada sobre cada parámetro y configuración de directiva, incluida la lista de mensajes de turnos desactivados predefinidos que puede elegir, vea [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Ejemplo 1

En este ejemplo, creamos una nueva directiva denominada Off Shift Teams mensaje predeterminado de Access. En esta directiva, la presencia basada en turnos está activada y el mensaje predeterminado se muestra cada vez que un usuario al que se asigna esta directiva tiene acceso a Teams cuando está desactivado. El usuario puede usar Teams si acepta el mensaje y el período de gracia entre cuando se inicia el primer turno o finaliza el último turno y cuando el acceso está restringido es de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use el **parámetro MayúsNoticeMessageType** para establecer el mensaje que desea mostrar. Para ver una lista de los mensajes predefinidos que puede elegir para este parámetro, vea [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Ejemplo 2 

En este ejemplo, creamos una nueva directiva denominada Off Shift Teams mensaje personalizado de Access. En esta directiva, la presencia basada en turnos está activada y se muestra un mensaje personalizado cada vez que un usuario al que se asigna esta directiva tiene acceso a Teams cuando está desactivado. El usuario puede usar Teams turno desactivado si acepta el mensaje y el período de gracia entre cuando se inicia el primer turno o finaliza el último turno y cuando el acceso está restringido es de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use el **parámetro MayúsNoticeMessageType** para establecer el mensaje que desea mostrar. Para obtener más información, [vea New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Ejemplo 3

En este ejemplo, creamos una nueva directiva denominada Off Shift Teams Access Message1. En esta directiva, la presencia basada en turnos está activada y el siguiente mensaje predefinido se muestra cada vez que un usuario al que se asigna esta directiva accede a Teams cuando está desactivado.

  "Su empresa no autoriza ni aprueba el uso de su red, aplicaciones, sistemas o herramientas por empleados no exentos o por horas durante sus horas no laborables. Al aceptar, reconoce que el uso de Teams mientras está fuera del turno no está autorizado y no se le compensará". 

El usuario puede usar Teams turno desactivado si acepta el mensaje y el período de gracia entre cuando se inicia el primer turno o finaliza el último turno y cuando el acceso está restringido es de tres minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use el **parámetro MayúsNoticeMessageType** para establecer el mensaje que desea mostrar. Para ver una lista de los mensajes predefinidos que puede elegir para este parámetro, vea [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Ejemplo 4

En este ejemplo, asignamos una directiva denominada Off Shift Teams mensaje personalizado de Access a un usuario denominado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Temas relacionados

- [Administrar la aplicación Turnos para su organización en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Descripción de PowerShell para Teams](../../teams-powershell-overview.md)