---
title: Asignar a Microsoft como proveedor de servicios de audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237766"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar a Microsoft como proveedor de servicios de audioconferencia

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Para usar las conferencias de audio en Microsoft 365 o Office 365 con Skype Empresarial y Microsoft Teams, los usuarios de su organización deben tener asignada una licencia de conferencias de audio. Vea [Probar o comprar audioconferencias](try-or-purchase-audio-conferencing-in-office-365.md) en Microsoft 365 o Office 365 para obtener más información sobre licencias y cuánto cuesta.

Microsoft AudioConferencing proporciona números de teléfono de acceso telefónico local, PINs e identificación de conferencia que los participantes de la reunión pueden usar para unirse a las reuniones de su organización. Solo necesita asignar Microsoft como proveedor de audioconferencias a personas que van a programar o dirigir Skype Empresarial o Microsoft Teams reuniones.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar a Microsoft como proveedor de servicios de audioconferencia

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Un icono que muestra Skype Empresarial logotipo](../images/sfb-logo-30x30.png) Using the Skype for Business admin center

1. Vaya al portal **heredado Microsoft Teams administrador** del centro de  >  **administración.**
    
2. En el **Skype Empresarial de administración**, en el panel de navegación izquierdo, vaya a **Audioconferencia.**
    
3. Si ve una pancarta en la que se le notifica que hay usuarios que tienen asignada una licencia de **audioconferencia** pero que aún no tienen Microsoft establecido como su proveedor de audioconferencias, haga clic en Haga clic aquí para moverlos. Si no ve la pancarta, en el centro de administración de Skype Empresarial haga clic en Usuarios **y, a continuación,** seleccione el filtro Usuarios listos para moverse al filtro **audioconferencia.**
    
4. En la página de propiedades del usuario, en **Nombre del proveedor,** seleccione **Microsoft** en la lista desplegable.
    
    > [!NOTE]
    > Como usa Microsoft como proveedor de audioconferencias y hay varios  números de teléfono, puede usar la lista desplegable Número de pago predeterminado para seleccionar un número de audio predeterminado para el usuario.
  
5. Haga clic en **Guardar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Usar un script de Windows PowerShell para un pequeño número de usuarios

Para ahorrar tiempo o automatizar esto, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de audioconferencias para un pequeño número de usuarios.

> [!NOTE]
> Cuando el proveedor se cambia de otro proveedor a **Microsoft,** se reemplazará la información de audioconferencia para el usuario (id. de conferencia, números gratuitos y de pago). Debe guardar esta información antes de cambiar el proveedor. 

  
Para cambiar el proveedor a Microsoft para un pequeño número de usuarios, puede usar el cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Usar un script de Windows PowerShell para un gran número de usuarios
Para ahorrar tiempo o automatizar esto, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de audioconferencias para un gran número de usuarios.

Cuando el proveedor se cambia de otro proveedor a **Microsoft,** se reemplazará la información de audioconferencia para el usuario (id. de conferencia, números gratuitos y de pago). Debe guardar esta información antes de cambiar el proveedor. 
  
Puede guardar el siguiente script como un archivo de script de PowerShell y, a continuación, ejecutarlo con cualquiera de sus parámetros de entrada.

**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Ejemplo 3:** En este ejemplo, puede usar este script para cambiar el proveedor de audioconferencia de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de su organización.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Este es el script:

  ```PowerShell
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
Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Temas relacionados
[Pruebe o compre Audioconferencia en Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurar Skype Empresarial online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
