---
title: Integración entre Skype Empresarial Online y Exchange Server
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuración de la autenticación de OAuth entre Exchange local y Skype Empresarial Online habilita las características de Skype Empresarial e Integración de Exchange que se describen en Compatibilidad con características.
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886647"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configuración de integración y OAuth entre Skype Empresarial Online y Exchange Server 

La configuración de la integración entre exchange server y Skype Empresarial Online permite las características de Skype Empresarial e Integración de Exchange que se describen en [Compatibilidad con características](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tema se aplica a la integración con Exchange Server 2013 hasta 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar esta tarea: 15 minutos

-  Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el tema [Permisos de infraestructura de Exchange y Shell](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) .

- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte [Métodos abreviados de teclado en el Centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Para obtener información sobre la compatibilidad, vea [Compatibilidad de Skype Empresarial con aplicaciones de Office](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configuración de la integración entre Exchange Server y O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Paso 1: Configurar la autenticación de OAuth entre Exchange Server y O365

Siga los pasos descritos en el artículo siguiente:

[Configurar la autenticación OAuth entre organizaciones de Exchange y Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Paso 2: Crear una nueva cuenta de usuario de correo para la aplicación de partners de Skype Empresarial Online

Este paso se realiza en el servidor Exchange. Creará un usuario de correo y le asignará los derechos de rol de administración adecuados. Esta cuenta se usará en el paso siguiente.

Especifique un dominio comprobado para su organización de Exchange. Este dominio debe ser el mismo que el dominio SMTP principal usado para las cuentas de Exchange locales. Este dominio se conoce como \<your Verified Domain\> en el procedimiento siguiente. Además, \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Este comando ocultará el nuevo usuario de correo de las listas de direcciones.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Estos dos comandos siguientes asignarán el rol de administración UserApplication y ArchiveApplication a esta nueva cuenta.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Paso 3: Creación y habilitación de una aplicación de partner para Skype Empresarial Online 

Cree una nueva aplicación de asociado y usará la cuenta que acaba de crear. Ejecute el siguiente comando en Exchange PowerShell en la organización de Exchange local.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Paso 4: Exportación del certificado de autorización local

Ejecute un script de PowerShell para exportar el certificado de autorización local, que importará a su organización de Skype Empresarial Online en el paso siguiente.

Guarde el siguiente texto en un archivo de script de PowerShell llamado, por ejemplo, ExportAuthCert.ps1.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

En Exchange PowerShell en la organización local de Exchange, ejecute el script de PowerShell que acaba de crear. Por ejemplo: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Paso 5: Carga del certificado de autorización local en ACS de Azure Active Directory

A continuación, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS). Para ello, ya se debe instalar el módulo de Azure Active Directory para los cmdlets de Windows PowerShell. Si no están instalados, vaya a [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) para instalar el Módulo Azure Active Directory para Windows PowerShell. Una vez instalado el Módulo Azure Active Directory para Windows PowerShell, complete los siguientes pasos.

1. Haga clic en el acceso directo del **Módulo Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell que tenga los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán mediante la consola de Windows PowerShell para Azure Active Directory.

2. Guarde el texto siguiente en un archivo de script de PowerShell denominado, por ejemplo,  `UploadAuthCert.ps1`.

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. Ejecute el script de PowerShell que creó en el paso anterior. Por ejemplo:  `.\UploadAuthCert.ps1`

4. Después de iniciar el script, se abre un cuadro de diálogo de credenciales. Escriba las credenciales de la cuenta de administrador de inquilinos de la organización de Microsoft Online Azure AD. Tras ejecutar el script, deje abierta la sesión de Windows PowerShell para Azure AD. La usará para ejecutar un script de PowerShell en el paso siguiente.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Paso 6: Comprobar que el certificado se ha cargado en la entidad de servicio de Skype Empresarial
1. En PowerShell abierto y autenticado en Azure Active Directory, ejecute lo siguiente.

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. Presione Entrar cuando se le solicite ReturnKeyValues.
3. Confirme que ve una clave que aparece con datos de fecha de inicio y finalización que coincidan con las fechas de inicio y finalización del certificado de Oauth de Exchange.

### <a name="verify-your-success"></a>Comprobar que se ha realizado correctamente

Compruebe que la configuración es correcta comprobando que algunas de las características funcionan correctamente. 

1. Confirme que los usuarios de Skype Empresarial con el servicio correo de voz en la nube, en una organización con una configuración híbrida de Exchange Server, pueden cambiar correctamente sus saludos de correo de voz.

2. Confirme que el historial de conversaciones de los clientes móviles está visible en la carpeta Historial de conversaciones de Outlook.

3. Confirme que los mensajes de chat archivados se depositan en el buzón local del usuario en la carpeta Purgas mediante [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).

Como alternativa, examine el tráfico. El tráfico de un protocolo de enlace de OAuth es realmente distintivo (y no se parece a la autenticación básica), especialmente en los reinos, donde empezará a ver el tráfico del emisor que tiene este aspecto: 00000004-0000-0ff1-ce00-0000000000@ (a veces con un / antes del signo @) en los tokens que se pasan. No verá un nombre de usuario ni una contraseña, que es el punto de OAuth. Pero verá que el emisor de "Office" (en este caso, "4" es Skype Empresarial) y el dominio de su suscripción.

Si desea asegurarse de que usa correctamente OAuth, asegúrese de saber qué esperar y saber cómo debe ser el tráfico. Por [lo tanto, esto es lo que hay que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), este es un ejemplo bastante estándar [del tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (muy útil de leer, aunque no usa tokens de actualización) y hay extensiones de Fiddler que le permitirán examinar el JWT de OAuth (JSON Web Token).

Este es un [ejemplo de configuración de uno](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), pero puede usar cualquier herramienta de seguimiento de red que desee para llevar a cabo este proceso.

## <a name="related-topics"></a>Temas relacionados

[Configurar la autenticación OAuth entre organizaciones de Exchange y Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
