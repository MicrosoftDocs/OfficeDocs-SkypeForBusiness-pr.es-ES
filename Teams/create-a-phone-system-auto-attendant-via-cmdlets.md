---
title: Crear un operador automático mediante cmdlets
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar operadores automáticos mediante cmdlets
ms.openlocfilehash: a3f669a6540e42cd0ff4a016da0215ca79f3bd22
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676622"
---
# <a name="create-an-auto-attendant-via-cmdlets"></a>Crear un operador automático mediante cmdlets

## <a name="assumptions"></a>Suposiciones

1. PowerShell está instalado en el equipo

   - Configurar el equipo para [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - Módulo MSTeams instalado

     ```PowerShell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - Módulo MSOnline instalado

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. Tiene derechos de administración de inquilinos
3. Has comprado Teléfono Microsoft Teams
4. Las colas de llamadas a las que se hace referencia a continuación ya se han configurado siguiendo la guía [Creación de colas de llamadas con cmdlets de PowerShell](create-a-phone-system-call-queue-via-cmdlets.md) .

**Nota**: Algunos de los cmdlets a los que se hace referencia a continuación pueden formar parte de la versión preliminar pública de Teams módulo de PowerShell. Para obtener más información, vea [Instalar Teams versión preliminar pública de PowerShell](teams-powershell-install.md) y vea [también Microsoft Teams notas de la versión de PowerShell](teams-powershell-release-notes.md).

Los usuarios que ya tienen instalado el módulo MicrosoftTeams deben `Update-Module MicrosoftTeams` asegurarse de que está instalada la versión más actualizada.

## <a name="scenario"></a>Escenario

Se creará el siguiente flujo de llamadas del operador automático:

![Diagrama del flujo de llamadas del operador automático que se crea con cmdlets.](media/create-a-phone-system-auto-attendant-via-cmdlets.png)

Información de configuración adicional:

- Operador automático: Contoso Main
  - Operador: Adele Vance
  - Habilitar entradas de voz: Desactivado
  - Búsqueda en el directorio: Ninguna
  - Vacaciones:
    - 1 de enero de 2022
    - 24 de diciembre de 2022
    - 25 de diciembre de 2022

- Operador automático: Contoso Dial by name
  - Operador: Adele Vance
  - Zona horaria: UTC
  - Idioma: inglés (EE. UU.)
  - Habilitar entradas de voz: Activado
  - Saludo: Ninguno
  - Menú: TTS, "Di o escribe el nombre de la persona con la que te gustaría contactar. Para volver al menú anterior, pulse 9"
  - Búsqueda en el directorio: marcar por nombre
  - Ámbito de marcado: miembros del soporte técnico & ventas

## <a name="login"></a>Inicio de sesión

Se le pedirá que escriba sus credenciales de administrador de Teams.

```PowerShell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="get-operator-information"></a>Obtener información del operador

```PowerShell
$operatorID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity

$operatorEntity = New-CsAutoAttendantCallableEntity -Identity $operatorID -Type User
```

## <a name="dial-by-name-auto-attendant---resource-account-creation"></a>Operador automático Marcado por nombre: creación de cuentas de recursos

**Nota**: Crear una cuenta de recursos aquí para que se pueda hacer referencia a ella en el operador automático principal. El operador automático marcado por nombre real se creará más adelante.

### <a name="get-license-types"></a>Obtener tipos de licencia

```PowerShell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Crear y asignar cuenta de recursos

**Nota**: Teléfono número no necesario aquí, ya que la cola de llamadas es front-ended por un operador automático

- Id. de aplicación
  - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
  - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoDialByNameAA-RA@contoso.com -DisplayName "Contoso Dial By Name AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$dialByNameApplicationInstanceID = (Get-CsOnlineUser "ContosoDialByNameAA-RA@contoso.com").ObjectID
```

## <a name="contoso-main-menu-auto-attendant"></a>Operador automático del menú principal de Contoso

### <a name="create-holiday-schedules"></a>Crear programaciones navideñas

```PowerShell
$dtr = New-CsOnlineDateTimeRange -Start "24/12/2022" -End "25/12/2022"

$christmasSchedule = New-CsOnlineSchedule -Name "Christmas" -FixedSchedule -DateTimeRanges @($dtr)

$dtr = New-CsOnlineDateTimeRange -Start "01/01/2022" -End "02/01/2022"

$newyearSchedule = New-CsOnlineSchedule -Name "New Year" -FixedSchedule -DateTimeRanges @($dtr)
```

### <a name="create-address-fax-and-email-information-prompt"></a>Crear mensaje de información de dirección, FAX y correo electrónico

```PowerShell
$addressPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To repeat this information at any time press the * key. Our mailing address is: 123 Main Street, Any town, Any Place, County. Our email address is: info@contoso.com. Our fax number is: 929-555-0151"
```

### <a name="create-holiday-prompts-and-menu-options"></a>Crear avisos de días festivos y opciones de menú

```PowerShell
$christmasGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the Christmas holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$christmasMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$christmasMenu = New-CsAutoAttendantMenu -Name "Christmas Menu" -MenuOptions @($christmasMenuOption)

$christmasCallFlow = New-CsAutoAttendantCallFlow -Name "Christmas" -Greetings @($christmasGreetingPrompt) -Menu $christmasMenu

$christmasCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $christmasSchedule.Id -CallFlowId $christmasCallFlow.Id

$newyearGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the New Year's holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$newyearMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$newyearMenu = New-CsAutoAttendantMenu -Name "New Year Menu" -MenuOptions @($newyearMenuOption)

$newyearCallFlow = New-CsAutoAttendantCallFlow -Name "New Year" -Greetings @($newyearGreetingPrompt) -Menu $newyearMenu

$newyearCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $newyearSchedule.Id -CallFlowId $newyearCallFlow.Id
```

### <a name="create-after-hours-schedules"></a>Crear programaciones fuera del horario laboral

```PowerShell
$timerangeMoFr = New-CsOnlineTimeRange -Start 08:30 -end 17:00

$timerangeSa = New-CsOnlineTimeRange -Start 10:00 -end 16:00

$afterHoursSchedule = New-CsOnlineSchedule -Name "After Hours Schedule" -WeeklyRecurrentSchedule -MondayHours @($timerangeMoFr) -TuesdayHours @($timerangeMoFr) -WednesdayHours @($timerangeMoFr) -ThursdayHours @($timerangeMoFr) -FridayHours @($timerangeMoFr) -SaturdayHours @($timerangeSa) -Complement
```

### <a name="create-after-hours-prompts-and-menu-options"></a>Crear mensajes de fuera del horario laboral y opciones de menú

```PowerShell
$afterHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices are now closed. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time."

$afterHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To leave a voicemail for our sales team press 1.To leave a message for our support team press 2.If you know the name of the person you would like to reach, press 3.For our address, email and fax information press 4."

$afterHoursMenuOption1Target = (Get-Team -displayname "Sales").GroupID

$afterHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption1Target -Type SharedVoiceMail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $afterHoursMenuOption1Entity

$afterHoursMenuOption2Target = (Get-Team -displayname "Support").GroupID

$afterHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption2Target -Type SharedVoicemail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $afterHoursMenuOption2Entity

$dialbynameAAOption3Target = (Get-CsOnlineUser -Identity "ContosoDialByNameAA-RA@contso.com").Identity

$dialbynameAAMenuOption3Entity = New-CsAutoAttendantCallableEntity -Identity $dialbynameAAOption3Target -Type applicationendpoint

$dialbynameAAMenuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $dialbynameAAMenuOption3Entity

$afterHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt
```

### <a name="create-after-hours-menu-and-call-flow"></a>Menú Crear fuera del horario laboral y Flow de llamadas

```PowerShell
$afterHoursMenu = New-CsAutoAttendantMenu -Name "After Hours Menu" -MenuOptions @($afterHoursMenuOption1, $afterHoursMenuOption2, $dialbynameAAMenuOption3, $afterHoursMenuOption4) -Prompt $afterHoursMenuPrompt

$afterHoursCallFlow = New-CsAutoAttendantCallFlow -Name "After Hours Call Flow" -Greetings @($afterHoursGreetingPrompt) -Menu $afterHoursMenu

$afterHoursCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type AfterHours -ScheduleId $afterHoursSchedule.Id -CallFlowId $afterHoursCallFlow.Id
```

### <a name="create-open-hours-prompts-and-menu-options"></a>Crear mensajes de horas abiertas y opciones de menú

```PowerShell
$openHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt " Thank you for calling Contoso."

$openHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "For Sales press 1. For Support press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information, press 4. For all other inquiries press 0 to speak with the operator."

$openHoursMenuOption1Target = (Get-CsOnlineUser "Sales-RA@contoso.com").ObjectID

$openHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption1Target -Type applicationendpoint

$openHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $openHoursMenuOption1Entity

$openHoursMenuOption2Target = (Get-CsOnlineUser "Support-RA@contoso.com").ObjectID

$openHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption2Target -Type applicationendpoint

$openHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $openHoursMenuOption2Entity

$openHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt

$openHoursMenuOption0 = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
```

### <a name="create-open-hours-menu"></a>Menú Crear horas abiertas

```PowerShell
$openHoursMenu = New-CsAutoAttendantMenu -Name "Open Hours Menu" -MenuOptions @($openHoursMenuOption1, $openHoursMenuOption2, $dialbynameAAMenuOption3, $openHoursMenuOption4, $openHoursMenuOption0) -Prompt $openHoursMenuPrompt

$openHoursCallFlow = New-CsAutoAttendantCallFlow -Name "Open Hours Call Flow" -Greetings @($openHoursGreetingPrompt) -Menu $openHoursMenu
```

### <a name="create-auto-attendant"></a>Crear operador automático

```PowerShell
$autoAttendant = New-CsAutoAttendant -Name "Contoso Main" -DefaultCallFlow $openHoursCallFlow -CallFlows @($afterHoursCallFlow, $christmasCallFlow, $newyearCallFlow) -CallHandlingAssociations @($afterHoursCallHandlingAssociation, $christmasCallHandlingAssociation, $newyearCallHandlingAssociation) -LanguageId "en-US" -TimeZoneId "Eastern Standard Time" -Operator $operatorEntity
```

### <a name="get-license-types"></a>Obtener tipos de licencia

```PowerShell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Crear y asignar cuenta de recursos

- Id. de aplicación
  - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
  - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoMainAA-RA@contoso.com -DisplayName "Contoso Main AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoMainAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "ContosoMainAA-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$autoAttendantID = (Get-CsAutoAttendant -NameFilter "Contoso Main").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $autoAttendantID -ConfigurationType AutoAttendant
```

### <a name="get-list-of-unassigned-service-numbers"></a>Obtener una lista de números de servicio no asignados

```PowerShell
Get-CsOnlineTelephoneNumber -IsNotAssigned -InventoryType Service
```

#### <a name="assign-available-phone-number"></a>Asignar número de teléfono disponible
Nota: La ubicación de uso asignada al número de teléfono debe coincidir con la ubicación de uso asignada a la cuenta de recursos.

```PowerShell
Set-CsPhoneNumberAssignment -Identity ContosoMainAA-RA@contoso.com -PhoneNumber +{spare number from output of above command} -PhoneNumberType CallingPlan
```

## <a name="dial-by-name-auto-attendant---completion"></a>Operador automático marcado por nombre: finalización

### <a name="create-dial-scope"></a>Crear ámbito de marcado

```PowerShell
$salesGroupID = Find-CsGroup -SearchQuery "Sales" | % { $_.Id }

$supportGroupID = Find-CsGroup -SearchQuery "Support" | % { $_.Id }

$dialScope = New-CsAutoAttendantDialScope -GroupScope -GroupIds @($salesGroupID, $supportGroupID)
```

### <a name="create-prompts-and-menu-options"></a>Crear mensajes y opciones de menú

```PowerShell
$dialByNameMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9"

$dialByNameMenuOption9Target = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$dialByNameMenuOption9Entity = New-CsAutoAttendantCallableEntity -Identity $dialByNameMenuOption9Target -Type applicationendpoint

$dialByNameMenuOption9 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone9 -CallTarget $dialByNameMenuOption9Entity

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt -EnableDialByName -DirectorySearchMethod ByName

$dialByNameCallFlow = New-CsAutoAttendantCallFlow -Name "Contoso Dial By Name Call Flow" -Menu $dialByNameMenu

$dialByNameAutoAttendant = New-CsAutoAttendant -Name "Contoso Dial By Name" -DefaultCallFlow $dialByNameCallFlow -LanguageId "en-US" -TimeZoneId "UTC" -Operator $operatorEntity -EnableVoiceResponse -InclusionScope $dialScope
```

### <a name="assign-resource-account"></a>Asignar cuenta de recursos

```PowerShell
New-CsOnlineApplicationInstanceAssociation -Identities @($dialByNameApplicationInstanceID) -ConfigurationID $dialByNameAutoAttendant.Id -ConfigurationType AutoAttendant
```
