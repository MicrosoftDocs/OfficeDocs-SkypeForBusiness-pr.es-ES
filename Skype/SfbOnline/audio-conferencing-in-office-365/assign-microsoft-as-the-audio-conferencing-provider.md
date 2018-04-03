---
title: Asignar Microsoft como proveedor de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar Microsoft como proveedor de conferencia de audio

Para utilizar Audio conferencia en Office 365 con Skype para empresas y Teams de Microsoft, los usuarios de su organización necesitan tener una licencia de conferencias de Audio que se les asigne. Vea [probar o comprar Audio conferencia en Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obtener más información sobre licencias y cuánto cuestan.

Conferencia de Audio de Microsoft proporciona identificadores que puede utilizarse para unirse a las reuniones de la organización por los participantes de la reunión de la conferencia, pasadores y números de teléfono de acceso telefónico. Sólo debe asignar Microsoft como proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.

Si una licencia de **Conferencia de Audio de Microsoft** se asigna a un usuario que no tiene un proveedor de conferencia de audio, proveedor del usuario se establecerá automáticamente en **Microsoft** y no tienes que hacer nada más. Si el usuario ya tiene un proveedor de conferencia de audio, debe cambiar el proveedor del usuario a Microsoft después de la asignación de una licencia de conferencia de Audio.

Si desea poder ver que Microsoft aparece como el proveedor de conferencia de audio, debe asignar al usuario una licencia de conferencia de Audio.


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar Microsoft como proveedor de conferencia de audio

### <a name="using-the-skype-for-business-admin-center"></a>Usar el Centro de administración de Skype Empresarial

1. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
    > [!NOTE]
    > Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos). Debe guardar esta información antes de cambiar el proveedor. 
  
2. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**.
    
3. Si ve un titular le notifica que hay usuarios que tienen una **Conferencia de Audio** licencia asignada pero no tiene Microsoft establecer como su proveedor de conferencia de audio aún, haga clic en **haga clic aquí para moverlos**. Si no ve la pancarta, en el **Skype para el centro de administración de negocios** , haga clic en **usuarios**y, a continuación, seleccione el filtro de **usuarios listos para moverlos a las conferencias de Audio** .
    
4. En la página de propiedades para el usuario, en **nombre del proveedor**, seleccione **Microsoft** en la lista desplegable.
    
    > [!NOTE]
    > Puesto que está utilizando Microsoft como proveedor de conferencia de audio y hay varios números de teléfono, puede utilizar la lista desplegable de **número de peaje predeterminado** para seleccionar un número de audio predeterminado para el usuario.
  
5. Haga clic en **Guardar**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Usar un script de Windows PowerShell para un pequeño número de usuarios

Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un número reducido de usuarios.

> [!NOTE]
> Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos). Debe guardar esta información antes de cambiar el proveedor. 

  
Para cambiar el proveedor de Microsoft para un número reducido de usuarios, puede utilizar el cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Usar un script de Windows PowerShell para un gran número de usuarios
Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un gran número de usuarios.

Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos). Debe guardar esta información antes de cambiar el proveedor. 
  
Puede guardar la siguiente secuencia de comandos como un archivo de secuencia de comandos de PowerShell y ejecutarlo utilizando cualquiera de sus parámetros de entrada.

**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Ejemplo 3:** En este ejemplo, puede utilizar esta secuencia de comandos para cambiar el proveedor de conferencia de audio de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de la organización.
    
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
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
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
  
    
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

