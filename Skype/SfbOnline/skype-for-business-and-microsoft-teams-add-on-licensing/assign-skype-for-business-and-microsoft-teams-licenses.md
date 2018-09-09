---
title: Asignar licencias de Skype Empresarial y Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: 1131d8daf4b865d648f51b011fc8819dee55f6b9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883506"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="c0af4-103">Asignar licencias de Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0af4-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="c0af4-104">Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios para acceder a características como las Audioconferencias, el Sistema telefónico y los Planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c0af4-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="c0af4-105">También proporciona scripts para asignar varias licencias a la vez.</span><span class="sxs-lookup"><span data-stu-id="c0af4-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0af4-106">Vea [las licencias de Skype para complemento de negocio y equipos de Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información acerca de qué licencias que necesitará comprar y **cómo comprar** ellos, dependiendo de su Office 365 planeación - por lo que los usuarios obtener conferencias de Audio, los números gratuitos y la posibilidad de llamar a números de teléfono fuera de su negocio.</span><span class="sxs-lookup"><span data-stu-id="c0af4-106">See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c0af4-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="c0af4-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="c0af4-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="c0af4-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="c0af4-109">**¿Está usando conectividad RTC local para los usuarios híbridos?**</span><span class="sxs-lookup"><span data-stu-id="c0af4-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="c0af4-110">Si es así, sólo necesita asignar una licencia de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="c0af4-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="c0af4-111">Debe **no** asignar un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="c0af4-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="c0af4-112">**Latencia después de la asignación de licencias**: debido a la latencia entre Office 365 y Skype para profesionales en línea, posiblemente puede demorar hasta 24 horas para un usuario que se asignará a una llamada a Plan después de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="c0af4-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="c0af4-113">Si después de 24 horas el usuario no está asignado a un Plan de llamada, [atención de contacto para los productos de negocio - ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="c0af4-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="c0af4-114">**Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto.</span><span class="sxs-lookup"><span data-stu-id="c0af4-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="c0af4-115">Si necesita comprar más licencias de planeación de la llamada, elija **comprar más**.</span><span class="sxs-lookup"><span data-stu-id="c0af4-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="c0af4-116">**Pasos siguientes**: después de asignar licencias de planeación de la llamada a los usuarios, necesitará obtener sus números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="c0af4-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c0af4-117">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="c0af4-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="c0af4-118">Cómo asignar una licencia de sistema telefónico y planeación de la llamada a un usuario</span><span class="sxs-lookup"><span data-stu-id="c0af4-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="c0af4-p106">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c0af4-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="c0af4-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="c0af4-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="c0af4-122">Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**.</span><span class="sxs-lookup"><span data-stu-id="c0af4-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="c0af4-123">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="c0af4-123">Don't have the module installed?</span></span> <span data-ttu-id="c0af4-124">Vea [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="c0af4-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="c0af4-125">Instale el **Módulo Microsoft Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c0af4-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="c0af4-126">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="c0af4-126">Don't have the module installed?</span></span> <span data-ttu-id="c0af4-127">Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [administrar Windows Azure con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="c0af4-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="c0af4-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="c0af4-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="c0af4-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="c0af4-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="c0af4-130">El nombre de las licencias o nombres de producto en la secuencia de comandos se muestran en texto cursiva (vea **sistema telefónico y llamar a planear los nombres de productos o SKU usadas para secuencias de comandos**, después en el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="c0af4-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c0af4-131">Sistema telefónico y llamar a los planes de nombres de producto o SKU usadas para scripting</span><span class="sxs-lookup"><span data-stu-id="c0af4-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="c0af4-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="c0af4-132">**Product name**</span></span>|<span data-ttu-id="c0af4-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="c0af4-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0af4-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="c0af4-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="c0af4-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c0af4-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="c0af4-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c0af4-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c0af4-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c0af4-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c0af4-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c0af4-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c0af4-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c0af4-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c0af4-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c0af4-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c0af4-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c0af4-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c0af4-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="c0af4-142">Phone System</span></span>  <br/> |<span data-ttu-id="c0af4-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="c0af4-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="c0af4-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="c0af4-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="c0af4-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="c0af4-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="c0af4-146">Plan de llamada nacional</span><span class="sxs-lookup"><span data-stu-id="c0af4-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="c0af4-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="c0af4-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="c0af4-148">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="c0af4-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="c0af4-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="c0af4-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c0af4-150">Conferencias de audio: Sugerencias y secuencias de comandos para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="c0af4-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="c0af4-151">¿Qué necesita saber antes de la asignación de licencias de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="c0af4-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="c0af4-152">**Proveedor de conferencia de audio de terceros**: si ya alguien está configurado para usar un proveedor de conferencia de audio de terceros, cuando se asigna una licencia de **Conferencias de Audio** , se cambiarán para usar Microsoft como las conferencias de audio proveedor.</span><span class="sxs-lookup"><span data-stu-id="c0af4-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c0af4-153">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="c0af4-153">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="c0af4-154">Pasos siguientes: después de asignar licencias de **Conferencias de Audio** , es necesario asignarle un proveedor de conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="c0af4-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="c0af4-155">Consulte [Asignar a Microsoft como proveedor de audioconferencias].</span><span class="sxs-lookup"><span data-stu-id="c0af4-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="c0af4-156">Cómo asignar una licencia de conferencias de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="c0af4-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="c0af4-p111">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c0af4-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="c0af4-159">Cómo asignar licencias de conferencias de Audio de forma masiva</span><span class="sxs-lookup"><span data-stu-id="c0af4-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="c0af4-160">Descargue e instale [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="c0af4-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="c0af4-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="c0af4-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="c0af4-163">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="c0af4-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="c0af4-164">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="c0af4-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="c0af4-165">Vea [los nombres de producto de conferencias de Audio o SKU usadas para secuencias de comandos](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para todos los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="c0af4-165">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="c0af4-166">En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="c0af4-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c0af4-167">Nombres de productos de conferencia de audio o SKU usadas para scripting</span><span class="sxs-lookup"><span data-stu-id="c0af4-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="c0af4-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="c0af4-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="c0af4-169">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="c0af4-169">**Product name**</span></span>|<span data-ttu-id="c0af4-170">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="c0af4-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0af4-171">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="c0af4-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="c0af4-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="c0af4-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="c0af4-173">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="c0af4-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c0af4-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c0af4-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c0af4-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c0af4-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c0af4-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c0af4-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c0af4-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c0af4-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c0af4-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c0af4-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c0af4-179">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="c0af4-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c0af4-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="c0af4-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="c0af4-181">E5 Enterprise (con las conferencias de Audio)</span><span class="sxs-lookup"><span data-stu-id="c0af4-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c0af4-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c0af4-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="c0af4-183">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="c0af4-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="c0af4-184">¿Qué necesita saber antes de la asignación de licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="c0af4-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="c0af4-185">**Los clientes de empresa E5**: incluso si los usuarios se asignan las licencias de empresa E5, aún se recomienda asígneles licencias de **Créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="c0af4-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="c0af4-186">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="c0af4-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c0af4-187">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="c0af4-187">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="c0af4-188">Cómo asignar una licencia de créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="c0af4-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="c0af4-p115">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c0af4-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="c0af4-191">Cómo asignar licencias de créditos de comunicaciones de forma masiva</span><span class="sxs-lookup"><span data-stu-id="c0af4-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="c0af4-192">Eche un vistazo en el script de ejemplo para la asignación de licencias de **Conferencias de Audio** .</span><span class="sxs-lookup"><span data-stu-id="c0af4-192">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="c0af4-193">Para actualizarlo con la información de asignación de licencias de **Créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="c0af4-193">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0af4-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c0af4-194">Related topics</span></span>
  
[<span data-ttu-id="c0af4-195">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="c0af4-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="c0af4-196">Agregar fondos y administrar Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="c0af4-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
