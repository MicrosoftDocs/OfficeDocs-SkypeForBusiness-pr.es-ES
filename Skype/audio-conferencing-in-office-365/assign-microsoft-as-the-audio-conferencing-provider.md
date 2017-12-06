---
title: "Asignar Microsoft como proveedor de conferencias de audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# Asignar Microsoft como proveedor de conferencias de audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](d935a90d-ea61-433d-a820-b400ed9c1f5d.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/d935a90d-ea61-433d-a820-b400ed9c1f5d). 
  
Un proveedor de servicios de audioconferencia proporciona el  *puente de conferencia*  . Puente de conferencia proporciona los números de teléfono de acceso telefónico, bordes e identificadores de conferencia para las reuniones que se crean. Solo debe asignar un proveedor de servicios de audioconferencia a las personas que van a programar o dirigir reuniones de Microsoft Teams o Skype Empresarial.
  
Si desea poder muestre **Microsoft** como proveedor de audio, debe asignar una licencia de ** Conferencias de Audio** para el usuario.
  
> [!NOTE]
> Si se asigna una licencia de **Conferencias de Audio** a una persona que no tiene un proveedor de servicios de audioconferencia de terceros, Microsoft se asigna automáticamente como el proveedor de servicios de audioconferencia. Puede[Asignar a un tercero como el proveedor de conferencias de audio](assign-a-third-party-as-the-audio-conferencing-provider.md) si es necesario.
  
## Asignar Microsoft como proveedor de conferencias de audio

### Usar el Centro de administración de Skype Empresarial

1. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
    > [!NOTE]
    > Cuando se cambia el proveedor de servicios de otro proveedor a **Microsoft**, se reemplazará la información de conferencias de audio para el usuario (identificador de conferencia, y de pago y números gratuitos). Debe guardar esta información antes de cambiar el proveedor de servicios. 
  
2. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.
    
3. En el panel de acciones, haga clic en **Editar**.
    
4. En la página de propiedades para el usuario, en **nombre del proveedor**, seleccione **Microsoft** en la lista desplegable.
    
    > [!NOTE]
    > Puesto que usa Microsoft como el proveedor de servicios de audioconferencia y hay varios números de teléfono, puede usar la lista desplegable de **número de teléfono predeterminado** para seleccionar un número de audio predeterminado para el usuario.
  
5. Haga clic en **Guardar**.
    
### Uso de un script de Windows PowerShell para un pequeño número de usuarios

Para ahorrar tiempo o automatizar este proceso, puede usar el siguiente script de PowerShell para configurar Microsoft como el proveedor de servicios de audioconferencia para un pequeño número de usuarios.
  
> [!NOTE]
> Cuando se cambia el proveedor de servicios de otro proveedor a **Microsoft**, se reemplazará la información de conferencias de audio para el usuario (identificador de conferencia, y de pago y números gratuitos). Debe guardar esta información antes de cambiar el proveedor de servicios. 
  
Puede guardar uno o más de los siguientes scripts como un script de PowerShell y luego ejecutarlo.
  
Para cambiar el proveedor a Microsoft para un pequeño número de usuarios, puede utilizar [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
> **Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### Usar un script de Windows PowerShell para un gran número de usuarios

Para ahorrar tiempo o automatizar este proceso, puede usar el siguiente script de PowerShell para configurar Microsoft como el proveedor de servicios de audioconferencia para un gran número de usuarios.
  
> [!NOTE]
> Cuando se cambia el proveedor de servicios de otro proveedor a **Microsoft**, se reemplazará la información de conferencias de audio para el usuario (identificador de conferencia, y de pago y números gratuitos). Debe guardar esta información antes de cambiar el proveedor de servicios. 
  
Puede guardar uno o más de los siguientes scripts como un script de PowerShell y luego ejecutarlo.
  
> **Ejemplo 1:** En este ejemplo, puede usar esta secuencia de comandos para cambiar el proveedor de servicios de audioconferencia de Intercall (o de otro proveedor) a **Microsoft** para un gran número de usuarios de su organización.
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **Aquí está el script:**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## ¿Qué más debo saber?

- Un usuario se puede asignar solo un proveedor de servicios de audioconferencia.
    
- Puede cambiar el proveedor de conferencias de audio de Microsoft a un proveedor de terceros en cualquier momento. Para obtener más información, consulte [Asignar a un tercero como el proveedor de conferencias de audio](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- En su organización, puede tener algunas personas que usen Microsoft como su proveedor de conferencias de audio y otras personas que utilicen un proveedor de terceros. Pero es más difícil de configurar y administrar.
    
## Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

