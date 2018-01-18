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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="445f9-104">Asignar Microsoft como proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="445f9-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="445f9-105">Un proveedor de conferencia de audio proporciona el *puente de conferencia*.</span><span class="sxs-lookup"><span data-stu-id="445f9-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="445f9-106">El puente de conferencia proporciona los números de teléfono de acceso telefónico, pasadores y conferencia identificadores para las reuniones que se crean.</span><span class="sxs-lookup"><span data-stu-id="445f9-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="445f9-107">Sólo debe asignar a un proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="445f9-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="445f9-108">Si desea poder ver listados de **Microsoft** como proveedor de audio, debe asignar al usuario una licencia de **Conferencia de Audio** .</span><span class="sxs-lookup"><span data-stu-id="445f9-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="445f9-109">Si asigna una licencia de **Conferencias de Audio** a una persona que no tiene un proveedor de conferencia de audio de otros fabricantes, Microsoft se asigna automáticamente como el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="445f9-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="445f9-110">Puede [asignar un tercero como el proveedor de conferencia de audio](assign-a-third-party-as-the-audio-conferencing-provider.md) si es necesario.</span><span class="sxs-lookup"><span data-stu-id="445f9-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="445f9-111">Asignar Microsoft como proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="445f9-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="445f9-112">Usar el Centro de administración de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="445f9-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="445f9-113">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="445f9-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="445f9-114">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos).</span><span class="sxs-lookup"><span data-stu-id="445f9-114">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="445f9-115">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="445f9-115">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="445f9-116">En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.</span><span class="sxs-lookup"><span data-stu-id="445f9-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="445f9-117">En el panel de acciones, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="445f9-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="445f9-118">En la página de propiedades para el usuario, en **nombre del proveedor**, seleccione **Microsoft** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="445f9-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="445f9-119">Puesto que está utilizando Microsoft como proveedor de conferencia de audio y hay varios números de teléfono, puede utilizar la lista desplegable de **número de peaje predeterminado** para seleccionar un número de audio predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="445f9-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="445f9-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="445f9-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="445f9-121">Usar un script de Windows PowerShell para un pequeño número de usuarios</span><span class="sxs-lookup"><span data-stu-id="445f9-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="445f9-122">Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un número reducido de usuarios.</span><span class="sxs-lookup"><span data-stu-id="445f9-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="445f9-123">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos).</span><span class="sxs-lookup"><span data-stu-id="445f9-123">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="445f9-124">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="445f9-124">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="445f9-125">Puede guardar uno o más de los siguientes scripts como un script de PowerShell y luego ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="445f9-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="445f9-126">Para cambiar el proveedor de Microsoft para un número reducido de usuarios, puede utilizar el [CsOnlineDialInConferencingUser de habilitar](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span><span class="sxs-lookup"><span data-stu-id="445f9-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="445f9-127">**Ejemplo 1:** Puede ejecutar este script proporcionando una lista de usuarios que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="445f9-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="445f9-128">**Ejemplo 2:** Puede ejecutar este script proporcionando un archivo .csv que contenga la dirección de correo electrónico (alias) de cada usuario que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="445f9-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="445f9-129">Usar un script de Windows PowerShell para un gran número de usuarios</span><span class="sxs-lookup"><span data-stu-id="445f9-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="445f9-130">Para ahorrar tiempo o automatizar esta tarea, puede utilizar el siguiente script de PowerShell para configurar Microsoft como proveedor de conferencia de audio para un gran número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="445f9-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="445f9-131">Cuando se cambia el proveedor de otro proveedor a **Microsoft**, se reemplazará la información de conferencia de audio para el usuario (Id. de conferencia, cuota y números de teléfono gratuitos).</span><span class="sxs-lookup"><span data-stu-id="445f9-131">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="445f9-132">Debe guardar esta información antes de cambiar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="445f9-132">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="445f9-133">Puede guardar uno o más de los siguientes scripts como un script de PowerShell y luego ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="445f9-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="445f9-134">**Ejemplo 1:** En este ejemplo, puede utilizar esta secuencia de comandos para cambiar el proveedor de conferencia de audio de Intercall (u otro proveedor) a **Microsoft** para un gran número de usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="445f9-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="445f9-135">Aquí está la secuencia de comandos:</span><span class="sxs-lookup"><span data-stu-id="445f9-135">Here is the script:</span></span>

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
<span data-ttu-id="445f9-136">Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="445f9-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="445f9-137">¿Qué más debo saber?</span><span class="sxs-lookup"><span data-stu-id="445f9-137">What else should I know?</span></span>

- <span data-ttu-id="445f9-138">Un usuario puede asignar a solo un proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="445f9-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="445f9-139">Puede cambiar el proveedor de conferencia de audio de Microsoft a un proveedor en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="445f9-139">You can change the audio conferencing provider from Microsoft to a third-party provider at any time.</span></span> <span data-ttu-id="445f9-140">Para obtener más información, vea [asignar un tercero como el proveedor de conferencia de audio](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="445f9-140">To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="445f9-141">En su organización, puede tener algunas personas que usan Microsoft como su proveedor de conferencia de audio y otras personas que utilizan un proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="445f9-141">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="445f9-142">Pero esto es más complicado configurar y administrar.</span><span class="sxs-lookup"><span data-stu-id="445f9-142">But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="445f9-143">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="445f9-143">Related topics</span></span>

[<span data-ttu-id="445f9-144">Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft</span><span class="sxs-lookup"><span data-stu-id="445f9-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="445f9-145">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="445f9-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)