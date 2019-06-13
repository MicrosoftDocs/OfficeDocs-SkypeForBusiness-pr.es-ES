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
f1keywords: None
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: 997cffce5b98ed992371a0f43e701b2efc1ae128
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "34768779"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="7aa77-103">Asignar licencias de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="7aa77-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="7aa77-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="7aa77-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7aa77-106">Consulte [licencias complementarias de Skype empresarial](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información sobre las licencias que necesita comprar y **Cómo** realizarlas, en función de su plan de 365 de Office, para que los usuarios reciban conferencias de audio, números gratuitos y la posibilidad de llamar a números de teléfono fuera tu empresa.</span><span class="sxs-lookup"><span data-stu-id="7aa77-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="7aa77-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="7aa77-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="7aa77-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="7aa77-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="7aa77-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="7aa77-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="7aa77-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="7aa77-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="7aa77-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="7aa77-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="7aa77-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="7aa77-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="7aa77-118">Cómo asignar un sistema telefónico y una licencia de plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="7aa77-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="7aa77-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="7aa77-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="7aa77-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="7aa77-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="7aa77-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="7aa77-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="7aa77-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="7aa77-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="7aa77-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="7aa77-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="7aa77-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="7aa77-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="7aa77-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="7aa77-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="7aa77-130">El nombre de las licencias o nombres de productos en la secuencia de comandos se muestra en cursiva (consulte **nombres de producto del plan de llamadas y sistemas telefónicos o SKU usados para scripting**, después del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="7aa77-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="7aa77-131">Sistema telefónico y planes de llamadas nombres de producto o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="7aa77-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="7aa77-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="7aa77-132">**Product name**</span></span>|<span data-ttu-id="7aa77-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="7aa77-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7aa77-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="7aa77-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="7aa77-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="7aa77-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="7aa77-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="7aa77-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="7aa77-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="7aa77-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="7aa77-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="7aa77-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="7aa77-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="7aa77-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="7aa77-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7aa77-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="7aa77-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="7aa77-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="7aa77-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="7aa77-142">Phone System</span></span>  <br/> |<span data-ttu-id="7aa77-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="7aa77-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="7aa77-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="7aa77-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="7aa77-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="7aa77-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="7aa77-146">Plan de llamadas nacionales (3000 min Estados Unidos/1200 mín. planes de la UE)</span><span class="sxs-lookup"><span data-stu-id="7aa77-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="7aa77-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="7aa77-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="7aa77-148">Plan de llamadas nacionales (120)</span><span class="sxs-lookup"><span data-stu-id="7aa77-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="7aa77-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="7aa77-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="7aa77-150">Plan de llamadas nacionales (240)</span><span class="sxs-lookup"><span data-stu-id="7aa77-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="7aa77-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="7aa77-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="7aa77-152">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="7aa77-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="7aa77-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="7aa77-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="7aa77-154">Audioconferencias: sugerencias y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="7aa77-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="7aa77-155">Lo que debe saber antes de asignar licencias de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="7aa77-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="7aa77-156">**Proveedor de servicios de audioconferencia de terceros**: si alguien ya está configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de **Conferencia** de audio, se cambiará para usar Microsoft como Conferencia de audio. proveedor.</span><span class="sxs-lookup"><span data-stu-id="7aa77-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="7aa77-157">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="7aa77-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="7aa77-158">Pasos siguientes: después de asignar las licencias de **audioconferencia** , debe asignar un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="7aa77-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="7aa77-159">Consulte [Asignar a Microsoft como proveedor de audioconferencias].</span><span class="sxs-lookup"><span data-stu-id="7aa77-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="7aa77-160">Cómo asignar una licencia de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="7aa77-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="7aa77-161">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7aa77-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="7aa77-162">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="7aa77-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="7aa77-163">Cómo asignar licencias de audioconferencia en masa</span><span class="sxs-lookup"><span data-stu-id="7aa77-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="7aa77-164">Descargue e instale [el ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="7aa77-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="7aa77-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="7aa77-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="7aa77-167">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="7aa77-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="7aa77-168">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="7aa77-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="7aa77-169">Ver los nombres de los [productos de audioconferencia o las SKU usadas para](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) los scripts de todos los nombres de productos.</span><span class="sxs-lookup"><span data-stu-id="7aa77-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="7aa77-170">Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="7aa77-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="7aa77-171">Nombres de los productos de audioconferencias o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="7aa77-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="7aa77-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="7aa77-172"></span></span>

|<span data-ttu-id="7aa77-173">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="7aa77-173">**Product name**</span></span>|<span data-ttu-id="7aa77-174">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="7aa77-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7aa77-175">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="7aa77-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="7aa77-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="7aa77-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="7aa77-177">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7aa77-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="7aa77-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="7aa77-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="7aa77-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="7aa77-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="7aa77-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="7aa77-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="7aa77-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="7aa77-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="7aa77-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="7aa77-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="7aa77-183">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="7aa77-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="7aa77-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="7aa77-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="7aa77-185">Enterprise E5 (con audioconferencias)</span><span class="sxs-lookup"><span data-stu-id="7aa77-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="7aa77-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="7aa77-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="7aa77-187">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="7aa77-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="7aa77-188">Lo que debe saber antes de asignar licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="7aa77-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="7aa77-189">**Clientes de Enterprise E5**: incluso si los usuarios tienen asignadas licencias Enterprise E5, le recomendamos que les asigne licencias de **créditos para comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="7aa77-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="7aa77-190">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="7aa77-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="7aa77-191">Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="7aa77-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="7aa77-192">Cómo asignar una licencia de créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="7aa77-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="7aa77-193">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="7aa77-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="7aa77-194">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="7aa77-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="7aa77-195">Cómo asignar las licencias de crédito de comunicaciones a granel</span><span class="sxs-lookup"><span data-stu-id="7aa77-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="7aa77-196">Eche un vistazo a la secuencia de comandos de ejemplo para asignar licencias de **audioconferencia** .</span><span class="sxs-lookup"><span data-stu-id="7aa77-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="7aa77-197">Actualícelo con la información para asignar licencias de **créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="7aa77-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7aa77-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7aa77-198">Related topics</span></span>
  
[<span data-ttu-id="7aa77-199">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="7aa77-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="7aa77-200">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="7aa77-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
