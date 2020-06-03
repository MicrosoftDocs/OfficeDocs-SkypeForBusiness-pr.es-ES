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
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="09337-103">Asignar licencias de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="09337-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="09337-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="09337-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09337-106">Consulte [licencias complementarias de Skype empresarial](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información sobre las licencias que necesita comprar y **Cómo** realizarlas, en función de su plan de Microsoft 365 u Office 365, de modo que los usuarios reciban conferencias de audio, números gratuitos y la posibilidad de llamar a números de teléfono fuera de su empresa.</span><span class="sxs-lookup"><span data-stu-id="09337-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="09337-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="09337-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="09337-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="09337-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="09337-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="09337-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="09337-p103">**Latencia después de asignar licencias**: debido a la latencia entre Microsoft 365 u Office 365 y Skype empresarial online, puede que un usuario tarde hasta 24 horas en asignar un plan de llamadas después de asignar una licencia. Si, después de 24 horas, el usuario no tiene asignado un plan de llamadas, [póngase en contacto con el soporte técnico para productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="09337-p103">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="09337-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="09337-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="09337-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="09337-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="09337-118">Cómo asignar un sistema telefónico y una licencia de plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="09337-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="09337-119">Los pasos son los mismos que asignar una licencia de Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="09337-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="09337-120">Consulte [asignar o quitar licencias de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="09337-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="09337-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="09337-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="09337-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="09337-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="09337-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="09337-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="09337-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="09337-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="09337-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="09337-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="09337-130">El nombre de las licencias o nombres de productos en la secuencia de comandos se muestra en cursiva (consulte **nombres de producto del plan de llamadas y sistemas telefónicos o SKU usados para scripting**, después del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="09337-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="09337-131">Sistema telefónico y planes de llamadas nombres de producto o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="09337-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="09337-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="09337-132">**Product name**</span></span>|<span data-ttu-id="09337-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="09337-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09337-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="09337-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="09337-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="09337-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="09337-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="09337-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="09337-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="09337-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="09337-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="09337-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="09337-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="09337-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="09337-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="09337-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="09337-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="09337-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="09337-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="09337-142">Phone System</span></span>  <br/> |<span data-ttu-id="09337-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="09337-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="09337-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="09337-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="09337-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="09337-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="09337-146">Plan de llamadas nacionales (3000 min Estados Unidos/1200 mín. planes de la UE)</span><span class="sxs-lookup"><span data-stu-id="09337-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="09337-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="09337-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="09337-148">Plan de llamadas nacionales (120)</span><span class="sxs-lookup"><span data-stu-id="09337-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="09337-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="09337-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="09337-150">Plan de llamadas nacionales (240)</span><span class="sxs-lookup"><span data-stu-id="09337-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="09337-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="09337-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="09337-152">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="09337-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="09337-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="09337-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="09337-154">Audioconferencias: sugerencias y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="09337-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="09337-155">Lo que debe saber antes de asignar licencias de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="09337-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="09337-156">**Proveedor de servicios de audioconferencia de terceros**: si alguien ya está configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de **audioconferencia** , se cambiará para usar Microsoft como el proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="09337-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="09337-157">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="09337-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="09337-158">Pasos siguientes: después de asignar las licencias de **audioconferencia** , debe asignar un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="09337-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="09337-159">Consulte [Asignar a Microsoft como proveedor de audioconferencias].</span><span class="sxs-lookup"><span data-stu-id="09337-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="09337-160">Cómo asignar una licencia de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="09337-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="09337-161">Los pasos son los mismos que asignar una licencia de Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="09337-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="09337-162">Consulte [asignar o quitar licencias de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="09337-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="09337-163">Cómo asignar licencias de audioconferencia en masa</span><span class="sxs-lookup"><span data-stu-id="09337-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="09337-164">Descargue e instale [el ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="09337-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="09337-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="09337-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="09337-167">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="09337-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="09337-168">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="09337-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="09337-169">Ver los nombres de los [productos de audioconferencia o las SKU usadas para los scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) de todos los nombres de productos.</span><span class="sxs-lookup"><span data-stu-id="09337-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="09337-170">Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="09337-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="09337-171">Nombres de los productos de audioconferencias o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="09337-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="09337-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="09337-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="09337-173">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="09337-173">**Product name**</span></span>|<span data-ttu-id="09337-174">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="09337-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09337-175">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="09337-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="09337-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="09337-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="09337-177">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="09337-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="09337-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="09337-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="09337-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="09337-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="09337-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="09337-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="09337-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="09337-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="09337-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="09337-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="09337-183">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="09337-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="09337-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="09337-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="09337-185">Enterprise E5 (con audioconferencias)</span><span class="sxs-lookup"><span data-stu-id="09337-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="09337-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="09337-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="09337-187">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="09337-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="09337-188">Lo que debe saber antes de asignar licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="09337-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="09337-189">**Clientes de Enterprise E5**: incluso si los usuarios tienen asignadas licencias Enterprise E5, le recomendamos que les asigne licencias de **créditos para comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="09337-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="09337-190">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="09337-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="09337-191">Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="09337-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="09337-192">Cómo asignar una licencia de créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="09337-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="09337-193">Los pasos son los mismos que asignar una licencia de Microsoft 365 o de Office 365.</span><span class="sxs-lookup"><span data-stu-id="09337-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="09337-194">Consulte [asignar o quitar licencias de Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="09337-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="09337-195">Cómo asignar las licencias de crédito de comunicaciones a granel</span><span class="sxs-lookup"><span data-stu-id="09337-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="09337-196">Eche un vistazo a la secuencia de comandos de ejemplo para asignar licencias de **audioconferencia** .</span><span class="sxs-lookup"><span data-stu-id="09337-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="09337-197">Actualícelo con la información para asignar licencias de **créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="09337-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09337-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="09337-198">Related topics</span></span>
  
[<span data-ttu-id="09337-199">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="09337-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="09337-200">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="09337-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
