---
title: Asignar licencias de Skype for Business y Microsoft Teams
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: 'Obtenga información sobre cómo asignar licencias de Skype Empresarial para el Sistema telefónico, las Audioconferencias, los Planes de llamadas y los Créditos de Comunicaciones. '
ms.openlocfilehash: af2b7357c5dbe9e11b84ac87e0f72721d10a6a30
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856057"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="9366e-103">Asignar licencias de Skype for Business y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9366e-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="9366e-104">Este artículo ofrece sugerencias acerca de cómo asignar licencias a los usuarios para acceder a características como las Audioconferencias, el Sistema telefónico y los Planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9366e-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="9366e-105">También proporciona scripts para asignar varias licencias a la vez.</span><span class="sxs-lookup"><span data-stu-id="9366e-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9366e-106">Vea [Licencias de complementos para Skype for Business y Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obtener información sobre qué licencias necesitará comprar y **cómo comprarlas**, dependiendo de su plan de Office 365, para que los usuarios puedan realizar Audioconferencias, consigan números gratuitos y puedan llamar a números de teléfono fuera de su negocio.</span><span class="sxs-lookup"><span data-stu-id="9366e-106">IMPORTANT: See[Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get dial-in conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="9366e-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="9366e-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="9366e-108">Lo que necesita saber antes de asignar las licencias de Audioconferencia, Sistema telefónico y Plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="9366e-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="9366e-109">**¿Está usando conectividad RTC local para los usuarios híbridos?**</span><span class="sxs-lookup"><span data-stu-id="9366e-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="9366e-110">Si es así, solo necesita asignar una licencia de **Sistema telefónico**.</span><span class="sxs-lookup"><span data-stu-id="9366e-110">If so, you only need to assign a Skype for Business Cloud PBX license.</span></span> <span data-ttu-id="9366e-111">**NO** tiene que asignar un Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9366e-111">You should **NOT** assign a PSTN Calling plan.</span></span>

- <span data-ttu-id="9366e-112">**Latencia tras la asignación de licencias**: Debido a la latencia entre Office 365 y Skype Empresarial Online, es posible que se necesiten hasta 24 horas para que a un usuario se le asigne un Plan de llamadas después de que asignes una licencia.</span><span class="sxs-lookup"><span data-stu-id="9366e-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be enabled for PSTN Calling after you assign a license.</span></span> <span data-ttu-id="9366e-113">Si transcurridas 24 horas al usuario no se le ha asignado un Plan de llamadas, por favor [Póngase en contacto con el servicio de soporte técnico para los productos empresariales - Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="9366e-113">If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="9366e-114">**Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto.</span><span class="sxs-lookup"><span data-stu-id="9366e-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="9366e-115">Si necesita comprar más licencias de Plan de llamadas, seleccione **Comprar más**.</span><span class="sxs-lookup"><span data-stu-id="9366e-115">If you need to buy more licenses to enable this user for PSTN Calling, choose **Buy more**.</span></span>
    
- <span data-ttu-id="9366e-116">**Siguientes pasos**: después de asignar licencias de Plan de llamadas a sus usuarios, tendrá que obtener los números de teléfono para su organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="9366e-116">**Next steps**: After you assign PSTN Calling plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="9366e-117">Si desea consultar las instrucciones paso a paso, vea [Configurar Planes de llamadas](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9366e-117">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="9366e-118">Cómo asignar una licencia de Sistema telefónico y Plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="9366e-118">How to assign a Cloud PBX and PSTN Calling license to one user</span></span>

<span data-ttu-id="9366e-p106">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9366e-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="9366e-121">Cómo asignar licencias de Sistema telefónico y Plan de llamadas de forma masiva</span><span class="sxs-lookup"><span data-stu-id="9366e-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="9366e-122">Instale el **Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)**.</span><span class="sxs-lookup"><span data-stu-id="9366e-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="9366e-123">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="9366e-123">Don't have the module installed?</span></span> <span data-ttu-id="9366e-124">Consulte [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="9366e-124">See[Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="9366e-125">Instale el **Módulo Microsoft Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9366e-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="9366e-126">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="9366e-126">Don't have the module installed?</span></span> <span data-ttu-id="9366e-127">Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [Administrar Azure AD con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="9366e-127">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="9366e-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="9366e-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="9366e-129">En este ejemplo se asigna una **licencia Enterprise E3** junto con una licencia de **Sistema telefónico** y otra de **Plan de llamadas nacionales**.</span><span class="sxs-lookup"><span data-stu-id="9366e-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="9366e-130">El nombre de las licencias o de los productos en el script se muestran en letra cursiva (vea **Nombres de productos o SKU de Sistemas telefónicos y Planes de llamadas usados para scripting**, tras el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="9366e-130">The name of the licenses or product names in the script are listed in italics text (see **Cloud PBX and PSTN Calling product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="9366e-131">Nombres de productos o SKU de Sistemas telefónicos y Planes de llamadas usados para scripting</span><span class="sxs-lookup"><span data-stu-id="9366e-131">Cloud PBX and PSTN Calling product names or SKUs used for scripting</span></span>

|<span data-ttu-id="9366e-132">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="9366e-132">**Product name**</span></span>|<span data-ttu-id="9366e-133">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="9366e-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9366e-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="9366e-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="9366e-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9366e-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="9366e-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9366e-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="9366e-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9366e-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="9366e-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9366e-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="9366e-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9366e-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="9366e-140">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9366e-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="9366e-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="9366e-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="9366e-142">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="9366e-142">Phone System</span></span>  <br/> |<span data-ttu-id="9366e-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="9366e-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="9366e-144">Plan de llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="9366e-144">International and Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="9366e-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="9366e-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="9366e-146">Plan de llamada nacional</span><span class="sxs-lookup"><span data-stu-id="9366e-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="9366e-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="9366e-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="9366e-148">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9366e-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="9366e-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="9366e-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="9366e-150">Audioconferencia: sugerencias y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="9366e-150">PSTN conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="9366e-151">Lo que necesita saber antes de asignar licencias de Audioconferencias</span><span class="sxs-lookup"><span data-stu-id="9366e-151">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="9366e-152">**Proveedor de servicios de audioconferencia de terceros**: si hay alguien ya configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de **Audioconferencia**, cambiará para usar Microsoft como proveedor de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="9366e-152">**Third-party conferencing provider**: If someone is already set up to use a third-party dial-in conferencing provider, when you assign them a **Skype for Business PSTN Conferencing** license, they will be changed to use Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="9366e-153">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="9366e-153">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="9366e-154">Siguientes pasos: tras asignar licencias de **Audioconferencia**, es necesario asignar un proveedor de audioconferencias.
</span><span class="sxs-lookup"><span data-stu-id="9366e-154">Next steps: After you assign PSTN conferencing licenses, you need to assign a dial-in conferencing provider.</span></span> <span data-ttu-id="9366e-155">Consulte [Asignar a Microsoft como proveedor de audioconferencias].</span><span class="sxs-lookup"><span data-stu-id="9366e-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="9366e-156">Cómo asignar una licencia de Audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="9366e-156">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="9366e-p111">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9366e-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="9366e-159">Asignar licencias de Audioconferencia de forma masiva</span><span class="sxs-lookup"><span data-stu-id="9366e-159">How to assign PSTN conferencing licenses in bulk</span></span>

1. <span data-ttu-id="9366e-160">Descargue e instale el [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="9366e-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="9366e-p112">Descargue e instale el **Módulo Microsoft Azure Active Directory**. Vea las instrucciones de descarga y la sintaxis del cmdlet en[Administrar Azure AD mediante Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="9366e-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="9366e-163">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="9366e-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="9366e-164">El nombre de las licencias o nombres de los productos en el script se muestran en letra cursiva.</span><span class="sxs-lookup"><span data-stu-id="9366e-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="9366e-165">Consulte [Nombres de productos o SKU de Audioconferencias usados para scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para ver todos los nombres de productos.</span><span class="sxs-lookup"><span data-stu-id="9366e-165">See [Dial-in conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="9366e-166">En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="9366e-166">This example assigns an Enterprise E3 license along with a PSTN Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="9366e-167">Nombres de productos de Audioconferencia o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="9366e-167">Dial-in conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="9366e-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="9366e-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="9366e-169">**Nombre del producto**</span><span class="sxs-lookup"><span data-stu-id="9366e-169">**Product name**</span></span>|<span data-ttu-id="9366e-170">**Nombre de la parte SKU**</span><span class="sxs-lookup"><span data-stu-id="9366e-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9366e-171">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="9366e-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="9366e-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="9366e-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="9366e-173">Plan independiente 2 de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9366e-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="9366e-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="9366e-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="9366e-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9366e-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="9366e-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9366e-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="9366e-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9366e-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="9366e-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9366e-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="9366e-179">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="9366e-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="9366e-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="9366e-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="9366e-181">Enterprise E5 (con Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="9366e-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="9366e-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9366e-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="9366e-183">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9366e-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="9366e-184">Lo que necesita saber antes de asignar licencias de Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9366e-184">What you need to know before assigning PSTN Consumption licenses</span></span>

- <span data-ttu-id="9366e-185">**Clientes de Enterprise E5**: incluso aunque a sus usuarios se les hayan asignado licencias de Enterprise E5, se recomienda asignarles licencias de **Créditos de comunicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9366e-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Skype for Business PSTN Consumption** licenses.</span></span>
    
- <span data-ttu-id="9366e-186">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="9366e-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="9366e-187">Si desea consultar las instrucciones paso a paso, vea [Configurar Planes de llamadas](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9366e-187">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="9366e-188">Cómo asignar una licencia de Créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="9366e-188">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="9366e-p115">Los pasos son los mismos que se siguen para asignar una licencia de Office 365. Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9366e-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="9366e-191">Cómo asignar licencias de Créditos de comunicaciones de forma masiva</span><span class="sxs-lookup"><span data-stu-id="9366e-191">How to assign PSTN conferencing licenses in bulk</span></span>

<span data-ttu-id="9366e-192">Eche un vistazo al script de ejemplo para asignar licencias de **Audioconferencias**.</span><span class="sxs-lookup"><span data-stu-id="9366e-192">Take a look at the sample script for assigning PSTN Conferencing licenses.</span></span> <span data-ttu-id="9366e-193">Actualícelo con la información de asignación de licencias de **Créditos de comunicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9366e-193">Update it with the info for assigning PSTN Consumption licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9366e-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9366e-194">Related topics</span></span>
  
[<span data-ttu-id="9366e-195">Configurar Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="9366e-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="9366e-196">Agregar fondos y administrar Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9366e-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
