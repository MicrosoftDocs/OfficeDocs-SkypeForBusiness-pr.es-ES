---
title: Asignar licencias de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Obtenga información sobre cómo asignar licencias para características como conferencias de Audio, el sistema de teléfono, y los planes de llamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198740"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="9c3cb-103">Asignación de licencias de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c3cb-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="9c3cb-104">Puede asignar licencias a los usuarios para determinadas características como conferencias de Audio, sistema telefónico y planes de llamada.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="9c3cb-105">En este artículo se explica cómo agregar estas licencias de forma masiva y para un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9c3cb-106">Vea [las licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obtener información acerca de qué planeación las licencias que necesitará comprar y cómo comprar, dependiendo de su Office 365, por lo que los usuarios obtener conferencias de Audio, los números gratuitos y la posibilidad de llamar a números de teléfono fuera de su negocio.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="9c3cb-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="9c3cb-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="9c3cb-108">Aquí es lo que necesita saber antes de asignar licencias de conferencias de Audio, sistema telefónico y planeación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="9c3cb-109">**¿Está usando conectividad RTC local para los usuarios híbridos?**</span><span class="sxs-lookup"><span data-stu-id="9c3cb-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="9c3cb-110">Si es así, sólo necesita asignar una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="9c3cb-111">NO debe asignar un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="9c3cb-112">**Latencia después de la asignación de licencias**: debido a la latencia entre Office 365 y Microsoft Teams, puede demorar hasta 24 horas para un usuario que se asignará a una llamada a Plan después de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="9c3cb-113">Si después de 24 horas el usuario no está asignado a una llamada a Plan, por favor, [póngase en contacto con soporte técnico para productos de negocio: Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="9c3cb-114">**Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="9c3cb-115">Si necesita comprar más licencias de planeación de la llamada, elija **comprar más**.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="9c3cb-116">**Pasos siguientes**: después de asignar licencias de planeación de la llamada a los usuarios, necesitará obtener sus números de teléfono para su organización y, a continuación, asignar los números a las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="9c3cb-117">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="9c3cb-118">Asigna una licencia de sistema telefónico y planeación de la llamada a un usuario</span><span class="sxs-lookup"><span data-stu-id="9c3cb-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="9c3cb-119">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="9c3cb-120">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="9c3cb-121">Asignación de licencias de sistema telefónico y llamar a planear de forma masiva</span><span class="sxs-lookup"><span data-stu-id="9c3cb-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="9c3cb-122">Instale el Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="9c3cb-123">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="9c3cb-123">Don't have the module installed?</span></span> <span data-ttu-id="9c3cb-124">Vea [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="9c3cb-125">Instale el Módulo Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="9c3cb-126">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="9c3cb-126">Don't have the module installed?</span></span> <span data-ttu-id="9c3cb-127">Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [administrar Windows Azure con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="9c3cb-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="9c3cb-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="9c3cb-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="9c3cb-129">En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de Sistema telefónico y otra de Plan de llamadas nacionales.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="9c3cb-130">El nombre de las licencias o nombres de producto en la secuencia de comandos se muestran en cursiva (vea [sistema telefónico y llamar a los planes de nombres de producto o SKU usadas para secuencias de comandos](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), después en el ejemplo).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="9c3cb-131">Sistema telefónico y llamar a los planes de nombres de producto o SKU usadas para scripting</span><span class="sxs-lookup"><span data-stu-id="9c3cb-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="9c3cb-132">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9c3cb-132">Product name</span></span> | <span data-ttu-id="9c3cb-133">Nombre de la parte SKU</span><span class="sxs-lookup"><span data-stu-id="9c3cb-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="9c3cb-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="9c3cb-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9c3cb-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="9c3cb-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9c3cb-136">Enterprise E3</span></span> | <span data-ttu-id="9c3cb-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9c3cb-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="9c3cb-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9c3cb-138">Enterprise E1</span></span> | <span data-ttu-id="9c3cb-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9c3cb-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="9c3cb-140">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="9c3cb-140">Phone System</span></span> | <span data-ttu-id="9c3cb-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="9c3cb-141">MCOEV</span></span> |
| <span data-ttu-id="9c3cb-142">Plan de llamadas internacionales nacionales &</span><span class="sxs-lookup"><span data-stu-id="9c3cb-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="9c3cb-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="9c3cb-143">MCOPSTN2</span></span> |
| <span data-ttu-id="9c3cb-144">Nacionales llamar a planear (3000 minutos por usuario y mes para Estados Unidos/PR/CA, 1200 minutos por usuario y mes para países de la UE)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="9c3cb-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="9c3cb-145">MCOPSTN1</span></span> |
| <span data-ttu-id="9c3cb-146">Nacionales llamar a planear (120 minutos por usuario y mes para cada país)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="9c3cb-147">*Nota: este plan no está disponible en Estados Unidos*.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="9c3cb-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="9c3cb-148">MCOPSTN5</span></span> |
| <span data-ttu-id="9c3cb-149">Nacionales llamar a planear (240 minutos por usuario y mes para cada país)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="9c3cb-150">*Nota: este plan no está disponible en Estados Unidos*.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="9c3cb-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="9c3cb-151">MCOPSTN6</span></span> |
| <span data-ttu-id="9c3cb-152">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9c3cb-152">Communications Credits</span></span> | <span data-ttu-id="9c3cb-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="9c3cb-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="9c3cb-154">Conferencias de audio: sugerencias y secuencias de comandos para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="9c3cb-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="9c3cb-155">Aquí es lo que necesita saber antes de la asignación de licencias de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="9c3cb-156">**Proveedor de conferencia de audio de terceros**: si ya alguien está configurado para usar un proveedor de conferencia de audio de terceros, cuando se asigna una licencia de conferencias de Audio, se cambiarán para usar Microsoft como el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="9c3cb-157">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="9c3cb-158">**Pasos siguientes**: después de asignar licencias de conferencias de Audio, es necesario asignarle un proveedor de conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="9c3cb-159">Vea [Asignar Microsoft como proveedor de conferencias de audio](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="9c3cb-160">Asignar una licencia de conferencias de Audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="9c3cb-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="9c3cb-161">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="9c3cb-162">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="9c3cb-163">Asignar licencias de conferencias de Audio de forma masiva</span><span class="sxs-lookup"><span data-stu-id="9c3cb-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="9c3cb-164">Descargue e instale [Microsoft Asistente en línea de servicios de inicio de sesión para RTW de profesionales de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="9c3cb-165">Descargue e instale el Módulo Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="9c3cb-166">Para obtener instrucciones de descarga y sintaxis de cmdlet, vea [administrar Windows Azure con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="9c3cb-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="9c3cb-167">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="9c3cb-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="9c3cb-168">El nombre de las licencias o nombres de producto en la secuencia de comandos se muestran en cursiva.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="9c3cb-169">Vea [los nombres de producto de conferencias de Audio o SKU usadas para secuencias de comandos](#audio-conferencing-product-names-or-skus-used-for-scripting) para todos los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="9c3cb-170">En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="9c3cb-171">Nombres de productos de conferencia de audio o SKU usadas para scripting</span><span class="sxs-lookup"><span data-stu-id="9c3cb-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="9c3cb-172">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9c3cb-172">Product name</span></span> | <span data-ttu-id="9c3cb-173">Nombre de la parte SKU</span><span class="sxs-lookup"><span data-stu-id="9c3cb-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="9c3cb-174">Conferencias de audio (suscripción)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="9c3cb-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="9c3cb-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="9c3cb-176">Audio conferencia de pago por minuto (retenidos)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="9c3cb-177">*Nota: requiere comunicaciones créditos necesario configurar y habilitar*.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="9c3cb-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="9c3cb-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="9c3cb-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9c3cb-179">Enterprise E1</span></span> | <span data-ttu-id="9c3cb-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9c3cb-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="9c3cb-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9c3cb-181">Enterprise E3</span></span> | <span data-ttu-id="9c3cb-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9c3cb-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="9c3cb-183">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="9c3cb-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="9c3cb-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="9c3cb-185">E5 Enterprise (con las conferencias de Audio)</span><span class="sxs-lookup"><span data-stu-id="9c3cb-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="9c3cb-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9c3cb-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="9c3cb-187">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9c3cb-187">Communications Credits</span></span>

<span data-ttu-id="9c3cb-188">Aquí es lo que necesita saber antes de la asignación de licencias de créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="9c3cb-189">**Los clientes de empresa E5**: incluso si los usuarios se asignan las licencias de empresa E5, aún se recomienda asígneles licencias de créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="9c3cb-190">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="9c3cb-191">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="9c3cb-192">Asigna una licencia de créditos de comunicaciones para un usuario</span><span class="sxs-lookup"><span data-stu-id="9c3cb-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="9c3cb-193">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="9c3cb-194">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="9c3cb-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="9c3cb-195">Asignar licencias de créditos de comunicaciones de forma masiva</span><span class="sxs-lookup"><span data-stu-id="9c3cb-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="9c3cb-196">Eche un vistazo en el script de ejemplo para la asignación de licencias de conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="9c3cb-197">Para actualizarlo con la información de asignación de licencias de créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="9c3cb-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9c3cb-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9c3cb-198">Related topics</span></span>

[<span data-ttu-id="9c3cb-199">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="9c3cb-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="9c3cb-200">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="9c3cb-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
