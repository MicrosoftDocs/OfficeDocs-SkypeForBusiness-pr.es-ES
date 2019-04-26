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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: e81c4c4d2fc11202ac114912ca309d93b00f2062
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226124"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="77e82-103">Asignar licencias de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="77e82-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="77e82-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="77e82-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77e82-106">Vea [Skype para Business licensing del complemento](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información acerca de qué licencias que necesitará comprar y **cómo comprar** ellos, dependiendo de su Office 365 planeación - por lo que los usuarios obtener conferencias de Audio, los números gratuitos y la posibilidad de llamar a números de teléfono externos su negocio.</span><span class="sxs-lookup"><span data-stu-id="77e82-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="77e82-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="77e82-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="77e82-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="77e82-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="77e82-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="77e82-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="77e82-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="77e82-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="77e82-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="77e82-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="77e82-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="77e82-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="77e82-118">Cómo asignar una licencia de sistema telefónico y planeación de la llamada a un usuario</span><span class="sxs-lookup"><span data-stu-id="77e82-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="77e82-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="77e82-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="77e82-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="77e82-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="77e82-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="77e82-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="77e82-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="77e82-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="77e82-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="77e82-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="77e82-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="77e82-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="77e82-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="77e82-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="77e82-130">El nombre de las licencias o nombres de producto en la secuencia de comandos se muestran en texto cursiva (vea **sistema telefónico y llamar a planear los nombres de productos o SKU usadas para secuencias de comandos**, después en el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="77e82-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="77e82-131">Sistema telefónico y llamar a los planes de nombres de producto o SKU usadas para scripting</span><span class="sxs-lookup"><span data-stu-id="77e82-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="77e82-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="77e82-132">**Product name**</span></span>|<span data-ttu-id="77e82-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="77e82-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77e82-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="77e82-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="77e82-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="77e82-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="77e82-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="77e82-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="77e82-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="77e82-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="77e82-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="77e82-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="77e82-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="77e82-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="77e82-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77e82-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="77e82-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="77e82-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="77e82-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="77e82-142">Phone System</span></span>  <br/> |<span data-ttu-id="77e82-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="77e82-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="77e82-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="77e82-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="77e82-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="77e82-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="77e82-146">Plan de llamada nacional</span><span class="sxs-lookup"><span data-stu-id="77e82-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="77e82-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="77e82-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="77e82-148">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="77e82-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="77e82-149">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="77e82-149">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="77e82-150">Conferencias de audio: Sugerencias y secuencias de comandos para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="77e82-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="77e82-151">¿Qué necesita saber antes de la asignación de licencias de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="77e82-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="77e82-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span><span class="sxs-lookup"><span data-stu-id="77e82-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="77e82-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span><span class="sxs-lookup"><span data-stu-id="77e82-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="77e82-156">Cómo asignar una licencia de conferencias de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="77e82-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="77e82-157">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="77e82-157">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="77e82-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="77e82-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="77e82-159">Cómo asignar licencias de conferencias de Audio de forma masiva</span><span class="sxs-lookup"><span data-stu-id="77e82-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="77e82-160">Descargue e instale [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="77e82-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="77e82-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="77e82-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="77e82-163">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="77e82-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="77e82-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span><span class="sxs-lookup"><span data-stu-id="77e82-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="77e82-166">En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="77e82-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="77e82-167">Nombres de productos de conferencia de audio o SKU usadas para scripting</span><span class="sxs-lookup"><span data-stu-id="77e82-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="77e82-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="77e82-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="77e82-169">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="77e82-169">**Product name**</span></span>|<span data-ttu-id="77e82-170">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="77e82-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77e82-171">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="77e82-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="77e82-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="77e82-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="77e82-173">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="77e82-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="77e82-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="77e82-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="77e82-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="77e82-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="77e82-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="77e82-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="77e82-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="77e82-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="77e82-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="77e82-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="77e82-179">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="77e82-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="77e82-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="77e82-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="77e82-181">E5 Enterprise (con las conferencias de Audio)</span><span class="sxs-lookup"><span data-stu-id="77e82-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="77e82-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="77e82-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="77e82-183">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="77e82-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="77e82-184">¿Qué necesita saber antes de la asignación de licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="77e82-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="77e82-185">**Los clientes de empresa E5**: incluso si los usuarios se asignan las licencias de empresa E5, aún se recomienda asígneles licencias de **Créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="77e82-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="77e82-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="77e82-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="77e82-188">Cómo asignar una licencia de créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="77e82-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="77e82-189">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="77e82-189">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="77e82-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="77e82-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="77e82-191">Cómo asignar licencias de créditos de comunicaciones de forma masiva</span><span class="sxs-lookup"><span data-stu-id="77e82-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="77e82-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span><span class="sxs-lookup"><span data-stu-id="77e82-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77e82-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="77e82-194">Related topics</span></span>
  
[<span data-ttu-id="77e82-195">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="77e82-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="77e82-196">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="77e82-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
