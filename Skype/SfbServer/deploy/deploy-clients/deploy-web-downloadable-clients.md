---
title: Implementar clientes descargables en Internet en Skype empresarial Server
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
ms.openlocfilehash: 5f4cc14ab3774096846053e6da41647c1987a1dd
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768963"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implementar clientes descargables en Internet en Skype empresarial Server

**Resumen:** Implementar la aplicación Web de Skype empresarial 2015 y la aplicación reuniones de Skype que se usa con Skype empresarial Server.

La aplicación Web de Skype empresarial es un cliente web de Internet Information Services (IIS) instalado en el servidor que ejecuta Skype empresarial Server y, de forma predeterminada, se implementa a petición para los usuarios que aún no tienen el cliente de Skype empresarial. Estos usuarios de reuniones son más frecuentes que los casos de usuarios que no se conectan desde fuera de la red. Siempre que un usuario haga clic en una dirección URL de la reunión pero no tenga instalado el cliente de Skype empresarial, se le presentará al usuario la opción de unirse a la reunión con la versión más reciente de la aplicación Web de Skype empresarial, la aplicación reuniones de Skype o Skype empresarial para Mac.

Las características de voz, vídeo y uso compartido de la aplicación Web de Skype empresarial requieren un control ActiveX de Microsoft que el explorador del usuario Use como complemento. Puede instalar el control ActiveX por adelantado o permitir que los usuarios lo instalen cuando se le pida, que es la primera vez que usan la aplicación Web de Skype empresarial o la primera vez que tienen acceso a una característica que requiere el control ActiveX.

> [!NOTE]
> En las implementaciones de servidor perimetral de Skype empresarial Server, se necesita un proxy inverso HTTPS en la red perimetral para el acceso de cliente de la aplicación Web de Skype empresarial. También debe publicar direcciones URL sencillas. Para obtener más información, consulte [configuración de servidores proxy inversos](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) y [requisitos de DNS para direcciones URL simples en Skype empresarial Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar la autenticación multifactor para la aplicación Web de Skype empresarial
<a name="MFA"> </a>

La aplicación Web de Skype empresarial, la aplicación reuniones de Skype y Skype empresarial para Mac admiten la autenticación multifactor. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Skype empresarial. Puede habilitar la autenticación multifactor si implementa el servidor de Federación de servicio de Federación de Active Directory (AD FS) y habilita la autenticación pasiva en Skype empresarial Server. Después de configurar AD FS, los usuarios externos que intenten unirse a reuniones de Skype empresarial recibirán una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña junto con los métodos de autenticación adicionales que ha configurado.

> [!IMPORTANT]
> A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor:

- La autenticación multifactor de AD FS funciona si el usuario que participa en la reunión y el organizador están en la misma organización o si ambos provienen de una organización federada de AD FS. La autenticación multifactor de AD FS no funciona para usuarios federados de Lync porque la infraestructura web de Lync Server no lo admite en este momento.

- Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes de los clientes de la aplicación Web de Skype empresarial o de la aplicación de reuniones se controlen mediante el mismo servidor front-end.

- Al establecer una relación de confianza para usuario autenticado entre los servidores de Skype empresarial Server y AD FS, asigne un token de duración que sea lo suficientemente largo como para abarcar la máxima duración de las reuniones de Skype empresarial. Por lo general, una duración de token de 240 minutos es suficiente.

- Esta configuración no se aplica a los clientes móviles de Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar la autenticación multifactor

1. Instale un rol del servidor de federación de AD FS. Para obtener más información, consulte la [Guía de implementación de servicios de Federación de active directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Cree certificados para AD FS. Para obtener más información, consulte la sección ["certificados de servidor de Federación"](https://go.microsoft.com/fwlink/p/?LinkId=285376) de los temas planear e implementar AD FS para su uso con el inicio de sesión único.

3. Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Establezca una relación de usuario mediante la ejecución del siguiente comando:

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Defina las siguientes reglas de usuario de confianza:

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Deshabilitar BranchCache 
<a name="MFA"> </a>

La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de la aplicación Web de Skype empresarial. Para evitar problemas con los usuarios de la aplicación Web de Skype empresarial, asegúrese de que BranchCache no está habilitado.

Para obtener más información sobre cómo deshabilitar BranchCache, consulte la [Guía de implementación de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Comprobar la implementación de la aplicación Web de Skype empresarial
<a name="MFA"> </a>

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA). Para obtener más información sobre este cmdlet, consulte [probar-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) en la documentación del shell de administración de Skype empresarial Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solución de problemas de instalación de complementos en Windows Server 2008 R2
<a name="MFA"> </a>

Si se produce un error en la instalación del complemento en un equipo con Windows Server 2008 R2, es posible que tenga que modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar la configuración de seguridad de Internet Explorer

1. Abra Internet Explorer.

2. Haga clic en **Herramientas **, en **Opciones de Internet** y en **Opciones avanzadas**.

3. Desplácese hacia abajo hasta la sección **Seguridad**.

4. Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.

    > [!NOTE]
    > Si se selecciona, esta configuración también provocará un error al intentar descargar un archivo adjunto desde la aplicación Web de Skype empresarial.

5. Vuelva a unirse a la reunión. El complemento se debe descargar sin errores.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar la configuración del Registro DisableMSI

1. Haga clic en  **Inicio ** y en  **Ejecutar **.

2. Para acceder al Editor del Registro, escriba **regedit**.

3. Navegue hasta HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modifique o agregue la clave del Registro DisableMSI de tipo REG_DWORD, y defínala en 0.

5. Vuelva a unirse a la reunión.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial (opcional, Skype empresarial Server 2015 solamente)
<a name="SMA_Enable"> </a>

Este procedimiento es opcional y se aplica a Skype empresarial Server 2015 CU5 y versiones posteriores. Si no lo usa, los usuarios externos seguirán combinando reuniones con la aplicación Web de Skype empresarial.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar el método simplificado para unirse a las reuniones y la aplicación Reuniones de Skype

1. Al habilitar el acceso a la red de entrega de contenido (CDN), los usuarios podrán conectarse a la red CDN en línea y obtener la aplicación reuniones de Skype (en Windows) y Skype empresarial para Mac (en Mac), y usarán la experiencia de la combinación de reuniones simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir la telemetría de registro del lado cliente de la Página Web de la Unión a reuniones o de la aplicación reuniones de Skype para enviarla a los servidores de Microsoft (el comando tiene el valor predeterminado falso).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    La información enviada a Microsoft es estrictamente compatible con las [prácticas de recopilación de datos de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Establezca el tiempo de espera antes de volver a la experiencia de la aplicación Web de Skype empresarial hospedada localmente si CDN no está disponible. El valor predeterminado es 6 segundos. En caso de que fuese 0, no habría tiempo de espera.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Con MeetingUxUseCdn en Skype empresarial Server 2015, actualización acumulativa 5, el valor predeterminado se establece en false. Esto causa un problema en el que el cliente de Skype empresarial para Mac no puede unir reuniones de socios no federados como invitado, incluso si el administrador de Skype empresarial ha establecido MeetingUxUseCdn en true. Para ello, Skype empresarial Server 2015 debe tener la actualización acumulativa 7, 6.0.9319.534 o posterior. Consulte [Habilitar la aplicación reuniones de Skype para reemplazar la aplicación Web de Skype empresarial en Skype empresarial Server 2015](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Vea también
<a name="SMA_Enable"> </a>

[Planear clientes de reuniones (aplicación web y aplicación reuniones)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar la página de combinación de reuniones en Skype empresarial Server](../../manage/conferencing/meeting-join-page.md)

[Declaración de privacidad de Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Términos de licencia y documentación](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
