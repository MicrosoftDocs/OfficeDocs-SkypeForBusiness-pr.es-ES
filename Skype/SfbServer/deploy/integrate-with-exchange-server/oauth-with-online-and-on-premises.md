---
title: Integración entre Skype empresarial online y Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuración de la autenticación de OAuth entre Exchange local y Skype empresarial online habilita las características de integración de Skype empresarial e Exchange descritas en compatibilidad de características.
ms.openlocfilehash: 28cf0471b13fc57c6b72c6a6216b3dd3b65726d8
ms.sourcegitcommit: f735495849f02e0ea23c7d6f250e9c0656daeea1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "34933844"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="51eb6-103">Configurar la integración y OAuth entre Skype empresarial online y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="51eb6-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="51eb6-104">La configuración de la integración entre Exchange Server y Skype empresarial online habilita las características de integración de Skype empresarial e Exchange descritas en [compatibilidad de características](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="51eb6-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="51eb6-105">Este tema se aplica a la integración con Exchange Server 2013 a 2019.</span><span class="sxs-lookup"><span data-stu-id="51eb6-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51eb6-106">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="51eb6-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51eb6-107">Tiempo estimado para finalizar esta tarea: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="51eb6-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="51eb6-108">Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos.</span><span class="sxs-lookup"><span data-stu-id="51eb6-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="51eb6-109">Para ver qué permisos necesita, consulte el tema [Exchange and Shell Infrastructure](https://go.microsoft.com/fwlink/p/?LinkId=746511) Permissions.</span><span class="sxs-lookup"><span data-stu-id="51eb6-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="51eb6-110">Para obtener información sobre los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este tema, consulte [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="51eb6-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="51eb6-111">Para obtener información sobre la compatibilidad, consulte [compatibilidad de Skype empresarial con las aplicaciones de Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span><span class="sxs-lookup"><span data-stu-id="51eb6-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="51eb6-112">Configurar la integración entre Exchange Server y O365</span><span class="sxs-lookup"><span data-stu-id="51eb6-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="51eb6-113">Paso 1: configurar la autenticación de OAuth entre Exchange Server y O365</span><span class="sxs-lookup"><span data-stu-id="51eb6-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="51eb6-114">Siga los pasos que se indican en el artículo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51eb6-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="51eb6-115">Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51eb6-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="51eb6-116">Paso 2: crear una nueva cuenta de usuario de correo para la aplicación de socio de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="51eb6-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="51eb6-117">Este paso se realiza en el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="51eb6-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="51eb6-118">Creará un usuario de correo y le asignará los derechos de roles de administración apropiados.</span><span class="sxs-lookup"><span data-stu-id="51eb6-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="51eb6-119">Esta cuenta se usará en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="51eb6-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="51eb6-120">Especifique un dominio verificado para la organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="51eb6-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="51eb6-121">Este dominio debe ser el mismo dominio usado como el dominio SMTP principal usado para las cuentas de Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="51eb6-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="51eb6-122">Este dominio se denomina \<dominio\> verificado en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="51eb6-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="51eb6-123">Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="51eb6-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="51eb6-124">Este comando ocultará al nuevo usuario de correo de las listas de direcciones.</span><span class="sxs-lookup"><span data-stu-id="51eb6-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="51eb6-125">Los dos comandos siguientes asignarán los roles de administración UserApplication y ArchiveApplication a esta nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="51eb6-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="51eb6-126">Paso 3: crear y habilitar una aplicación de socio para Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="51eb6-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="51eb6-127">Cree una aplicación de socio y use la cuenta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="51eb6-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="51eb6-128">Ejecute el siguiente comando en el PowerShell de Exchange de su organización de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="51eb6-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="51eb6-129">Paso 4: exportar el certificado de autorización local</span><span class="sxs-lookup"><span data-stu-id="51eb6-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="51eb6-130">Ejecute un script de PowerShell para exportar el certificado de autorización local que va a importar a su organización de Skype empresarial online en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="51eb6-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="51eb6-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="51eb6-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

``` Powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="51eb6-132">En Exchange PowerShell, en su organización de Exchange local, ejecute el script de PowerShell que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="51eb6-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="51eb6-133">Por ejemplo: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="51eb6-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="51eb6-134">Paso 6: Cargar el certificado de autorización local a Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="51eb6-134">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="51eb6-135">A continuación, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="51eb6-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="51eb6-136">Para ello, debe tener instalado el módulo de Azure Active Directory para cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51eb6-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="51eb6-137">Si no está instalado, vaya a [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar el módulo Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51eb6-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="51eb6-138">Complete los siguientes pasos después de instalar el módulo de Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51eb6-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="51eb6-p107">Haga clic en el acceso directo **Módulo de Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell con los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán con la consola de Windows PowerShell para Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="51eb6-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="51eb6-141">Guarde el siguiente texto en un archivo de script de PowerShell denominado, por `UploadAuthCert.ps1`ejemplo,.</span><span class="sxs-lookup"><span data-stu-id="51eb6-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ``` Powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="51eb6-142">Ejecute el script de PowerShell que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="51eb6-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="51eb6-143">Por ejemplo:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="51eb6-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="51eb6-p109">Después de iniciar el script, se mostrará un cuadro de diálogo de credenciales. Escriba las credenciales para la cuenta de administrador del inquilino de su organización de Microsoft Online Azure AD. Después de ejecutar el script, deje la sesión de Windows PowerShell para Azure AD abierta. La usará para ejecutar un script de PowerShell en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="51eb6-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="51eb6-148">Comprobar que realizó todo correctamente</span><span class="sxs-lookup"><span data-stu-id="51eb6-148">Verify your success</span></span>

<span data-ttu-id="51eb6-149">Verifique que la configuración sea correcta verificando que algunas de las características funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="51eb6-149">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="51eb6-150">Confirmar el historial de conversaciones para clientes móviles está visible en la carpeta Historial de conversaciones de Outlook.</span><span class="sxs-lookup"><span data-stu-id="51eb6-150">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

2. <span data-ttu-id="51eb6-151">Confirme que los mensajes de chat archivados se depositan en el buzón local del usuario en la carpeta purgadores mediante [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span><span class="sxs-lookup"><span data-stu-id="51eb6-151">Confirm that archived chat messages are deposited in the user's on premise mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="51eb6-152">Como alternativa, mire el tráfico.</span><span class="sxs-lookup"><span data-stu-id="51eb6-152">Alternately, look at your traffic.</span></span> <span data-ttu-id="51eb6-153">El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no se parece a la autenticación básica), en particular en relación con territorios, donde comenzará a ver el tráfico de emisor que tiene el siguiente aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con un/antes el signo @), en los tokens que se están transmitiendo.</span><span class="sxs-lookup"><span data-stu-id="51eb6-153">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="51eb6-154">No verá un nombre de usuario o una contraseña, que es el punto de OAuth.</span><span class="sxs-lookup"><span data-stu-id="51eb6-154">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="51eb6-155">Pero verá el emisor ' Office ' (en este caso, ' 4 ' es Skype empresarial) y el territorio de su plan.</span><span class="sxs-lookup"><span data-stu-id="51eb6-155">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="51eb6-156">Si quiere asegurarse de que está usando OAuth correctamente, asegúrese de que sabe qué esperar y sepa qué aspecto tiene el tráfico.</span><span class="sxs-lookup"><span data-stu-id="51eb6-156">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="51eb6-157">Esto [es lo que debe esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí tiene un ejemplo muy estándar [de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (lo que es realmente útil leer, aunque no usa tokens de actualización) y hay extensiones de Fiddler que le permitirán consultar su JWT de OAuth (JSON). Token Web).</span><span class="sxs-lookup"><span data-stu-id="51eb6-157">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="51eb6-158">Este es un [ejemplo de configuración de una](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero puede usar cualquier herramienta de seguimiento de red que desee para realizar este proceso.</span><span class="sxs-lookup"><span data-stu-id="51eb6-158">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51eb6-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="51eb6-159">Related topics</span></span>

[<span data-ttu-id="51eb6-160">Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51eb6-160">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
