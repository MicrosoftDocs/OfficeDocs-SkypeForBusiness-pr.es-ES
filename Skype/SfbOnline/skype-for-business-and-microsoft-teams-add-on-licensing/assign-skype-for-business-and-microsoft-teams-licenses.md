---
title: Asignar licencias de Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204851"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="b17d9-103">Asignar licencias de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b17d9-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="b17d9-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="b17d9-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b17d9-106">Consulte las licencias de complementos de [Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md) Empresarial para obtener  información sobre qué licencias debe comprar y cómo comprarlas (según el plan de Microsoft 365 u Office 365) para que los usuarios obtengan Audioconferencia, números gratuitos y la capacidad de llamar a números de teléfono externos a su empresa.</span><span class="sxs-lookup"><span data-stu-id="b17d9-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b17d9-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="b17d9-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="b17d9-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="b17d9-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="b17d9-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="b17d9-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="b17d9-p103">**Latencia** después de asignar licencias: Debido a la latencia entre Microsoft 365 u Office 365 y Skype Empresarial Online, es posible que un plan de llamadas tarde hasta 24 horas en asignarse a un usuario después de asignar una licencia. Si después de 24 horas el usuario no tiene asignado un plan de llamadas, póngase en contacto con el soporte técnico para productos [empresariales: ayuda para administradores.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="b17d9-p103">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b17d9-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="b17d9-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="b17d9-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="b17d9-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="b17d9-118">Cómo asignar una licencia de sistema telefónico y plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="b17d9-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="b17d9-119">Los pasos son los mismos que se indican para asignar una licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="b17d9-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="b17d9-120">Vea [Asignar o quitar licencias de Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="b17d9-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="b17d9-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="b17d9-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="b17d9-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="b17d9-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="b17d9-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="b17d9-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="b17d9-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="b17d9-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="b17d9-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="b17d9-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="b17d9-130">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva (consulte los nombres de los productos de Sistema telefónico y Plan de llamadas o SKU usados para **scripting,** después del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="b17d9-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b17d9-131">Nombres de productos o SKU de planes de llamadas y sistema telefónicos usados para scripting</span><span class="sxs-lookup"><span data-stu-id="b17d9-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="b17d9-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="b17d9-132">**Product name**</span></span>|<span data-ttu-id="b17d9-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="b17d9-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b17d9-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="b17d9-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="b17d9-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b17d9-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="b17d9-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b17d9-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b17d9-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b17d9-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b17d9-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b17d9-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b17d9-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b17d9-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b17d9-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b17d9-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b17d9-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b17d9-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b17d9-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b17d9-142">Phone System</span></span>  <br/> |<span data-ttu-id="b17d9-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b17d9-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="b17d9-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="b17d9-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="b17d9-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b17d9-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="b17d9-146">Plan de llamadas nacionales (3000 min ee. UU. / planes de UE de 1200 min)</span><span class="sxs-lookup"><span data-stu-id="b17d9-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="b17d9-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b17d9-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="b17d9-148">Plan de llamadas nacionales (plan de llamadas a 120 min)</span><span class="sxs-lookup"><span data-stu-id="b17d9-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="b17d9-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="b17d9-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="b17d9-150">Plan de llamadas nacionales (plan de llamadas de 240 min)</span><span class="sxs-lookup"><span data-stu-id="b17d9-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="b17d9-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="b17d9-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="b17d9-152">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="b17d9-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="b17d9-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="b17d9-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b17d9-154">Audioconferencia: Sugerencias y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="b17d9-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="b17d9-155">Lo que debe saber antes de asignar licencias de Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b17d9-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="b17d9-156">**Proveedor** de servicios de audioconferencia de terceros: si un usuario ya está configurado para usar un proveedor de servicios de audioconferencia de terceros, al asignarle una licencia de **Audioconferencia,** se cambiará para usar Microsoft como el proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="b17d9-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b17d9-157">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="b17d9-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="b17d9-158">Pasos siguientes: Después de asignar **licencias de Audioconferencia,** debe asignar un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="b17d9-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="b17d9-159">Consulte [Asignar a Microsoft como proveedor de audioconferencias].</span><span class="sxs-lookup"><span data-stu-id="b17d9-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="b17d9-160">Cómo asignar una licencia de Audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="b17d9-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="b17d9-161">Los pasos son los mismos que se indican para asignar una licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="b17d9-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="b17d9-162">Vea [Asignar o quitar licencias de Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="b17d9-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="b17d9-163">Cómo asignar licencias de Audioconferencia en masa</span><span class="sxs-lookup"><span data-stu-id="b17d9-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="b17d9-164">Descargue e instale [el Microsoft Online Services Sign-In para profesionales de TI (RTW).](https://go.microsoft.com/fwlink/?LinkId=625123)</span><span class="sxs-lookup"><span data-stu-id="b17d9-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="b17d9-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en [Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="b17d9-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="b17d9-167">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="b17d9-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="b17d9-168">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="b17d9-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="b17d9-169">Consulte [los nombres de los productos de Audioconferencia o los SKU usados](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para scripting para todos los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="b17d9-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="b17d9-170">En este ejemplo se asigna una licencia de Enterprise E3 junto con una licencia de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="b17d9-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
    #Example of text file:
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
        }
    ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b17d9-171">Nombres de los productos de Audioconferencia o de los SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="b17d9-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="b17d9-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="b17d9-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="b17d9-173">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="b17d9-173">**Product name**</span></span>|<span data-ttu-id="b17d9-174">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="b17d9-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b17d9-175">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b17d9-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="b17d9-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b17d9-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="b17d9-177">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b17d9-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b17d9-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b17d9-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b17d9-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b17d9-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b17d9-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b17d9-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b17d9-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b17d9-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b17d9-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b17d9-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b17d9-183">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="b17d9-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b17d9-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b17d9-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="b17d9-185">Enterprise E5 (con Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="b17d9-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b17d9-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b17d9-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="b17d9-187">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="b17d9-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="b17d9-188">Lo que debe saber antes de asignar licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="b17d9-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="b17d9-189">**Clientes de Enterprise E5:** Incluso si los usuarios tienen asignadas licencias Enterprise E5, se recomienda asignarles licencias de **créditos** de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="b17d9-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="b17d9-190">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="b17d9-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="b17d9-191">Para obtener instrucciones detalladas, consulte [Configurar planes de llamadas.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="b17d9-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="b17d9-192">Cómo asignar una licencia de Créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="b17d9-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="b17d9-193">Los pasos son los mismos que se indican para asignar una licencia de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="b17d9-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="b17d9-194">Vea [Asignar o quitar licencias de Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="b17d9-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="b17d9-195">Cómo asignar licencias de créditos de comunicaciones en masa</span><span class="sxs-lookup"><span data-stu-id="b17d9-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="b17d9-196">Vea el script de ejemplo para asignar licencias de **Audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="b17d9-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="b17d9-197">Actualífilo con la información para asignar licencias **de créditos** de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="b17d9-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b17d9-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b17d9-198">Related topics</span></span>
  
[<span data-ttu-id="b17d9-199">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="b17d9-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="b17d9-200">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="b17d9-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
