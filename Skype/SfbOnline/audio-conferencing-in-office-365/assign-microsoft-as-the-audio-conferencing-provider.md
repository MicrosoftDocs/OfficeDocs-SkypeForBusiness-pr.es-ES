---
title: Asignar Microsoft como proveedor de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 2ccb2b9a2b0a611d46056a8369dcb92d294c081f
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="8bc3e-103">Asignar Microsoft como proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="8bc3e-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="8bc3e-104">Para utilizar Audio conferencia en Office 365 con Skype para empresas y Teams de Microsoft, los usuarios de su organización necesitan tener una licencia de conferencias de Audio que se les asigne.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="8bc3e-105">Vea [probar o comprar Audio conferencia en Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obtener más información sobre licencias y cuánto cuestan.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="8bc3e-106">Conferencia de Audio de Microsoft proporciona identificadores que puede utilizarse para unirse a las reuniones de la organización por los participantes de la reunión de la conferencia, pasadores y números de teléfono de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="8bc3e-107">Sólo debe asignar Microsoft como proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="8bc3e-108">Asignar Microsoft como proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="8bc3e-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="8bc3e-109">Usar el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8bc3e-109">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="8bc3e-110">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-110">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="8bc3e-111">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="8bc3e-112">Si ve un titular le notifica que hay usuarios que tienen una **Conferencia de Audio** licencia asignada pero no tiene Microsoft establecer como su proveedor de conferencia de audio aún, haga clic en **haga clic aquí para moverlos**.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-112">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="8bc3e-113">Si no ve la pancarta, en el **Skype para el centro de administración de negocios** , haga clic en **usuarios**y, a continuación, seleccione el filtro de **usuarios listos para moverlos a las conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="8bc3e-113">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="8bc3e-114">En la página de propiedades para el usuario, en **nombre del proveedor**, seleccione **Microsoft** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-114">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8bc3e-115">Puesto que está utilizando Microsoft como proveedor de conferencia de audio y hay varios números de teléfono, puede utilizar la lista desplegable de **número de peaje predeterminado** para seleccionar un número de audio predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-115">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="8bc3e-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-116">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="8bc3e-117">Usar un script de Windows PowerShell para un pequeño número de usuarios</span><span class="sxs-lookup"><span data-stu-id="8bc3e-117">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="8bc3e-118">Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un número reducido de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-118">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc3e-119">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos).</span><span class="sxs-lookup"><span data-stu-id="8bc3e-119">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="8bc3e-120">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-120">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="8bc3e-121">Para cambiar el proveedor de Microsoft para un número reducido de usuarios, puede utilizar el cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8bc3e-121">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="8bc3e-122">Usar un script de Windows PowerShell para un gran número de usuarios</span><span class="sxs-lookup"><span data-stu-id="8bc3e-122">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="8bc3e-123">Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-123">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="8bc3e-124">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos).</span><span class="sxs-lookup"><span data-stu-id="8bc3e-124">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="8bc3e-125">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-125">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="8bc3e-126">Puede guardar la siguiente secuencia de comandos como un archivo de secuencia de comandos de PowerShell y ejecutarlo utilizando cualquiera de sus parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-126">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="8bc3e-127">**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="8bc3e-128">**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="8bc3e-129">**Ejemplo 3:** En este ejemplo, puede utilizar esta secuencia de comandos para cambiar el proveedor de conferencia de audio de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="8bc3e-129">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="8bc3e-130">Aquí está la secuencia de comandos:</span><span class="sxs-lookup"><span data-stu-id="8bc3e-130">Here is the script:</span></span>

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
<span data-ttu-id="8bc3e-131">Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="8bc3e-131">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8bc3e-132">See also</span><span class="sxs-lookup"><span data-stu-id="8bc3e-132">Related topics</span></span>
<span data-ttu-id="8bc3e-133">[Probar o comprar Audio conferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Configurar Skype para los negocios en línea](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="8bc3e-133">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

