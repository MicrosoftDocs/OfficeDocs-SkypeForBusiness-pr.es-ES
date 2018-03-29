---
title: Implementar clientes web descargables en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumen: Implementar el Skype para Business Web App y App de reuniones de Skype utilizado con Skype para el negocio.'
ms.openlocfilehash: e1cee2741e1538da1e4c5ed8e25509415cb16ac3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a>Implementar clientes web descargables en Skype Empresarial Server 2015
 
**Resumen:** Implementar el Skype para Business Web App y App de reuniones de Skype utilizado con Skype para el negocio.
  
Skype para el negocio de la aplicación Web es un cliente de web de servicios de Internet Information Server (IIS) está instalado en el servidor que ejecuta Skype para Business Server 2015 y se implementa de forma predeterminada a petición a los usuarios de la reunión que no tiene ya el Skype para cliente de empresa. Estos usuarios de reuniones son más frecuentes que los casos de usuarios que no se conectan desde fuera de la red. Cada vez que un usuario hace clic en una dirección URL de la reunión pero no tiene el Skype para Business client instalado, se presenta al usuario con la opción para unirse a la reunión utilizando la versión más reciente de Skype para el negocio de la aplicación Web.
  
Cuenta con la voz, vídeo y uso compartida de Skype para Business Web App requieren un control Microsoft ActiveX que se utiliza como un complemento en el explorador del usuario. Puede instalar el control ActiveX de antemano o que los usuarios puedan instalarlo cuando se le pida, que se produce la primera vez que utilizan Skype para Business Web App o la primera vez que acceden a una función que requiere el control ActiveX.
  
> [!NOTE]
> En Skype para implementaciones de servidor perimetral de Business Server 2015, un proxy inverso de HTTPS en la red perimetral se requiere para Skype para acceso de cliente de empresa de la aplicación Web. También debe publicar direcciones URL sencillas. Para obtener más información, vea [Setting Up Servers de Proxy inverso](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) y [Planear simples direcciones URL](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Habilitar la autenticación con varios factores para Skype para Business Web App
<a name="MFA"> </a>

El Skype para Business Server 2015 versión de Skype para el negocio de la aplicación Web admite la autenticación con varios factores. Además de nombre de usuario y contraseña, puede requerir otros métodos de autenticación, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unan a redes externas cuando inician sesión en Skype para reuniones de negocios. Puede habilitar la autenticación con varios factores al implementar servidor de federación de servicio de federación de Active Directory (AD FS) y habilitar la autenticación pasiva en Skype para Business Server 2015. Después de configurar AD FS, los usuarios externos que intentan unirse a Skype para reuniones de negocios se presentan con una página Web de autenticación con varios factores de AD FS que contiene el nombre de usuario y contraseña desafío junto con los métodos de autenticación adicionales ha configurado.
  
> [!IMPORTANT]
> A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor: 
  
- La autenticación multifactor de AD FS funciona si el usuario que participa en la reunión y el organizador están en la misma organización o si ambos provienen de una organización federada de AD FS. La autenticación multifactor de AD FS no funciona para usuarios federados de Lync porque la infraestructura web de Lync Server no lo admite en este momento.
    
- Si utiliza equilibradores de carga hardware, habilitar la persistencia de la cookie en los equilibradores de carga para que se traten todas las solicitudes desde el Skype para el negocio de la aplicación Web cliente por el mismo servidor de Front-End.
    
- Al establecer una confianza de fabricantes de confianza entre Skype para servidores Business Server y AD FS, asignar una vida token que es suficiente para abarcar la longitud máxima de su Skype para reuniones de negocios. Por lo general, una duración de token de 240 minutos es suficiente.
    
- Esta configuración no se aplica a los clientes móviles de Lync.
    
### <a name="configure-multi-factor-authentication"></a>Configurar la autenticación multifactor

1. Instale un rol del servidor de federación de AD FS. Para obtener más información, consulte la [Guía de implementación de Active Directory federación de servicios 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)
    
2. Cree certificados para AD FS. Para obtener más información, consulte la sección ["Certificados de servidor de federación"](https://go.microsoft.com/fwlink/p/?LinkId=285376) del Plan de e implementar AD FS para su uso con el tema de inicio de sesión único.
    
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
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Deshabilitar BranchCache 
<a name="MFA"> </a>

La característica BranchCache de Windows 7 y Windows Server 2008 R2 puede interferir con Skype para componentes web de negocio de la aplicación Web. Para evitar problemas de Skype para los usuarios de negocio de la aplicación Web, asegúrese de que no está habilitada la característica BranchCache. 
  
Para obtener detalles acerca de cómo deshabilitar BranchCache, vea la Guía de implementación de BranchCache, que está disponible en formato de Word en Microsoft Download Center en [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) y en formato HTML en la biblioteca Windows Server 2008 R2 técnica en [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).
  
## <a name="verifying-skype-for-business-web-app-deployment"></a>Comprobación de Skype para la implementación de aplicaciones Web empresariales
<a name="MFA"> </a>

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA). Para obtener más información acerca de este cmdlet, vea [Prueba CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) en el Skype para la documentación del Shell de administración de servidor empresarial.
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Solución de problemas de instalación del complemento en Windows Server 2008 R2
<a name="MFA"> </a>

Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, puede que necesite modificar la configuración de seguridad de Internet Explorer o la configuración de clave del registro DisableMSI.
  
### <a name="modify-the-security-setting-in-internet-explorer"></a>Modificar la configuración de seguridad de Internet Explorer

1. Abra Internet Explorer.
    
2. Haga clic en **Herramientas **, en **Opciones de Internet** y en **Opciones avanzadas**.
    
3. Desplácese hacia abajo hasta la sección **Seguridad**.
    
4. Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.
    
    > [!NOTE]
    > Si se selecciona, esta opción también se producirá un error al intentar descargar un archivo adjunto de Skype para el negocio de la aplicación Web. 
  
5. Vuelva a unirse a la reunión. El complemento se debe descargar sin errores.
    
### <a name="modify-the-disablemsi-registry-setting"></a>Modificar la configuración del Registro DisableMSI

1. Haga clic en  **Inicio ** y en  **Ejecutar **.
    
2. Para acceder al Editor del Registro, escriba **regedit**.
    
3. Navegue hasta HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.
    
4. Modifique o agregue la clave del Registro DisableMSI de tipo REG_DWORD, y defínala en 0.
    
5. Vuelva a unirse a la reunión.
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a>Habilitar la aplicación Reuniones de Skype para reemplazar la aplicación web de Skype Empresarial (opcional)
<a name="SMA_Enable"> </a>

Este procedimiento es opcional. Si no se utiliza, los usuarios externos seguirán unirse a reuniones mediante Skype para el negocio de la aplicación Web. 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Habilitar el método simplificado para unirse a las reuniones y la aplicación Reuniones de Skype

1. Al habilitar el acceso a Content Delivery Network (CDN), los usuarios tendrán la capacidad de conectarse a CDN en línea y obtener la aplicación de las reuniones de Skype y utilizará el simplificado experiencia de unión de la reunión. 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Permitir cliente telemetría de lado el registro de la reunión de unirse a la página web o la aplicación de las reuniones de Skype para enviarse a los servidores de Microsoft (el comando predeterminado es false). 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Información enviada a Microsoft es en estricto cumplimiento de [Skype para las prácticas de recopilación de datos de negocio](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).
    
3. Establecer el tiempo de espera antes de retroceso a la Skype hospedado localmente para la experiencia del negocio de la aplicación Web si CDN no está disponible. El valor predeterminado es 6 segundos. En caso de que fuese 0, no habría tiempo de espera.
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Vea también
<a name="SMA_Enable"> </a>

#### 

[Plan para clientes de reuniones (Web App y App de reuniones)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[Plan para clientes de reuniones (Web App y App de reuniones)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
#### 

[Configurar la página Join Meeting](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[Declaración de privacidad de Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[Los términos de licencia y documentación](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

