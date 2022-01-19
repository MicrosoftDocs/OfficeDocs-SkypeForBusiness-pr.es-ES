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
description: Obtenga información sobre cómo configurar las colas de llamadas a través de cmdlets
ms.openlocfilehash: 8ffbef5541a230755bb7439507e3002a5cb92462
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071119"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Crear una cola de llamadas a través de cmdlets

## <a name="assumptions"></a>Supuestos
1)  PowerShell está instalado en el equipo
- Configurar el equipo para [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
- Módulo MSTeams instalado ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Módulo MSOnline instalado ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Tiene derechos de administración de inquilinos
3)  Has comprado Microsoft Teams Teléfono
4)  Los agentes, las listas de distribución y los Teams a los que se hace referencia a continuación ya se han creado

Nota: El cmdlet Teams channel que se usa a continuación forma parte de la versión de vista previa pública de Teams módulo de PowerShell.  Para obtener más información, vea Instalar Teams vista previa pública de [PowerShell](teams-powershell-install.md) y vea también Microsoft Teams [notas de la versión de PowerShell.](teams-powershell-release-notes.md)

Los usuarios que ya tienen instalado el módulo MicrosoftTeams deben asegurarse de que la versión más actualizada ````Update-Module MicrosoftTeams```` está instalada.


## <a name="scenario"></a>Escenario

Se crearán las tres colas de llamadas siguientes:

Información de cola de llamadas de ventas:
- Delante de Operador automático: Sí
- Llamadas directas desde RTC: No
- Idioma: Inglés EE. UU.
- Saludo: Ninguno
- Música en espera: Reproducir un archivo de audio
- - Nombre de archivo: sales-hold-in-queue-music.wav
- Respuesta a llamadas: Usuarios
- - Bill@contoso.com
- - Mary@contoso.com
- Modo de conferencia: On
- Método de enrutamiento: Operador
- Enrutamiento basado en presencia: Desactivado
- Los agentes de llamadas pueden optar por no realizar llamadas: Sí
- Hora de alerta del agente de llamada: 15
- Administración de desbordamiento de llamadas: 200
- - Redirigir a: Adele@contoso.com
- Control del tiempo de espera de la llamada: 120 segundos
- - Redirigir a: Adele@contoso.com

Información de cola de llamadas de soporte técnico:
- Delante de Operador automático: Sí
- Llamadas directas desde RTC: No
-   Idioma: Inglés Reino Unido
-   Saludo: Reproducir un archivo de audio
-   - Nombre de archivo: support-greeting.wav
-   Música en espera: Reproducir un archivo de audio
-   - Nombre de archivo: support-hold-in-queue-music.wav
-   Respuesta a llamadas: Lista de distribución de soporte técnico
-   - Support@contoso.com
-   Modo de conferencia: On
-   Método de enrutamiento: Tiempo inactivo más largo
-   Enrutamiento basado en presencia: N/A: encendido de forma predeterminada debido a la inactividad más larga
-   Los agentes de llamadas pueden optar por no realizar llamadas: No
-   Hora de alerta del agente de llamada: 15
-   Administración de desbordamiento de llamadas: 200
-   - Redirigir: Admitir correo de voz compartido
- - -   Reproducir un archivo de audio (support-shared-voicemail-greeting.wav)
- - -   Transcripción habilitada
-   Control del tiempo de espera de la llamada: 45 minutos
-   - Redirigir: Admitir correo de voz compartido
- - - TTS: "Sentimos haberte hecho esperar y ahora estás transfiriendo la llamada al correo de voz".
- - - Transcripción habilitada


Información de la cola de llamadas colaborativa de Instalaciones:
- Delante de Operador automático: No
- Llamadas directas desde RTC: No (solo llamadas internas)
-   Idioma: FRANCÉS FR
-   Saludo: Ninguno
-   Música en espera: predeterminado
-   Respuesta a llamadas: Equipo: Instalaciones
-   Call Answering Channel: Help Desk
-   - Propietario del canal: Fred@contoso.com
-   Modo de conferencia: On
-   Método de enrutamiento: Round Robin
-   Enrutamiento basado en presencia: On
-   Los agentes de llamadas pueden optar por no realizar llamadas: No
-   Hora de alerta del agente de llamada: 15
-   Administración de desbordamiento de llamadas: 200
-   - Desconectar
-   Control del tiempo de espera de la llamada: 45 minutos
-   - Desconectar


## <a name="login"></a>Inicio de sesión
Se le pedirá que escriba sus credenciales Teams administrador.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Cola de ventas
### <a name="create-audio-files"></a>Crear archivos de audio
Reemplace "d: " por la ruta a la que se almacenan los archivos \\ wav en el equipo.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Obtener id. de usuarios
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>Obtener una lista de idiomas admitidos
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Crear cola de llamadas
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obtener tipos de licencia
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Crear y asignar una cuenta de recursos
Nota: Teléfono número no obligatorio aquí, ya que la cola de llamadas está delante de una Operador automático
- Id. de aplicación
- - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
- - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Cola de soporte técnico
### <a name="create-audio-files"></a>Crear archivos de audio
Reemplace "d: " por la ruta a la que se almacenan los archivos \\ wav en el equipo.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Obtener id. de grupo de equipo de soporte técnico
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Obtener una lista de idiomas admitidos
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Crear cola de llamadas
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obtener tipos de licencia
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Crear y asignar una cuenta de recursos
Nota: Teléfono número no obligatorio aquí, ya que la cola de llamadas está delante de una Operador automático
- Id. de aplicación
- - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
- - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Cola de llamadas colaborativas de instalaciones
### <a name="get-facilities-team-group-id"></a>Obtener id. de grupo de grupo de Instalaciones
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Id. de canal de equipo de Get Facilities Help Desk
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>Obtener el id. de usuario de Ower del canal de ayuda de Get Facilities
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Obtener en nombre de llamar id. de cuenta de recurso
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>Obtener una lista de idiomas admitidos
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Crear cola de llamadas
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Obtener tipos de licencia
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Crear y asignar una cuenta de recursos
Nota: Teléfono número no obligatorio aquí, ya que la cola de llamadas está delante de una Operador automático
- Id. de aplicación
- - Operador automático: ce933385-9390-45d1-9512-c8d228074e07
- - Cola de llamadas: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
