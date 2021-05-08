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
ms.openlocfilehash: 41f1788e4c562f3b4cc1f43d7875b64805b19ed8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237496"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="8329d-103">Asignar licencias de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8329d-103">Assign Skype for Business licenses</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="8329d-104">Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios para acceder a características como las Audioconferencias, el Sistema telefónico y los Planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8329d-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="8329d-105">También proporciona scripts para asignar varias licencias a la vez.</span><span class="sxs-lookup"><span data-stu-id="8329d-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8329d-106">Consulte Skype Empresarial licencias de complementos para obtener información sobre las  licencias que necesita comprar y cómo comprarlas ,según su plan de Microsoft 365 o Office 365, para que los usuarios obtengan audioconferencias, números gratuitos y la capacidad de llamar [a](skype-for-business-and-microsoft-teams-add-on-licensing.md) números de teléfono fuera de su empresa.</span><span class="sxs-lookup"><span data-stu-id="8329d-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="8329d-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="8329d-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="8329d-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="8329d-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="8329d-109">**¿Está usando conectividad RTC local para los usuarios híbridos?**</span><span class="sxs-lookup"><span data-stu-id="8329d-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="8329d-110">Si es así, solo tiene que asignar una **Sistema telefónico** licencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="8329d-111">NO debe **asignar** un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8329d-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="8329d-112">Latencia después de asignar **licencias:** debido a la latencia entre Microsoft 365 o Office 365 y Skype Empresarial Online, es posible que tarde hasta 24 horas en asignar un plan de llamadas a un usuario después de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="8329d-113">Si después de 24 horas el usuario no tiene asignado un plan de llamadas, póngase en contacto con el soporte técnico para productos [empresariales: Ayuda para administradores.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="8329d-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="8329d-114">**Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto.</span><span class="sxs-lookup"><span data-stu-id="8329d-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="8329d-115">Si necesita comprar más licencias del Plan de llamadas, elija **Comprar más.**</span><span class="sxs-lookup"><span data-stu-id="8329d-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="8329d-116">**Pasos siguientes:** Después de asignar licencias del Plan de llamadas a los usuarios, tendrá que obtener los números de teléfono de su organización y, a continuación, asignar esos números a las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="8329d-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="8329d-117">Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="8329d-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="8329d-118">Cómo asignar una licencia de Sistema telefónico y plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="8329d-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="8329d-119">Los pasos son los mismos que asignar una Microsoft 365 o Office 365 licencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="8329d-120">Vea [Asignar o quitar licencias para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="8329d-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="8329d-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="8329d-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="8329d-122">Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**.</span><span class="sxs-lookup"><span data-stu-id="8329d-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="8329d-123">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="8329d-123">Don't have the module installed?</span></span> <span data-ttu-id="8329d-124">Consulte [Microsoft Online Services Sign-In asistente para profesionales de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="8329d-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="8329d-125">Instale el **Módulo Microsoft Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8329d-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="8329d-126">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="8329d-126">Don't have the module installed?</span></span> <span data-ttu-id="8329d-127">Consulte [Administrar Azure AD con Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) instrucciones de descarga y sintaxis de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="8329d-127">See [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="8329d-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8329d-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="8329d-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="8329d-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="8329d-130">El nombre de las licencias o los nombres de producto del script se muestran en texto en cursiva (vea Sistema telefónico y Nombres de producto del plan de llamadas o SKU usados para **scripting,** después del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="8329d-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="8329d-131">Sistema telefónico y planes de llamadas o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="8329d-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="8329d-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="8329d-132">**Product name**</span></span>|<span data-ttu-id="8329d-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="8329d-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8329d-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="8329d-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="8329d-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="8329d-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="8329d-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8329d-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="8329d-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="8329d-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="8329d-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8329d-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="8329d-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="8329d-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="8329d-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8329d-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="8329d-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="8329d-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="8329d-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="8329d-142">Phone System</span></span>  <br/> |<span data-ttu-id="8329d-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="8329d-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="8329d-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="8329d-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="8329d-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="8329d-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="8329d-146">Plan de llamadas nacionales (3000 min ee. UU. / 1200 min planes de la UE)</span><span class="sxs-lookup"><span data-stu-id="8329d-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="8329d-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="8329d-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="8329d-148">Plan de llamadas nacionales (plan de llamadas de 120 minutos)</span><span class="sxs-lookup"><span data-stu-id="8329d-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="8329d-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="8329d-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="8329d-150">Plan de llamadas nacionales (plan de llamadas de 240 minutos)</span><span class="sxs-lookup"><span data-stu-id="8329d-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="8329d-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="8329d-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="8329d-152">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="8329d-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="8329d-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="8329d-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="8329d-154">Audioconferencia: Sugerencias y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="8329d-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="8329d-155">Lo que necesita saber antes de asignar licencias de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="8329d-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="8329d-156">Proveedor de servicios de **audioconferencia** de terceros: si alguien ya está configurado para usar un  proveedor de audioconferencia de terceros, al asignarle una licencia de audioconferencia, se cambiará para usar Microsoft como proveedor de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="8329d-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="8329d-157">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="8329d-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="8329d-158">Pasos siguientes: Después de asignar licencias de **conferencias** de audio, debe asignar un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="8329d-159">Consulte [Asignar a Microsoft como proveedor de audioconferencias].</span><span class="sxs-lookup"><span data-stu-id="8329d-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="8329d-160">Cómo asignar una licencia de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="8329d-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="8329d-161">Los pasos son los mismos que asignar una Microsoft 365 o Office 365 licencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="8329d-162">Vea [Asignar o quitar licencias para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="8329d-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="8329d-163">Cómo asignar licencias de audioconferencia en masa</span><span class="sxs-lookup"><span data-stu-id="8329d-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="8329d-164">Descargar e instalar [Microsoft Online Services Sign-In asistente para profesionales de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="8329d-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="8329d-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en [Administrar Azure AD mediante Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="8329d-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="8329d-167">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="8329d-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="8329d-168">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="8329d-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="8329d-169">Vea [Nombres de productos de audioconferencia o SKU](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) usados para scripting para todos los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="8329d-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="8329d-170">En este ejemplo se asigna una Enterprise de E3 junto con una licencia de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="8329d-171">Nombres de productos de audioconferencia o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="8329d-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="8329d-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="8329d-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="8329d-173">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="8329d-173">**Product name**</span></span>|<span data-ttu-id="8329d-174">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="8329d-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8329d-175">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="8329d-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="8329d-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="8329d-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="8329d-177">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8329d-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="8329d-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="8329d-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="8329d-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="8329d-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="8329d-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="8329d-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="8329d-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="8329d-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="8329d-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="8329d-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="8329d-183">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="8329d-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="8329d-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="8329d-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="8329d-185">Enterprise E5 (con audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="8329d-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="8329d-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="8329d-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="8329d-187">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="8329d-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="8329d-188">Lo que necesita saber antes de asignar licencias de créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="8329d-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="8329d-189">**Enterprise clientes de E5:** Incluso si los usuarios están asignados Enterprise licencias de E5, le recomendamos que les asigne licencias de créditos **de** comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="8329d-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="8329d-190">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="8329d-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="8329d-191">Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="8329d-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="8329d-192">Cómo asignar una licencia de créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="8329d-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="8329d-193">Los pasos son los mismos que asignar una Microsoft 365 o Office 365 licencia.</span><span class="sxs-lookup"><span data-stu-id="8329d-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="8329d-194">Vea [Asignar o quitar licencias para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="8329d-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="8329d-195">Cómo asignar licencias de créditos de comunicaciones en masa</span><span class="sxs-lookup"><span data-stu-id="8329d-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="8329d-196">Echa un vistazo al script de ejemplo para asignar **licencias de audioconferencia.**</span><span class="sxs-lookup"><span data-stu-id="8329d-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="8329d-197">Actualíctela con la información para asignar licencias **de créditos de** comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="8329d-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8329d-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8329d-198">Related topics</span></span>
  
[<span data-ttu-id="8329d-199">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="8329d-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="8329d-200">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="8329d-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
