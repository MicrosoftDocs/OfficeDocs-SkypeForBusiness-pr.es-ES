---
title: Asignar licencias de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Obtenga información sobre cómo asignar licencias de características como audioconferencia, sistema telefónico y planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 967b67c1d8bc92009e1319260373c9b8abc52b99
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826318"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="663c2-103">Asignar licencias de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="663c2-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="663c2-104">Puede asignar licencias a los usuarios para características como audioconferencia, sistema telefónico y planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="663c2-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="663c2-105">En este artículo se explica cómo agregar estas licencias a granel y para un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="663c2-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="663c2-106">Consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obtener información sobre las licencias que necesita comprar y sobre cómo obtenerlas, en función de su plan 365 de Office, para que los usuarios reciban conferencias de audio, números gratuitos y la posibilidad de llamar a números de teléfono fuera de su empresa.</span><span class="sxs-lookup"><span data-stu-id="663c2-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="663c2-107">Sistema telefónico y Planes de llamadas: sugerencias  y scripts para la asignación de licencias</span><span class="sxs-lookup"><span data-stu-id="663c2-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="663c2-108">Esto es lo que debe saber antes de asignar las conferencias de audio, el sistema telefónico y las licencias del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="663c2-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="663c2-109">**¿Está usando conectividad RTC local para los usuarios híbridos?**</span><span class="sxs-lookup"><span data-stu-id="663c2-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="663c2-110">Si es así, solo tiene que asignar una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="663c2-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="663c2-111">NO debe asignar un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="663c2-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="663c2-112">**Latencia después**de asignar licencias: debido a la latencia entre Office 365 y Microsoft Teams, un usuario puede tardar hasta 24 horas en asignarse a un plan de llamadas después de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="663c2-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="663c2-113">Si, después de 24 horas, el usuario no tiene asignado un plan de llamadas, [póngase en contacto con el soporte técnico para productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="663c2-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="663c2-114">**Mensajes de error**: Recibirá un mensaje de error si no ha adquirido el número de licencias correcto.</span><span class="sxs-lookup"><span data-stu-id="663c2-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="663c2-115">Si necesita comprar más licencias del plan de llamadas, elija **comprar más**.</span><span class="sxs-lookup"><span data-stu-id="663c2-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="663c2-116">**Pasos siguientes**: después de asignar las licencias del plan de llamadas a los usuarios, tendrá que obtener los números de teléfono de la organización y, a continuación, asignar esos números a las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="663c2-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="663c2-117">Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="663c2-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="663c2-118">Asignar un sistema telefónico y una licencia de plan de llamadas a un usuario</span><span class="sxs-lookup"><span data-stu-id="663c2-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="663c2-119">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="663c2-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="663c2-120">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="663c2-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="663c2-121">Asignar licencias de plan y sistema telefónico a granel</span><span class="sxs-lookup"><span data-stu-id="663c2-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="663c2-122">Instale el Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW).</span><span class="sxs-lookup"><span data-stu-id="663c2-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="663c2-123">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="663c2-123">Don't have the module installed?</span></span> <span data-ttu-id="663c2-124">Consulte [ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para descargarlo.</span><span class="sxs-lookup"><span data-stu-id="663c2-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="663c2-125">Instale el Módulo Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="663c2-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="663c2-126">¿No tiene instalado el módulo?</span><span class="sxs-lookup"><span data-stu-id="663c2-126">Don't have the module installed?</span></span> <span data-ttu-id="663c2-127">Consulte [administrar Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obtener instrucciones de descarga y la sintaxis del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="663c2-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="663c2-128">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="663c2-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="663c2-129">En este ejemplo se asigna una licencia Enterprise E3 junto con una licencia de Sistema telefónico y otra de Plan de llamadas nacionales.</span><span class="sxs-lookup"><span data-stu-id="663c2-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="663c2-130">El nombre de las licencias o nombres de los productos en la secuencia de comandos se muestra en cursiva (consulte el [sistema telefónico y los nombres de los productos o SKU usados para scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), después del ejemplo).</span><span class="sxs-lookup"><span data-stu-id="663c2-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="663c2-131">Sistema telefónico y planes de llamadas nombres de producto o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="663c2-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="663c2-132">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="663c2-132">Product name</span></span> | <span data-ttu-id="663c2-133">Nombre de la parte SKU</span><span class="sxs-lookup"><span data-stu-id="663c2-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="663c2-134">Enterprise E5 (con Sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="663c2-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="663c2-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="663c2-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="663c2-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="663c2-136">Enterprise E3</span></span> | <span data-ttu-id="663c2-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="663c2-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="663c2-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="663c2-138">Enterprise E1</span></span> | <span data-ttu-id="663c2-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="663c2-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="663c2-140">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="663c2-140">Phone System</span></span> | <span data-ttu-id="663c2-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="663c2-141">MCOEV</span></span> |
| <span data-ttu-id="663c2-142">Plan de llamadas nacionales & internacionales</span><span class="sxs-lookup"><span data-stu-id="663c2-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="663c2-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="663c2-143">MCOPSTN2</span></span> |
| <span data-ttu-id="663c2-144">Plan de llamadas nacionales (3000 minutos por usuario y mes para Estados Unidos/PR/CA, 1200 minutos por usuario y mes para países de la UE)</span><span class="sxs-lookup"><span data-stu-id="663c2-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="663c2-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="663c2-145">MCOPSTN1</span></span> |
| <span data-ttu-id="663c2-146">Plan de llamadas nacionales (120 minutos por usuario/mes por país)</span><span class="sxs-lookup"><span data-stu-id="663c2-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="663c2-147">*Nota: este plan no está disponible en nosotros*.</span><span class="sxs-lookup"><span data-stu-id="663c2-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="663c2-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="663c2-148">MCOPSTN5</span></span> |
| <span data-ttu-id="663c2-149">Plan de llamadas nacionales (240 minutos por usuario/mes por país)</span><span class="sxs-lookup"><span data-stu-id="663c2-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="663c2-150">*Nota: este plan no está disponible en nosotros*.</span><span class="sxs-lookup"><span data-stu-id="663c2-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="663c2-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="663c2-151">MCOPSTN6</span></span> |
| <span data-ttu-id="663c2-152">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="663c2-152">Communications Credits</span></span> | <span data-ttu-id="663c2-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="663c2-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="663c2-154">Audioconferencias: sugerencias y scripts para asignar licencias</span><span class="sxs-lookup"><span data-stu-id="663c2-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="663c2-155">Esto es lo que debe saber antes de asignar licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="663c2-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="663c2-156">**Proveedor de servicios de audioconferencia de terceros**: si alguien ya está configurado para usar un proveedor de servicios de audioconferencia de terceros, cuando le asigne una licencia de audioconferencia, se cambiará para usar Microsoft como el proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="663c2-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="663c2-157">Puede volver a cambiar al usuario al proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="663c2-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="663c2-158">**Pasos siguientes**: después de asignar las licencias de audioconferencia, debe asignar un proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="663c2-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="663c2-159">Consulte [asignar Microsoft como el proveedor de servicios de audioconferencia](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="663c2-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="663c2-160">Asignar una licencia de audioconferencia a un usuario</span><span class="sxs-lookup"><span data-stu-id="663c2-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="663c2-161">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="663c2-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="663c2-162">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="663c2-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="663c2-163">Asignar licencias de audioconferencia en masa</span><span class="sxs-lookup"><span data-stu-id="663c2-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="663c2-164">Descargue e instale [el ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="663c2-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="663c2-165">Descargue e instale el Módulo Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="663c2-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="663c2-166">Consulte [administrar Azure ad con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obtener instrucciones de descarga y la sintaxis del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="663c2-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="663c2-167">Después de instalar los módulos, use el símbolo del sistema de Windows PowerShell y la sintaxis siguiente para asignar las licencias a los usuarios:</span><span class="sxs-lookup"><span data-stu-id="663c2-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="663c2-168">El nombre de las licencias o nombres de los productos en la secuencia de comandos se muestra en cursiva.</span><span class="sxs-lookup"><span data-stu-id="663c2-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="663c2-169">Ver los nombres de los [productos de audioconferencia o las SKU usadas para los scripts](#audio-conferencing-product-names-or-skus-used-for-scripting) de todos los nombres de productos.</span><span class="sxs-lookup"><span data-stu-id="663c2-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="663c2-170">Este ejemplo asigna una licencia Enterprise E3 junto con una licencia de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="663c2-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="663c2-171">Nombres de los productos de audioconferencias o SKU usados para scripting</span><span class="sxs-lookup"><span data-stu-id="663c2-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="663c2-172">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="663c2-172">Product name</span></span> | <span data-ttu-id="663c2-173">Nombre de la parte SKU</span><span class="sxs-lookup"><span data-stu-id="663c2-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="663c2-174">Audioconferencia (suscripción)</span><span class="sxs-lookup"><span data-stu-id="663c2-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="663c2-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="663c2-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="663c2-176">Pago de audioconferencias por minuto (pagar a medida que hablas)</span><span class="sxs-lookup"><span data-stu-id="663c2-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="663c2-177">*Nota: es necesario configurar y habilitar el crédito*de las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="663c2-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="663c2-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="663c2-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="663c2-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="663c2-179">Enterprise E1</span></span> | <span data-ttu-id="663c2-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="663c2-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="663c2-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="663c2-181">Enterprise E3</span></span> | <span data-ttu-id="663c2-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="663c2-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="663c2-183">Enterprise E5 (sin Audioconferencia)</span><span class="sxs-lookup"><span data-stu-id="663c2-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="663c2-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="663c2-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="663c2-185">Enterprise E5 (con audioconferencias)</span><span class="sxs-lookup"><span data-stu-id="663c2-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="663c2-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="663c2-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="663c2-187">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="663c2-187">Communications Credits</span></span>

<span data-ttu-id="663c2-188">Esto es lo que debe saber antes de asignar licencias de créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="663c2-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="663c2-189">**Clientes de Enterprise E5**: incluso si los usuarios tienen asignadas licencias Enterprise E5, le recomendamos que les asigne licencias de créditos para comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="663c2-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="663c2-190">**Pasos siguientes**: Después de asignar estas licencias, tendrá que obtener los números de teléfono para la organización y asignarlos a los miembros de esta.</span><span class="sxs-lookup"><span data-stu-id="663c2-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="663c2-191">Para obtener instrucciones paso a paso, consulte [configurar planes de llamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="663c2-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="663c2-192">Asignar una licencia de créditos de comunicaciones a un usuario</span><span class="sxs-lookup"><span data-stu-id="663c2-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="663c2-193">Los pasos son los mismos que se siguen para asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="663c2-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="663c2-194">Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="663c2-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="663c2-195">Asignar créditos de comunicaciones licencias a granel</span><span class="sxs-lookup"><span data-stu-id="663c2-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="663c2-196">Eche un vistazo a la secuencia de comandos de ejemplo para asignar licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="663c2-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="663c2-197">Actualícelo con la información para asignar licencias de créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="663c2-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="663c2-198">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="663c2-198">Related topics</span></span>

[<span data-ttu-id="663c2-199">Configurar planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="663c2-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="663c2-200">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="663c2-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
