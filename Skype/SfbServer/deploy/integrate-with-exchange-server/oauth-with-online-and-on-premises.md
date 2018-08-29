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
ms.openlocfilehash: e5510605dc07f8ad3babda45984f258e8a81689f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250206"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a>Configurar OAuth entre Skype Empresarial Online y Exchange local

Configuración de OAuth autenticación entre Exchange local y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en [función de soporte técnico](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

En este tema se aplica a Exchange Server 2016 y Exchange Server 2013.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para finalizar esta tarea: 15 minutos

-  Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos. Para ver qué permisos necesita, vea el tema de [permisos de infraestructura de Exchange y el Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Para obtener información sobre los métodos abreviados de teclado que se pueden aplicar a los procedimientos descritos en este tema, vea [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a>Configurar la autenticación OAuth entre su Exchange local y organizaciones de Skype Empresarial

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a>Paso 1: Crear un objeto de servidor de autorización para su organización de Skype Empresarial Online

Especifique un dominio comprobado su Skype para la organización en línea de negocio. Este dominio debería ser el mismo que el dominio de SIP principal que se usa para las cuentas basadas en la nube. Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento.

Ejecute el siguiente comando en el Shell de administración de Exchange (Exchange PowerShell) en sus instalaciones de organización de Exchange.

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a>Paso 2: Habilitar la aplicación de socio para su organización de Skype Empresarial Online

Ejecute el siguiente comando en Exchange PowerShell en sus instalaciones de organización de Exchange.

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>Paso 3: Crear una cuenta de usuario de correo para la aplicación de socio de Skype Empresarial Online

Este paso se realiza localmente. Creará un usuario de correo y le asignará los derechos de roles de administración apropiados. Esta cuenta se usará en el siguiente paso.

Especifique un dominio comprobado para la organización de Exchange. Este dominio debe ser el mismo dominio que se utiliza como el dominio SMTP principal que se utiliza para las cuentas de Exchange local. Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento. Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.

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

Cree una aplicación de socio y use la cuenta que acaba de crear. Ejecute el siguiente comando en Exchange PowerShell en sus instalaciones de organización de Exchange.

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a>Paso 5: Exportar el certificado de autorización local

Ejecutar un script de PowerShell para exportar el certificado de autorización local, que se va a importar a su Skype para la organización en línea de negocio en el paso siguiente.

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

En Exchange PowerShell en la organización de Exchange local, ejecute el script de PowerShell que acaba de crear. Por ejemplo:.\ExportAuthCert.ps1

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>Paso 6: Cargar el certificado de autorización local a Azure Active Directory ACS

A continuación, use Windows PowerShell para cargar el certificado de autorización local que exportó en el paso anterior a Azure Active Directory Access Control Services (ACS). Para ello, debe tener instalado el módulo de Azure Active Directory para cmdlets de Windows PowerShell. Si no está instalada, vaya a [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar Azure Active Directory módulo para Windows PowerShell. Complete los siguientes pasos después de instalar el módulo de Azure Active Directory para Windows PowerShell.

1. Haga clic en el acceso directo **Módulo de Azure Active Directory para Windows PowerShell** para abrir un área de trabajo de Windows PowerShell con los cmdlets de Azure AD instalados. Todos los comandos de este paso se ejecutarán con la consola de Windows PowerShell para Azure Active Directory.

2. Guarde el siguiente texto en un archivo de secuencia de comandos de PowerShell llamado, por ejemplo, `UploadAuthCert.ps1`.

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

Especifique un dominio comprobado para la organización de Exchange. Este dominio debe ser el mismo dominio que se utiliza como el dominio SMTP principal que se utiliza para las cuentas de Exchange local. Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento.

> [!NOTE]
> Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section. 

1. Guarde el siguiente texto en un script de PowerShell con nombre, por ejemplo, RegisterEndpoints.ps1. Este ejemplo usa un carácter comodín para registrar todos los puntos de conexión para contoso.com. Reemplace contoso.com con una entidad de certificación de nombre de host para la organización de Exchange local

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

1. Iniciar el Skype para la aplicación empresarial de móvil en su dispositivo de iOS o Windows Phone e iniciar sesión como un Skype para usuario empresarial en línea con un 2016 de Exchange o un buzón de Exchange 2013 local.

2. Tener una conversación de mensajería instantánea con otro Skype para usuarios profesionales en línea.

3. Cierre la ventana de la conversación de MI.

4. Inicie la sesión de Outlook de este usuario y compruebe que la conversación está visible en la carpeta Historial de conversación de Outlook.

Como alternativa, examine el tráfico. El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no el aspecto de la autenticación básica), especialmente alrededor de dominios, donde podrá comenzar a ver el tráfico de emisor que tiene este aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con una / antes de el signo @), en los tokens que se pasan. No podrá ver un nombre de usuario o contraseña, que es el punto de OAuth. Pero se verá al emisor 'Office': en este caso '4' es Skype para empresas – y el dominio Kerberos de su suscripción.

Si desea estar seguro de que ya está utilizando OAuth, asegúrese de que saber qué esperar y saber lo que el tráfico debe ser similar. Es así [aquí es qué esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí es bastante estándar de [ejemplo de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente útil para leer, aunque no utilice tokens de actualización) y hay extensiones de Fiddler que le permiten buscar en su OAuth JWT (JSON Token de Web).

Este es un [ejemplo de configuración de una copia de seguridad](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero se puede usar cualquier herramienta de seguimiento de red que desee para llevar a cabo este proceso.
