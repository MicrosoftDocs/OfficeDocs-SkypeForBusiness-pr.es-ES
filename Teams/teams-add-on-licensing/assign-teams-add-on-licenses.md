---
title: Asignar licencias de complementos de Teams a los usuarios
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Obtenga información sobre cómo asignar licencias de complementos de Teams a los usuarios para características como audioconferencias, sistema telefónico y planes de llamadas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116938"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="b626e-103">Asignar licencias de complementos de Teams a los usuarios</span><span class="sxs-lookup"><span data-stu-id="b626e-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="b626e-104">Las licencias de complementos son licencias para características específicas de Teams, como audioconferencias, sistemas telefónicos y planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b626e-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="b626e-105">En este artículo se describe cómo asignar licencias de complementos a usuarios individuales y a grandes conjuntos de usuarios en masa.</span><span class="sxs-lookup"><span data-stu-id="b626e-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="b626e-106">Consulte [Licencias de complementos de Teams](./microsoft-teams-add-on-licensing.md) para características de Teams que están disponibles con licencias de complementos.</span><span class="sxs-lookup"><span data-stu-id="b626e-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="b626e-107">También encontrará información sobre qué licencias necesita comprar y cómo comprarlas (según su plan), para que los usuarios puedan obtener características como Audioconferencia, números gratuitos y la capacidad de llamar a números de teléfono fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="b626e-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="b626e-108">Después de decidir qué características desea para los usuarios, asígneles las licencias.</span><span class="sxs-lookup"><span data-stu-id="b626e-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="b626e-109">Puede usar el Centro de administración de Microsoft 365 o PowerShell para asignar licencias a usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="b626e-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="b626e-110">Debe ser administrador global o administrador de administración de usuarios para administrar licencias.</span><span class="sxs-lookup"><span data-stu-id="b626e-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="b626e-111">Lo que necesita saber antes de asignar licencias de Sistema telefónico, Plan de llamadas y Créditos de comunicación</span><span class="sxs-lookup"><span data-stu-id="b626e-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="b626e-112">Antes de empezar, revise los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="b626e-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="b626e-113">Si usa la conectividad local de red telefónica conmutada (RTC) para los usuarios híbridos, solo tiene que asignar una licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="b626e-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="b626e-114">No asigne una licencia del plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b626e-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="b626e-115">Debido a la latencia entre Microsoft 365 y Microsoft Teams, puede tardar hasta 24 horas en asignar un plan de llamadas a un usuario después de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="b626e-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="b626e-116">Si al usuario no se le asigna un plan de llamadas después de 24 horas, póngase en contacto con el soporte técnico para productos [empresariales: ayuda para administradores.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="b626e-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b626e-117">Recibe un mensaje de error si no ha comprado el número correcto de licencias.</span><span class="sxs-lookup"><span data-stu-id="b626e-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="b626e-118">Si necesita comprar más licencias del Plan de llamadas, elija la opción para comprar más.</span><span class="sxs-lookup"><span data-stu-id="b626e-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="b626e-119">Incluso si a los usuarios se les asignan licencias [](../what-are-communications-credits.md) de Enterprise E5, aún debe asignarles licencias de créditos de comunicaciones si quieren realizar o recibir llamadas desde la RTC.</span><span class="sxs-lookup"><span data-stu-id="b626e-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="b626e-120">Después de asignar licencias de planes de llamadas o créditos de comunicación a los usuarios, tendrá que obtener números de teléfono para su organización y, a continuación, asignar esos números a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b626e-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="b626e-121">Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](../set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="b626e-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="b626e-122">Usar el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b626e-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="b626e-123">Use el Centro de administración de Microsoft 365 para asignar licencias a usuarios individuales o conjuntos pequeños de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="b626e-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="b626e-124">Asigne licencias en la página **Licencias** (para un máximo de 20 usuarios a la vez) o en la **página Usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="b626e-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="b626e-125">El método que elija depende de si desea administrar licencias de productos para usuarios específicos o administrar licencias de usuario para productos específicos.</span><span class="sxs-lookup"><span data-stu-id="b626e-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="b626e-126">Para obtener instrucciones paso a paso, vea [Asignar licencias a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="b626e-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="b626e-127">Si necesita asignar licencias para un gran número de usuarios, como cientos o miles de usuarios, use Powershell o licencias basadas en grupos en [Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="b626e-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="b626e-128">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b626e-128">Using PowerShell</span></span>

<span data-ttu-id="b626e-129">Use PowerShell para asignar licencias a usuarios en masa.</span><span class="sxs-lookup"><span data-stu-id="b626e-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="b626e-130">Para obtener más información, vea [Asignar licencias a cuentas de usuario con PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="b626e-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="b626e-131">Script de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b626e-131">Example script</span></span>

<span data-ttu-id="b626e-132">Este es un ejemplo de cómo usar un script para asignar licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b626e-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="b626e-133">Instale la versión de 64 bits del asistente Microsoft Online Services inicio de sesión para profesionales de [TI RTW.](/collaborate/connect-redirect?DownloadID=59185)</span><span class="sxs-lookup"><span data-stu-id="b626e-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="b626e-134">Instale el módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b626e-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="b626e-135">Abra un símbolo Windows PowerShell símbolo del sistema (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="b626e-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="b626e-136">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b626e-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="b626e-137">Si se le solicita que instale el proveedor de NuGet, escriba **Y** y, después, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="b626e-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="b626e-138">Si se le solicita que instale el módulo desde PSGallery, escriba **Y** y, después, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="b626e-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="b626e-139">En el Windows PowerShell de comandos, ejecute el siguiente script para asignar licencias a los usuarios, donde se encuentra el nombre de su organización y el identificador de la licencia que \<CompanyName:License> desea asignar.</span><span class="sxs-lookup"><span data-stu-id="b626e-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="b626e-140">Por ejemplo, litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="b626e-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="b626e-141">El identificador es diferente del nombre descriptivo de la licencia.</span><span class="sxs-lookup"><span data-stu-id="b626e-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="b626e-142">Por ejemplo, el identificador de audioconferencia es MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="b626e-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="b626e-143">Para obtener más información, vea [Nombres de producto e identificadores de SKU para licencias.](#product-names-and-sku-identifiers-for-licensing)</span><span class="sxs-lookup"><span data-stu-id="b626e-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="b626e-144">Por ejemplo, para asignar licencias de Microsoft 365 Enterprise 1 y audioconferencias, use la sintaxis siguiente en el script:</span><span class="sxs-lookup"><span data-stu-id="b626e-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="b626e-145">Para asignar una licencia de Microsoft Business Voice (sin plan de llamadas), use la sintaxis siguiente en el script:</span><span class="sxs-lookup"><span data-stu-id="b626e-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="b626e-146">Nombres de producto e identificadores de SKU para licencias</span><span class="sxs-lookup"><span data-stu-id="b626e-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="b626e-147">Esta es una lista parcial de nombres de producto y sus correspondientes nombres de partes de SKU que puede usar como referencia cuando use PowerShell para administrar licencias en Teams.</span><span class="sxs-lookup"><span data-stu-id="b626e-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="b626e-148">Para obtener más información, vea Ver licencias y servicios con [PowerShell,](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)Nombres de productos e identificadores de [plan](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)de servicio para licencias y Referencia [de SKU de educación.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="b626e-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="b626e-149">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b626e-149">Product name</span></span>| <span data-ttu-id="b626e-150">Nombre de la parte SKU</span><span class="sxs-lookup"><span data-stu-id="b626e-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="b626e-151">Microsoft Enterprise E5 (con sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="b626e-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="b626e-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b626e-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b626e-153">Microsoft Enterprise E5 (sin conferencias de audio)</span><span class="sxs-lookup"><span data-stu-id="b626e-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="b626e-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b626e-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="b626e-155">Microsoft Enterprise E5 (con audioconferencias)</span><span class="sxs-lookup"><span data-stu-id="b626e-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="b626e-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b626e-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b626e-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b626e-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="b626e-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b626e-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="b626e-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b626e-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="b626e-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b626e-160">STANDARDPACK</span></span> |
| <span data-ttu-id="b626e-161">Microsoft 365 Empresa Básico</span><span class="sxs-lookup"><span data-stu-id="b626e-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="b626e-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="b626e-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="b626e-163">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="b626e-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="b626e-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="b626e-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="b626e-165">Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="b626e-165">Microsoft 365 Business</span></span> | <span data-ttu-id="b626e-166">SPB</span><span class="sxs-lookup"><span data-stu-id="b626e-166">SPB</span></span>|
| <span data-ttu-id="b626e-167">Microsoft Business Voice (Canadá)</span><span class="sxs-lookup"><span data-stu-id="b626e-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="b626e-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="b626e-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="b626e-169">Microsoft Business Voice (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="b626e-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="b626e-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="b626e-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="b626e-171">Microsoft Business Voice (Estados Unidos)</span><span class="sxs-lookup"><span data-stu-id="b626e-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="b626e-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="b626e-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="b626e-173">Microsoft Business Voice (sin plan de llamadas)</span><span class="sxs-lookup"><span data-stu-id="b626e-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="b626e-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="b626e-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="b626e-175">Microsoft Business Voice (sin plan de llamadas) para Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="b626e-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="b626e-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="b626e-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="b626e-177">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b626e-177">Audio Conferencing</span></span> | <span data-ttu-id="b626e-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b626e-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="b626e-179">Pago por minuto de audioconferencia (pagar a medida que vaya)</span><span class="sxs-lookup"><span data-stu-id="b626e-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="b626e-180">*Requiere que los créditos de comunicaciones se configuren y habiliten.*</span><span class="sxs-lookup"><span data-stu-id="b626e-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="b626e-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="b626e-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="b626e-182">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b626e-182">Phone System</span></span> | <span data-ttu-id="b626e-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b626e-183">MCOEV</span></span> |
| <span data-ttu-id="b626e-184">Plan de llamadas nacionales e internacionales</span><span class="sxs-lookup"><span data-stu-id="b626e-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="b626e-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b626e-185">MCOPSTN2</span></span> |
| <span data-ttu-id="b626e-186">Plan de llamadas nacionales (3000 minutos por usuario/mes para EE.UU./PR/CA, 1.200 minutos por usuario/mes para países de la UE)</span><span class="sxs-lookup"><span data-stu-id="b626e-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="b626e-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b626e-187">MCOPSTN1</span></span> |
| <span data-ttu-id="b626e-188">Plan de llamadas nacionales (120 minutos por usuario/mes para cada país)</span><span class="sxs-lookup"><span data-stu-id="b626e-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b626e-189">*Este plan no está disponible en Estados Unidos.*</span><span class="sxs-lookup"><span data-stu-id="b626e-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="b626e-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="b626e-190">MCOPSTN5</span></span> |
| <span data-ttu-id="b626e-191">Plan de llamadas nacionales (240 minutos por usuario/mes para cada país)</span><span class="sxs-lookup"><span data-stu-id="b626e-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b626e-192">*Este plan no está disponible en Estados Unidos.*</span><span class="sxs-lookup"><span data-stu-id="b626e-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="b626e-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="b626e-193">MCOPSTN6</span></span> |
| <span data-ttu-id="b626e-194">Créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="b626e-194">Communications Credits</span></span> | <span data-ttu-id="b626e-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="b626e-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b626e-196">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b626e-196">Related topics</span></span>

- [<span data-ttu-id="b626e-197">Licencias complementarias de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b626e-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="b626e-198">Gestionar acceso de los usuarios a Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b626e-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="b626e-199">Ver licencias y servicios con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b626e-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="b626e-200">Nombres de productos e identificadores de planes de servicio para licencias</span><span class="sxs-lookup"><span data-stu-id="b626e-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="b626e-201">Referencia de SKU de educación</span><span class="sxs-lookup"><span data-stu-id="b626e-201">Education SKU reference</span></span>](../sku-reference-edu.md)