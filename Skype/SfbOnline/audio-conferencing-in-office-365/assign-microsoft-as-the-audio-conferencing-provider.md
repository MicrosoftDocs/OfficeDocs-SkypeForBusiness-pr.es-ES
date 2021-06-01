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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c9ba3-103">Asignar a Microsoft como proveedor de servicios de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="c9ba3-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="c9ba3-104">Para usar las conferencias de audio en Microsoft 365 o Office 365 con Skype Empresarial y Microsoft Teams, los usuarios de su organización deben tener asignada una licencia de conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="c9ba3-105">Vea [Probar o comprar audioconferencias](try-or-purchase-audio-conferencing-in-office-365.md) en Microsoft 365 o Office 365 para obtener más información sobre licencias y cuánto cuesta.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="c9ba3-106">Microsoft AudioConferencing proporciona números de teléfono de acceso telefónico local, PINs e identificación de conferencia que los participantes de la reunión pueden usar para unirse a las reuniones de su organización.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="c9ba3-107">Solo necesita asignar Microsoft como proveedor de audioconferencias a personas que van a programar o dirigir Skype Empresarial o Microsoft Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c9ba3-108">Asignar a Microsoft como proveedor de servicios de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="c9ba3-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Un icono que muestra Skype Empresarial logotipo](../images/sfb-logo-30x30.png) <span data-ttu-id="c9ba3-110">Using the Skype for Business admin center</span><span class="sxs-lookup"><span data-stu-id="c9ba3-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="c9ba3-111">Vaya al portal **heredado Microsoft Teams administrador** del centro de  >  **administración.**</span><span class="sxs-lookup"><span data-stu-id="c9ba3-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="c9ba3-112">En el **Skype Empresarial de administración**, en el panel de navegación izquierdo, vaya a **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="c9ba3-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c9ba3-113">Si ve una pancarta en la que se le notifica que hay usuarios que tienen asignada una licencia de **audioconferencia** pero que aún no tienen Microsoft establecido como su proveedor de audioconferencias, haga clic en Haga clic aquí para moverlos.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="c9ba3-114">Si no ve la pancarta, en el centro de administración de Skype Empresarial haga clic en Usuarios **y, a continuación,** seleccione el filtro Usuarios listos para moverse al filtro **audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="c9ba3-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="c9ba3-115">En la página de propiedades del usuario, en **Nombre del proveedor,** seleccione **Microsoft** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c9ba3-116">Como usa Microsoft como proveedor de audioconferencias y hay varios  números de teléfono, puede usar la lista desplegable Número de pago predeterminado para seleccionar un número de audio predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="c9ba3-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="c9ba3-118">Usar un script de Windows PowerShell para un pequeño número de usuarios</span><span class="sxs-lookup"><span data-stu-id="c9ba3-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="c9ba3-119">Para ahorrar tiempo o automatizar esto, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de audioconferencias para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ba3-120">Cuando el proveedor se cambia de otro proveedor a **Microsoft,** se reemplazará la información de audioconferencia para el usuario (id. de conferencia, números gratuitos y de pago).</span><span class="sxs-lookup"><span data-stu-id="c9ba3-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="c9ba3-121">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="c9ba3-122">Para cambiar el proveedor a Microsoft para un pequeño número de usuarios, puede usar el cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="c9ba3-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="c9ba3-123">Usar un script de Windows PowerShell para un gran número de usuarios</span><span class="sxs-lookup"><span data-stu-id="c9ba3-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="c9ba3-124">Para ahorrar tiempo o automatizar esto, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de audioconferencias para un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="c9ba3-125">Cuando el proveedor se cambia de otro proveedor a **Microsoft,** se reemplazará la información de audioconferencia para el usuario (id. de conferencia, números gratuitos y de pago).</span><span class="sxs-lookup"><span data-stu-id="c9ba3-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="c9ba3-126">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="c9ba3-127">Puede guardar el siguiente script como un archivo de script de PowerShell y, a continuación, ejecutarlo con cualquiera de sus parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="c9ba3-128">**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="c9ba3-129">**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="c9ba3-130">**Ejemplo 3:** En este ejemplo, puede usar este script para cambiar el proveedor de audioconferencia de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="c9ba3-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="c9ba3-131">Este es el script:</span><span class="sxs-lookup"><span data-stu-id="c9ba3-131">Here is the script:</span></span>

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
<span data-ttu-id="c9ba3-132">Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba3-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c9ba3-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c9ba3-133">Related topics</span></span>
<span data-ttu-id="c9ba3-134">[Pruebe o compre Audioconferencia en Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurar Skype Empresarial online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="c9ba3-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>
