---
title: Implementar a los clientes que se pueden descargar de Web en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumen: Implementar la Skype para la aplicación empresarial de Web y aplicación de las reuniones de Skype se utiliza con Skype para la empresa.'
ms.openlocfilehash: c50a8afc4d12d7f3cf35fdcc966e322bd48199fc
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699540"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implementar a los clientes que se pueden descargar de Web en Skype para Business Server

**Resumen:** Implemente el Skype para profesionales de 2015 Web App y aplicación de las reuniones de Skype se utiliza con Skype para Business Server 2015.

Skype para la aplicación empresarial de Web es un cliente de web de Internet Information Services (IIS) que está instalado en el servidor que ejecuta Skype para Business Server 2015 y de forma predeterminada se implementa a petición a los usuarios de reunión que ya no tienen la Skype para clientes empresariales. Estos usuarios de reuniones son más frecuentes que los casos de usuarios que no se conectan desde fuera de la red. Cada vez que un usuario hace clic en una dirección URL de la reunión, pero no tiene el Skype para Business client instalado, se presenta al usuario con la opción para unirse a la reunión mediante el uso de la versión más reciente de Skype para la aplicación empresarial de Web o aplicación de las reuniones de Skype.

Las características de la voz, vídeo y uso compartida en Skype para la aplicación empresarial de Web requieren un control ActiveX de Microsoft que se usa como un complemento en el explorador del usuario. Puede instalar el control ActiveX de antemano o permitir a los usuarios que lo instale cuando se le solicite, lo que ocurre la primera vez que usa Skype para la aplicación empresarial de Web o la primera vez que tienen acceso a una característica que requiere el control ActiveX.

> [!NOTE]
> En Skype para implementaciones de servidor perimetral de Business Server 2015, un proxy inverso de HTTPS en la red perimetral se requiere para Skype para acceso de cliente de la aplicación Web de negocio. También debe publicar direcciones URL sencillas. Para obtener más información, vea [Setting Up Servers de Proxy inverso](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) y [los requisitos de DNS para direcciones URL simples en Skype para Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar la autenticación multifactor para Skype para la aplicación empresarial de Web
<a name="MFA"> </a>

El Skype para la aplicación empresarial de Web y aplicación de las reuniones de Skype admiten la autenticación multifactor. Además de nombre de usuario y contraseña, puede requerir que los métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unan a las redes externas cuando inician sesión Skype para reuniones de negocios. Puede habilitar la autenticación multifactor mediante la implementación de servidor de federación de servicios de federación de Active Directory (AD FS) y la habilitación de autenticación pasiva en Skype para Business Server. Después de configurar AD FS, los usuarios externos que intenten unirse a Skype para reuniones de negocios se presentan con una página Web de autenticación multifactor de AD FS que contiene el nombre de usuario y contraseña desafiar junto con los métodos de autenticación adicionales ha configurado.

> [!IMPORTANT]
> A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor:

- La autenticación multifactor de AD FS funciona si el usuario que participa en la reunión y el organizador están en la misma organización o si ambos provienen de una organización federada de AD FS. La autenticación multifactor de AD FS no funciona para usuarios federados de Lync porque la infraestructura web de Lync Server no lo admite en este momento.

- Si usa equilibradores de carga de hardware, habilite la persistencia de cookies en los equilibradores de carga para que todas las solicitudes de la Skype para clientes empresariales Web App o aplicación de las reuniones se controlan mediante el mismo servidor de Front-End.

- Al establecer una relación de confianza entre Skype para servidores Business Server y AD FS, asigne una token vida que es suficiente para abarcar la longitud máxima de su Skype para reuniones de negocios. Por lo general, una duración de token de 240 minutos es suficiente.

- Esta configuración no se aplica a los clientes móviles de Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar la autenticación multifactor

1. Instale un rol del servidor de federación de AD FS. Para obtener información detallada, consulte la [Guía de implementación de Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Cree certificados para AD FS. Para obtener más información, vea la sección ["Certificados de servidor de federación"](https://go.microsoft.com/fwlink/p/?LinkId=285376) del Plan para e implementar AD FS para su uso con el tema de inicio de sesión único.

3. Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Establezca una relación de usuario mediante la ejecución del siguiente comando:

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Defina las siguientes reglas de usuario de confianza:

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Deshabilitar BranchCache 
<a name="MFA"> </a>

La característica BranchCache de Windows 7 y Windows Server 2008 R2 puede interferir con Skype para los componentes web de negocio Web App. Para evitar problemas de Skype para usuarios de la aplicación Web de negocio, asegúrese de que no está habilitada la característica BranchCache.

Para obtener información detallada acerca de cómo deshabilitar BranchCache, vea la [Guía de implementación de BranchCache](https://docs.microsoft.com/en-us/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Comprobación de Skype para la implementación de aplicaciones Web de empresa
<a name="MFA"> </a>

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA). Para obtener información detallada sobre este cmdlet, vea [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) en el Skype para la documentación del Shell de administración de servidor empresarial.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solución de problemas de instalación del complemento en Windows Server 2008 R2
<a name="MFA"> </a>

Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, debe modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar la configuración de seguridad de Internet Explorer

1. Abra Internet Explorer.

2. Haga clic en **Herramientas **, en **Opciones de Internet** y en **Opciones avanzadas**.

3. Desplácese hacia abajo hasta la sección **Seguridad**.

4. Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.

    > [!NOTE]
    > Si se selecciona, esta configuración también se producirá un error al intentar descargar datos adjuntos de Skype para la aplicación empresarial de Web.

5. Vuelva a unirse a la reunión. El complemento se debe descargar sin errores.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar la configuración del Registro DisableMSI

1. Haga clic en  **Inicio ** y en  **Ejecutar **.

2. Para acceder al Editor del Registro, escriba **regedit**.

3. Navegue hasta HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modifique o agregue la clave del Registro DisableMSI de tipo REG_DWORD, y defínala en 0.

5. Vuelva a unirse a la reunión.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar la aplicación de las reuniones de Skype reemplazar Skype para la aplicación empresarial de Web (opcional, Skype para Business Server solo 2015)
<a name="SMA_Enable"> </a>

Este procedimiento es opcional y se aplica a Skype para Business Server 2015 CU5 y versiones posteriores. Si no se utiliza, los usuarios externos seguirán unirse a reuniones con Skype para la aplicación empresarial de Web.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar el método simplificado para unirse a las reuniones y la aplicación Reuniones de Skype

1. Al habilitar el acceso a la red de entrega de contenido (CDN), los usuarios tendrán la capacidad para conectarse a CDN en línea y obtener la aplicación de las reuniones de Skype y usará el simplificada experiencia de unirse a la reunión.

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir la telemetría de registro del lado de la reunión cliente unirse a la página web o la aplicación de las reuniones de Skype que se envíen a los servidores de Microsoft (el comando predeterminado es false).

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    La información que se envía a Microsoft cumple rigurosamente con las [prácticas de recopilación de datos de Skype Empresarial](https://docs.microsoft.com/en-us/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Establecer el tiempo de espera antes de retroceso a la Skype hospedado localmente para la experiencia de la aplicación Web de negocio si CDN no está disponible. El valor predeterminado es 6 segundos. En caso de que fuese 0, no habría tiempo de espera.

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Vea también
<a name="SMA_Enable"> </a>

[Planeación de los clientes de las reuniones (Web App y aplicación de las reuniones)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configuración de la reunión de la página de participación en Skype para Business Server](../../manage/conferencing/meeting-join-page.md)

[Declaración de privacidad de Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Los términos de licencia y documentación](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)