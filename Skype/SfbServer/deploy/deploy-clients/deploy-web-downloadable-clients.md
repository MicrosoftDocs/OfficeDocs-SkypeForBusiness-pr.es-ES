---
title: Implementar clientes descargables web en Skype Empresarial Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Summary: Deploy the aplicación web de Skype Empresarial and Skype Meetings App used with Skype Empresarial.'
ms.openlocfilehash: 2fca7600232e9293dedbe9228075470097335d5836fb77c0cb428625e809a609
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330564"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implementar clientes descargables web en Skype Empresarial Server

**Resumen:** Implemente la Skype Empresarial web de 2015 y la aplicación Skype reuniones que se usa con Skype Empresarial Server.

aplicación web de Skype Empresarial es un cliente web de Internet Information Services (IIS) que está instalado en el servidor que ejecuta Skype Empresarial Server y, de forma predeterminada, se implementa a petición para los usuarios que aún no tienen el cliente Skype Empresarial. Estos usuarios de reuniones suelen no conectarse desde fuera de la red. Cada vez que un usuario hace clic en una dirección URL de reunión pero no tiene instalado el cliente de Skype Empresarial, el usuario se presenta con la opción de unirse a la reunión mediante la versión más reciente de aplicación web de Skype Empresarial, Skype Meetings App o Skype Empresarial para Mac.

Las características de voz, vídeo y uso compartido de aplicación web de Skype Empresarial requieren un control de microsoft ActiveX que el explorador del usuario usa como complemento. Puede instalar el control ActiveX por adelantado o permitir que los usuarios lo instalen cuando se le pida, lo que ocurre la primera vez que usan aplicación web de Skype Empresarial o la primera vez que acceden a una característica que requiere el control ActiveX.

> [!NOTE]
> En Skype Empresarial Server de servidor perimetral, se requiere un proxy inverso HTTPS en la red perimetral para el aplicación web de Skype Empresarial cliente. También debe publicar direcciones URL sencillas. Para obtener más información, vea [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and DNS requirements for simple [URLs in Skype Empresarial Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar la autenticación multifactor para aplicación web de Skype Empresarial
<a name="MFA"> </a>

aplicación web de Skype Empresarial, Skype Meetings App y Skype Empresarial para Mac admiten la autenticación multifactor. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en Skype Empresarial reuniones. Para habilitar la autenticación multifactor, implemente el servidor de federación del Servicio de federación de Active Directory (AD FS) y habilite la autenticación pasiva en Skype Empresarial Server. Una vez configurado AD FS, los usuarios externos que intentan unirse Skype Empresarial reuniones se presentan con una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña junto con los métodos de autenticación adicionales que haya configurado.

> [!IMPORTANT]
> Las siguientes son consideraciones importantes si tiene previsto configurar AD FS para la autenticación multifactor:

- La autenticación multifactor ADFS funciona si el participante y el organizador de la reunión están en la misma organización o son ambos de una organización federada de AD FS. La autenticación multifactor ADFS no funciona para los usuarios federados de Lync porque la infraestructura web de Lync Server no la admite actualmente.

- Si usa equilibradores de carga de hardware, habilite la persistencia de cookies en los equilibradores de carga para que todas las solicitudes de los clientes de la aplicación aplicación web de Skype Empresarial o Meetings sean manejadas por el mismo servidor front-end.

- Al establecer una confianza de usuario de confianza entre los servidores de Skype Empresarial Server y AD FS, asigne una vida de token lo suficientemente larga como para abarcar la longitud máxima de las reuniones Skype Empresarial usuario. Normalmente, una vida de token de 240 minutos es suficiente.

- Esta configuración no se aplica a los clientes móviles de Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar la autenticación multifactor

1. Instalar un rol de servidor de federación de AD FS. Para obtener más información, consulte la Guía de implementación de Servicios de federación [de Active Directory 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Crear certificados para AD FS. Para obtener más información, vea [la sección "Certificados](/previous-versions/azure/azure-services/jj205462(v=azure.100)) de servidor de federación" del tema Planear e implementar AD FS para su uso con el inicio de sesión único.

3. Desde la Windows PowerShell de línea de comandos, ejecute el siguiente comando:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Para establecer una asociación, ejecute el siguiente comando:

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Establezca las siguientes reglas de usuario de confianza:

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Deshabilitar BranchCache
<a name="MFA"> </a>

La característica BranchCache de Windows 7 y Windows Server 2008 R2 pueden interferir con aplicación web de Skype Empresarial web. Para evitar problemas para aplicación web de Skype Empresarial usuarios, asegúrese de que BranchCache no está habilitado.

Para obtener más información sobre cómo deshabilitar BranchCache, consulte la [Guía de implementación de BranchCache](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Comprobación de aplicación web de Skype Empresarial implementación
<a name="MFA"> </a>

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar en una conferencia mediante la API web de comunicaciones unificadas (UCWA). Para obtener más información acerca de este cmdlet, vea [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) en la documentación Skype Empresarial Server Shell de administración.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solución de problemas de instalación de complementos en Windows Server 2008 R2
<a name="MFA"> </a>

Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de clave del Registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar la configuración de seguridad en Internet Explorer

1. Abra Internet Explorer.

2. Haga **clic en Herramientas**, en Opciones de **Internet** y, a continuación, en **Opciones avanzadas.**

3. Desplácese hacia abajo hasta la **sección** Seguridad.

4. Desactive **No guardar páginas cifradas en el disco** y, a continuación, haga clic en **Aceptar**.

    > [!NOTE]
    > Si se selecciona, esta configuración también provocará un error al intentar descargar datos adjuntos de aplicación web de Skype Empresarial.

5. Vuelva a unirse a la reunión. El complemento debe descargarse sin errores.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar la configuración del Registro DisableMSI

1. Haga clic en **Inicio** y luego en **Ejecutar**.

2. Para obtener acceso al Editor del Registro, escriba **regedit**.

3. Vaya a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Edite o agregue la clave del Registro DisableMSI del tipo REG_DWORD y estadíla en 0.

5. Vuelva a unirse a la reunión.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar Skype de reuniones para reemplazar aplicación web de Skype Empresarial (opcional, Skype Empresarial Server 2015 solamente)
<a name="SMA_Enable"> </a>

Este procedimiento es opcional y se aplica a Skype Empresarial Server 2015 CU5 y versiones posteriores. Si no lo usa, los usuarios externos seguirán uniendo reuniones con aplicación web de Skype Empresarial.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar una reunión simplificada y Skype de reuniones

1. Al habilitar el acceso a Content Delivery Network (CDN), los usuarios tendrán la capacidad de conectarse a CDN en línea y obtener Skype Meetings App (en Windows) y Skype Empresarial para Mac (en Mac), y usarán la experiencia de unión a reuniones simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir que la telemetría de registro del lado cliente desde la página web de unión a la reunión o la aplicación de reuniones de Skype se envíe a los servidores de Microsoft (el comando tiene el valor predeterminado false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    La información enviada a Microsoft cumple estrictamente con Skype Empresarial [prácticas de recopilación de datos](/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Establezca el tiempo de espera antes de volver a la experiencia de aplicación web de Skype Empresarial local si CDN no está disponible. El valor predeterminado es 6 segundos. Si este valor se establece en 0, no habrá tiempo de espera.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Con MeetingUxUseCdn en Skype Empresarial Server 2015 Cumulative Update 5, el valor predeterminado se establece en False. Esto provoca un problema en el que Skype Empresarial para Mac cliente no puede unirse a reuniones de socios no federados como invitado, incluso si Skype Empresarial Admin ha establecido MeetingUxUseCdn en True. Para que esto funcione, Skype Empresarial Server 2015 debe tener la actualización acumulativa 7, 6.0.9319.534 o posterior. Consulta [Habilitar la Skype reuniones para reemplazar aplicación web de Skype Empresarial en Skype Empresarial Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Consulte también
<a name="SMA_Enable"> </a>

[Plan for Meetings clients (Web App and Meetings App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar la página de unión a la reunión en Skype Empresarial Server](../../manage/conferencing/meeting-join-page.md)

[Declaración de privacidad de servicios en línea Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Términos y documentación de licencia](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)