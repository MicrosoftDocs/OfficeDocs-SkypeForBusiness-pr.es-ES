---
title: Crear una cola de llamadas a través de cmdlets
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar colas de llamadas a través de cmdlets
ms.openlocfilehash: 8d62d3648d35cc302e333c2efa552bb2094cb14d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674582"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Crear una cola de llamadas a través de cmdlets

## <a name="assumptions"></a>Suposiciones

1. PowerShell está instalado en el equipo
   - Configurar el equipo para [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - Módulo MSTeams instalado

     ```powershell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - Módulo MSOnline instalado

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. Tiene derechos de administración de inquilinos
3. Has comprado Teléfono Microsoft Teams
4. Los agentes, las listas de distribución y los canales de Teams a los que se hace referencia a continuación ya se han creado

Nota: El cmdlet de canal de Teams que se usa a continuación forma parte de la versión preliminar pública del módulo de PowerShell Teams.  Para obtener más información, vea [Instalar Teams versión preliminar pública de PowerShell](teams-powershell-install.md) y vea [también Microsoft Teams notas de la versión de PowerShell](teams-powershell-release-notes.md).

Los usuarios que ya tienen instalado el módulo MicrosoftTeams deben `Update-Module MicrosoftTeams` asegurarse de que está instalada la versión más actualizada.

## <a name="scenario"></a>Escenario

Se crearán las tres colas de llamadas siguientes:

Información de la cola de llamadas de ventas:

- Frontal por operador automático: Sí
- Llamadas directas desde RTC: No
- Idioma: inglés (EE. UU.)
- Saludo: Ninguno
- Música en espera: Reproducir un archivo de audio
  - Nombre de archivo: sales-hold-in-queue-music.wav
- Respuesta de llamadas: usuarios
  - Bill@contoso.com
  - Mary@contoso.com
- Modo de conferencia: Activado
- Método de enrutamiento: Operador
- Enrutamiento basado en presencia: Desactivado
- Los agentes de llamadas pueden dejar de realizar llamadas: Sí
- Hora de alerta del agente de llamadas: 15
- Administración de desbordamiento de llamadas: 200
  - Redirigir a: Adele@contoso.com
- Administración del tiempo de espera de llamadas: 120 segundos
  - Redirigir a: Adele@contoso.com

Información de la cola de llamadas de soporte técnico:

- Frontal por operador automático: Sí
- Llamadas directas desde RTC: No
- Idioma: inglés (Reino Unido)
- Saludo: Reproducir un archivo de audio
  - Nombre de archivo: support-greeting.wav
- Música en espera: Reproducir un archivo de audio
  - Nombre de archivo: support-hold-in-queue-music.wav
- Respuesta de llamadas: lista de distribución de soporte técnico
  - Support@contoso.com
- Modo de conferencia: Activado
- Método de enrutamiento: el más largo de los inactivos
- Enrutamiento basado en presencia: N/A: activado de forma predeterminada debido a la inactividad más larga
- Los agentes de llamadas pueden dejar de realizar llamadas: No
- Hora de alerta del agente de llamadas: 15
- Administración de desbordamiento de llamadas: 200
  - Redirigir: admitir correo de voz compartido
    - Reproducir un archivo de audio (support-shared-voicemail-greeting.wav)
    - Transcripción habilitada
- Administración del tiempo de espera de llamadas: 45 minutos
  - Redirigir: admitir correo de voz compartido
    - TTS: "Sentimos haberte hecho esperar y ahora estamos transfiriendo tu llamada al correo de voz".
    - Transcripción habilitada

Información de la cola de llamadas colaborativas de las instalaciones:

- Delante del operador automático: No
- Llamadas directas desde RTC: No (solo llamadas internas)
- Idioma: francés FR
- Saludo: Ninguno
- Música en espera: predeterminado
- Respuesta de llamadas: equipo: instalaciones
- Canal de contestador de llamadas: Servicio de asistencia
  - Propietario del canal: Fred@contoso.com
- Modo de conferencia: Activado
- Método de enrutamiento: Round Robin
- Enrutamiento basado en presencia: Activado
- Los agentes de llamadas pueden dejar de realizar llamadas: No
- Hora de alerta del agente de llamadas: 15
- Administración de desbordamiento de llamadas: 200
  - Desconectar
- Administración del tiempo de espera de llamadas: 45 minutos
  - Desconectar

## <a name="login"></a>Inicio de sesión

Se le pedirá que escriba sus credenciales de administrador de Teams.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="sales-queue"></a>Cola de ventas

### <a name="create-audio-files"></a>Crear archivos de audio

Reemplace "d:\\" por la ruta de acceso a la ubicación de almacenamiento de los archivos wav en el equipo.

```powershell
$content = Get-Content "d:\sales-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### <a name="get-users-id"></a>Obtener id. de usuario

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Obtener una lista de idiomas admitidos

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Crear cola de llamadas

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### <a name="get-license-types"></a>Obtener tipos de licencia

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Crear y asignar cuenta de recursos

Nota: Teléfono número no es necesario aquí, ya que la cola de llamadas es front-ended por un operador automático

- Id. de aplicación
  - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
  - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: El tipo de licencia que se muestra a continuación (PHONESYSTEM_VIRTUALUSER) debe ser uno enumerado por el cmdlet de Get-MsolAccountSku anterior.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Sales-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="support-queue"></a>Cola de soporte técnico

### <a name="create-audio-files"></a>Crear archivos de audio

Reemplace "d:\\" por la ruta de acceso a la ubicación de almacenamiento de los archivos wav en el equipo.

```powershell
$content = Get-Content "d:\support-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content "d:\support-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content "d:\support-shared-voicemail-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
```

### <a name="get-support-team-group-id"></a>Obtener el id. de grupo del equipo de soporte técnico

```powershell
$teamSupportID = (Get-Team -displayname "Support").GroupID
```

### <a name="get-list-of-supported-languages"></a>Obtener una lista de idiomas admitidos

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Crear cola de llamadas

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### <a name="get-license-types"></a>Obtener tipos de licencia

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Crear y asignar cuenta de recursos

Nota: Teléfono número no es necesario aquí, ya que la cola de llamadas es front-ended por un operador automático

- Id. de aplicación
  - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
  - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: El tipo de licencia que se muestra a continuación (PHONESYSTEM_VIRTUALUSER) debe ser uno enumerado por el cmdlet de Get-MsolAccountSku anterior.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Support-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="facilities-collaborative-calling-queue"></a>Cola de llamadas colaborativas de Facilities

### <a name="get-facilities-team-group-id"></a>Obtener id. de grupo del equipo de Instalaciones

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### <a name="get-facilities-help-desk-team-channel-id"></a>Obtener id. de canal de equipo del servicio de asistencia de Facilities

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Obtener identificador de usuario del propietario del canal de asistencia de Facilities

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Obtener en nombre del identificador de cuenta de recurso de llamada

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Obtener una lista de idiomas admitidos

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Crear cola de llamadas

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
```

### <a name="get-license-types"></a>Obtener tipos de licencia

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Crear y asignar cuenta de recursos

**Nota**: Teléfono número no es necesario aquí, ya que la cola de llamadas es front-ended por un operador automático

- Id. de aplicación
  - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
  - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: El tipo de licencia que se muestra a continuación (PHONESYSTEM_VIRTUALUSER) debe ser uno enumerado por el cmdlet de Get-MsolAccountSku anterior.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Facilities-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```
