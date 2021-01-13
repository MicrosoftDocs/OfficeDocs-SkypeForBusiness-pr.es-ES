---
title: Implementar clientes web descargables en Skype Empresarial Server
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
description: 'Resumen: implemente la aplicación web de Skype Empresarial y la aplicación reuniones de Skype que se usa con Skype Empresarial.'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805930"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Implementar clientes web descargables en Skype Empresarial Server

**Resumen:** Implemente la aplicación web de Skype Empresarial 2015 y la aplicación reuniones de Skype que se usa con Skype Empresarial Server.

Skype Empresarial Web App es un cliente web de Internet Information Services (IIS) que está instalado en el servidor que ejecuta Skype Empresarial Server y, de forma predeterminada, se implementa a petición para los usuarios que aún no tienen el cliente de Skype Empresarial. Estos usuarios de reuniones suelen no conectarse desde fuera de la red. Cuando un usuario hace clic en una dirección URL de la reunión pero no tiene instalado el cliente de Skype Empresarial, se le ofrece la opción de unirse a la reunión con la versión más reciente de Skype Empresarial Web App, la aplicación Reuniones de Skype o Skype Empresarial para Mac.

Las características de voz, vídeo y uso compartido de Skype Empresarial Web App requieren un control de Microsoft ActiveX que el explorador del usuario usa como complemento. Puede instalar el control ActiveX por adelantado o permitir a los usuarios instalarlo cuando se le pida, lo que ocurre la primera vez que usan Skype Empresarial Web App o la primera vez que acceden a una característica que requiere el control ActiveX.

> [!NOTE]
> En las implementaciones del servidor perimetral de Skype Empresarial Server, se necesita un proxy inverso HTTPS en la red perimetral para el acceso de cliente de Skype Empresarial Web App. También debe publicar direcciones URL sencillas. Para obtener más información, consulte [Configuración de servidores proxy inversos](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) y requisitos dns para direcciones URL [sencillas en Skype Empresarial Server.](../../plan-your-deployment/network-requirements/simple-urls.md)

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar la autenticación multifactor para la aplicación web de Skype Empresarial
<a name="MFA"> </a>

La aplicación web de Skype Empresarial, la aplicación reuniones de Skype y Skype Empresarial para Mac admiten la autenticación multifactor. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Skype Empresarial. Puede habilitar la autenticación multifactor implementando el servidor de federación del Servicio de federación de Active Directory (AD FS) y habilitando la autenticación pasiva en Skype Empresarial Server. Después de configurar AD FS, los usuarios externos que intentan unirse a reuniones de Skype Empresarial se presentan con una página web de autenticación multifactor de AD FS que contiene el nombre de usuario y el desafío de contraseña junto con los métodos de autenticación adicionales que haya configurado.

> [!IMPORTANT]
> Las siguientes son consideraciones importantes si planea configurar AD FS para la autenticación multifactor:

- La autenticación multifactor ADFS funciona si el participante y el organizador de la reunión están en la misma organización o si ambos son de una organización federada de AD FS. La autenticación ADFS multifactor no funciona para los usuarios federados de Lync porque la infraestructura web de Lync Server no la admite actualmente.

- Si usa equilibradores de carga de hardware, habilite la persistencia de cookies en los equilibradores de carga para que el mismo servidor front-end controle todas las solicitudes de los clientes de la aplicación web de Skype Empresarial o de la aplicación Meetings.

- Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Skype Empresarial Server y AD FS, asigne una vida de token lo suficientemente larga como para abarcar la duración máxima de las reuniones de Skype Empresarial. Normalmente, una vida de token de 240 minutos es suficiente.

- Esta configuración no se aplica a los clientes móviles de Lync.

### <a name="configure-multi-factor-authentication"></a>Configurar la autenticación multifactor

1. Instalar un rol de servidor de federación de AD FS. Para obtener más información, consulte la Guía de implementación de Servicios de federación [de Active Directory 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Crear certificados para AD FS. Para obtener más información, [vea la sección "Certificados](https://go.microsoft.com/fwlink/p/?LinkId=285376) de servidor de federación" del tema Planear e implementar AD FS para su uso con el inicio de sesión único.

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

La característica BranchCache de Windows 7 y Windows Server 2008 R2 puede interferir con los componentes web de Skype Empresarial Web App. Para evitar problemas para los usuarios de Skype Empresarial Web App, asegúrese de que BranchCache no está habilitado.

Para obtener más información sobre cómo deshabilitar BranchCache, consulta la [Guía de implementación de BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Comprobar la implementación de aplicaciones web de Skype Empresarial
<a name="MFA"> </a>

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba pueden participar en una conferencia mediante la API web de comunicaciones unificadas (UCWA). Para obtener más información sobre este cmdlet, [consulte Test-CsUcwaConference en](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) la documentación del Shell de administración de Skype Empresarial Server.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solución de problemas de la instalación de complementos en Windows Server 2008 R2
<a name="MFA"> </a>

Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del Registro DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar la configuración de seguridad en Internet Explorer

1. Abra Internet Explorer.

2. Haga **clic en Herramientas,** **opciones de Internet** y, a continuación, haga clic en **Opciones avanzadas.**

3. Desplácese hacia abajo hasta la **sección** Seguridad.

4. Desactive **No guardar páginas cifradas en el disco** y, a continuación, haga clic en **Aceptar.**

    > [!NOTE]
    > Si se selecciona, esta configuración también provocará un error al intentar descargar datos adjuntos de la aplicación web de Skype Empresarial.

5. Vuelva a unirse a la reunión. El complemento debe descargarse sin errores.

### <a name="modify-the-disablemsi-registry-setting"></a>Modificar la configuración del Registro DisableMSI

1. Haga clic en **Inicio** y luego en **Ejecutar**.

2. Para obtener acceso al Editor del Registro, **escriba regedit**.

3. Vaya a HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Edita o agrega la clave del Registro DisableMSI del tipo REG_DWORD y esta establece en 0.

5. Vuelva a unirse a la reunión.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Habilitar la aplicación Reuniones de Skype para reemplazar la aplicación web de Skype Empresarial (opcional, solo Skype Empresarial Server 2015)
<a name="SMA_Enable"> </a>

Este procedimiento es opcional y se aplica a Skype Empresarial Server 2015 CU5 y versiones posteriores. Si no lo usa, los usuarios externos seguirán unirse a las reuniones con Skype Empresarial Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar la participación en reuniones simplificada y la aplicación Reuniones de Skype

1. Cuando habilite el acceso a la red de entrega de contenido (CDN), los usuarios podrán conectarse a la red CDN en línea y obtener la aplicación Reuniones de Skype (en Windows) y Skype Empresarial para Mac (en Mac), y usarán la experiencia de participación en reuniones simplificada.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir que la telemetría de registro del lado cliente desde la página web de participación en la reunión o la aplicación reuniones de Skype se envíe a los servidores de Microsoft (el comando predeterminado es false).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    La información enviada a Microsoft se cumple estrictamente con las [prácticas de recopilación](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)de datos de Skype Empresarial.

3. Establezca el tiempo de espera antes de volver a la experiencia de Skype Empresarial Web App hospedada localmente si la red CDN no está disponible. El valor predeterminado es 6 segundos. Si este valor se establece en 0, no habrá tiempo de espera.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Con MeetingUxUseCdn en la actualización acumulativa 5 de Skype Empresarial Server 2015, el valor predeterminado se establece en False. Esto provoca un problema por el que el cliente de Skype Empresarial para Mac no puede unirse a reuniones de socios no federados como invitado, incluso si el administrador de Skype Empresarial ha establecido MeetingUxUseCdn en True. Para que esto funcione, Skype Empresarial Server 2015 debe tener la actualización acumulativa 7, 6.0.9319.534 o posterior. Consulte Habilitar la aplicación Reuniones de Skype para reemplazar la aplicación web de Skype Empresarial [en Skype Empresarial Server 2015.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>Ver también
<a name="SMA_Enable"> </a>

[Planeación de clientes de reuniones (aplicación web y aplicación de reuniones)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurar la página de participación en la reunión en Skype Empresarial Server](../../manage/conferencing/meeting-join-page.md)

[Declaración de privacidad de servicios en línea Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Términos y documentación de licencias](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
