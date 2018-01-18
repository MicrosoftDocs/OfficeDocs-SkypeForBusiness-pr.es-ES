---
title: Asignar Microsoft como proveedor de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: c42bf80b456517eb6305a993cbb11c3b9a245c20
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar Microsoft como proveedor de conferencia de audio

Un proveedor de conferencia de audio proporciona el *puente de conferencia*. El puente de conferencia proporciona los números de teléfono de acceso telefónico, pasadores y conferencia identificadores para las reuniones que se crean. Sólo debe asignar a un proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.
  
Si desea poder ver listados de **Microsoft** como proveedor de audio, debe asignar al usuario una licencia de **Conferencia de Audio** .
  
> [!NOTE]
> Si asigna una licencia de **Conferencias de Audio** a una persona que no tiene un proveedor de conferencia de audio de otros fabricantes, Microsoft se asigna automáticamente como el proveedor de conferencia de audio. Puede [asignar un tercero como el proveedor de conferencia de audio](assign-a-third-party-as-the-audio-conferencing-provider.md) si es necesario.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar Microsoft como proveedor de conferencia de audio

### <a name="using-the-skype-for-business-admin-center"></a>Usar el Centro de administración de Skype Empresarial

1. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
    > [!NOTE]
    > Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos). Debe guardar esta información antes de cambiar el proveedor. 
  
2. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.
    
3. En el panel de acciones, haga clic en **Editar**.
    
4. En la página de propiedades para el usuario, en **nombre del proveedor**, seleccione **Microsoft** en la lista desplegable.
    
    > [!NOTE]
    > Puesto que está utilizando Microsoft como proveedor de conferencia de audio y hay varios números de teléfono, puede utilizar la lista desplegable de **número de peaje predeterminado** para seleccionar un número de audio predeterminado para el usuario.
  
5. Haga clic en **Guardar**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Usar un script de Windows PowerShell para un pequeño número de usuarios

Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un número reducido de usuarios.

> [!NOTE]
> Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos). Debe guardar esta información antes de cambiar el proveedor. 
  
Puede guardar uno o más de los siguientes scripts como un script de PowerShell y luego ejecutarlo.
  
Para cambiar el proveedor de Microsoft para un número reducido de usuarios, puede utilizar el [CsOnlineDialInConferencingUser de habilitar](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Usar un script de Windows PowerShell para un gran número de usuarios
Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un gran número de usuarios.

Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos). Debe guardar esta información antes de cambiar el proveedor. 
  
Puede guardar uno o más de los siguientes scripts como un script de PowerShell y luego ejecutarlo.

**Ejemplo 1:** En este ejemplo, puede utilizar esta secuencia de comandos para cambiar el proveedor de conferencia de audio de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de la organización.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Aquí está la secuencia de comandos:

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Un usuario puede asignar a solo un proveedor de conferencia de audio.
    
- Puede cambiar el proveedor de conferencia de audio de Microsoft a un proveedor en cualquier momento. Para obtener más información, vea [asignar un tercero como el proveedor de conferencia de audio](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- En su organización, puede tener algunas personas que usan Microsoft como su proveedor de conferencia de audio y otras personas que utilizan un proveedor de terceros. Pero esto es más complicado configurar y administrar.
    
## <a name="related-topics"></a>Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)