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
ms.openlocfilehash: 8ce128c2fa19668ed93c6ad387feecbee2e00a8d
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164527"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar a Microsoft como proveedor de servicios de audioconferencia

Para usar Audioconferencia en Microsoft 365 u Office 365 con Skype Empresarial y Microsoft Teams, los usuarios de su organización necesitan tener asignada una licencia de Audioconferencia. Vea Probar o comprar Audioconferencia en [Microsoft 365 u Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obtener más información sobre licencias y cuánto cuesta.

Microsoft Audioconferencia proporciona números de teléfono de acceso telefónico local, NÚMEROS PIN e identificacións de conferencia que pueden usar los participantes de la reunión para unirse a las reuniones de su organización. Solo tiene que asignar Microsoft como el proveedor de servicios de audioconferencia a personas que van a programar o dirigir reuniones de Skype Empresarial o Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Asignar a Microsoft como proveedor de servicios de audioconferencia

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Un icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) Using the Skype for Business admin center

1. Vaya al Portal **heredado del Centro de administración** de Microsoft  >  Teams.
    
2. En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, vaya a **Audioconferencia.**
    
3. Si ve un banner en el que se le notifica que hay usuarios que tienen asignada una licencia de  **Audioconferencia** pero aún no han configurado Microsoft como su proveedor de servicios de audioconferencia, haga clic aquí para moverlos. Si no ve la pancarta, en el Centro de administración de **Skype** Empresarial, haga clic en Usuarios y, a continuación, seleccione los usuarios listos para moverse al filtro **Audioconferencia.**
    
4. En la página de propiedades del usuario, en **Nombre del** proveedor, seleccione **Microsoft** en la lista desplegable.
    
    > [!NOTE]
    > Dado que está usando Microsoft como el proveedor de servicios de audioconferencia y hay varios números de teléfono, puede usar la lista desplegable número de pago predeterminado para seleccionar un número de audio predeterminado para el usuario. 
  
5. Haga clic en **Guardar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Usar un script de Windows PowerShell para un pequeño número de usuarios

Para ahorrar tiempo o automatizar este proceso, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de servicios de audioconferencia para un pequeño número de usuarios.

> [!NOTE]
> Cuando se cambia el proveedor de otro proveedor a **Microsoft,** se reemplaza la información de audioconferencia para el usuario (Id. de conferencia, números gratuitos y de pago). Debe guardar esta información antes de cambiar el proveedor. 

  
Para cambiar el proveedor a Microsoft para un pequeño número de usuarios, puede usar el cmdlet [Enable-CsOnlineDialInConferencingUser.](https://technet.microsoft.com/library/mt243813.aspx)
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Usar un script de Windows PowerShell para un gran número de usuarios
Para ahorrar tiempo o automatizar este proceso, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de servicios de audioconferencia para un gran número de usuarios.

Cuando se cambia el proveedor de otro proveedor a **Microsoft,** se reemplaza la información de audioconferencia para el usuario (Id. de conferencia, números gratuitos y de pago). Debe guardar esta información antes de cambiar el proveedor. 
  
Puede guardar el script siguiente como un archivo de script de PowerShell y, a continuación, ejecutarlo con cualquiera de sus parámetros de entrada.

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

**Ejemplo 3:** En este ejemplo, puede usar este script para cambiar el proveedor de servicios de audioconferencia de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de su organización.
    
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
Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="related-topics"></a>Temas relacionados
[Probar o comprar Audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

