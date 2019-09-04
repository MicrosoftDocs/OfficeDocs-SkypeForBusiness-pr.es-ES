---
title: Integración entre Skype empresarial online y Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuración de la autenticación de OAuth entre Exchange local y Skype empresarial online habilita las características de integración de Skype empresarial e Exchange descritas en compatibilidad de características.
ms.openlocfilehash: fe6d7bbe1be9418b7e960de02e91cecf1c808d2b
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715812"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurar la integración y OAuth entre Skype empresarial online y Exchange Server 

La configuración de la integración entre Exchange Server y Skype empresarial online habilita las características de integración de Skype empresarial e Exchange descritas en [compatibilidad de características](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tema se aplica a la integración con Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para finalizar esta tarea: 15 minutos

-  Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos. Para ver qué permisos necesita, consulte el tema [Exchange and Shell Infrastructure](https://go.microsoft.com/fwlink/p/?LinkId=746511) Permissions.

- Para obtener información sobre los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este tema, consulte [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Para obtener información sobre la compatibilidad, consulte [compatibilidad de Skype empresarial con las aplicaciones de Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar la integración entre Exchange Server y O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Paso 1: configurar la autenticación de OAuth entre Exchange Server y O365

Siga los pasos que se indican en el artículo siguiente:

[Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Paso 2: crear una nueva cuenta de usuario de correo para la aplicación de socio de Skype empresarial online

Este paso se realiza en el servidor de Exchange. Creará un usuario de correo y le asignará los derechos de roles de administración apropiados. Esta cuenta se usará en el siguiente paso.

Especifique un dominio verificado para la organización de Exchange. Este dominio debe ser el mismo dominio usado como el dominio SMTP principal usado para las cuentas de Exchange locales. Este dominio se denomina \<dominio\> verificado en el siguiente procedimiento. Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Este comando ocultará al nuevo usuario de correo de las listas de direcciones.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Los dos comandos siguientes asignarán los roles de administración UserApplication y ArchiveApplication a esta nueva cuenta.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Paso 3: crear y habilitar una aplicación de socio para Skype empresarial online 

Cree una aplicación de socio y use la cuenta que acaba de crear. Ejecute el siguiente comando en el PowerShell de Exchange de su organización de Exchange local.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Paso 4: exportar el certificado de autorización local

Ejecute un script de PowerShell para exportar el certificado de autorización local que va a importar a su organización de Skype empresarial online en el siguiente paso.

Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.

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

En Exchange PowerShell, en su organización de Exchange local, ejecute el script de PowerShell que acaba de crear. Por ejemplo: .\ExportAuthCert.ps1

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Paso 6: Cargar el certificado de autorización local a Azure Active Directory ACS

A continuación, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS). Para ello, debe tener instalado el módulo de Azure Active Directory para cmdlets de Windows PowerShell. Si no está instalado, vaya a [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar el módulo Azure Active Directory para Windows PowerShell. Complete los siguientes pasos después de instalar el módulo de Azure Active Directory para Windows PowerShell.

1. Haga clic en el acceso directo **Módulo de Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell con los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán con la consola de Windows PowerShell para Azure Active Directory.

2. Guarde el siguiente texto en un archivo de script de PowerShell denominado, por `UploadAuthCert.ps1`ejemplo,.

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

3. Ejecute el script de PowerShell que creó en el paso anterior. Por ejemplo:`.\UploadAuthCert.ps1`

4. Después de iniciar el script, se mostrará un cuadro de diálogo de credenciales. Escriba las credenciales para la cuenta de administrador del inquilino de su organización de Microsoft Online Azure AD. Después de ejecutar el script, deje la sesión de Windows PowerShell para Azure AD abierta. La usará para ejecutar un script de PowerShell en el siguiente paso.

### <a name="step-7-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Paso 7: comprobar que el certificado se ha cargado en la entidad de servicio de Skype empresarial
1. En PowerShell abierto y autenticado en Azure Active Directory, ejecute el siguiente
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Presione entrar cuando se le solicite ReturnKeyValues
3. Confirmar que ve una clave listada con fechas de inicio y de fin que coinciden con las fechas de inicio y finalización del certificado de OAuth de Exchange

### <a name="verify-your-success"></a>Comprobar que realizó todo correctamente

Verifique que la configuración sea correcta verificando que algunas de las características funcionen correctamente. 

1. Confirmar que los usuarios de Skype empresarial con el servicio de buzón de voz de nube en una organización con una configuración de Exchange Server híbrida pueden cambiar correctamente sus saludos de buzón de voz.

2. Confirmar el historial de conversaciones para clientes móviles está visible en la carpeta Historial de conversaciones de Outlook.

3. Confirme que los mensajes de chat archivados se depositan en el buzón local del usuario en la carpeta purgadores mediante [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

Como alternativa, mire el tráfico. El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no se parece a la autenticación básica), en particular en relación con territorios, donde comenzará a ver el tráfico de emisor que tiene el siguiente aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con un/antes el signo @), en los tokens que se están transmitiendo. No verá un nombre de usuario o una contraseña, que es el punto de OAuth. Pero verá el emisor ' Office ' (en este caso, ' 4 ' es Skype empresarial) y el territorio de su plan.

Si quiere asegurarse de que está usando OAuth correctamente, asegúrese de que sabe qué esperar y sepa qué aspecto tiene el tráfico. Esto [es lo que debe esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí tiene un ejemplo muy estándar [de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (lo que es realmente útil leer, aunque no usa tokens de actualización) y hay extensiones de Fiddler que le permitirán consultar su JWT de OAuth (JSON). Token Web).

Este es un [ejemplo de configuración de una](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero puede usar cualquier herramienta de seguimiento de red que desee para realizar este proceso.

## <a name="related-topics"></a>Temas relacionados

[Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
