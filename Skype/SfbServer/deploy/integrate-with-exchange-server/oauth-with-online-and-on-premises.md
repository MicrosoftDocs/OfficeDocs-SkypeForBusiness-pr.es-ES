---
title: Integración entre Skype Empresarial Online y Exchange Server
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuración de la autenticación de OAuth entre Exchange local y Skype Empresarial Online habilita las características de integración de Skype Empresarial y Exchange descritas en la compatibilidad con características.
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833980"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>Configurar la integración y OAuth entre Skype Empresarial Online y Exchange Server 

Configurar la integración entre Exchange Server y Skype Empresarial Online habilita las características de integración de Skype Empresarial y Exchange que se describen en [la compatibilidad con características.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

Este tema se aplica a la integración Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tiempo estimado para finalizar esta tarea: 15 minutos

-  Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el tema sobre permisos de infraestructura del Shell y de [Exchange.](https://go.microsoft.com/fwlink/p/?LinkId=746511)

- Para obtener información acerca de los métodos abreviados de teclado aplicables a los procedimientos de este tema, consulte [Métodos abreviados de teclado en el Centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

- Para obtener información sobre la compatibilidad, [consulte Compatibilidad de Skype Empresarial con aplicaciones de Office.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar la integración entre Exchange Server y O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Paso 1: Configurar la autenticación de OAuth entre Exchange Server y O365

Realice los pasos del siguiente artículo:

[Configurar la autenticación OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Paso 2: Crear una nueva cuenta de usuario de correo para la aplicación de socio de Skype Empresarial Online

Este paso se realiza en el servidor Exchange. Creará un usuario de correo y le asignará los derechos de rol de administración adecuados. Esta cuenta se usará en el paso siguiente.

Especifique un dominio comprobado para su organización de Exchange. Este dominio debe ser el mismo que el dominio SMTP principal usado para las cuentas de Exchange locales. Este dominio se hace referencia al \<your Verified Domain\> procedimiento siguiente. Además, debe \<DomainControllerFQDN\> ser el FQDN de un controlador de dominio.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>Paso 3: Crear y habilitar una aplicación de socio para Skype Empresarial Online 

Crea una nueva aplicación de partner y usará la cuenta que acaba de crear. Ejecute el siguiente comando en Exchange PowerShell en la organización de Exchange local.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>Paso 4: Exportar el certificado de autorización local

Ejecute un script de PowerShell para exportar el certificado de autorización local, que importará a su organización de Skype Empresarial Online en el paso siguiente.

Guarde el siguiente texto en un archivo de script de PowerShell llamado, por ejemplo, ExportAuthCert.ps1.

```powershell
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

En Exchange PowerShell en su organización de Exchange local, ejecute el script de PowerShell que acaba de crear. Por ejemplo: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Paso 5: Cargar el certificado de autorización local en Azure Active Directory ACS

Después, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS). Para ello, el Módulo Azure Active Directory para Windows PowerShell cmdlets ya debe estar instalado. Si no están instalados, vaya a [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar el Módulo Azure Active Directory para Windows PowerShell. Una vez instalado el Módulo Azure Active Directory para Windows PowerShell, complete los siguientes pasos.

1. Haga clic en el acceso directo del **Módulo Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell que tenga los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán mediante la consola de Windows PowerShell para Azure Active Directory.

2. Guarde el siguiente texto en un archivo de script de PowerShell denominado, por ejemplo,  `UploadAuthCert.ps1` .

   ```powershell
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

3. Ejecute el script de PowerShell que creó en el paso anterior. Por ejemplo:  `.\UploadAuthCert.ps1`

4. Después de iniciar el script, se abre un cuadro de diálogo de credenciales. Escribe las credenciales de la cuenta de administrador de inquilinos de tu organización de Microsoft Online Azure AD. Tras ejecutar el script, deje abierta la sesión de Windows PowerShell para Azure AD. La usará para ejecutar un script de PowerShell en el paso siguiente.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>Paso 6: Comprobar que el certificado se ha cargado en la entidad de servicio de Skype Empresarial
1. En el PowerShell abierto y autenticado en Azure Active Directory, ejecute lo siguiente
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. Presione ENTRAR cuando se le solicite ReturnKeyValues
3. Confirme que ve una clave con los datos de fecha de inicio y finalización que coinciden con las fechas de inicio y finalización del certificado Oauth de Exchange

### <a name="verify-your-success"></a>Comprobar que se ha correcto

Compruebe que la configuración es correcta comprobando que algunas de las características funcionan correctamente. 

1. Confirme que los usuarios de Skype Empresarial con el servicio de correo de voz en la nube, en una organización con una configuración de Exchange Server híbrida, pueden cambiar correctamente sus saludos de correo de voz.

2. Confirme que el historial de conversaciones para clientes móviles esté visible en la carpeta Historial de conversaciones de Outlook.

3. Confirme que los mensajes de chat archivados se depositan en el buzón local del usuario en la carpeta Purgas mediante [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).

Como alternativa, mira el tráfico. El tráfico de un protocolo de enlace de OAuth es realmente distintivo (y no se parece a la autenticación básica), especialmente en torno a los dominios kerberos, donde empezará a ver el tráfico de emisor con este aspecto: 00000004-0000-0ff1-ce00-000000000000@ (a veces con un signo / antes del signo @) en los tokens que se pasan. No verá un nombre de usuario ni una contraseña, que es el punto de OAuth. Pero verá el emisor de "Office", en este caso "4" es Skype Empresarial, y el dominio kerberos de su suscripción.

Si quieres asegurarte de que estás usando OAuth correctamente, asegúrate de saber qué esperar y saber qué aspecto debe tener el tráfico. Por lo tanto, esto es lo que hay que [esperar,](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)este es un ejemplo bastante estándar del tráfico de [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  en una aplicación de Microsoft (realmente útil para leer, aunque no usa tokens de actualización) y hay extensiones de Fiddler que te permitirán buscar en el JWT de OAuth (token web JSON).

Este es un ejemplo [de configuración](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)de uno, pero puede usar cualquier herramienta de seguimiento de red que quiera para llevar a cabo este proceso.

## <a name="related-topics"></a>Temas relacionados

[Configurar la autenticación OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
