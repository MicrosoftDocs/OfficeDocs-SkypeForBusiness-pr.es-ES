---
title: Asignar Skype para licencias de negocio y Teams de Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Aprenda cómo asignar Skype para licencias profesionales para el sistema telefónico, conferencias de Audio, llamando a los planes y créditos de comunicaciones. "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="bf3c6-103">Asignar Skype para licencias de negocio y Teams de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf3c6-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="bf3c6-104">Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios características como conferencias de Audio, sistema de teléfono y llamar a los planes.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="bf3c6-105">También proporciona scripts para asignar varias licencias a la vez.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="bf3c6-106">**Importante**: Véase [Skype para negocios y equipos de Microsoft licencias adicionales](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información acerca de las licencias del cliente necesita comprar y **cómo comprar** , dependiendo de su plan de Office 365 - por lo que los usuarios obtienen las conferencias de Audio, números de teléfono gratuitos, y la posibilidad de llamar a números de teléfono fuera de su negocio.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="bf3c6-107">Sistema y planes de llamada de teléfono: consejos y secuencias de comandos para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="bf3c6-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="bf3c6-108">Lo que necesita saber antes de asignar las conferencias de Audio, sistema telefónico y Plan de llamadas licencias</span><span class="sxs-lookup"><span data-stu-id="bf3c6-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="bf3c6-109">**¿Está usando conectividad RTC local para los usuarios híbridos?**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="bf3c6-110">Si es así, sólo necesita asignar una licencia de **Sistema de teléfono** .</span><span class="sxs-lookup"><span data-stu-id="bf3c6-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="bf3c6-111">Debe **no** asignar un Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-111">You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="bf3c6-112">**Latencia después de asignar licencias**: debido a la latencia entre Office 365 y Skype para los negocios en línea, posiblemente puede tardar hasta 24 horas para que un usuario asignará un Plan de llamadas después de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="bf3c6-113">Si después de 24 horas el usuario no está asignado a un Plan de llamadas, por favor, [en soporte técnico para los productos business - ayuda de Admin](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="bf3c6-114">**Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="bf3c6-115">Si necesita adquirir más licencias de Plan de llamadas, elija **comprar más**.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="bf3c6-116">**Próximos pasos**: después de asignar licencias de Plan de llamadas a los usuarios, necesitará obtener sus números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="bf3c6-117">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="bf3c6-118">Cómo asignar una licencia de sistema telefónico y Plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="bf3c6-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="bf3c6-p106">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="bf3c6-121">Cómo asignar licencias de sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="bf3c6-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="bf3c6-122">Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="bf3c6-123">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="bf3c6-123">Don't have the module installed?</span></span> <span data-ttu-id="bf3c6-124">Consulte [Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="bf3c6-125">Instale el **Módulo Microsoft Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="bf3c6-126">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="bf3c6-126">Don't have the module installed?</span></span> <span data-ttu-id="bf3c6-127">Consulte [administrar AD Azure mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obtener instrucciones de descarga y sintaxis del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="bf3c6-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="bf3c6-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="bf3c6-129">Este ejemplo asigna una **licencia de Enterprise E3** junto con un **Sistema de teléfono** y una licencia de **Plan de llamadas nacionales** .</span><span class="sxs-lookup"><span data-stu-id="bf3c6-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="bf3c6-130">El nombre de las licencias o los nombres de producto en la secuencia de comandos se muestran en texto cursiva (Véase **sistema telefónico y Plan de llamadas nombres de producto o SKU utilizados para secuencias de comandos**, después del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="bf3c6-131">Nombres de productos de sistema de teléfono y llamar a planes o SKU utilizados para secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="bf3c6-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="bf3c6-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-132">**Product name**</span></span>|<span data-ttu-id="bf3c6-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf3c6-134">E5 Enterprise (con sistema de teléfono)</span><span class="sxs-lookup"><span data-stu-id="bf3c6-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="bf3c6-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="bf3c6-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="bf3c6-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="bf3c6-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="bf3c6-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="bf3c6-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="bf3c6-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="bf3c6-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="bf3c6-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="bf3c6-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="bf3c6-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bf3c6-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="bf3c6-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="bf3c6-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="bf3c6-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="bf3c6-142">Phone System</span></span>  <br/> |<span data-ttu-id="bf3c6-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="bf3c6-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="bf3c6-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="bf3c6-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="bf3c6-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="bf3c6-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="bf3c6-146">Plan de llamada nacional</span><span class="sxs-lookup"><span data-stu-id="bf3c6-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="bf3c6-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="bf3c6-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="bf3c6-148">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="bf3c6-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="bf3c6-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="bf3c6-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="bf3c6-150">Conferencias de audio: Los consejos y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="bf3c6-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="bf3c6-151">Lo que necesita saber antes de asignar licencias de conferencia de Audio</span><span class="sxs-lookup"><span data-stu-id="bf3c6-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="bf3c6-152">**Proveedor de conferencia de audio de terceros**: si ya alguien está configurado para utilizar un proveedor de conferencia de audio de terceros, cuando se asigna una licencia de **Conferencias de Audio** , se modificarán para utilizar Microsoft como el conferencias de audio proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="bf3c6-153">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-153">You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="bf3c6-154">Próximos pasos: después de asignar licencias de **Conferencias de Audio** , debe asignar un proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="bf3c6-155">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf3c6-155">Do one of the following:</span></span>
    
  - [<span data-ttu-id="bf3c6-156">Asignar a Microsoft como proveedor de servicios de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bf3c6-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="bf3c6-157">O bien, [asignar un tercero como el proveedor de conferencia de audio](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="bf3c6-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="bf3c6-158">Cómo asignar una licencia de conferencia de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="bf3c6-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="bf3c6-p111">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="bf3c6-161">Cómo asignar licencias de conferencia de Audio de forma masiva</span><span class="sxs-lookup"><span data-stu-id="bf3c6-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="bf3c6-162">Descargue e instale el [Asistente Microsoft Online Services inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="bf3c6-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="bf3c6-165">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="bf3c6-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="bf3c6-166">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-166">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="bf3c6-167">Ver [los nombres de productos de conferencia de Audio o SKU utilizados para secuencias de comandos](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para todos los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-167">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="bf3c6-168">Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="bf3c6-169">Nombres de productos de audio conferencia o SKU utilizados para secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="bf3c6-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="bf3c6-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="bf3c6-170"></span></span>

|<span data-ttu-id="bf3c6-171">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-171">**Product name**</span></span>|<span data-ttu-id="bf3c6-172">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="bf3c6-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf3c6-173">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="bf3c6-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="bf3c6-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="bf3c6-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="bf3c6-175">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bf3c6-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="bf3c6-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="bf3c6-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="bf3c6-177">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="bf3c6-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="bf3c6-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="bf3c6-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="bf3c6-179">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="bf3c6-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="bf3c6-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="bf3c6-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="bf3c6-181">E5 de la empresa (sin conferencias de Audio)</span><span class="sxs-lookup"><span data-stu-id="bf3c6-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="bf3c6-182">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="bf3c6-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="bf3c6-183">E5 Enterprise (con conferencias de Audio)</span><span class="sxs-lookup"><span data-stu-id="bf3c6-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="bf3c6-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="bf3c6-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="bf3c6-185">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="bf3c6-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="bf3c6-186">Lo que necesita saber antes de asignar licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="bf3c6-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="bf3c6-187">**Los clientes de empresa E5**: incluso si los usuarios se asignan licencias Enterprise E5, aun así es recomendable asignarlos licencias de **Créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="bf3c6-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="bf3c6-188">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="bf3c6-188">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="bf3c6-189">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-189">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="bf3c6-190">Cómo asignar una licencia de créditos de comunicaciones para un usuario</span><span class="sxs-lookup"><span data-stu-id="bf3c6-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="bf3c6-p115">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="bf3c6-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="bf3c6-193">Cómo asignar licencias de créditos de comunicaciones en masa</span><span class="sxs-lookup"><span data-stu-id="bf3c6-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="bf3c6-194">Observemos la secuencia de comandos para asignar licencias de **Conferencia de Audio** .</span><span class="sxs-lookup"><span data-stu-id="bf3c6-194">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="bf3c6-195">Para actualizarlo con la información de asignación de licencias de **Créditos de comunicaciones** .</span><span class="sxs-lookup"><span data-stu-id="bf3c6-195">Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bf3c6-196">See also</span><span class="sxs-lookup"><span data-stu-id="bf3c6-196">Related topics</span></span>

[<span data-ttu-id="bf3c6-197">Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf3c6-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="bf3c6-198">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="bf3c6-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="bf3c6-199">Agregar fondos y administrar Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="bf3c6-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  