---
title: Administrar el acceso basado en turnos para trabajadores de los Firstline en Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a administrar el acceso basado en turnos en Teams para trabajadores de los Firstline de su organización.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ec470422e402da07171bef627d1592c73d6c12f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514137"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Administrar el acceso basado en turnos para trabajadores de los Firstline en Teams

> [!IMPORTANT]
> A partir del 30 de junio de 2020, se ha retirado a Microsoft StaffHub. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub ha dejado de funcionar para todos los usuarios el 30 de junio de 2020. Cualquier persona que intente abrir StaffHub verá un mensaje que le indica que debe descargar Teams. Para obtener más información, vea se ha [retirado Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Información general

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Presencia en Microsoft Teams indica la disponibilidad y el estado actuales de un usuario a otros usuarios. La presencia de trabajadores de los Firstline es a menudo menos predecible que otras personas, ya que sus horas de trabajo no suelen ser las mismas cada día. Como administrador, puede configurar Teams para mostrar un conjunto de Estados de presencia basada en el turno para los trabajadores de la los Firstline de su organización para indicar cuándo están activados y desplazados.

Esta marca de verificación verde sólida de los Estados de presencia basados en el turno, indica que se desplazan en el turno &mdash; ![ ](../../media/flw-presence-on-shift.png) **On shift**, el ![ círculo gris con x, indica que no se ha cambiado la tecla Mayús ](../../media/flw-presence-off-shift.png) **Off shift**, ![ un círculo rojo sólido, indica ](../../media/flw-presence-busy.png) **Busy** &mdash; que ocupado está separado del [conjunto predeterminado de Estados de presencia](../../presence-admins.md) en Teams. Con estos dos conjuntos de Estados de presencia, puede configurar diferentes experiencias para las personas de su organización basándose en su función.

Con Access basado en turnos puede administrar el acceso a los equipos cuando los trabajadores de los Firstline están desplazados. Por ejemplo, puede configurar Teams para que muestre un mensaje que los trabajadores de los Firstline deban reconocer antes de que puedan usar Teams cuando no estén en un turno programado.  

## <a name="scenario"></a>Escenario

Este es un ejemplo de cómo su organización puede administrar el acceso basado en turnos.

Tiene los Firstline trabajadores de su organización a los que solo se debe pagar horas que trabajan en un turno en el que su director programó y aprobó. No se deben pagar por el tiempo empleado en trabajar fuera de un turno programado, lo que incluye usar la aplicación de Teams. Configure un mensaje personalizado que indica "su tiempo en Teams cuando está de desactivado el turno no se va a pagar por horas", que se muestra cuando los trabajadores de los Firstline intentan acceder a teams cuando no hay turno. Si optan por usar Teams, hacen **clic en Acepto con** la comprensión de que no se le cobrará por este momento.

También tiene trabajadores de información en su organización que están asalariados y que no trabajan. Configure los trabajadores de la información para que usen los Estados de presencia predeterminados en Teams a la vez que le ofrecen a los trabajadores de los Firstline la presencia basada en turnos.

## <a name="shift-based-presence-states"></a>Estados de presencia basados en turnos

Estos son los Estados de presencia basados en el turno.

|Aplicación configurada |Configurado por el usuario  |Más información  |
|---------|---------|---------|
|![Marca de verificación verde sólido, indica en Mayús](../../media/flw-presence-on-shift.png) Al desplazarse     |         |Establecer automáticamente al principio de un turno         |
|![Círculo gris con x, indica que no hay Mayús](../../media/flw-presence-off-shift.png) Desactivar Mayús     |         |Establecer automáticamente al final de un turno         |
|![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado      | ![Círculo rojo sólido, indica Ocupado](../../media/flw-presence-busy.png) Ocupado         |Se establece de forma automática. También se puede establecer manualmente cuando el trabajador de los Firstline está en turno.|

## <a name="off-shift-access-to-teams"></a>Desactivar el acceso a los equipos

Esta característica le permite administrar el acceso a los equipos cuando los trabajadores de los Firstline están desplazados. Puede establecer que Teams muestre un mensaje para que los trabajadores de los Firstline tengan acceso a teams cuando estén desplazados. Los trabajadores de los Firstline deben hacer clic en **acepto** para confirmar el mensaje antes de que puedan usar Teams.

Puede usar el mensaje predeterminado, elegir un conjunto de mensajes predefinidos o personalizar el mensaje para que muestre el texto que desee. Este es el mensaje predeterminado:

![Captura de pantalla del mensaje predeterminado](../../media/shifts-presence-message.png)

También puede establecer la frecuencia con la que se muestra el mensaje y establecer un período de gracia entre el momento en que empieza el primer turno o el último turno y cuando el acceso a teams está restringido.

## <a name="manage-shift-based-access"></a>Administrar el acceso basado en turnos

Como administrador, use directivas para controlar la presencia basada en turnos de los trabajadores de los Firstline de su organización. Estas directivas se administran con los siguientes cmdlets de PowerShell:

- [Nuevo: CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Use el cmdlet New-CsTeamsShiftsPolicy para crear una nueva Directiva, establecer la configuración de directiva que desee y, a continuación, usar el cmdlet de Grant-CsTeamsShiftsPolicy para asignar la Directiva a los usuarios.

A continuación se muestran algunos ejemplos. Para obtener información detallada sobre cada parámetro y configuración de Directiva, incluida la lista de mensajes de turno predefinidos que puede elegir, consulte [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Ejemplo 1

En este ejemplo, se crea una nueva Directiva denominada deshabilitar el acceso al mensaje predeterminado. En esta Directiva, la presencia basada en turnos se activa y el mensaje predeterminado se muestra cada vez que un usuario al que se le asigna esta directiva accede a teams cuando se desactiva la tecla Mayús. El usuario puede usar Teams cuando está desactivado la tecla Mayús si acepta el mensaje y el período de gracia entre el momento en que se inicia el primer turno o el último turno se termina y cuando Access está restringido es de 10 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Use el parámetro **ShiftNoticeMessageType** para establecer el mensaje que quiera mostrar. Para ver una lista de los mensajes predefinidos que puede elegir para este parámetro, vea [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Ejemplo 2 

En este ejemplo, se crea una nueva Directiva denominada deshabilitar el acceso a los equipos personalizados. En esta Directiva, la presencia basada en turnos está activada y se muestra un mensaje personalizado cada vez que un usuario al que se le asigna esta directiva accede a teams cuando se desactiva la tecla Mayús. El usuario puede usar Teams cuando está desactivado la tecla Mayús si acepta el mensaje y el período de gracia entre cuando el primer turno se inicia o el último turno finaliza y el acceso restringido es de 15 minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Use el parámetro **ShiftNoticeMessageType** para establecer el mensaje que quiera mostrar. Para obtener más información, vea [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Ejemplo 3

En este ejemplo, se crea una nueva Directiva denominada desactivar equipos de Access Message1. En esta Directiva, la presencia basada en turnos está activada y el siguiente mensaje predefinido se muestra cada vez que un usuario que tiene asignada la Directiva accede a teams cuando se desactiva la tecla Mayús.

  "Su empleador no autoriza ni aprueba el uso de su red, aplicaciones, sistemas o herramientas por empleados no exentos o por horas durante los períodos no laborables. Al aceptar, usted reconoce que su uso de Teams mientras está desactivado el turno no está autorizado y no se le compensará. 

El usuario puede usar Teams cuando está desactivado la tecla Mayús si acepta el mensaje y el período de gracia entre el momento en que comienza el primer turno o el último turno y el acceso restringido es de tres minutos.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Use el parámetro **ShiftNoticeMessageType** para establecer el mensaje que quiera mostrar. Para ver una lista de los mensajes predefinidos que puede elegir para este parámetro, vea [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Ejemplo 4

En este ejemplo, asignamos una directiva llamada OFF Teams Access Custom Message a un usuario denominado remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Temas relacionados

- [Administrar la aplicación Turnos para su organización en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Descripción de PowerShell para Teams](../../teams-powershell-overview.md)
