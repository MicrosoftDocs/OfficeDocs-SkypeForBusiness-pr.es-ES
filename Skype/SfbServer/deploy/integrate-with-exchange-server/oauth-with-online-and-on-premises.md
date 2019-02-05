---
title: Configurar OAuth entre Skype Empresarial Online y Exchange local
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configuración de OAuth autenticación entre Exchange local y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en compatibilidad con la característica.
ms.openlocfilehash: f6108842f827cbb9cfb6761495c4787ed2b7868b
ms.sourcegitcommit: fddb1d6798e7a716ad87b0613f45a76deff6a043
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2019
ms.locfileid: "29735177"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="eec79-103">Configurar OAuth entre Skype Empresarial Online y Exchange local</span><span class="sxs-lookup"><span data-stu-id="eec79-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>

<span data-ttu-id="eec79-104">Configuración de OAuth autenticación entre Exchange local y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en [función de soporte técnico](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="eec79-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="eec79-105">En este tema se aplica a Exchange Server 2016 y Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eec79-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eec79-106">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="eec79-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eec79-107">Tiempo estimado para finalizar esta tarea: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="eec79-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="eec79-108">Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos.</span><span class="sxs-lookup"><span data-stu-id="eec79-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="eec79-109">Para ver qué permisos necesita, vea el tema de [permisos de infraestructura de Exchange y el Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="eec79-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="eec79-110">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [Métodos abreviados de teclado en el Centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="eec79-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="eec79-111">Configurar la autenticación OAuth entre su Exchange local y organizaciones de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="eec79-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="eec79-112">Paso 1: Crear un objeto de servidor de autorización para su organización de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eec79-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="eec79-113">Especifique un dominio comprobado su Skype para la organización en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="eec79-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="eec79-114">Este dominio debería ser el mismo que el dominio de SIP principal que se usa para las cuentas basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="eec79-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="eec79-115">Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eec79-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

<span data-ttu-id="eec79-116">Ejecute el siguiente comando en el Shell de administración de Exchange (Exchange PowerShell) en sus instalaciones de organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="eec79-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="eec79-117">Paso 2: Habilitar la aplicación de socio para su organización de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eec79-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="eec79-118">Ejecute el siguiente comando en Exchange PowerShell en sus instalaciones de organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="eec79-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="eec79-119">Paso 3: Crear una cuenta de usuario de correo para la aplicación de socio de Skype Empresarial Online </span><span class="sxs-lookup"><span data-stu-id="eec79-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="eec79-p103">Este paso se realiza localmente. Creará un usuario de correo y le asignará los derechos de roles de administración apropiados. Esta cuenta se usará en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="eec79-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>

<span data-ttu-id="eec79-123">Especifique un dominio comprobado para la organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="eec79-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="eec79-124">Este dominio debe ser el mismo dominio que se utiliza como el dominio SMTP principal que se utiliza para las cuentas de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="eec79-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="eec79-125">Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eec79-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="eec79-126">Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="eec79-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="eec79-127">Este comando ocultará al nuevo usuario de correo de las listas de direcciones.</span><span class="sxs-lookup"><span data-stu-id="eec79-127">This command will hide the new mail user from address lists.</span></span>

```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="eec79-128">Los dos comandos siguientes asignarán los roles de administración UserApplication y ArchiveApplication a esta nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="eec79-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="eec79-129">Paso 4: Crear y habilitar una aplicación de socio para Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="eec79-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="eec79-130">Cree una aplicación de socio y use la cuenta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="eec79-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="eec79-131">Ejecute el siguiente comando en Exchange PowerShell en sus instalaciones de organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="eec79-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="eec79-132">Paso 5: Exportar el certificado de autorización local</span><span class="sxs-lookup"><span data-stu-id="eec79-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="eec79-133">Ejecutar un script de PowerShell para exportar el certificado de autorización local, que se va a importar a su Skype para la organización en línea de negocio en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="eec79-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="eec79-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="eec79-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```
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

<span data-ttu-id="eec79-135">En Exchange PowerShell en la organización de Exchange local, ejecute el script de PowerShell que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="eec79-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="eec79-136">Por ejemplo:.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="eec79-136">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="eec79-137">Paso 6: Cargar el certificado de autorización local a Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="eec79-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="eec79-138">A continuación, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="eec79-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="eec79-139">Para ello, debe tener instalado el módulo de Azure Active Directory para cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eec79-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="eec79-140">Si no está instalada, vaya a [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar Azure Active Directory módulo para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eec79-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="eec79-141">Complete los siguientes pasos después de instalar el módulo de Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eec79-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="eec79-p108">Haga clic en el acceso directo **Módulo de Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell con los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán con la consola de Windows PowerShell para Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eec79-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="eec79-144">Guarde el siguiente texto en un archivo de secuencia de comandos de PowerShell llamado, por ejemplo, `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="eec79-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```
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

3. <span data-ttu-id="eec79-145">Ejecute el script de PowerShell que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="eec79-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="eec79-146">Por ejemplo:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="eec79-146">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="eec79-p110">Después de iniciar el script, se mostrará un cuadro de diálogo de credenciales. Escriba las credenciales para la cuenta de administrador del inquilino de su organización de Microsoft Online Azure AD. Después de ejecutar el script, deje la sesión de Windows PowerShell para Azure AD abierta. La usará para ejecutar un script de PowerShell en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="eec79-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="eec79-151">Paso 7: Registrar las autoridades del nombre de host para el dominio de SMTP</span><span class="sxs-lookup"><span data-stu-id="eec79-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="eec79-152">Especifique un dominio comprobado para la organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="eec79-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="eec79-153">Este dominio debe ser el mismo dominio que se utiliza como el dominio SMTP principal que se utiliza para las cuentas de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="eec79-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="eec79-154">Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eec79-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="eec79-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span><span class="sxs-lookup"><span data-stu-id="eec79-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span>

1. <span data-ttu-id="eec79-156">Guarde el siguiente texto en un script de PowerShell con nombre, por ejemplo, RegisterEndpoints.ps1.</span><span class="sxs-lookup"><span data-stu-id="eec79-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="eec79-157">Este ejemplo usa un carácter comodín para registrar todos los puntos de conexión para contoso.com.</span><span class="sxs-lookup"><span data-stu-id="eec79-157">This example uses a wildcard to register all endpoints for contoso.com.</span></span> <span data-ttu-id="eec79-158">Reemplace contoso.com con una entidad de certificación de nombre de host para la organización de Exchange local</span><span class="sxs-lookup"><span data-stu-id="eec79-158">Replace contoso.com with a hostname authority for your on-premises Exchange organization</span></span>

   ```
   $externalAuthority="*.<your Verified Domain>"
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName;
   $spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority);
   $p.ServicePrincipalNames.Add($spn);
   Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames;
   ```

2. <span data-ttu-id="eec79-159">En Windows PowerShell para Azure Active Directory, ejecute el script de Windows PowerShell que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="eec79-159">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="eec79-160">Por ejemplo: `.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="eec79-160">For example: `.\RegisterEndpoints.ps1`</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="eec79-161">Comprobar que realizó todo correctamente</span><span class="sxs-lookup"><span data-stu-id="eec79-161">Verify your success</span></span>

<span data-ttu-id="eec79-162">Compruebe que la configuración de OAuth es correcta verificando que algunas características funcionan correctamente, como disponer de un historial de conversación para clientes móviles visible en la carpeta Historial de conversación de Outlook.</span><span class="sxs-lookup"><span data-stu-id="eec79-162">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>

1. <span data-ttu-id="eec79-163">Iniciar el Skype para la aplicación empresarial de móvil en su dispositivo de iOS o Windows Phone e iniciar sesión como un Skype para usuario empresarial en línea con un 2016 de Exchange o un buzón de Exchange 2013 local.</span><span class="sxs-lookup"><span data-stu-id="eec79-163">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>

2. <span data-ttu-id="eec79-164">Tener una conversación de mensajería instantánea con otro Skype para usuarios profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="eec79-164">Have an instant messaging conversation with another Skype for Business Online user.</span></span>

3. <span data-ttu-id="eec79-165">Cierre la ventana de la conversación de MI.</span><span class="sxs-lookup"><span data-stu-id="eec79-165">Close the IM conversation window.</span></span>

4. <span data-ttu-id="eec79-166">Inicie la sesión de Outlook de este usuario y compruebe que la conversación está visible en la carpeta Historial de conversación de Outlook.</span><span class="sxs-lookup"><span data-stu-id="eec79-166">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>

<span data-ttu-id="eec79-167">Como alternativa, examine el tráfico.</span><span class="sxs-lookup"><span data-stu-id="eec79-167">Alternately, look at your traffic.</span></span> <span data-ttu-id="eec79-168">El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no el aspecto de la autenticación básica), especialmente alrededor de dominios, donde podrá comenzar a ver el tráfico de emisor que tiene este aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con una / antes de el signo @), en los tokens que se pasan.</span><span class="sxs-lookup"><span data-stu-id="eec79-168">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="eec79-169">No podrá ver un nombre de usuario o contraseña, que es el punto de OAuth.</span><span class="sxs-lookup"><span data-stu-id="eec79-169">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="eec79-170">Pero se verá al emisor 'Office': en este caso '4' es Skype para empresas – y el dominio Kerberos de su suscripción.</span><span class="sxs-lookup"><span data-stu-id="eec79-170">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="eec79-171">Si desea estar seguro de que ya está utilizando OAuth, asegúrese de que saber qué esperar y saber lo que el tráfico debe ser similar.</span><span class="sxs-lookup"><span data-stu-id="eec79-171">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="eec79-172">Es así [aquí es qué esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí es bastante estándar de [ejemplo de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente útil para leer, aunque no utilice tokens de actualización) y hay extensiones de Fiddler que le permiten buscar en su OAuth JWT (JSON Token de Web).</span><span class="sxs-lookup"><span data-stu-id="eec79-172">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="eec79-173">Este es un [ejemplo de configuración de una copia de seguridad](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero se puede usar cualquier herramienta de seguimiento de red que desee para llevar a cabo este proceso.</span><span class="sxs-lookup"><span data-stu-id="eec79-173">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>
