---
title: Asignar Microsoft como el proveedor de conferencia de audio
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 934513c3f119044f05835e49fe73f8aba74de753
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703732"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="61d1d-103">Asignar Microsoft como el proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="61d1d-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="61d1d-104">Para utilizar la conferencia de Audio en Office 365 con Skype para empresas y Microsoft Teams, los usuarios de la organización necesitan tener una licencia de conferencias de Audio asignada a ellos.</span><span class="sxs-lookup"><span data-stu-id="61d1d-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="61d1d-105">Vea [probar o comprar conferencias de Audio en Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obtener más información sobre licencias y cuánto cuesta.</span><span class="sxs-lookup"><span data-stu-id="61d1d-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="61d1d-106">Conferencia de Audio de Microsoft proporciona los números de teléfono de acceso telefónico, el NIP y la conferencia identificadores que pueden usarse por los participantes de la reunión para unirse a las reuniones de la organización.</span><span class="sxs-lookup"><span data-stu-id="61d1d-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="61d1d-107">Sólo debe asignar Microsoft como proveedor de conferencias de audio a las personas que se van a programar o un cliente potencial Skype para las reuniones de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61d1d-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="61d1d-108">Asignar Microsoft como el proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="61d1d-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="61d1d-110">Usar el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="61d1d-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="61d1d-111">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="61d1d-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="61d1d-112">En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio**.</span><span class="sxs-lookup"><span data-stu-id="61d1d-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="61d1d-113">Si ve un titular que le informa de que no hay usuarios que tienen una **Conferencia de Audio** licencia asignada pero no tiene Microsoft establecer como su proveedor de servicios de audioconferencia aún, haga clic en **haga clic aquí para moverlos**.</span><span class="sxs-lookup"><span data-stu-id="61d1d-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="61d1d-114">Si no ve la pancarta, en el **Skype para el centro de administración de negocio** , haga clic en **usuarios**y, a continuación, seleccione el filtro **listos para moverse a la conferencia de Audio de los usuarios** .</span><span class="sxs-lookup"><span data-stu-id="61d1d-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="61d1d-115">En la página de propiedades para el usuario, en **nombre del proveedor**, seleccione **Microsoft** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="61d1d-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="61d1d-116">Debido a que está utilizando Microsoft como proveedor de conferencias de audio y hay varios números de teléfono, puede usar la lista desplegable de **número de teléfono de pago predeterminado** para seleccionar un número de audio predeterminada para el usuario.</span><span class="sxs-lookup"><span data-stu-id="61d1d-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="61d1d-117">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="61d1d-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="61d1d-118">Usar un script de Windows PowerShell para un pequeño número de usuarios</span><span class="sxs-lookup"><span data-stu-id="61d1d-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="61d1d-119">Para ahorrar tiempo o automatizar esto, puede usar el siguiente script de PowerShell para configurar Microsoft como el proveedor de conferencia de audio para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="61d1d-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="61d1d-120">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (identificador de conferencia, teléfono de pago y los números gratuitos).</span><span class="sxs-lookup"><span data-stu-id="61d1d-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="61d1d-121">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="61d1d-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="61d1d-122">Para cambiar el proveedor de Microsoft para un pequeño número de usuarios, puede usar el cmdlet [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="61d1d-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="61d1d-123">Usar un script de Windows PowerShell para un gran número de usuarios</span><span class="sxs-lookup"><span data-stu-id="61d1d-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="61d1d-124">Para ahorrar tiempo o automatizar esto, puede usar el siguiente script de PowerShell para establecer Microsoft como el proveedor de conferencia de audio para un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="61d1d-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="61d1d-125">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (identificador de conferencia, teléfono de pago y los números gratuitos).</span><span class="sxs-lookup"><span data-stu-id="61d1d-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="61d1d-126">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="61d1d-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="61d1d-127">Puede guardar la siguiente secuencia de comandos como un archivo de secuencia de comandos de PowerShell y, a continuación, ejecútelo con cualquiera de sus parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="61d1d-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="61d1d-128">**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="61d1d-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="61d1d-129">**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="61d1d-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="61d1d-130">**El ejemplo 3:** En este ejemplo, puede usar esta secuencia de comandos para cambiar el proveedor de conferencia de audio de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios en la organización.</span><span class="sxs-lookup"><span data-stu-id="61d1d-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="61d1d-131">Aquí está la secuencia de comandos:</span><span class="sxs-lookup"><span data-stu-id="61d1d-131">Here is the script:</span></span>

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
<span data-ttu-id="61d1d-132">Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="61d1d-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="61d1d-133">See also</span><span class="sxs-lookup"><span data-stu-id="61d1d-133">Related topics</span></span>
<span data-ttu-id="61d1d-134">[Probar o comprar conferencias de Audio en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype para profesionales en línea](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="61d1d-134">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

