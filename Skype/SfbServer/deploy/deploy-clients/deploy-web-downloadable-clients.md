---
title: Implementar clientes Web descargables en Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumen: implemente la aplicación Web de Skype empresarial y la aplicación reuniones de Skype que se usan con Skype empresarial.'
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429426"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implementar clientes Web descargables en Skype empresarial Server

**Resumen:** Implemente la aplicación Web de Skype empresarial 2015 y la aplicación reuniones de Skype que se usa con Skype empresarial Server.

La aplicación Web de Skype empresarial es un cliente web de Internet Information Services (IIS) que se instala en el servidor que ejecuta Skype empresarial Server y, de forma predeterminada, se implementa a petición para los usuarios que aún no tienen el cliente de Skype empresarial. Estos usuarios de reunión son con mayor frecuencia que no se conectan desde fuera de la red. Cada vez que un usuario hace clic en la dirección URL de una reunión pero no tiene instalado el cliente de Skype empresarial, se le muestra al usuario la opción de unirse a la reunión con la versión más reciente de la aplicación Web de Skype empresarial, la aplicación reuniones de Skype o Skype empresarial para Mac.

Las características de voz, vídeo y uso compartido de la aplicación Web de Skype empresarial requieren un control ActiveX de Microsoft que el explorador del usuario usa como complemento. Puede instalar el control ActiveX con antelación o permitir que los usuarios lo instalen cuando se le solicite, lo que sucede la primera vez que usan la aplicación Web de Skype empresarial o la primera vez que tienen acceso a una característica que requiere el control ActiveX.

> [!NOTE]
> En las implementaciones del servidor perimetral de Skype empresarial Server, se requiere un proxy inverso HTTPS en la red perimetral para el acceso de cliente de la aplicación Web de Skype empresarial. También debe publicar direcciones URL sencillas. Para obtener más información, consulte Configuración de los [servidores de proxy inverso](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) y [los requisitos de DNS para las direcciones URL sencillas en Skype empresarial Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar multi-factor Authentication para la aplicación Web de Skype empresarial
<a name="MFA"> </a>

La aplicación Web de Skype empresarial, la aplicación reuniones de Skype y Skype empresarial para Mac admiten la autenticación multifactor. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Skype empresarial. Puede habilitar la autenticación multifactor mediante la implementación del servidor de Federación del servicio de Federación de Active Directory (AD FS) y la habilitación de la autenticación pasiva en Skype empresarial Server. Una vez configurado AD FS, los usuarios externos que intenten unirse a reuniones de Skype empresarial recibirán una página web de autenticación multifactor de AD FS con el nombre de usuario y la contraseña, junto con los métodos de autenticación adicionales que haya configurado.

> [!IMPORTANT]
> A continuación, se indican algunas consideraciones importantes que debe tener en cuenta si tiene previsto configurar AD FS para la autenticación multifactor:

- La autenticación multifactor de ADFS funciona si el participante de la reunión y el organizador están en la misma organización o son de una organización federada de AD FS. La autenticación multifactor de ADFS no funciona para los usuarios federados de Lync porque la infraestructura Web de Lync Server no lo admite en este momento.

- Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes de los clientes de la aplicación web o de la aplicación de reuniones de Skype empresarial se controlen con el mismo servidor front-end.

- Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Skype empresarial Server y AD FS, asigne una duración de token que sea lo suficientemente prolongada como para abarcar la longitud máxima de las reuniones de Skype empresarial. Normalmente, una duración de token de 240 minutos es suficiente.

- Esta configuración no se aplica a los clientes móviles de Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar la autenticación multifactor

1. Instale un rol de servidor de Federación de AD FS. Para obtener más información, consulte la guía de implementación de los [servicios de Federación de active directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Crear certificados para AD FS. Para obtener más información, consulte la sección ["certificados de servidor de Federación"](https://go.microsoft.com/fwlink/p/?LinkId=285376) del tema Plan for and Deploy AD FS for use with Single Sign-on.

3. Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Establezca una asociación mediante la ejecución del siguiente comando:

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

La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de la aplicación Web de Skype empresarial. Para evitar problemas con los usuarios de la aplicación Web de Skype empresarial, asegúrese de que BranchCache no está habilitado.

Para obtener más información acerca de cómo deshabilitar BranchCache, vea la [Guía de implementación de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Comprobar la implementación de la aplicación Web de Skype empresarial
<a name="MFA"> </a>

Puede usar el cmdlet test-CsUcwaConference para comprobar que un par de usuarios de prueba pueden participar en una conferencia mediante la API Web de comunicaciones unificadas (UCWA). Para obtener más información sobre este cmdlet, vea [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) en la documentación del shell de administración de Skype empresarial Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solución de problemas de instalación de complementos en Windows Server 2008 R2
<a name="MFA"> </a>

Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar la configuración de seguridad en Internet Explorer

1. Abra Internet Explorer.

2. Haga clic en **herramientas**, en **Opciones de Internet**y, a continuación, en **avanzadas**.

3. Desplácese hacia abajo hasta la sección **seguridad** .

4. Desactive no **guardar las páginas cifradas en el disco**y, a continuación, haga clic en **Aceptar**.

    > [!NOTE]
    > Si esta opción está activada, también se producirá un error al intentar descargar datos adjuntos de la aplicación Web de Skype empresarial.

5. Vuelva a unirse a la reunión. El complemento debe descargarse sin errores.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificación de la configuración del registro DisableMSI

1. Haga clic en **Inicio** y luego en **Ejecutar**.

2. Para obtener acceso al editor del registro, escriba **regedit**.

3. Ir a HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer.

4. Edite o agregue la clave del registro DisableMSI de tipo REG_DWORD y establézcalo en 0.

5. Vuelva a unirse a la reunión.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional, solo Skype empresarial Server 2015)
<a name="SMA_Enable"> </a>

Este procedimiento es opcional y se aplica a Skype empresarial Server 2015 CU5 y versiones posteriores. Si no la usa, los usuarios externos seguirán combinando reuniones con la aplicación Web de Skype empresarial.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar la Unión a reuniones simplificada y la aplicación reuniones de Skype

1. Si habilita el acceso a la red de entrega de contenido (CDN), los usuarios podrán conectarse a la red CDN en línea y obtener la aplicación reuniones de Skype (en Windows) y Skype empresarial para Mac (en Mac), y usarán la experiencia de participación en reuniones simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir la telemetría de registro del lado cliente de la Página Web de unirse a la reunión o la aplicación reuniones de Skype se enviará a los servidores de Microsoft (el comando predeterminado es false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    La información que se envía a Microsoft se ajusta al estricto cumplimiento de la [privacidad y Microsoft Teams](../../../../Teams/teams-privacy.md).

3. Establezca el tiempo de espera antes de revertir a la experiencia de la aplicación Web de Skype empresarial hospedada localmente si la red CDN no está disponible. El valor predeterminado es 6 segundos. Si este valor se establece en 0, no habrá tiempo de espera.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Con MeetingUxUseCdn en Skype empresarial Server 2015 de la actualización acumulativa 5, el valor predeterminado se establece en false. Esto causa un problema en el que el cliente de Skype empresarial para Mac no puede unirse a reuniones de socios no federados como invitado, incluso si el administrador de Skype empresarial ha establecido MeetingUxUseCdn en true. Para que esto funcione, Skype empresarial Server 2015 debe tener la actualización acumulativa 7, 6.0.9319.534 o posterior. Consulte [Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial en Skype empresarial Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Consulte también
<a name="SMA_Enable"> </a>

[Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar la página de participación en reuniones en Skype empresarial Server](../../manage/conferencing/meeting-join-page.md)

[Declaración de privacidad de servicios en línea Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Términos de licencia y documentación](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
