---
title: Administrar el acceso basado en turnos para los trabajadores de la línea frontal en Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo administrar el acceso basado en turnos en Teams para trabajadores de línea directa de su organización.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 437902136bf72685dabf5bd6359dd6221c7467de
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909474"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Administrar el acceso basado en turnos para los trabajadores de la línea frontal en Teams

> [!IMPORTANT]
> A partir del 30 de junio de 2020, Se ha retirado Microsoft StaffHub. Estamos creando funciones de StaffHub en Microsoft Teams. Hoy en día, Teams incluye la aplicación Turnos para la administración de programación y otras funcionalidades se irán lanzando a lo largo del tiempo. StaffHub dejó de funcionar para todos los usuarios el 30 de junio de 2020. Cualquier persona que intente abrir StaffHub se mostrará un mensaje que le dirigirá a descargar Teams. Para obtener más información, [vea Microsoft StaffHub se ha retirado.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview"></a>Descripción general

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presencia en Microsoft Teams indica la disponibilidad y el estado actuales de un usuario a otros usuarios. La presencia de los trabajadores de primera línea suele ser menos predecible que el resto del personal, ya que sus horas de trabajo normalmente no son las mismas cada día. Como administrador, puede configurar Teams para que muestre un conjunto de estados de presencia basados en turnos para que los trabajadores de la línea frontal de su organización indiquen cuándo se encuentran en el turno de entrada y de salida.

Estos estados de presencia basados en turnos indican Marca de verificación verde sólida, indica Al desplazarse en el turno, círculo gris con x, indica Desactivado turno, Círculo rojo sólido, indica Que ocupado está separado del conjunto predeterminado de estados de presencia en &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Con estos dos conjuntos de estados de presencia, puede configurar experiencias diferentes para las personas de su organización en función de su rol.

Con el acceso basado en turnos, puede administrar el acceso a Teams cuando los Trabajadores de la línea frontal están fuera de turno. Por ejemplo, puede configurar Teams para que muestre un mensaje que los trabajadores de frontline workers deben confirmar antes de que puedan usar Teams cuando no están en un turno programado.  

## <a name="scenario"></a>Escenario

Este es un ejemplo de cómo su organización puede administrar el acceso basado en turnos.

Tiene trabajadores de primera línea en su organización que solo deberían pagar por las horas que trabajan en un turno que su jefe programó y aprobó. No deben pagar por el tiempo invertido en trabajar fuera de un turno programado, lo que incluye el uso de la aplicación Teams. Usted configura un mensaje personalizado que dice "Su tiempo en Teams cuando está fuera del turno no cuenta para las horas de pago", que se muestra cuando los trabajadores de la línea frontal intentan acceder a Teams cuando está fuera de turno. Si deciden usar Teams, hacen clic en **Acepto** con la idea de que no se les pagará por este momento.

También tiene en su organización trabajadores con salarios y que no trabajan en turnos. Configure a los trabajadores de la información para que usen los estados de presencia predeterminados en Teams mientras proporciona la presencia basada en turnos de los Trabajadores de la línea frontal.

## <a name="shift-based-presence-states"></a>Estados de presencia basado en turnos

Estos son los estados de presencia basados en turnos.

|Aplicación configurada |Configurado por el usuario  |Más información  |
|---------|---------|---------|
|![Marca de verificación verde sólida, indica Al desplazarse](../../media/flw-presence-on-shift.png) En turno     |         |Establecido automáticamente al comienzo de un turno         |
|![Círculo gris con x, indica Mayús desactivado](../../media/flw-presence-off-shift.png) Mayús desactivado     |         |Establecido automáticamente al final de un turno         |
|![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Establecido automáticamente. También se puede establecer manualmente cuando el trabajador de la línea frontal está en el turno.|

## <a name="off-shift-access-to-teams"></a>Desactivar el acceso por turnos a Teams

Esta característica le permite administrar el acceso a Teams cuando los Trabajadores de la línea frontal están fuera de turno. Puede configurar que Teams muestre un mensaje a los trabajadores de la línea frontal si acceden a Teams cuando están fuera de turno. Los trabajadores de primera línea **deben hacer clic en Aceptar** para aceptar el mensaje antes de que puedan usar Teams.

Puede usar el mensaje predeterminado, elegir entre un conjunto de mensajes predefinidos o personalizar el mensaje para mostrar el texto que desee. Este es el mensaje predeterminado:

![Captura de pantalla del mensaje predeterminado](../../media/shifts-presence-message.png)

También puede establecer la frecuencia cuando se muestra el mensaje y establecer un período de gracia entre el momento en que comienza o termina el último turno del primer turno y cuando se restringe el acceso a Teams.

## <a name="manage-shift-based-access"></a>Administrar el acceso basado en turnos

Como administrador, puede usar directivas para controlar la presencia basada en turnos para los trabajadores de la línea frontal de su organización. Puede administrar estas directivas con los siguientes cmdlets de PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Use el cmdlet New-CsTeamsShiftsPolicy para crear una directiva, establecer la configuración de directiva que desee y, después, usar el cmdlet Grant-CsTeamsShiftsPolicy para asignar la directiva a los usuarios.

Por ejemplo: Para obtener información detallada sobre cada parámetro y configuración de directiva, incluida la lista de mensajes de turnos desactivados predefinidos que puede elegir, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Ejemplo 1

En este ejemplo, creamos un nuevo mensaje predeterminado denominado Acceso a equipos de turnos. En esta directiva, la presencia basada en turnos está activada y el mensaje predeterminado se muestra cada vez que un usuario al que se le asigna esta directiva tiene acceso a Teams cuando está desactivado. El usuario puede usar Teams cuando está fuera del turno si acepta el mensaje y el período de gracia entre el momento en que comienza o termina el último turno y cuando se restringe el acceso es de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use el **parámetro ShiftNoticeMessageType** para establecer el mensaje que quiere mostrar. Para ver una lista de los mensajes predefinidos que puede elegir para este parámetro, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Ejemplo 2 

En este ejemplo, creamos un nuevo mensaje personalizado denominado Acceso a equipos sin turnos. En esta directiva, la presencia basada en turnos está activada y se muestra un mensaje personalizado cada vez que un usuario al que se asigna esta directiva tiene acceso a Teams cuando está desactivado. El usuario puede usar Teams si está desactivado si acepta el mensaje y el período de gracia entre el momento en que comienza o termina el último turno y cuando se restringe el acceso es de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use el **parámetro ShiftNoticeMessageType** para establecer el mensaje que quiere mostrar. Para obtener más información, [consulte New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Ejemplo 3

En este ejemplo, creamos una nueva directiva denominada Off Shift Teams Access Message1. En esta directiva, la presencia basada en turnos está activada y se muestra el siguiente mensaje predefinido cada vez que un usuario al que se asigna esta directiva tiene acceso a Teams cuando está desactivado.

  "Su empresa no autoriza ni aprueba el uso de su red, aplicaciones, sistemas o herramientas por parte de los empleados no exentos o cada hora durante su horario no laborable. Al aceptar, reconoce que el uso de Teams mientras está fuera de su turno no está autorizado y no se le compensará". 

El usuario puede usar Teams cuando está desactivado si acepta el mensaje y el período de gracia entre el momento en que comienza o termina el último turno y cuando se restringe el acceso es de tres minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use el **parámetro ShiftNoticeMessageType** para establecer el mensaje que quiere mostrar. Para ver una lista de los mensajes predefinidos que puede elegir para este parámetro, consulte [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Ejemplo 4

En este ejemplo, asignamos un mensaje personalizado de acceso de equipos desactivados a un usuario llamado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Temas relacionados

- [Administrar la aplicación Turnos para su organización en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Descripción de PowerShell para Teams](../../teams-powershell-overview.md)
