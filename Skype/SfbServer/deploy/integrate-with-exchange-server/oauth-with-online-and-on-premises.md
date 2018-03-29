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
description: Configuración OAuth autenticación entre Exchange en instalaciones y Skype para los negocios en línea permite la Skype para funciones empresariales y la integración de Exchange descrito en la compatibilidad de la característica.
ms.openlocfilehash: adb811a8934fdc6ea574dc934efa57ee28e6fba6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>Configurar OAuth entre Skype Empresarial Online y Exchange local
 
Configuración OAuth autenticación entre Exchange en instalaciones y Skype para los negocios en línea permite la Skype para funciones empresariales y la integración de Exchange descrito en [función de soporte](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).
  
En este tema se aplica a Exchange Server 2016 y 2013 de Exchange Server.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para finalizar esta tarea: 15 minutos
    
-  Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos. Para ver qué permisos necesita, consulte el tema de [permisos de infraestructura de Exchange y el Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .
    
- Para obtener información sobre métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, vea [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>Configurar la autenticación OAuth entre su Exchange local y organizaciones de Skype Empresarial

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>Paso 1: Crear un objeto de servidor de autorización para su organización de Skype Empresarial Online

Especifique un dominio verificado para su Skype para la organización de los negocios en línea. Este dominio debería ser el mismo que el dominio de SIP principal que se usa para las cuentas basadas en la nube. Este dominio se conoce como \<su dominio comprobado\> en el procedimiento siguiente.
  
Ejecute el siguiente comando en el Shell de administración de Exchange (la PowerShell de Exchange) en sus instalaciones de organización de Exchange.
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>Paso 2: Habilitar la aplicación de socio para su organización de Skype Empresarial Online

Ejecute el siguiente comando en el PowerShell de Exchange en sus instalaciones de organización de Exchange.
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Paso 3: Crear una cuenta de usuario de correo para la aplicación de socio de Skype Empresarial Online

Este paso se realiza localmente. Creará un usuario de correo y le asignará los derechos de roles de administración apropiados. Esta cuenta se usará en el siguiente paso.
  
Especifique un dominio verificado para la organización de Exchange. Este dominio debe ser el mismo dominio que se utiliza como el dominio de SMTP principal utilizado para las cuentas de Exchange local. Este dominio se conoce como \<su dominio comprobado\> en el procedimiento siguiente. Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio. 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

Este comando ocultará al nuevo usuario de correo de las listas de direcciones.
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

Los dos comandos siguientes asignarán los roles de administración UserApplication y ArchiveApplication a esta nueva cuenta.
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 

```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Paso 4: Crear y habilitar una aplicación de socio para Skype Empresarial Online

Cree una aplicación de socio y use la cuenta que acaba de crear. Ejecute el siguiente comando en el PowerShell de Exchange en sus instalaciones de organización de Exchange. 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>Paso 5: Exportar el certificado de autorización local

Ejecutar un script de PowerShell para exportar el certificado de autorización local, que se importa a su Skype para la organización empresarial en línea en el paso siguiente.
  
Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.
  
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

En Exchange PowerShell en su organización de Exchange local, ejecute el script de PowerShell que acaba de crear. Por ejemplo:.\ExportAuthCert.ps1
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Paso 6: Cargar el certificado de autorización local a Azure Active Directory ACS

A continuación, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS). Para ello, debe tener instalado el módulo de Azure Active Directory para cmdlets de Windows PowerShell. Si no está instalado, vaya a [https://aka.ms/aadposh](https://aka.ms/aadposh) a instalar Azure Active Directory módulo para Windows PowerShell. Complete los siguientes pasos después de instalar el módulo de Azure Active Directory para Windows PowerShell.
  
1. Haga clic en el acceso directo **Módulo de Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell con los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán con la consola de Windows PowerShell para Azure Active Directory.
    
2. Guarde el siguiente texto en un archivo de script de PowerShell denominado, por ejemplo, `UploadAuthCert.ps1`.
    
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
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName 
New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue 
  ```

3. Ejecute el script de PowerShell que creó en el paso anterior. Por ejemplo:`.\UploadAuthCert.ps1`
    
4. Después de iniciar el script, se mostrará un cuadro de diálogo de credenciales. Escriba las credenciales para la cuenta de administrador del inquilino de su organización de Microsoft Online Azure AD. Después de ejecutar el script, deje la sesión de Windows PowerShell para Azure AD abierta. La usará para ejecutar un script de PowerShell en el siguiente paso.
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a>Paso 7: Registrar las autoridades del nombre de host para el dominio de SMTP

Especifique un dominio verificado para la organización de Exchange. Este dominio debe ser el mismo dominio que se utiliza como el dominio de SMTP principal utilizado para las cuentas de Exchange local. Este dominio se conoce como \<su dominio comprobado\> en el procedimiento siguiente.
  
> [!NOTE]
> Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.  
  
1. Guarde el siguiente texto en un script de PowerShell con nombre, por ejemplo, RegisterEndpoints.ps1. Este ejemplo utiliza un carácter comodín para registrar todos los extremos para contoso.com. Reemplace contoso.com con una autoridad de nombre de host para la organización de Exchange local
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  En Windows PowerShell para Azure Active Directory, ejecute el script de Windows PowerShell que creó en el paso anterior. Por ejemplo: `.\RegisterEndpoints.ps1`
    
### <a name="verify-your-success"></a>Comprobar que realizó todo correctamente

Compruebe que la configuración de OAuth es correcta verificando que algunas características funcionan correctamente, como disponer de un historial de conversación para clientes móviles visible en la carpeta Historial de conversación de Outlook.
  
1. Inicie el Skype para aplicaciones móviles de negocio en el Windows Phone o el dispositivo iOS e iniciar sesión como un Skype para el usuario de negocios en línea con un 2016 de Exchange o el buzón de Exchange 2013 local.
    
2. Tener una conversación de mensajería instantánea con otro Skype para usuarios de negocios en línea.
    
3. Cierre la ventana de la conversación de MI.
    
4. Inicie la sesión de Outlook de este usuario y compruebe que la conversación está visible en la carpeta Historial de conversación de Outlook.
    

